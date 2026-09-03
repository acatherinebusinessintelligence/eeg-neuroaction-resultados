# Plan de seudonimización (no ejecutado)

**Estado:** cerrado para `cano` y `villanueva`; no se sustituyen archivos de resultados.

Confirmación de la autora: `cano` y `villanueva` **ya son códigos institucionales pseudonimizados**. No deben interpretarse como nombres reales. **No se recodifican** a `S01`/`S02`.

Un mapa local opcional (`docs/MAPA_PSEUDONIMIZACION_LOCAL.md`) permanece gitignored y **no** debe ir a release ni Zenodo. No usar ese mapa para reconstruir identidades.

El resto de esta nota conserva el inventario de *dónde aparecen* los códigos, por si en el futuro se decide recodificar solo identificadores numéricos. **No ejecutar sustituciones ahora.**

## Archivos afectados

### Carpetas (30)

`figures/<id>/` y `figures/por_sujeto/<id>/` para cada uno de los 15 identificadores.

### Nombres de archivo PNG / CSV de matrices

Familias cuyo nombre incluye el ID:

- `figures/<id>/confusion_<id>_*.png`
- `figures/por_sujeto/<id>/<id>_*.png`
- `figures/scroll/`, `figures/spectral/`, `figures/resumen/`, `figures/topomaps/` (prefijo de sujeto en el filename)
- `reports/balanceo/matrices_confusion_balanceo/confusion_<id>_*.csv` y `*.png`

Conteos de archivos con el ID en la ruta (aprox.): 107–253 por sujeto.

### CSV de reporte (contenido; ~25–27 archivos de texto por ID)

Incluyen, entre otros:

- `reports/evaluacion_sujetos.csv`
- `reports/archivos_eeg_reconocidos.csv`
- `reports/archivos_generados.csv`
- `reports/pares_eeg.csv`, `reports/pares_txt_csv_eeg.csv`, `reports/pruebas_csv_espanol_eeg.csv`
- `reports/diagnostico_tiempos_csv_txt.csv` (solo IDs numéricos; no `cano`/`villanueva`)
- `reports/reporte_artefactos_sospechados_detalle.csv` (122 279 filas; columna `sujeto` y `archivo`)
- `reports/reporte_artefactos_sospechados_resumen.csv`
- `reports/reporte_filtrado.csv`, `reports/reporte_limpieza_artefactos.csv`, `reports/reporte_mapeo.csv`
- `reports/reporte_figuras_generadas.csv`, `figures/reporte_figuras_generadas.csv`
- `reports/reporte_visor_interactivo.csv`
- `reports/resultados_modelos_global.csv` (columna `dataset` y `sujeto`)
- `reports/comparacion_variantes_limpieza_modelos.csv`
- `reports/comparacion_balanceo_modelos.csv` y copia en `reports/balanceo/`
- `reports/comparacion_balanceo_por_sujeto.csv` y copia en `reports/balanceo/`
- `reports/recall_por_clase_balanceo.csv` y copia en `reports/balanceo/`
- `reports/resumen_exportacion_por_usuario.csv`
- `reports/resumen_procesamiento_eeg.csv`
- `reports/resumen_eventos_txt.csv`
- `reports/validacion_salidas_pipeline.csv` (rutas Kaggle con IDs en nombres de XLSX de modelos)

### XLSX (16)

Duplicados binarios de reportes CSV. No se inspeccionó el XML interno. Deben tratarse como afectados. Sustitución requiere herramienta de hoja de cálculo, no un reemplazo de texto plano.

### HTML (9) y JSON embebido

No hay `.json` independientes. El visor incrusta JSON en `<script type="application/json" id="data-json">`.

- `index.html` — no lista IDs de sujeto en la inspección previa.
- `visor_interactivo_eeg.html` y `reports/visor_interactivo_eeg.html`
- `dashboard_eeg_neuroaction.html` y `figures/dashboard_eeg_neuroaction.html`
- `informe_evaluacion_resultados.html` y `reports/informe_evaluacion_resultados.html`
- `reports/balanceo/resumen_balanceo.html`
- `reports/index_kaggle.html` — rutas de corrida; no es el inventario de sujetos.

Captions/títulos: el visor y el informe muestran el ID en tablas y pies de matriz. Los PNG no se leyeron con OCR; puede haber texto rasterizado con el ID.

### Documentación ya versionada

- `README.md` (mención genérica, no lista los 15 IDs)
- `docs/RESULTADOS.md`, `docs/REVISION_PUBLICACION.md`, `docs/metodologia.md`
- Este plan y `docs/IDENTIFICADORES.md` (este último **no** debe ir a Zenodo con IDs originales tras la sustitución)

### No afectados como datos de sujeto

- `CITATION.cff`
- `CHANGELOG.md`
- Plotly.js embebido (la palabra `timestamp` ahí es del bundle, no de sesiones)

## Referencias afectadas

| Dónde | Qué hay que sustituir |
| --- | --- |
| Columna `sujeto` | Token completo del ID |
| Columnas `archivo`, `dataset`, `archivos_csv`, `archivos_txt`, `csv`, `txt` | Prefijos y nombres de archivo fuente |
| Columnas `ruta`, `ruta_archivo` | Segmentos de path Kaggle que contienen el ID |
| Nombres de carpeta y de archivo | Token del ID; en fuentes en español, apellidos `Cano` / `Villanueva` |
| HTML/JSON del visor | IDs en filtros, tablas, `src` de imágenes |
| Comentarios técnicos | Solo el token de ID, no reescribir el juicio de calidad |

## Riesgos de romper enlaces

1. **Visor:** rutas relativas `figures/por_sujeto/<id>/...` y matrices de balanceo. Si se renombran PNG y no el JSON embebido (o al revés), las miniaturas quedan rotas.
2. **Copias duplicadas:** hay HTML y CSV repetidos en raíz, `reports/` y `figures/`. Hay que sustituir **todas** las copias o el visor de Pages y el de `reports/` divergirán.
3. **Orden de reemplazo:** IDs numéricos no se solapan entre sí con matching de token completo. `cano` es subcadena de nombres de archivo `*_Cano_*` (mayúscula): hace falta paso case-insensitive para apellidos, acotado a esos identificadores, para no tocar palabras ajenas.
4. **XLSX:** un sed sobre el `.xlsx` lo corrompe. Hay que reescribir hojas o regenerar desde CSV ya seudonimizado **sin cambiar valores numéricos**.
5. **PNG:** el nombre cambia; el píxel no. Si el ID está dibujado en la figura, seguirá visible salvo regenerar imágenes (fuera de alcance: no recalcular resultados). Documentar como residual.
6. **GitHub Pages** sirve `index.html` → `visor_interactivo_eeg.html`. Un visor a medias sustituido rompe el sitio público.
7. **`run_20260902_145353`** no es un ID de sujeto. No sustituir.

## Estrategia de sustitución

**No ejecutar.** `cano` y `villanueva` se conservan como códigos institucionales. No hay recodificación a `S01`–`S15` en esta preparación.

Si en el futuro se recodificaran solo códigos numéricos, habría que hacerlo en una rama, sin recalcular métricas y sin publicar el mapa local.

## Validaciones de esta preparación

- Los códigos `cano` y `villanueva` se documentan como institucionales, no como nombres reales.
- No se declara anonimato absoluto.
- `docs/MAPA_PSEUDONIMIZACION_LOCAL.md` sigue ausente de `git ls-files`.
- No se modifican CSV, XLSX, PNG ni HTML de resultados.
