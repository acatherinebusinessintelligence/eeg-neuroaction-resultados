# Inventario de resultados

**Versión:** v1.0.0 Release Candidate  
**Rama inspeccionada:** `main`  
**Corrida de origen registrada en los HTML:** `/kaggle/working/outputs/TESE_pruebas/run_20260902_145353`

Este documento describe **qué existe y dónde**. No interpreta el significado estadístico de las métricas.

Conteo de archivos versionados en `main` al momento de la inspección: **2417** (1747 PNG, 643 CSV, 16 XLSX, 9 HTML, 1 Markdown original, 1 TXT).

## Interfaz y reportes HTML

| Recurso | Ubicación | Notas |
| --- | --- | --- |
| Entrada GitHub Pages | `index.html` | Enlaza el visor. |
| Visor interactivo (español) | `visor_interactivo_eeg.html` | Copia en `reports/visor_interactivo_eeg.html`. Selector Español \| English. |
| Visor interactivo (English) | `visor_interactivo_eeg_en.html` | Traducción de la interfaz y la narrativa. Mismos datos embebidos que el visor español. |
| Dashboard | `dashboard_eeg_neuroaction.html` | Copia en `figures/dashboard_eeg_neuroaction.html`. Plotly.js v2.35.2 embebido. |
| Informe de evaluación | `informe_evaluacion_resultados.html` | Copia en `reports/informe_evaluacion_resultados.html`. |
| Índice de salidas Kaggle | `reports/index_kaggle.html` | Enlaza ZIP externos que no están en este repo. |
| Resumen de balanceo | `reports/balanceo/resumen_balanceo.html` | |
| Resumen ejecutivo TXT | `reports/resumen_ejecutivo_resultados.txt` | 15 sujetos; clasificación de evidencia de modelado. |

Visor publicado: <https://acatherinebusinessintelligence.github.io/eeg-neuroaction-resultados/>

## Archivos EEG reconocidos (metadatos, no series)

Los CSV/TXT de señal **no están** en este repositorio. Sí está el inventario:

- `reports/archivos_eeg_reconocidos.csv` / `.xlsx` — 60 archivos reconocidos (30 `leftRight`, 30 `pushPull`).
- `reports/pares_eeg.csv` / `.xlsx`
- `reports/pares_txt_csv_eeg.csv` / `.xlsx`
- `reports/pruebas_csv_espanol_eeg.csv` / `.xlsx`
- `reports/resumen_procesamiento_eeg.csv` / `.xlsx`
- `reports/resumen_eventos_txt.csv`
- `reports/diagnostico_tiempos_csv_txt.csv`

Orígenes anotados: `txt_csv_prueba_completa` (52) y `csv_accion_individual` (8).

`reports/archivos_generados.csv` lista salidas EDF y otras rutas Kaggle; los EDF **no** están versionados aquí.

## Evaluación por sujetos

15 identificadores en `reports/evaluacion_sujetos.csv`:

`211260561`, `212260563`, `212260567`, `212260569`, `212260666`, `212260668`, `212260672`, `222260671`, `22260552`, `231260558`, `252260554`, `252260556`, `252260670`, `cano`, `villanueva`.

El resumen ejecutivo reporta, en esa corrida: 0 aprobados fuertes sin restricciones, 2 aprobados moderados, 11 en revisión y 2 no confiables.

## Comparación de balanceo

| Recurso | Ubicación |
| --- | --- |
| Comparación de modelos × estrategia | `reports/comparacion_balanceo_modelos.csv` / `.xlsx` (copia bajo `reports/balanceo/`) |
| Mejor estrategia por sujeto | `reports/comparacion_balanceo_por_sujeto.csv` / `.xlsx` (copia bajo `reports/balanceo/`) |
| Recall por clase | `reports/recall_por_clase_balanceo.csv` / `.xlsx` (copia bajo `reports/balanceo/`) |
| Matrices CSV de confusión de balanceo | `reports/balanceo/matrices_confusion_balanceo/` (612 CSV) |
| Matrices PNG de confusión de balanceo | `reports/balanceo/matrices_confusion_balanceo/` (612 PNG) |
| HTML resumen | `reports/balanceo/resumen_balanceo.html` |

Estrategias presentes: `sin_balanceo`, `random_oversampling`, `class_weight_balanced`, `smote`, `smote_tomek`, `random_undersampling_controlado`. Unidad de análisis y métricas: [MODELOS.md](MODELOS.md). Este inventario no declara qué estrategia es “mejor”.

## Variantes de limpieza

- `reports/comparacion_variantes_limpieza_modelos.csv` / `.xlsx`
- `reports/reporte_limpieza_artefactos.csv` / `.xlsx`
- `reports/reporte_filtrado.csv` / `.xlsx`

Variantes de figura/modelado observadas: `cleanSmooth`, `noOutliers`, `sinArtefactosConservador`, `sinArtefactosEstricto`.

## Modelos

- `reports/resultados_modelos_global.csv` / `.xlsx` — 168 filas; 7 clasificadores; 24 datasets `sujeto_all_variante`.
- Clasificadores: NaiveBayes, J48_C45, IBk_kNN, RandomForest, MLP, SMO_SVM, RBFNetwork_aprox.
- Matrices de confusión por sujeto (PNG) en `figures/<sujeto>/`.

`reports/validacion_salidas_pipeline.csv` menciona XLSX `*_Comparativa_Modelos_Final.xlsx` por sujeto en Kaggle; **no** están en este GitHub.

## Figuras

| Familia | Ubicación | Conteo inspeccionado |
| --- | --- | --- |
| Por sujeto (scroll, spectral, topomapas, resumen) | `figures/por_sujeto/<sujeto>/` | 480 PNG; 8 tipos × 60 combinaciones sujeto–variante |
| Topomapas (copia/organización adicional) | `figures/topomaps/` | 300 PNG |
| Scroll | `figures/scroll/` | 60 PNG |
| Spectral | `figures/spectral/` | 60 PNG |
| Resumen | `figures/resumen/` | 60 PNG |
| Exploración master | `figures/exploracion_master/` | 7 PNG |
| Confusión por sujeto (modelos de la evaluación principal) | `figures/<sujeto>/` | PNG `confusion_*.png` por sujeto y variante modelable |
| Inventario de figuras | `figures/reporte_figuras_generadas.csv` y `reports/reporte_figuras_generadas.csv` | |
| Resumen de figuras Kaggle / master | `reports/resumen_figuras_kaggle.csv`, `reports/resumen_figuras_master.csv` | |
| Cobertura del visor | `reports/reporte_visor_interactivo.csv` | |

Tipos de figura por sujeto: `resumen_visual`, `scroll_promedio_bandas`, `spectral_bandpower`, `topomap_alpha`, `topomap_betaL`, `topomap_betaH`, `topomap_gamma`, `topomap_theta`.

El visor incrustado declara `figuras_generadas: 528` en sus métricas globales; el árbol `figures/` más las matrices de `reports/balanceo/` suma más archivos porque hay copias organizadas por carpeta y PNG de balanceo.

## Artefactos sospechados (estructura, no interpretación clínica)

- Detalle: `reports/reporte_artefactos_sospechados_detalle.csv` / `.xlsx` (**122 279 filas**).
- Resumen: `reports/reporte_artefactos_sospechados_resumen.csv` / `.xlsx` (365 filas).

Columnas del detalle: `sujeto`, `movimiento`, `archivo`, `fila`, `canal`, `banda`, `columna`, `valor`, `z_robusto`, `z_salto`, `tipo_artefacto_sospechado`, `nivel_confirmacion`, `removido`, `observacion`.

| Pregunta estructural | Hallazgo |
| --- | --- |
| ¿Identificadores? | Sí: `sujeto` y `archivo` (15 códigos; `cano` y `villanueva` son códigos institucionales pseudonimizados, no nombres reales). |
| ¿Timestamps / fechas? | No hay columnas de tiempo ni fecha en este archivo. |
| ¿Métricas por persona? | Sí, en el **resumen** (365 filas): `sujeto`, `movimiento`, `tipo_artefacto_sospechado`, `eventos`, `canales_afectados`, `bandas_afectadas`, `z_max_abs`, `salto_max_abs`. |
| ¿Intervalos temporales? | No. El detalle usa `fila` (índice de registro), no inicio/fin en segundos ni Unix. |
| ¿Categorías? | Cinco etiquetas en detalle y resumen: `salto_brusco_estadistico` (44 298), `posible_muscular_beta_gamma` (30 457), `posible_no_fisiologico_salto_o_pico` (23 526), `outlier_estadistico_extremo` (12 492), `posible_ocular_frontal_banda_baja` (11 506). El visor también nombra `posible_no_fisiologico_canal_plano` entre tipos eliminados en variantes de limpieza; esa etiqueta no aparece en el conteo del detalle inspeccionado. |
| ¿Cómo se identifican? | Heurística sobre BANDPOWER: columnas `z_robusto`, `z_salto`, `tipo_artefacto_sospechado`. `observacion` (todas las filas del detalle): clasificación heurística; no equivale a confirmación fisiológica con EEG crudo/EOG/EMG/ECG. |
| ¿Confirmación / removido? | `nivel_confirmacion = sospecha_sobre_bandpower` y `removido = no` en las **122 279** filas del detalle. |
| ¿Señal cruda? | No. No hay voltajes continuos, EDF ni series temporales de EEG. |
| ¿Datos derivados? | Sí. `valor` por `canal` × `banda` (theta, alpha, betal, betah, gamma). |
| ¿Movimientos en el detalle? | `all`, `left`, `right`, `pull`, `push` (conteos de filas; no se interpretan clínicamente). |

No se interpretan estas etiquetas como diagnóstico clínico ni como artefactos confirmados en EEG crudo.

Este archivo es el principal volumen de características derivadas por sujeto. Redistribución de resultados autorizada; no se declara anonimato absoluto. No se modificó en esta auditoría.

## Dashboards e informes

Ya listados en la primera tabla. El dashboard muestra, entre otras tarjetas de esa corrida: 15 sujetos, 16 578 registros originales, 13 561 registros `noOutliers`, retención promedio 82.62 %, 3 009 outliers removidos y 122 279 artefactos sospechados.

## Exportación y verificación de pipeline

- `reports/resumen_exportacion_por_usuario.csv`
- `reports/archivos_generados.csv`
- `reports/validacion_salidas_pipeline.csv`
- `reports/verificacion_kaggle_salidas.csv`
- `reports/reporte_mapeo.csv` / `.xlsx` (mapeo a EDF / atributos conservados)

## Lo que no está en este repositorio

- código fuente del pipeline y notebooks (0 archivos `.py` / `.ipynb`);
- EEG crudo / EDF / BDF / FIF / NPY / MAT (0 en el árbol local);
- ZIP citados por `reports/index_kaggle.html`;
- XLSX individuales `*_Comparativa_Modelos_Final.xlsx`.

Clasificación: **C. características derivadas** (ver [EVIDENCIA_METODOLOGICA.md](EVIDENCIA_METODOLOGICA.md)).

Documentación de auditoría: `docs/IDENTIFICADORES.md`, `docs/PLAN_PSEUDONIMIZACION.md`, `docs/PIPELINE.md`, `docs/EVIDENCIA_METODOLOGICA.md`, `docs/MODELOS.md`. El mapa local de identidad no se versiona.
