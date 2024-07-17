# Proyecto de Análisis de Datos de Telecomunicaciones en Argentina

## Índice
1. [Introducción](#introducción)
2. [Herramientas Utilizadas](#herramientas-utilizadas)
3. [Proceso de ETL](#proceso-de-etl)
4. [Análisis Exploratorio de Datos (EDA)](#análisis-exploratorio-de-datos-eda)
5. [Desarrollo de KPIs](#desarrollo-de-kpis)
6. [Visualización en Power BI](#visualización-en-power-bi)
7. [Conclusiones](#conclusiones)
8. [Anexos](#anexos)

## Introducción
Este proyecto se centra en el análisis de datos de telecomunicaciones en Argentina, con un enfoque particular en los accesos a internet por tecnologías y por velocidades, tanto a nivel nacional como provincial. El objetivo principal fue identificar desigualdades y desequilibrios en los servicios de internet y extraer conclusiones significativas sobre el estado actual de las telecomunicaciones en el país.

## Herramientas Utilizadas
Para llevar a cabo este proyecto, se utilizaron las siguientes herramientas:
- **Python** (dentro de Visual Studio Code): Utilizado para el proceso de ETL y el Análisis Exploratorio de Datos (EDA).
  - Librerías: `pandas`, `numpy`, `matplotlib`, `seaborn`
- **Power BI**: Utilizado para la visualización de datos y la creación de dashboards interactivos.
- **DAX**: Lenguaje de expresiones utilizado en Power BI para crear medidas y cálculos avanzados.

## Proceso de ETL
El proceso de ETL (Extracción, Transformación y Carga) se realizó principalmente en Python. Las etapas incluyeron:
- **Extracción**: Se obtuvieron los datos de varias hojas de un archivo Excel proporcionado por la ENACOM.
- **Transformación**: 
  - Normalización de datos.
  - Descarte de tablas con alta proporción de información faltante.
  - Creación de columnas adicionales para el análisis.
  - Limpieza de datos y manejo de valores nulos.
- **Carga**: Los datos transformados se exportaron para ser utilizados en Power BI.

## Análisis Exploratorio de Datos (EDA)
Durante el EDA, se utilizaron gráficos y estadísticas descriptivas para comprender mejor los datos. Algunas de las técnicas y visualizaciones incluyeron:
- Histogramas y diagramas de caja (boxplots) para analizar la distribución de los datos.
- Gráficos de barras y líneas para visualizar tendencias temporales.
- Análisis de outliers y datos atípicos.

## Desarrollo de KPIs
Se plantearon tres KPIs iniciales, de los cuales dos fueron seleccionados para ser incluidos en el dashboard final:
1. **Crecimiento de Accesos por Provincia**:
   - Medida: Crecimiento porcentual de accesos a internet por cada 100 habitantes.
2. **Desigualdad en el Acceso**:
   - Medida: Comparación de accesos entre provincias centrales y no centrales.

### Medida de Crecimiento de Accesos (KPI)
```dax
Crecimiento Accesos (KPI) = 
    CALCULATE(
        SUM(resultado_penetracion_kpi_3[Accesos por cada 100 hab]),
        DATESINPERIOD(resultado_penetracion_kpi_3[Año], MAX(resultado_penetracion_kpi_3[Año]), -1, YEAR)
    )
Visualización en Power BI
Se creó un dashboard interactivo en Power BI con los siguientes elementos:

KPIs en primer plano: Los KPIs seleccionados se mostraron en la parte superior del dashboard para resaltar las métricas clave.
Gráficos de Análisis General:
Gráficos de barras para visualizar los accesos por tecnologías y velocidades.
Gráficos de líneas para mostrar tendencias temporales de accesos.
Medidas DAX: Utilizadas para cálculos específicos en los KPIs y otros análisis.
Conclusiones
Las conclusiones principales del análisis indican una gran desigualdad en el acceso a internet en diferentes partes del país:

Desigualdad Regional: Provincias como Buenos Aires y Capital Federal lideran en accesos, mientras que provincias no centrales muestran un acceso significativamente menor, con outliers como San Luis.
Variabilidad de los Datos: Los boxplots sugieren una gran variabilidad en los datos de acceso a internet y telecomunicaciones entre diferentes regiones, con frecuentes casos extremos o atípicos.
Gráficos y Análisis:

Anexos
Código Python: Código utilizado para el ETL y EDA.
Medidas DAX: Listado de todas las medidas creadas en Power BI.
Gráficos Adicionales: Gráficos y visualizaciones adicionales no incluidas en el dashboard principal.
