# 04 · Modeling

## Enfoque

Segmentación no supervisada mediante **K-means**, utilizando cinco variables de comportamiento comercial y transaccional.

## Procesamiento previo al entrenamiento

- Transformación logarítmica de variables sesgadas.
- Estandarización de variables.
- Evaluación de soluciones de `k=2` a `k=8` (se inspecciona también inercia del codo).
- Comparación por Silhouette y Davies–Bouldin.
- Ajuste de K-means con `k=4` y `random_state=123`.

## Resultado

**Cuatro grupos interpretables**: consolidados de alto valor, por reactivar, líderes en crecimiento y activos con potencial.

## Notebook

[03 · Segmentación de comercios K-means](03_segmentacion_comercios.ipynb)
