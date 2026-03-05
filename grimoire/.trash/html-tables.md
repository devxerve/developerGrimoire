---
cssclasses:
  - "centerTitles "
  - " centerImages "
  - " roundedImages"
---

---
# :dev_html5_original: Tablas Html5


```html cpp title:Tablas
<body>
	<style>  
            table{  
                border-collapse:collapse;  
                caption-side: bottom;  
            }  
            caption{  
                font-weight:bold;  
                margin-top:16px;  
            }  
            th,td{padding:5px 10px;}  
            td,th{border:1px solid #1c1c1c;text-align:center;}

	</style>
	<table>
		<caption>Este es el titulo de la tabla</caption>
		<thead>
			<tr>
				<th>Ciudad</th>
				<th>Aeropuerto</th>
				<th>Playa</th>
				<th>Habitantes</th>
			</tr>
		</thead>
		<tbody>
			<tr>
				<td>Salamanca</td>
				<td>Sí</td>
				<td>No</td>
				<td>180000</td>
			</tr>
			<tr>
				<td>Valencia</td>
				<td>Sí</td>
				<td>Sí</td>
				<td>450000</td>
			</tr>
			<tr>
				<td>Madrid</td>
				<td>Sí</td>
				<td>No</td>
				<td>40000000</td>
			</tr>
			<tr>
				<td>Palencia</td>
				<td>No</td>
				<td>No</td>
				<td>76738</td>
			</tr>
		</tbody>
	</table>
	<table>
        <tbody>
           <tr>
                <td>A</td>
                <td>B</td>
                <td>C</td>
                <td>D</td>
           </tr>
            <tr>
                <td rowspan="2">E,I</td>
                <td>F</td>
                <td colspan="2">G,H</td>
           </tr>
           <tr>
                <td>j</td>
                <td rowspan="2">K,O</td>
                <td>L</td>
           </tr>
	       <tr>
                <td>M</td>
                <td>N</td>
                <td>P</td>
           </tr>      
        </tbody>
    </table>
</body>
```





# References
