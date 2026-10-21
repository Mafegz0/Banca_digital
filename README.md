# Segmentación de comercios | Banca digital

**Proyecto de análisis de datos y segmentación no supervisada** · Python · K-means · Power BI · **ASUM-DM**

> **Tipo de trabajo:** prueba técnica de analítica de datos. Los resultados corresponden al conjunto de datos del ejercicio (diciembre de 2020 a mayo de 2021); **no constituyen evidencia de campañas ejecutadas o incrementos comerciales realizados**.

## Problema y objetivo

Una plataforma de pagos obtiene una comisión estimada del **5 %** sobre las ventas registradas. El objetivo planteado en el ejercicio consiste en estudiar cómo elevar en un **50 %** esa comisión mediante estrategias comerciales diferenciadas para sus comercios.

Se realizó análisis exploratorio, consolidación de terminales, ingeniería de variables, segmentación con K-means y diseño de un tablero analítico en Power BI.

## Resultados del ejercicio

| Indicador | Resultado reportado |
|---|---:|
| Comercios únicos analizados | 3.015 |
| Terminales | 3.071 |
| Segmentos seleccionados | 4 |
| Silhouette (k = 4) | 0,37 |
| Davies–Bouldin (k = 4) | 0,92 |
| Comisión mensual estimada (base) | $100,97 millones |
| Comisión objetivo (+50 %) | $151,45 millones |

**Segmentación propuesta**

| Perfil | Comercios | Aporte estimado a comisiones | Acción comercial propuesta |
|---|---:|---:|---|
| Consolidados de alto valor | 234 | 17,67 % | Fidelización y prevención de pérdida de actividad |
| Comercios por reactivar | 622 | 1,64 % | Reactivación |
| Líderes en crecimiento | 1.002 | 65,39 % | Protección, escalamiento y beneficios por crecimiento |
| Activos con potencial | 1.157 | 15,30 % | Mejorar frecuencia y volumen transaccional |

Estas cifras describen la muestra y el análisis del ejercicio, **no una implementación comercial en producción**.

## Estructura por metodología ASUM-DM

| Fase | Entregables accesibles |
|---|---|
| [01 · Business Understanding](01_Business_Understanding/README.md) | Problema, alcance, objetivo e indicadores de negocio |
| [02 · Data Understanding](02_Data_Understanding/README.md) | Exploración, granularidad, calidad y notebook EDA |
| [03 · Data Preparation](03_Data_Preparation/README.md) | Limpieza, agregación, variables y notebook de preparación |
| [04 · Modeling](04_Modeling/README.md) | Entrenamiento K-means, selección de k y perfiles de segmentos |
| [05 · Evaluation](05_Evaluation/README.md) | Métricas y evaluación de utilidad comercial; limitaciones |
| [06 · Deployment](06_Deployment/README.md) | Dashboard Power BI Desktop (.pbix) y documentación de entrega |

## Tecnologías

Python, pandas, NumPy, scikit-learn, Matplotlib, Seaborn, Excel y Power BI.

## Reproducibilidad y datos de la prueba

Este repositorio incorpora **los entregables originales de una prueba técnica de selección** autorizados para difusión por su autora: el libro Excel de entrada, cinco tablas CSV de datos intermedios/procesados, tres notebooks completos (incluyendo sus salidas de ejecución) y un archivo `.pbix` de Power BI Desktop.

### Ejecución de los notebooks

1. Instalar las dependencias indicadas en [`requirements.txt`](requirements.txt) (el inventario completo del entorno original está en [`requirements-full.txt`](requirements-full.txt)).
2. Abrir y ejecutar [`02_Data_Understanding/01_eda_comercios_transacciones.ipynb`](02_Data_Understanding/01_eda_comercios_transacciones.ipynb).
3. Ejecutar [`03_Data_Preparation/02_preparacion_base_segmentacion.ipynb`](03_Data_Preparation/02_preparacion_base_segmentacion.ipynb).
4. Ejecutar [`04_Modeling/03_segmentacion_comercios.ipynb`](04_Modeling/03_segmentacion_comercios.ipynb).
5. Abrir [`dashboard/Prueba_Analista_Datos_Banca_Digital.pbix`](dashboard/Prueba_Analista_Datos_Banca_Digital.pbix) en Power BI Desktop.

Los notebooks utilizan rutas relativas `../data/`; abrirlos desde sus respectivas carpetas de fase para conservar ese convenio. Si Power BI detecta un origen local previo, actualizar la ruta a las tablas de `data/processed` en la máquina de ejecución.

El dataset corresponde al enunciado del ejercicio, no a un sistema bancario conectado en tiempo real. El dashboard no acredita una publicación en Power BI Service, ni las estrategias comerciales propuestas prueban resultados productivos.

## Estado

**Análisis, preparación, segmentación y tablero:** documentados en el material original. **Ejecución de campañas, validación de impacto real, publicación en Power BI Service y operación productiva:** no demostradas en el material suministrado.
