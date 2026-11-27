# Examen-BI

Proyecto de Business Intelligence desarrollado como resolución del examen de BI Engineer.

## Descripción del proyecto

El proyecto analiza datos de ventas y órdenes de servicio correspondientes al año 2021. A partir de información distribuida en diferentes archivos CSV, se realizó la exploración, limpieza, transformación y procesamiento de los datos para construir un modelo analítico tipo estrella y, finalmente, desarrollar un dashboard en Power BI que permita visualizar y analizar los resultados.

## Datos utilizados

Los datos originales se encuentran en `data/raw/`:

- `Q1_2021.csv`: información correspondiente al primer trimestre de 2021.
- `Q2_2021.csv`: información correspondiente al segundo trimestre de 2021.
- `Directorio.csv`: información de referencia utilizada durante el análisis.

Los datos procesados se organizaron en:

- `data/preprocessed/datos_2021.csv`: datos obtenidos después de integrar y preprocesar las fuentes originales.
- `data/processed/datos_procesados_2021.csv`: datos finales preparados mediante ciertos criterios mas interpretativos y reglas de negocio.

## Trabajo realizado

### 1. Exploración de los datos

Se creó el notebook [`01_exploracion.ipynb`](src/01_exploracion.ipynb) para:

- Cargar y revisar las fuentes de información.
- Identificar columnas, tipos de datos y estructura de los archivos.
- Analizar valores, categorías y posibles inconsistencias.
- Comprender el contenido de los datos antes de realizar transformaciones.

### 2. Preprocesamiento

En [`02_preprocesamiento.ipynb`](src/02_preprocesamiento.ipynb) se realizó:

- Integración de los datos de los trimestres disponibles.
- Limpieza y normalización de la información.
- Tratamiento de los datos necesarios para el análisis.
- Generación del archivo `data/preprocessed/datos_2021.csv`.

### 3. Procesamiento

En [`03_procesamiento.ipynb`](src/03_procesamiento.ipynb) se llevó a cabo:

- La transformación adicional de los datos considerando criterios propios y reglas de negocio.
- La preparación de variables y atributos analíticos.
- La generación del dataset final almacenado en `data/processed/datos_procesados_2021.csv`.

### 4. Consultas y análisis

El notebook [`04_consultas_seccion-1.ipynb`](src/04_consultas_seccion-1.ipynb) contiene las consultas realizadas sobre los datos procesados para resolver los requerimientos analíticos del examen y obtener indicadores relevantes.

### 5. Modelo dimensional

En [`05_modelo_estrella.ipynb`](src/05_modelo_estrella.ipynb) se construyó un modelo de datos tipo estrella compuesto por:

- **Tabla de hechos:** `FACT_ORDENES.csv`, con las medidas y las claves de las dimensiones.
- **Dimensión de vehículo:** `DIM_VEHICULO.csv`.
- **Dimensión de sucursal:** `DIM_SUCURSAL.csv`.
- **Dimensión de servicio:** `DIM_SERVICIO.csv`.
- **Dimensión de fecha:** `DIM_FECHA.csv`.

El diseño del modelo está documentado en:

- [`docs/Modelo Estrella.drawio`](docs/Modelo%20Estrella.drawio)
- [`docs/Esquema Estrella.drawio.png`](docs/Esquema%20Estrella.drawio.png)

## Dashboard

El resultado final se encuentra en [`dashboard/Reporte_Ventas.pbix`](dashboard/Reporte_Ventas.pbix), creado en Microsoft Power BI.

El reporte utiliza las tablas dimensionales almacenadas en `dashboard/` y presenta una vista visual de los indicadores de ventas y órdenes para facilitar el análisis de la información.

Una versión exportada del reporte está disponible en [`docs/Reporte_Ventas.pdf`](docs/Reporte_Ventas.pdf).

## Herramientas utilizadas

- Python
- Jupyter Notebook
- Pandas y NumPy
- DuckDB
- Matplotlib
- Microsoft Power BI
- Archivos CSV
- Modelo dimensional tipo estrella

## Uso del proyecto

### Instalar las dependencias

```bash
pip install -r requirements.txt
```

### Ejecutar los notebooks

```bash
jupyter notebook
```

Los notebooks deben ejecutarse en orden, desde `01_exploracion.ipynb` hasta `05_modelo_estrella.ipynb`, para reproducir el flujo de exploración, transformación y construcción del modelo.

### Consultar el dashboard

Abre el archivo `dashboard/Reporte_Ventas.pbix` con Microsoft Power BI Desktop.

##  Estructura del repositorio

```text
Examen-BI/
├── data/
│   ├── raw/          # Datos originales
│   ├── preprocessed/ # Datos integrados y preprocesados
│   └── processed/    # Datos finales preparados
├── src/              # Notebooks de exploración y transformación
├── dashboard/        # Modelo final y reporte de Power BI
├── docs/             # Esquema del modelo y exportación del reporte
├── requirements.txt  # Dependencias de Python
└── README.md
```
