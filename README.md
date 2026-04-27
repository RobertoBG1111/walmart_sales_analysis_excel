# Análisis de Ventas Walmart 2012 — Eficiencia y Participación por Departamento
Autor: Roberto Barrera García

Programa: Certificación Data Analyst — TripleTen Bootcamp

Sprint: Transformando Datos para Insights de Negocio

Herramienta principal: Microsoft Excel / Google Sheets

## Contexto del proyecto
La dirección comercial de Walmart necesitaba información clara para tomar decisiones de presupuesto e inventario para el Q1 2013. El dataset contiene registros de ventas semanales por tienda y departamento durante el año 2012.

**Preguntas de negocio a responder:**

¿Qué departamentos fueron más eficientes en generar ventas por metro cuadrado?

¿Qué departamentos aportaron más al negocio y cuáles estuvieron por debajo de su potencial?

## Estructura del archivo
| Hoja | Descripción | Tipo |
|---|----|---|
| raw_ventas | Datos originales de ventas semanales por tienda y departamento | Raw Data |
| raw_departamento | Catálogo de departamentos con sus nombres | Lookup |
| raw_tiendas | Catálogo de tiendas con tipo (A/B) y tamaño en m² | Lookup | 
| clean_ventas | Datos depurados con uniones de catálogos, semana estandarizada y nombre de departamento | Clean Data |
| Pivot | Tablas dinámicas para el cálculo de KPIs | Análisis | 
| Dashboard | Visualización interactiva con selector de departamento | Visualización | 
| Resumen | Recopilación de hallazgos con contexto, insight e implicación | Reporte |

## Proceso de limpieza

- Se unieron los tres datasets (ventas, departamentos, tiendas) mediante referencias cruzadas.
- Se estandarizó el formato de fechas a semana (YYYY-WW).
- Se detectaron 27 registros con ventas negativas, interpretados como devoluciones o garantías. Se mantuvieron en el dataset ya que impactan proporcionalmente las ventas totales de sus departamentos en las tablas dinámicas.
- Se identificaron registros sin departamento asignado, clasificados como "No tiene dept" para no perder el dato.
- Se validó que ninguna tienda tuviera tamaño en m² igual a cero.

## KPIs utilizados
| KPI | Fórmula | Interpretación | 
| --- | --- | --- |
| Eficiencia (Ventas/m²) | Ventas totales / Tamaño promedio de tiendas | A mayor valor, mayor rendimiento por espacio físico. | 
| Participación del departamento | Ventas depto / Ventas totales | Indica el peso relativo de cada departamento en el negocio. |

## Visualizaciones
### Eficiencia por departamento (Ventas/m²)

<img width="1483" height="390" alt="Captura de pantalla 2026-04-23 131956" src="https://github.com/user-attachments/assets/5d157a10-6cc5-4ce3-a3f3-ab8fb776a0d6" />

### Participación por departamento

<img width="1230" height="398" alt="Captura de pantalla 2026-04-23 132013" src="https://github.com/user-attachments/assets/dfb5b152-cfac-4778-a9fe-c8c9ee3a34c3" />

### Dashboard interactivo

<img width="1247" height="603" alt="Captura de pantalla 2026-04-23 132142" src="https://github.com/user-attachments/assets/96373850-b508-4b8b-94cc-07b3f307ad55" />


*El dashboard permite seleccionar un departamento y visualizar sus KPIs individuales (eficiencia y participación) en el contexto del total de la cadena.*

## Hallazgos principales

1. Eficiencia (Ventas/m²)

*Despensa y Básicos lidera con $652.81/m², mientras que Jardín y Vida al Aire Libre registra la menor eficiencia con $42.86/m²: una brecha de 15x entre ambos departamentos.*

- Los 3 departamentos más eficientes concentran el mayor volumen de ventas absolutas.
- Jardín y Vida al Aire Libre, junto con Oficina, Escuela y Manualidades, muestran un rendimiento significativamente por debajo del promedio.

2. Participación del departamento

*Despensa y Básicos, Comida Fresca y Artículos del Hogar y Papel suman el 36.43% de las ventas totales de la cadena en 2012.*

- El 5.27% de las ventas corresponde a artículos sin departamento asignado, lo que representa una oportunidad de mejora en el registro de datos.
- Jardín y Oficina combinados apenas alcanzan el 2.54% de participación.

## Recomendaciones
| Acción | Responsable | Plazo |
| --- | --- | --- |
| Reducir el espacio físico asignado al dept. Jardín e incrementar inventario en los 3 departamentos más eficientes | Dirección Comercial | Q1 2013 |
| Reubicar en los departamentos correspondientes los artículos sin clasificación (5.27% de ventas) | Dirección Comercial | Q1 2013 |

## Limitaciones del proyecto

- El dashboard actualiza los KPIs individuales por departamento, pero las gráficas muestran el contexto general de toda la cadena (no se filtran por selección). Esto es una mejora identificada para versiones futuras con herramientas más avanzadas como Power BI o Tableau.
- El análisis de eficiencia por m² asume el tamaño promedio de tiendas como denominador, lo que nivela diferencias entre tiendas individuales.

## Habilidades practicadas

- Limpieza y validación de datos en hojas separadas.
- Unión de múltiples tablas mediante referencias cruzadas (VLOOKUP / BUSCARV).
- Construcción de tablas dinámicas para agregación y cálculo de KPIs.
- Diseño de gráficas orientadas a comunicar insights de negocio.
- Construcción de un dashboard básico con selector dinámico.
- Redacción de hallazgos en formato ejecutivo: contexto → insight → implicación.

---
*Proyecto desarrollado como parte del bootcamp de análisis de datos de TripleTen.*
