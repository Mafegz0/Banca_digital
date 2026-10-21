# 02 · Data Understanding

## Fuentes

El ejercicio parte de un libro Excel con dos hojas:

- `comercios`: nivel terminal/comercio, categoría, ciudad, fechas y ventas.
- `transacciones`: observaciones mensuales de actividad y número de transacciones.

## Granularidad y periodo

- Registros de origen de comercios/terminales: 3.071.
- Registros de transacciones: 8.357.
- Comercios únicos tras consolidación: 3.015.
- Periodo disponible: diciembre de 2020 a mayo de 2021.

## Controles reportados en el notebook

Revisión de faltantes, duplicados, IDs sin correspondencia, cobertura mensual, valores y consistencia de fechas. La interpretación y observaciones deben consultarse en el notebook.

## Notebook

[01 · EDA de comercios y transacciones](01_eda_comercios_transacciones.ipynb)

> El archivo fuente de la prueba se encuentra en [`data/raw/DataTransacciones_PruebasIngreso.xlsx`](../data/raw/DataTransacciones_PruebasIngreso.xlsx). El notebook mantiene las salidas originales del ejercicio.
