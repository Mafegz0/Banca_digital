# Segmentación de comercios — Prueba Analista de Datos

## Descripción

Este proyecto desarrolla el análisis y la segmentación de los comercios de una plataforma de pagos. El objetivo del negocio es incrementar en un 50 % las comisiones generadas por el uso de su API, teniendo en cuenta que la compañía recibe una comisión equivalente al 5 % de las ventas.

El trabajo incluye la exploración de los datos, la consolidación de los comercios y sus terminales, la creación de variables de comportamiento, un modelo de segmentación con K-means y un tablero en Power BI.

## Objetivo

Construir grupos de comercios con características similares para facilitar el diseño de campañas diferenciadas de fidelización, reactivación y crecimiento.

La unidad principal del análisis es:

> Una fila por comercio, consolidando todas sus terminales y su actividad durante los seis meses disponibles.

## Fuentes de información

El archivo original contiene dos hojas:

- `comercios`: información del comercio, categoría, ciudad, terminales y ventas.
- `transacciones`: cantidad mensual de transacciones por comercio.

El periodo analizado comprende desde diciembre de 2020 hasta mayo de 2021.

## Estructura del proyecto

```text
Prueba_Banca_digital/
├── data/
│   ├── raw/
│   ├── interim/
│   └── processed/
├── notebooks/
│   ├── 01_eda_comercios_transacciones.ipynb
│   ├── 02_preparacion_base_segmentacion.ipynb
│   └── 03_segmentacion_comercios.ipynb
├── dashboard/
├── README.md
├── requirements.txt
└── .gitignore
```

## Desarrollo

### 1. Análisis exploratorio

El notebook `01_eda_comercios_transacciones.ipynb` revisa:

- Estructura y tipos de datos.
- Valores faltantes, duplicados y valores inválidos.
- Cantidad de comercios y terminales.
- Comercios con múltiples terminales.
- Cobertura temporal.
- Evolución mensual de comercios activos y transacciones.
- Ventas por categoría y ciudad.
- Relación entre ventas, transacciones y comisiones.

### 2. Preparación de la base

El notebook `02_preparacion_base_segmentacion.ipynb`:

- Convierte las variables de fecha.
- Consolida las terminales para obtener una fila por comercio.
- Organiza las transacciones en columnas mensuales.
- Calcula recencia, frecuencia, meses activos y tendencia.
- Une la información comercial y transaccional.
- Calcula la comisión estimada del 5 %.

### 3. Segmentación

El notebook `03_segmentacion_comercios.ipynb` implementa K-means con las siguientes variables:

- `Recencia_meses`
- `Total_transacciones_6m`
- `Meses_activos`
- `Ventas_acumuladas`
- `Tendencia_transacciones`

Antes de entrenar el modelo se aplicó una transformación logarítmica a las variables con distribuciones muy asimétricas y posteriormente se estandarizaron los datos.

Se evaluaron soluciones entre 2 y 8 grupos utilizando:

- Método del codo.
- Coeficiente de Silhouette.
- Índice Davies-Bouldin.

Se seleccionaron cuatro segmentos por representar un equilibrio entre la calidad estadística y la posibilidad de construir perfiles comerciales útiles. La solución obtuvo un Silhouette de `0,37` y un Davies-Bouldin de `0,92`.

## Segmentos obtenidos

| Segmento | Comercios | Participación | Comisión | Estrategia sugerida |
|---|---:|---:|---:|---|
| Consolidados de alto valor | 234 | 7,76 % | 17,67 % | Fidelizar y prevenir la reducción de actividad |
| Comercios por reactivar | 622 | 20,63 % | 1,64 % | Recuperar el uso mediante campañas de reactivación |
| Líderes en crecimiento | 1.002 | 33,23 % | 65,39 % | Proteger, escalar y ofrecer beneficios por crecimiento |
| Activos con potencial | 1.157 | 38,37 % | 15,30 % | Aumentar la frecuencia y el valor transaccional |

## Hallazgos principales

- Se identificaron 3.015 comercios y 3.071 terminales.
- Existen 48 comercios con más de una terminal; el máximo es cinco.
- Todos los comercios tuvieron por lo menos una transacción durante el periodo analizado.
- En mayo se registraron 2.087 comercios activos y 22.949 transacciones.
- No se encontraron transacciones negativas, combinaciones comercio-mes duplicadas ni identificadores sin correspondencia entre las fuentes.
- Los 21 registros originales sin fecha de primera transacción corresponden a comercios o terminales sin ventas acumuladas. Después de consolidar terminales, representan 11 comercios.
- Se encontraron 1.233 comercios con ventas del último mes reportadas en cero.
- El segmento de líderes en crecimiento concentra el 65,39 % de las comisiones, aunque representa el 33,23 % de los comercios.

## Resultados de negocio

Las ventas del último mes reportado fueron de aproximadamente `$2.019 millones`, equivalentes a una comisión estimada de `$100,97 millones`.

Para incrementar la comisión en un 50 %, se requiere alcanzar aproximadamente:

- Comisión objetivo: `$151,45 millones`.
- Ventas objetivo: `$3.029 millones`.
- Incremento necesario en ventas: `$1.010 millones`.

## Archivos para Power BI

El tablero utiliza:

- `data/processed/comercios_segmentados.csv`: una fila por comercio con su segmento y sus indicadores.
- `data/processed/transacciones_mensuales.csv`: una fila por comercio y mes para analizar la evolución temporal.

La relación principal del modelo es:

```text
comercios_segmentados[Id_comercio]  1 ─── *  transacciones_mensuales[Id_comercio]
```

El tablero permite revisar:

- Comercios y terminales.
- Transacciones y comercios activos por mes.
- Ventas y comisiones.
- Meta de crecimiento del 50 % y brecha pendiente.
- Distribución y aporte de los segmentos.

