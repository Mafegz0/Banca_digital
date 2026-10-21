# 06 · Deployment

## Entregable analítico

El ZIP original incluye un reporte de Power BI Desktop denominado `Prueba_Analista_Datos_Banca_Digital.pbix`, respaldado por dos tablas preparadas:

- `comercios_segmentados`: una fila por comercio e indicadores de perfil.
- `transacciones_mensuales`: una fila por comercio y mes.

Relación prevista: `comercios_segmentados[Id_comercio]` **1 a muchos** `transacciones_mensuales[Id_comercio]`.

## Funcionalidad documentada

Dashboard para observar comercios y terminales, transacciones, actividad mensual, ventas, comisiones, meta comercial del 50 % y participación de los cuatro segmentos.

## Estado del despliegue

**Artefacto Power BI creado como entregable de una prueba técnica.** El material suministrado no permite verificar publicación en Power BI Service, usuarios productivos, canal CI/CD, operación ni despliegue automatizado. Por tanto, aquí se documenta el artefacto y su uso previsto, no un despliegue productivo.

## Entregables publicados

La autora autorizó publicar el archivo `.pbix` original junto con las tablas del ejercicio. El modelo se encuentra en [`dashboard/Prueba_Analista_Datos_Banca_Digital.pbix`](../dashboard/Prueba_Analista_Datos_Banca_Digital.pbix), y las tablas de entrada y preparadas en [`data/`](../data/). La existencia del `.pbix` no demuestra por sí sola que el informe estuviera publicado o consumido en un entorno productivo.
