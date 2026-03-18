---
cssclasses:
  - readable
---
```dataviewjs
// --- ⚙️ PERSISTENCE ENGINE ---
const defaultHabitNames = ["Reading", "Coding", "Meditate", "Gym"];
let savedHabits = JSON.parse(localStorage.getItem("zos-final-habits")) || defaultHabitNames;
localStorage.setItem("zos-final-habits", JSON.stringify(savedHabits));

// Banner title & subtitle persistence
let bannerTitle = localStorage.getItem("zos-banner-title") || "DASHBOARD ZEN";
let bannerSubtitle = localStorage.getItem("zos-banner-subtitle") || "";

// Configuración de Tareas
let taskSourceType = localStorage.getItem("zos-task-source-type") || "all"; // all, folder, file
let taskSourceValue = localStorage.getItem("zos-task-source-value") || "";

const container = dv.container.createDiv({ cls: "zos-dashboard animate-in" });

// Global pointers for dynamic updates
let bioBar, bioText, bioInfoEl, taskBar, taskText, taskTitleEl;

const Utils = {
    getGreeting: () => {
        const h = new Date().getHours();
        if (h < 5) return "Night of Stillness 🌙";
        if (h < 12) return "Morning Clarity ☀️";
        if (h < 18) return "Deep Focus ⚡";
        return "End of Day 🌌";
    },


    getFilteredTasks: () => {
        let allTasks = dv.pages().file.tasks;
        if (taskSourceType === "folder" && taskSourceValue) {
            return allTasks.where(t => t.path.startsWith(taskSourceValue));
        } else if (taskSourceType === "file" && taskSourceValue) {
            return allTasks.where(t => t.path === taskSourceValue);
        }
        return allTasks;
    },
    getStats: () => {
        const files = app.vault.getMarkdownFiles();
        const fTasks = Utils.getFilteredTasks();
        return {
            files: files ? files.length : 0,
            done: fTasks ? fTasks.where(t => t.completed).length : 0,
            allTasks: fTasks ? fTasks.length : 0
        };
    },
    getHabitStats: () => {
        let totalDots = savedHabits.length * 7;
        let activeDots = 0;
        savedHabits.forEach(h => {
            for(let i=1; i<=7; i++) {
                if(localStorage.getItem(`zos-v28-h-${h}-${i}`)) activeDots++;
            }
        });
        const perf = totalDots > 0 ? (activeDots / totalDots) * 100 : 0;
        return { total: totalDots, active: activeDots, percent: perf };
    },
    updateBars: () => {
        const hStats = Utils.getHabitStats();
        if (bioBar) bioBar.style.width = `${hStats.percent}%`;
        if (bioText) bioText.innerText = `Weekly Consistency: ${hStats.percent.toFixed(0)}%`;
        if (bioInfoEl) bioInfoEl.innerHTML = `Completed: <b>${hStats.active}</b> of <b>${hStats.total}</b> points.<br>${hStats.percent >= 80 ? "🔥 Elite performance detected." : "🚀 Keep maintaining your focus."}` ;
        
        const s = Utils.getStats();
        const tProgress = s.allTasks > 0 ? (s.done / s.allTasks) * 100 : 0;
        if (taskBar) taskBar.style.width = `${tProgress}%`;
        if (taskText) taskText.innerText = `Global Efficiency: ${tProgress.toFixed(0)}%`;
        
        if (taskSourceIndicator) {
             taskSourceIndicator.innerText = taskSourceType === "all" ? "FULL VAULT" : (taskSourceType === "folder" ? `FOLDER: ${taskSourceValue.split('/').pop()}` : `FILE: ${taskSourceValue.split('/').pop()}`);
        }
        
        renderTasks();
    },
    showModal: ({ title, value, onSave, onDelete, placeholder, type = "text", options = [] }) => {
        const overlay = document.body.createDiv({ cls: "zos-modal-overlay" });
        const modal = overlay.createDiv({ cls: "zos-modal" });
        
        modal.createDiv({ cls: "zos-modal-title", text: title });
        
        const close = () => overlay.remove();

        if (type === "text") {
            const input = modal.createEl("input", { 
                cls: "zos-modal-input", 
                attr: { type: "text", value: value || "", placeholder: placeholder || "Type here..." }
            });
            input.focus(); input.select();
            
            const btns = modal.createDiv({ cls: "zos-modal-btns" });
            const row = btns.createDiv({ cls: "zos-modal-row" });
            const cancelBtn = row.createEl("button", { cls: "zos-modal-btn zos-btn-cancel", text: "Cancel" });
            const saveBtn = row.createEl("button", { cls: "zos-modal-btn zos-btn-save", text: "Save" });
            
            cancelBtn.onclick = close;
            saveBtn.onclick = () => { onSave(input.value); close(); };
            input.onkeydown = (e) => { if(e.key === "Enter") saveBtn.click(); if(e.key === "Escape") close(); };
            if (onDelete) {
                const deleteBtn = btns.createEl("button", { cls: "zos-modal-btn zos-btn-delete", text: "🗑️ Delete Habit", attr: { style: "width: 100%; margin-top: 8px;" } });
                deleteBtn.onclick = () => { onDelete(); close(); };
            }
        } else if (type === "grid") {
            const gridCont = modal.createDiv({ attr: { style: "display: grid; grid-template-columns: 1fr; gap: 10px; margin-bottom: 20px;" } });
            options.forEach(opt => {
                const btn = gridCont.createEl("button", { 
                    cls: "zos-modal-btn", 
                    text: opt.label,
                    attr: { style: "background: rgba(255,255,255,0.05); color: white; border: 1px solid rgba(255,255,255,0.1); text-align: left; padding: 15px; font-weight: 600;" }
                });
                btn.onclick = () => { onSave(opt.value); close(); };
                btn.onmouseenter = () => { btn.style.background = "rgba(var(--zos-accent-rgb), 0.1)"; btn.style.borderColor = "var(--zos-accent)"; };
                btn.onmouseleave = () => { btn.style.background = "rgba(255,255,255,0.05)"; btn.style.borderColor = "rgba(255,255,255,0.1)"; };
            });
            modal.createEl("button", { cls: "zos-modal-btn zos-btn-cancel", text: "Close", attr: { style: "width: 100%" } }).onclick = close;
        } else if (type === "suggest") {
            const search = modal.createEl("input", { cls: "zos-modal-input", attr: { placeholder: "Search..." } });
            const listCont = modal.createDiv({ attr: { style: "max-height: 250px; overflow-y: auto; background: #111; border-radius: 12px; margin-bottom: 20px; border: 1px solid rgba(255,255,255,0.05);" } });
            
            const renderList = (filter = "") => {
                listCont.innerHTML = "";
                const filtered = options.filter(o => o.label.toLowerCase().includes(filter.toLowerCase())).slice(0, 40);
                if (filtered.length === 0) listCont.createDiv({ text: "No results", attr: { style: "padding: 20px; text-align: center; opacity: 0.3;" } });
                filtered.forEach(opt => {
                    const item = listCont.createDiv({ 
                        text: opt.label, 
                        attr: { style: "padding: 12px 15px; cursor: pointer; border-bottom: 1px solid rgba(255,255,255,0.03); color: #fff; font-size: 0.9em;" } 
                    });
                    item.onmouseenter = () => item.style.background = "rgba(var(--zos-accent-rgb), 0.1)";
                    item.onmouseleave = () => item.style.background = "transparent";
                    item.onclick = () => { onSave(opt.value); close(); };
                });
            };
            
            search.oninput = () => renderList(search.value);
            renderList();
            search.focus();
            modal.createEl("button", { cls: "zos-modal-btn zos-btn-cancel", text: "Close", attr: { style: "width: 100%" } }).onclick = close;
        }
        
        overlay.onclick = (e) => { if(e.target === overlay) close(); };
    }
};

let taskSourceIndicator;


// --- RENDER HEADER ---
const header = container.createDiv({ cls: "zos-header" });
const hero = header.createDiv({ cls: "zos-hero-text" });

const heroTitleEl = hero.createEl("h1", { 
    text: bannerTitle, 
    attr: { style: "font-size: 3.5em; font-weight: 900; letter-spacing: -2px; margin-bottom: 5px; background: linear-gradient(to right, #fff, rgba(255,255,255,0.4)); -webkit-background-clip: text; -webkit-text-fill-color: transparent;" } 
});

const heroSubtitleEl = hero.createDiv({ 
    text: bannerSubtitle || `${Utils.getGreeting()} — Welcome back. The entire system is ready. ✨`, 
    attr: { style: "opacity: 0.6; font-size: 1.1em; letter-spacing: 0.5px;" }
});

// Botón ⚙️ del banner
const bannerSettingsBtn = header.createDiv({ cls: "zos-banner-settings-btn" });
try { setIcon(bannerSettingsBtn, "settings"); } catch(e) { bannerSettingsBtn.innerText = "⚙️"; }

bannerSettingsBtn.onclick = () => {
    Utils.showModal({
        title: "Edit Banner",
        type: "grid",
        options: [
            { label: "✏️  Edit Title", value: "title" },
            { label: "💬  Edit Subtitle", value: "subtitle" }
        ],
        onSave: (choice) => {
            if (choice === "title") {
                Utils.showModal({
                    title: "Dashboard Title",
                    value: bannerTitle,
                    placeholder: "E.g.: MY DASHBOARD",
                    onSave: (val) => {
                        if (val.trim()) {
                            bannerTitle = val.trim().toUpperCase();
                            localStorage.setItem("zos-banner-title", bannerTitle);
                            heroTitleEl.innerText = bannerTitle;
                        }
                    }
                });
            } else if (choice === "subtitle") {
                Utils.showModal({
                    title: "Banner Subtitle",
                    value: bannerSubtitle || `${Utils.getGreeting()} — Welcome back. The entire system is ready. ✨`,
                    placeholder: "E.g.: Welcome back ✨",
                    onSave: (val) => {
                        bannerSubtitle = val.trim();
                        localStorage.setItem("zos-banner-subtitle", bannerSubtitle);
                        heroSubtitleEl.innerText = bannerSubtitle || `${Utils.getGreeting()} — Welcome back. The entire system is ready. ✨`;
                    }
                });
            }
        }
    });
};

const statsCont = header.createDiv({ cls: "zos-hero-stats" });
function renderHeroStats() {
    statsCont.innerHTML = "";
    const sInit = Utils.getStats();
    [
        { v: dv.pages().length, l: "Notes", i: "files" },
        { v: sInit.done, l: "Achievements", i: "check-circle" }
    ].forEach(stat => {
        const cube = statsCont.createDiv({ cls: "zos-stat-cube" });
        const topRow = cube.createDiv({ attr: { style: "display: flex; align-items: center; justify-content: flex-end; gap: 10px;" }});
        const iCont = topRow.createDiv();
        try { setIcon(iCont, stat.i); } catch(e) { iCont.innerText = "⭐"; }
        topRow.createDiv({ cls: "zos-stat-val", text: stat.v.toString() });
        cube.createDiv({ cls: "zos-stat-lab", text: stat.l });
    });
}
renderHeroStats();

// --- MAIN GRID ---
const grid = container.createDiv({ cls: "zos-grid" });

// ── LEFT COLUMN (span-4) ─────────────────────────────────────
const colLeft = grid.createDiv({ cls: "span-4" });

// Card: Objetivo
const cardFocus = colLeft.createDiv({ cls: "zos-card" });
cardFocus.createDiv({ cls: "zos-card-title", text: "🎯 OBJECTIVE" });
const focusVal = cardFocus.createDiv({ 
    text: localStorage.getItem("zos-final-focus") || "Define your success today...",
    attr: { contenteditable: true, style: "font-family: var(--zos-font-ser); font-size: 2.2em; outline: none; line-height: 1.1;" }
});
focusVal.onblur = () => localStorage.setItem("zos-final-focus", focusVal.innerText);

// Card: Sistema
const cardActions = colLeft.createDiv({ cls: "zos-card", attr: { style: "margin-top: 32px;" } });
cardActions.createDiv({ cls: "zos-card-title", text: "🛠️ SYSTEM" });
const aGrid = cardActions.createDiv({ attr: { style: "display: grid; grid-template-columns: 1fr 1fr; gap: 15px;" }});

const ops = [
    { n: "Daily", icon: "calendar", em: "📅", cmd: "daily-notes" },
    { n: "Search", icon: "search", em: "🔍", cmd: "global-search:open" },
    { n: "Graph", icon: "share-2", em: "🕸️", cmd: "graph:open" },
    { n: "New", icon: "plus-circle", em: "➕", cmd: "file-explorer:new-file" }
];

ops.forEach(op => {
    const btn = aGrid.createDiv({ cls: "zos-action-btn" });
    const iconCont = btn.createDiv();
    try { 
        const { setIcon } = require("obsidian");
        setIcon(iconCont, op.icon); 
    } catch(e) { 
        iconCont.innerText = op.em; 
    }
    btn.createDiv({ text: op.n.toUpperCase(), attr: { style: "font-size: 0.7em; font-weight: 700; margin-top: 5px;" }});
    btn.onclick = () => app.commands.executeCommandById(op.cmd);
});

// Card: Bio-Performance
const cardBioPerf = colLeft.createDiv({ cls: "zos-card", attr: { style: "margin-top: 32px;" } });
cardBioPerf.createDiv({ cls: "zos-card-title", text: "📈 BIO-PERFORMANCE" });

const hStats = Utils.getHabitStats();
bioText = cardBioPerf.createDiv({ 
    text: `Weekly Consistency: ${hStats.percent.toFixed(0)}%`, 
    attr: { style: "font-size: 1.1em; font-weight: 600; margin-bottom: 10px;" } 
});

const bioBarBg = cardBioPerf.createDiv({ attr: { style: "height: 8px; background: rgba(255,255,255,0.05); border-radius: 4px; overflow: hidden; margin-bottom: 15px;" }});
bioBar = bioBarBg.createDiv({ attr: { style: `height: 100%; width: ${hStats.percent}%; background: #00ff88; box-shadow: 0 0 10px rgba(0,255,136,0.3); transition: width 0.6s ease;` }});

bioInfoEl = cardBioPerf.createDiv({ attr: { style: "font-size: 0.75em; opacity: 0.6; line-height: 1.4;" } });
bioInfoEl.innerHTML = `Completed: <b>${hStats.active}</b> of <b>${hStats.total}</b> points.<br>${hStats.percent >= 80 ? "🔥 Elite performance detected." : "🚀 Keep maintaining your focus."}`;

// ── RIGHT COLUMN (span-8) ────────────────────────────────────
const colCenter = grid.createDiv({ cls: "span-8" });

// Card: Task Pipeline
const cardTasks = colCenter.createDiv({ cls: "zos-card" });
const tHeader = cardTasks.createDiv({ cls: "zos-card-title", attr: { style: "justify-content: space-between;" } });
const tLeftHeader = tHeader.createDiv({ attr: { style: "display: flex; align-items: center; gap: 10px;" } });
tLeftHeader.createDiv({ text: "⚡ TASK PIPELINE" });
taskSourceIndicator = tLeftHeader.createDiv({ cls: "zos-task-source-indicator", text: taskSourceType.toUpperCase() });

const settingsBtn = tHeader.createDiv({ cls: "zos-settings-btn" });
try { setIcon(settingsBtn, "settings"); } catch(e) { settingsBtn.innerText = "⚙️"; }

settingsBtn.onclick = () => {
    Utils.showModal({
        title: "Pipeline Mode",
        type: "grid",
        options: [
            { label: "📁 Full Vault", value: "all" },
            { label: "📂 Filter by Folder", value: "folder" },
            { label: "📄 Filter by File", value: "file" }
        ],
        onSave: (val) => {
            taskSourceType = val;
            localStorage.setItem("zos-task-source-type", val);
            if (val === "all") {
                taskSourceValue = "";
                localStorage.setItem("zos-task-source-value", "");
                Utils.updateBars();
                renderHeroStats();
            } else if (val === "folder") {
                const folders = [...new Set(app.vault.getAllLoadedFiles()
                                .filter(f => f.children)
                                .map(f => f.path))]
                                .sort()
                                .map(p => ({ label: p, value: p }));
                Utils.showModal({
                    title: "Choose Folder",
                    type: "suggest",
                    options: folders,
                    onSave: (path) => {
                        taskSourceValue = path;
                        localStorage.setItem("zos-task-source-value", path);
                        Utils.updateBars();
                        renderHeroStats();
                    }
                });
            } else if (val === "file") {
                const files = app.vault.getMarkdownFiles()
                                .map(f => ({ label: f.path, value: f.path }));
                Utils.showModal({
                    title: "Choose File",
                    type: "suggest",
                    options: files,
                    onSave: (path) => {
                        taskSourceValue = path;
                        localStorage.setItem("zos-task-source-value", path);
                        Utils.updateBars();
                        renderHeroStats();
                    }
                });
            }
        }
    });
};

const taskListCont = cardTasks.createDiv({ attr: { style: "max-height: 340px; overflow-y: auto; padding-right: 4px;" } });
function renderTasks() {
    taskListCont.innerHTML = "";
    const activeTasks = Utils.getFilteredTasks().where(t => !t.completed).sort(t => t.due, "asc");
    if (activeTasks.length > 0) {
        activeTasks.forEach(t => {
            const row = taskListCont.createDiv({ cls: "zos-task-row" });
            row.innerHTML = `
                <div class="zos-task-check"></div>
                <div style="flex-grow: 1;">
                    <div style="font-weight: 600;">${t.text}</div>
                    <div style="font-size: 0.7em; opacity: 0.5;">${t.path.split('/').pop().replace('.md', '')}</div>
                </div>
                <div class="zos-task-tag" style="${t.due && t.due <= dv.date('today') ? 'background: #ff555522; color: #ff5555;' : ''}">
                    ${t.due ? t.due.toLocaleString('es-ES', {day:'numeric', month:'short'}) : 'OPEN'}
                </div>
            `;
            row.onclick = () => app.workspace.openLinkText(t.path, "", false);
        });
    } else {
        taskListCont.createDiv({ cls: "zos-hint", text: "Pipeline clear or source has no tasks." });
    }
}
renderTasks();

// Card: Task Performance
const cardHealth = colCenter.createDiv({ cls: "zos-card", attr: { style: "margin-top: 32px;" } });
cardHealth.createDiv({ cls: "zos-card-title", text: "📊 TASK PERFORMANCE" });

const sCur = Utils.getStats();
const progress = sCur.allTasks > 0 ? (sCur.done / sCur.allTasks) * 100 : 0;
taskText = cardHealth.createDiv({ attr: { style: "font-size: 0.9em; margin-bottom: 12px; opacity: 0.7;" }, text: `Global Efficiency: ${progress.toFixed(0)}%` });
const barBg = cardHealth.createDiv({ attr: { style: "height: 8px; background: rgba(255,255,255,0.05); border-radius: 6px; overflow: hidden;" }});
taskBar = barBg.createDiv({ attr: { style: `height: 100%; width: ${progress}%; background: #00ff88; box-shadow: 0 0 10px rgba(0,255,136,0.3); transition: width 0.6s ease;` }});

// ── BIO-METRICS — en columna derecha, debajo de Task Performance ──
const cardHabits = colCenter.createDiv({ cls: "zos-card", attr: { style: "margin-top: 32px;" } });
const hHeader = cardHabits.createDiv({ cls: "zos-card-title", attr: { style: "justify-content: space-between;" } });
hHeader.createDiv({ text: "🧬 BIO-METRICS (WEEKLY)" });
const addBtn = hHeader.createDiv({ 
    text: "ADD HABIT +", 
    attr: { style: "font-size: 0.75em; opacity: 0.6; cursor: pointer; color: var(--zos-accent); font-weight: 800; background: rgba(var(--zos-accent-rgb), 0.1); padding: 5px 15px; border-radius: 20px; transition: all 0.3s ease;" }
});
// ── CARD: GITHUB ACTIVITY — devxerve ────────────────────────
const cardGH = dv.container.createDiv({ cls: "zos-card", attr: { style: "margin-top:32px;" } });
 
// Header con botón refresh
const ghHeader = cardGH.createDiv({ cls: "zos-card-title", attr: { style: "justify-content:space-between;" } });
ghHeader.createDiv({ text: "🐙 GITHUB — devxerve" });
const ghRefresh = ghHeader.createDiv({ cls: "zos-refresh-icon" });
try { setIcon(ghRefresh, "refresh-cw"); } catch(e) { ghRefresh.innerText = "↺"; }
 
const ghBody = cardGH.createDiv();
 
async function loadGitHub() {
    ghBody.innerHTML = `<div style="opacity:0.4;font-size:0.85em;padding:8px 0;">Loading GitHub data…</div>`;
 
    try {
        const USERNAME = "devxerve";
        const CACHE_KEY = "zos-gh-cache";
        const CACHE_TTL = 5 * 60 * 1000; // 5 min
 
        // Cache para no spammear la API
        const cached = localStorage.getItem(CACHE_KEY);
        let repos, events;
 
        if (cached) {
            const parsed = JSON.parse(cached);
            if (Date.now() - parsed.ts < CACHE_TTL) {
                repos  = parsed.repos;
                events = parsed.events;
            }
        }
 
        if (!repos || !events) {
            const [rRes, eRes] = await Promise.all([
                fetch(`https://api.github.com/users/${USERNAME}/repos?sort=pushed&per_page=5`),
                fetch(`https://api.github.com/users/${USERNAME}/events/public?per_page=30`)
            ]);
            repos  = await rRes.json();
            events = await eRes.json();
            localStorage.setItem(CACHE_KEY, JSON.stringify({ repos, events, ts: Date.now() }));
        }
 
        if (!Array.isArray(repos)) {
            ghBody.innerHTML = `<div style="opacity:0.4;font-size:0.85em;">GitHub API rate limit reached. Try again in a minute.</div>`;
            return;
        }
 
        // Commits de los últimos 30 eventos
        const pushEvents   = events.filter(e => e.type === "PushEvent");
        const totalCommits = pushEvents.reduce((acc, e) => acc + (e.payload.commits?.length || 0), 0);
 
        // Días con actividad (streak aproximado)
        const activeDays = [...new Set(pushEvents.map(e => e.created_at.slice(0, 10)))];
        activeDays.sort((a, b) => b.localeCompare(a));
 
        let streak = 0;
        const today = new Date();
        for (let i = 0; i < activeDays.length; i++) {
            const d = new Date(activeDays[i]);
            const diffDays = Math.round((today - d) / 86400000);
            if (diffDays === i || diffDays === i + 1) streak++;
            else break;
        }
 
        // Último evento
        const lastPush = pushEvents[0];
        const lastRepo = lastPush ? lastPush.repo.name.replace(`${USERNAME}/`, "") : "—";
        const lastMsg  = lastPush?.payload.commits?.[0]?.message?.split('\n')[0] || "—";
        const lastDate = lastPush ? new Date(lastPush.created_at) : null;
        const lastAgo  = lastDate ? (() => {
            const mins = Math.round((Date.now() - lastDate) / 60000);
            if (mins < 60)   return `${mins}m ago`;
            if (mins < 1440) return `${Math.round(mins/60)}h ago`;
            return `${Math.round(mins/1440)}d ago`;
        })() : "—";
 
        // Mini heatmap — últimos 14 días
        const commitsByDay = {};
        pushEvents.forEach(e => {
            const day = e.created_at.slice(0, 10);
            commitsByDay[day] = (commitsByDay[day] || 0) + (e.payload.commits?.length || 0);
        });
        const heatmapDays = Array.from({ length: 14 }, (_, i) => {
            const d = new Date(); d.setDate(d.getDate() - (13 - i));
            return d.toISOString().slice(0, 10);
        });
 
        const heatmapHTML = heatmapDays.map(day => {
            const count = commitsByDay[day] || 0;
            const alpha = count === 0 ? 0.06 : count <= 2 ? 0.3 : count <= 5 ? 0.6 : 1;
            const title = `${day}: ${count} commit${count !== 1 ? 's' : ''}`;
            return `<div title="${title}" style="width:16px;height:16px;border-radius:4px;background:rgba(var(--zos-accent-rgb),${alpha});cursor:default;transition:transform 0.15s;" onmouseenter="this.style.transform='scale(1.3)'" onmouseleave="this.style.transform='scale(1)'"></div>`;
        }).join("");
 
        // Repos list
        const reposHTML = repos.slice(0, 5).map(r => {
            const pushedAgo = (() => {
                const mins = Math.round((Date.now() - new Date(r.pushed_at)) / 60000);
                if (mins < 60)   return `${mins}m`;
                if (mins < 1440) return `${Math.round(mins/60)}h`;
                return `${Math.round(mins/1440)}d`;
            })();
            const lang = r.language || "—";
            const langColor = {
                JavaScript:"#f7df1e", TypeScript:"#3178c6", Java:"#b07219",
                Python:"#3572A5", Kotlin:"#A97BFF", "C++":"#f34b7d",
                HTML:"#e34c26", CSS:"#563d7c", Shell:"#89e051"
            }[lang] || "rgba(255,255,255,0.3)";
            return `
                <div style="display:flex;align-items:center;gap:10px;padding:10px 12px;border-radius:11px;background:rgba(255,255,255,0.02);border:1px solid rgba(255,255,255,0.05);margin-bottom:7px;transition:background 0.2s;"
                     onmouseenter="this.style.background='rgba(var(--zos-accent-rgb),0.05)'"
                     onmouseleave="this.style.background='rgba(255,255,255,0.02)'"
                     onclick="window.open('${r.html_url}','_blank')" style="cursor:pointer;">
                    <div style="flex-grow:1;min-width:0;">
                        <div style="font-weight:600;font-size:0.88em;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;">${r.name}</div>
                        <div style="font-size:0.65em;opacity:0.4;margin-top:2px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;">${r.description || 'No description'}</div>
                    </div>
                    <div style="display:flex;align-items:center;gap:8px;flex-shrink:0;">
                        <div style="display:flex;align-items:center;gap:4px;">
                            <div style="width:8px;height:8px;border-radius:50%;background:${langColor};"></div>
                            <span style="font-size:0.6em;font-family:var(--zos-font-mono);opacity:0.5;">${lang}</span>
                        </div>
                        <div style="font-size:0.6em;font-family:var(--zos-font-mono);opacity:0.35;">${pushedAgo}</div>
                        <div style="font-size:0.6em;opacity:0.35;">⭐${r.stargazers_count}</div>
                    </div>
                </div>`;
        }).join("");
 
        ghBody.innerHTML = `
            <!-- Stats row -->
            <div style="display:grid;grid-template-columns:repeat(3,1fr);gap:10px;margin-bottom:20px;">
                <div style="background:rgba(var(--zos-accent-rgb),0.07);border:1px solid rgba(var(--zos-accent-rgb),0.15);border-radius:12px;padding:12px;text-align:center;">
                    <div style="font-family:var(--zos-font-head);font-size:1.8em;font-weight:800;color:var(--zos-accent);line-height:1;">${totalCommits}</div>
                    <div style="font-size:0.58em;font-family:var(--zos-font-mono);text-transform:uppercase;letter-spacing:1.5px;opacity:0.45;margin-top:3px;">commits</div>
                </div>
                <div style="background:rgba(var(--zos-accent-rgb),0.07);border:1px solid rgba(var(--zos-accent-rgb),0.15);border-radius:12px;padding:12px;text-align:center;">
                    <div style="font-family:var(--zos-font-head);font-size:1.8em;font-weight:800;color:var(--zos-accent);line-height:1;">${streak}</div>
                    <div style="font-size:0.58em;font-family:var(--zos-font-mono);text-transform:uppercase;letter-spacing:1.5px;opacity:0.45;margin-top:3px;">day streak</div>
                </div>
                <div style="background:rgba(var(--zos-accent-rgb),0.07);border:1px solid rgba(var(--zos-accent-rgb),0.15);border-radius:12px;padding:12px;text-align:center;">
                    <div style="font-family:var(--zos-font-head);font-size:1.8em;font-weight:800;color:var(--zos-accent);line-height:1;">${repos.length}</div>
                    <div style="font-size:0.58em;font-family:var(--zos-font-mono);text-transform:uppercase;letter-spacing:1.5px;opacity:0.45;margin-top:3px;">repos</div>
                </div>
            </div>
 
            <!-- Last commit -->
            <div style="background:rgba(255,255,255,0.02);border:1px solid rgba(255,255,255,0.06);border-radius:12px;padding:12px 14px;margin-bottom:20px;">
                <div style="font-size:0.6em;font-family:var(--zos-font-mono);text-transform:uppercase;letter-spacing:2px;opacity:0.35;margin-bottom:6px;">Last push · ${lastAgo}</div>
                <div style="font-weight:600;font-size:0.88em;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;color:rgba(255,255,255,0.85);">${lastMsg}</div>
                <div style="font-size:0.65em;opacity:0.4;margin-top:3px;font-family:var(--zos-font-mono);">→ ${lastRepo}</div>
            </div>
 
            <!-- Heatmap 14 días -->
            <div style="margin-bottom:20px;">
                <div style="font-size:0.6em;font-family:var(--zos-font-mono);text-transform:uppercase;letter-spacing:2px;opacity:0.35;margin-bottom:8px;">Activity · last 14 days</div>
                <div style="display:flex;gap:5px;align-items:center;">${heatmapHTML}</div>
            </div>
 
            <!-- Repos -->
            <div>
                <div style="font-size:0.6em;font-family:var(--zos-font-mono);text-transform:uppercase;letter-spacing:2px;opacity:0.35;margin-bottom:10px;">Recent repos</div>
                ${reposHTML}
            </div>
        `;
    } catch(e) {
        ghBody.innerHTML = `<div style="opacity:0.4;font-size:0.85em;">Could not load GitHub data. Check your connection.</div>`;
        console.error("GitHub card error:", e);
    }
}
 
ghRefresh.onclick = (e) => {
    e.stopPropagation();
    localStorage.removeItem("zos-gh-cache");
    loadGitHub();
};
 
loadGitHub();

// Grid de hábitos: 2 columnas dentro del span-8
const hGrid = cardHabits.createDiv({ attr: { style: "display: grid; grid-template-columns: repeat(2, 1fr); gap: 14px;" }});

function renderHabits() {
    hGrid.innerHTML = "";
    savedHabits.forEach((h, idx) => {
        const strip = hGrid.createDiv({ cls: "zos-habit-strip" });
        const nameEl = strip.createDiv({ text: h.toUpperCase(), cls: "zos-habit-title" });
        
        strip.oncontextmenu = (e) => {
            e.preventDefault();
            Utils.showModal({
                title: "Edit Habit",
                value: h,
                onSave: (newName) => {
                    savedHabits[idx] = newName;
                    localStorage.setItem("zos-final-habits", JSON.stringify(savedHabits));
                    renderHabits();
                    Utils.updateBars();
                },
                onDelete: () => {
                    savedHabits.splice(idx, 1);
                    localStorage.setItem("zos-final-habits", JSON.stringify(savedHabits));
                    renderHabits();
                    Utils.updateBars();
                }
            });
        };

        const dots = strip.createDiv({ cls: "zos-dot-grid" });
        for(let i=1; i<=7; i++) {
            const key = `zos-v28-h-${h}-${i}`;
            const dot = dots.createDiv({ cls: `zos-dot ${localStorage.getItem(key) ? 'active' : ''}` });
            dot.onclick = (ev) => {
                ev.stopPropagation();
                dot.classList.toggle('active');
                localStorage.getItem(key) ? localStorage.removeItem(key) : localStorage.setItem(key, '1');
                Utils.updateBars();
            };
        }
    });
}

addBtn.onclick = () => {
    Utils.showModal({
        title: "New Habit",
        placeholder: "E.g.: Read 30 min...",
        onSave: (name) => {
            savedHabits.push(name);
            localStorage.setItem("zos-final-habits", JSON.stringify(savedHabits));
            renderHabits();
            Utils.updateBars();
        }
    });
};

addBtn.onmouseenter = () => { addBtn.style.opacity = "1"; addBtn.style.transform = "translateY(-2px)"; };
addBtn.onmouseleave = () => { addBtn.style.opacity = "0.6"; addBtn.style.transform = "translateY(0)"; };

renderHabits();
Utils.updateBars();

// --- DISCOVERY (span-12 full width) ---
const discovery = container.createDiv({ attr: { style: "margin-top: 28px;" }});
const cardSeren = discovery.createDiv({ cls: "zos-card" });
const sHead = cardSeren.createDiv({ cls: "zos-card-title", attr: { style: "justify-content: space-between;" }});
sHead.createDiv({ text: "💡 SERENDIPITY" });
const ref = sHead.createDiv({ cls: "zos-refresh-icon", text: "↺" });

const sBody = cardSeren.createDiv({ attr: { style: "margin-top: 10px;" } });
function getRand() {
    sBody.innerHTML = "";
    const all = dv.pages().array();
    const r = all[Math.floor(Math.random() * all.length)];
    if(r) {
        const l = sBody.createDiv({ text: r.file.name, attr: { style: "font-family: var(--zos-font-ser); font-size: 2.2em; cursor: pointer; color: var(--zos-accent);" }});
        l.onclick = () => app.workspace.openLinkText(r.file.path, "", false);
    }
}

ref.onclick = (e) => { e.stopPropagation(); getRand(); new Notice("Syncing new idea..."); };
getRand();
```