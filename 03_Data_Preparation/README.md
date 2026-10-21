# 03 · Data Preparation

## Procedimiento

1. Estandarización de campos de fechas y tipos de dato.
2. Consolidación de terminales en **una fila por comercio**.
3. Agregación de transacciones por comercio y mes.
4. Cálculo de recencia, meses activos, frecuencia, tendencia y ventas.
5. Preparación de una base única de entrenamiento y tablas para BI.

## Variables analíticas

- `Recencia_meses`
- `Total_transacciones_6m`
- `Meses_activos`
- `Ventas_acumuladas`
- `Tendencia_transacciones`

El cálculo de comisión aplica una tasa fija del 5 % definida en el enunciado de la prueba.

## Notebook

[02 · Preparación de la base de segmentación](02_preparacion_base_segmentacion.ipynb)

## Persistencia

Los CSV generados por el proceso se incluyen en [`data/interim/`](../data/interim/) y [`data/processed/`](../data/processed/). Para reproducir las transformaciones, ejecutar desde este directorio y conservar la ruta relativa `../data/`.
