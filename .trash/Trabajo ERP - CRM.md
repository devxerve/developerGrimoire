---
cssclasses:
  - center-titles
---
![[Logo_ufv.png]]
# Trabajo Benchmarking ERP-CRM

## 1. Objetivo del Trabajo

El objetivo principal es realizar un benchmarking de sistemas ERP-CRM, tanto propietarios como open source, junto con herramientas de datamining, para seleccionar la mejor opción CRM aplicable al trabajo de SGE (Sistema de Gestión Empresarial) en el contexto dual de la profesora Puebla. Este análisis permite comparar funcionalidades, costos y adaptabilidad a empresas medianas y pymes de Madrid, facilitando una decisión informada para implementación en entornos reales. Se busca equilibrar soporte profesional con flexibilidad económica, considerando necesidades como gestión de clientes, inventarios y análisis predictivo​

## 2. Tipos de Clientes y Empresas Objetivo

Las empresas objetivo son pymes y medianas empresas de Madrid en sectores como servicios (73% de pymes españolas), comercio, construcción e industria. Ejemplos concretos en Madrid incluyen Beedigital (soluciones digitales para negocios), Musal Defier (cerramientos de cristal y techos móviles), AR14 Soluciones Tecnológicas (tecnología), Electrofuture New Technology Systems (sistemas LED), y agencias de traducción especializadas. Estas empresas, con menos de 250 empleados y facturación bajo 50 millones de euros, necesitan ERP-CRM para optimizar ventas, clientes y operaciones diarias sin altos costos.​

| Tipo de Empresa     | Ejemplos Madrid                   | Tamaño Aproximado | Necesidades Clave                      |
| ------------------- | --------------------------------- | ----------------- | -------------------------------------- |
| Servicios digitales | Beedigital, AR14 Soluciones       | <50 empleados     | CRM para clientes, facturación modular |
| Construcción        | Musal Defier                      | 50-100 empleados  | Gestión proyectos, inventarios         |
| Tecnología          | Electrofuture                     | Micro-pyme        | Stock LED, ventas online               |
| Comercio            | Alquiler material infantil Madrid | <10 empleados     | CRM simple, campañas pymeactual+1      |

## 3. Descripción de Productos ERP-CRM Bajo Licencia (5)

Son programas de pago con código cerrado. El cliente paga licencias y depende del proveedor para soporte y actualizaciones.​

- SAP S/4HANA: ERP completo para grandes empresas (finanzas, ventas, producción).​
    
- Microsoft Dynamics 365: ERP + CRM integrado, por usuarios mensuales.​
    
- Oracle NetSuite: Todo en nube (contabilidad, CRM, inventarios).​
    
- Sage X3: Para pymes medianas, con módulos de fábrica y ventas.​
    
- Odoo Enterprise: Versión paga de Odoo con extras premium.​
    

Ventajas: Soporte oficial y fácil uso. Desventaja: Caro y menos flexible.​

## 4. Descripción de Productos ERP-CRM Libres (5)

Son gratis (código abierto), se pagan solo servicios. Puedes modificar el código.​

- Odoo Community: ERP+CRM modular (facturas, clientes, stock).​
    
- Dolibarr: Simple para pymes (facturación, CRM, proyectos).​
    
- ERPNext: Completo (producción, contabilidad, HR).​
    
- SuiteCRM: CRM puro (contactos, campañas, tickets).​
    
- Vtiger Open Source: CRM con ventas y soporte al cliente.[​
    

Ventajas: Gratis y personalizable. Desventaja: Necesita más configuración.​

## 5. Descripción de Productos Datamining (5)

Herramientas de datamining para análisis predictivo, integración con ERP-CRM en pymes.

- KNIME: Open source, visual para flujos de datos, machine learning sin código.​
    
- RapidMiner: Plataforma freemium, preparación datos y modelos predictivos para ventas.​
    
- Orange: Visual programming para datamining, ideal principiantes en análisis CRM.​
    
- Weka: Suite open source Java para clustering, clasificación en datos empresariales.​
    
- DataRobot: Automatizado con IA, para pronósticos en inventarios y clientes.​
    

Estas permiten extraer insights de datos CRM para pymes madrileñas, como predicción de churn en servicios.​

## 6. Estudio Comparativo

Se compara en dimensiones clave para pymes Madrid: costo, facilidad, escalabilidad y datamining.

| Categoría                  | Costo Inicial             | Facilidad Uso         | Escalabilidad | Integración Datamining | Ejemplo Uso Madrid               |
| -------------------------- | ------------------------- | --------------------- | ------------- | ---------------------- | -------------------------------- |
| Licencia (ej. Sage X3)     | Alto (licencias/usuarios) | Alta (soporte)        | Media-Alta    | Media (add-ons pagos)  | ppl-ai-file-upload.s3.amazonaws​ |
| Libre (ej. Odoo Community) | Bajo (solo hosting)       | Media (configuración) | Alta (custom) | Alta (plugins gratis)  | Musal Defier proyectos f​        |
| Datamining (ej. KNIME)     | Gratis                    | Alta (visual)         | Alta          | N/A (herramienta pura) | Análisis clientes AR14           |
|                            |                           |                       |               |                        |                                  |

Libres destacan en costo/escalabilidad para pymes; licenciados en soporte rápido.​

## 7. Selección del CRM para el Trabajo de SGE

Se selecciona Odoo Community como CRM para SGE dual Puebla: modular, gratis, integrable con datamining (KNIME vía APIs), ideal para pymes Madrid como Electrofuture. Soporta facturación, stock y campañas, personalizable sin vendor lock-in, alineado con presupuestos limitados y necesidades de crecimiento.

## 8. Resultados

Odoo Community ofrece mejor ROI para empresas objetivo: 80% ahorro vs licenciados, alta personalización para Madrid (ej. multimoneda EU), integración datamining para predictivos ventas. Recomendación: Implementar en SGE con prueba piloto en pyme ​

## 9. Referencias
​
- Directorio PYMEs Madrid[[pymeactual](https://www.pymeactual.es/empresas/p/madrid)]​
- Datos PYMEs España[[taxfix](https://taxfix.com/es-es/empresas/las-pymes-en-espana-ejemplos/)]​