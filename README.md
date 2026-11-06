# Proyecto Empresa Aliada – Entregable 2

## Análisis exploratorio y visualización de datos de ventas

## 1. Propósito del proyecto

El propósito de este proyecto es realizar un análisis exploratorio de los datos de ventas mediante herramientas de visualización en Python. Para desarrollar este entregable se utilizó el archivo `Productos.xlsx`, generado durante el proyecto anterior de limpieza e integración de datos. A partir de esta información se realizaron diferentes gráficas que permiten explorar la distribución de las ventas, analizar su comportamiento a través del tiempo, identificar relaciones entre variables, comparar las ventas por región.

Se realizó un tratamiento similar al proceso anterior, tomando como base la información previamente consolidada y utilizándola para generar nuevas visualizaciones y facilitar la interpretación de los datos.

## 2. Datos utilizados

Se utilizó el archivo:

- **Productos.xlsx:** documento generado en el entregable anterior, que contiene la información integrada de ventas, productos, categorías, segmentos y calendario.

Para este análisis se consideraron principalmente las siguientes variables:

| Variable | Descripción |
|---|---|
| `DATE` | Fecha de registro de las ventas. |
| `TOTAL_VALUE_SALES` | Valor total de las ventas. |
| `TOTAL_UNIT_SALES` | Cantidad de unidades vendidas. |
| `FORMAT` | Formato del producto. |
| `CATEGORY` | Categoría del producto. |
| `CATEGORY_y` | Categoría obtenida durante la integración de datos. |
| `BRAND` | Marca del producto. |
| `SEGMENT` | Segmento del producto. |
| `MANUFACTURER` | Fabricante del producto. |
| `REGION` | Región geográfica de las ventas. |

## 3. Herramientas y tecnologías utilizadas

- **Python:** lenguaje de programación utilizado para el análisis.
- **Pandas:** biblioteca para cargar, consultar y agrupar los datos.
- **NumPy:** biblioteca para operaciones numéricas.
- **Matplotlib:** herramienta para generar y personalizar gráficas.
- **Seaborn:** biblioteca utilizada para crear visualizaciones estadísticas.
- **Jupyter Notebook:** entorno de trabajo para ejecutar y documentar el código.

## 4. Técnicas de análisis y visualización aplicadas

### 4.1. Carga y revisión de los datos

Se cargó el archivo `Productos.xlsx` mediante la función `pd.read_excel()` de Pandas.

Posteriormente, se utilizó `info()` para revisar las columnas, los tipos de datos y la estructura general del DataFrame.

También se identificaron los valores únicos de diferentes variables, como `CATEGORY`, `CATEGORY_y`, `FORMAT`, `BRAND`, `SEGMENT` y `MANUFACTURER`, con la finalidad de conocer las categorías disponibles y seleccionar las variables adecuadas para el análisis.

### 4.2. Distribución de ventas por formato

Se utilizaron histogramas para visualizar la distribución del valor total de las ventas (`TOTAL_VALUE_SALES`) de acuerdo con los diferentes formatos de producto (`FORMAT`).

Para facilitar la interpretación, se generó una gráfica independiente para cada formato, evitando que la información se mezclara y dificultara su lectura.

Se utilizó la función `sns.histplot()`, configurando 30 intervalos (*bins*) y agregando una curva KDE para observar la distribución de los valores.

**Conclusión:**

La generación de histogramas independientes permite distinguir cómo se distribuyen las ventas en cada formato e identificar cuáles presentan una mayor concentración de valores de venta. Esta separación facilita la comparación y evita que las diferentes categorías se confundan en una sola visualización.

### 4.3. Tendencia de ventas a lo largo del tiempo

Se agruparon los registros por fecha mediante `groupby()` y se calculó la suma de `TOTAL_VALUE_SALES` para cada fecha.

Posteriormente, se utilizó una gráfica de líneas con `sns.lineplot()` para visualizar el comportamiento de las ventas a lo largo del periodo disponible.

**Conclusión:**

Esta gráfica permite observar el comportamiento de las ventas a través del tiempo, identificar fechas o periodos con mayores y menores valores de venta y reconocer posibles variaciones en la actividad comercial.

### 4.4. Relación entre unidades vendidas y valor de ventas

Se utilizó una gráfica de dispersión con línea de regresión mediante `sns.regplot()` para explorar la relación entre las variables:

- `TOTAL_UNIT_SALES`: cantidad de unidades vendidas.
- `TOTAL_VALUE_SALES`: valor total de las ventas.

**Conclusión:**

Esta visualización permite analizar si existe una relación entre la cantidad de unidades vendidas y el valor total de las ventas. También facilita observar si, al aumentar las unidades vendidas, generalmente se incrementa el valor de las ventas, así como identificar posibles registros que se alejan del comportamiento general.

### 4.5. Ventas totales por región

Se agruparon los datos por medio de la variable `REGION` y se calculó la suma de `TOTAL_VALUE_SALES` para cada región.

Posteriormente, se generó una gráfica de barras con `sns.barplot()` para comparar los valores totales de venta entre las diferentes regiones.

**Conclusión:**

La gráfica permite comparar el desempeño de las regiones e identificar cuáles concentran un mayor valor de ventas y cuáles presentan valores menores. Esta información facilita conocer la distribución geográfica de las ventas.

### 4.6. Detección de posibles valores atípicos (*outliers*) por región

Se utilizó un diagrama de caja y bigotes (*boxplot*) mediante `sns.boxplot()`, considerando la variable `REGION` y el valor de `TOTAL_VALUE_SALES`.

Esta visualización permite examinar la distribución de las ventas en cada región e identificar observaciones que podrían presentar valores inusualmente altos o bajos respecto al resto de los registros.

**Conclusión:**

El diagrama permite identificar posibles valores atípicos en las ventas de cada región. Estos registros pueden representar operaciones con valores considerablemente diferentes al comportamiento habitual y requieren una revisión para determinar si corresponden a situaciones reales o a posibles inconsistencias en los datos.

## 5. Archivos y resultados generados

Durante la ejecución del proyecto se generaron las siguientes visualizaciones:

| Archivo | Descripción |
|---|---|
| `histograma_ventas_[formato].png` | Histograma de distribución de ventas por cada formato disponible. |
| `Tendencia_de_venta_largo_tiempo.png` | Gráfica de tendencia de ventas a lo largo del tiempo. |
| `Relacion_unidades_vendidas_y_valor_ventas.png` | Gráfica de relación entre unidades vendidas y valor de ventas. |
| `venta_totales_región.png` | Gráfica de ventas totales por región. |
| `Deteccion_outliers_ventas_region.png` | Diagrama de caja para identificar posibles valores atípicos por región. |

Las gráficas se guardaron en formato PNG para facilitar su consulta, presentación y utilización en el análisis.

## 6. Conclusiones

En este segundo entregable se aprovechó la información consolidada durante el proceso de limpieza e integración de datos para realizar un análisis exploratorio mediante diferentes técnicas de visualización.

Los histogramas permitieron examinar la distribución del valor de las ventas por formato; la gráfica de líneas permitió observar su comportamiento a lo largo del tiempo; la gráfica de dispersión facilitó explorar la relación entre las unidades vendidas y el valor total de las ventas; la gráfica de barras permitió comparar las ventas por región; y el diagrama de caja ayudó a identificar posibles valores atípicos.

En conjunto, estas visualizaciones facilitan la comprensión de la información y permiten identificar patrones, diferencias y comportamientos que pueden ser útiles para posteriores análisis y la toma de decisiones.

## 7. Estructura general del proyecto

```text
Proyecto_Empresa_Aliada_Entregable_2/
│
├── Productos.xlsx
├── Codigo.ipynb
│
├── histogramas_ventas/
│   └── histograma_ventas_[formato].png
│
├── Tendencia_de_venta_largo_tiempo.png
├── Relacion_unidades_vendidas_y_valor_ventas.png
├── venta_totales_región.png
└── Deteccion_outliers_ventas_region.png
```

**Nota:** El archivo `Productos.xlsx` corresponde a la base de datos consolidada en el entregable anterior. Las visualizaciones se generan y guardan al ejecutar el código en el directorio de trabajo.
