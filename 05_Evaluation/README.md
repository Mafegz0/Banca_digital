# 05 · Evaluation

## Resultados documentados en el ejercicio

- Segmentos elegidos: **4**.
- Silhouette reportado: **0,37**.
- Índice Davies–Bouldin reportado: **0,92**.
- Total segmentado: **3.015 comercios**.

## Validación de utilidad

El ejercicio describe segmentos y oportunidades de acción según comportamiento de comercio: fidelización, reactivación, crecimiento y mejora de frecuencia. El segmento *líderes en crecimiento* agrupa 1.002 comercios y contribuye al 65,39 % de las comisiones estimadas en la muestra.

## Límites de interpretación

- Silhouette y Davies–Bouldin evalúan separación/cohesión relativa entre agrupamientos, **no** prueban impacto comercial.
- El aumento del 50 % es un **objetivo del caso**, no un resultado alcanzado.
- No se dispone aquí de experimentos A/B, resultados de campañas ni mediciones longitudinales posteriores.
- La fuente utilizada en el ejercicio se incluye en `data/raw/` para reproducir la evaluación.

## Evidencia

Cálculos y perfiles en [04_Modeling/03_segmentacion_comercios.ipynb](../04_Modeling/03_segmentacion_comercios.ipynb).
