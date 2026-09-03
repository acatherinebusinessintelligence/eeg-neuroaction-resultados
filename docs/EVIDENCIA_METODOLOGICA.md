# Matriz de evidencia metodológica

**Repositorio:** `acatherinebusinessintelligence/eeg-neuroaction-resultados`  
**Rama:** `main` (HEAD alineado con `origin/main` al iniciar esta auditoría)  
**Versión de preparación:** v0.9.0  
**Fecha de auditoría:** 2026-09-03  

Fuentes primarias usadas:

- A. El repositorio completo (nombres de archivo, CSV/XLSX de reporte, HTML, Markdown, `CITATION.cff`).
- B. Ficha Kaggle del dataset [EEG 25-1](https://www.kaggle.com/datasets/griseldacortes/eeg-25-1/data) (título público: EEG OF NEUROACTION LABELED).
- C. README, documentación y metadatos ya versionados.
- D. Descripción / Data Card visible en esa ficha Kaggle.

No se usaron blogs ni otros datasets Kaggle para completar detalles del experimento. No se recalcularon métricas. No se modificaron CSV/XLSX/PNG/HTML de resultados.

Estados permitidos: **Confirmado**, **Parcialmente documentado**, **No documentado**.

Las visualizaciones corresponden a características EEG BANDPOWER derivadas y no equivalen a qEEG clínico normativo ni a confirmación fisiológica con EEG crudo/EOG/EMG/ECG.

| Elemento metodológico | Evidencia encontrada | Fuente | Estado | Observación |
| --- | --- | --- | --- | --- |
| Qué publica este repositorio | Visor, dashboard, informe, reportes CSV/XLSX, figuras PNG y un TXT ejecutivo de una corrida Kaggle. Cero `.py` / `.ipynb`. Cero `.edf` / `.bdf` / `.fif` / `.mat` / `.npy`. | Árbol local; `docs/RESULTADOS.md` | Confirmado | Archivo de **resultados derivados**, no del experimento crudo. |
| Corrida registrada | Identificador `run_20260902_145353`; ruta `/kaggle/working/outputs/TESE_pruebas/run_20260902_145353`. | `visor_interactivo_eeg.html`; `dashboard_eeg_neuroaction.html`; `reports/index_kaggle.html`; `reports/verificacion_kaggle_salidas.csv` | Confirmado | Es registro de salidas, no un pipeline ejecutable en este repo. |
| Dataset fuente | Título de ficha: EEG OF NEUROACTION LABELED. Nombre usado en docs del repo: EEG 25-1. URL: https://www.kaggle.com/datasets/griseldacortes/eeg-25-1/data | Ficha Kaggle; `README.md`; `docs/metodologia.md` | Confirmado | Procedencia del dataset fuente. Los CSV/TXT fuente **no** están versionados aquí. |
| Autores del dataset/proyecto | Griselda Cortés Barrera; Alejandra Catherine Montaña Acevedo; Jesús Manuel Olivares Ceja; Jhacer Kharen Ruiz Garduño (orden de la ficha). | Ficha Kaggle EEG 25-1; `CITATION.cff` | Confirmado | Afiliaciones de tres autores siguen pendientes de confirmación. |
| Institución TESE | Tecnológico de Estudios Superiores de Ecatepec (México). Carpeta de corrida `TESE_pruebas`. | Confirmación documentada; rutas Kaggle | Confirmado | TESE nombra la institución de la corrida, no un protocolo de outliers con umbrales. |
| Laboratorio | “National Laboratory in Artificial Intelligence and Data Science” en la biografía pública de Griselda Cortés Barrera en la ficha Kaggle. | Ficha Kaggle (biografía) | Parcialmente documentado | No se traduce a nombre oficial en español ni se inventa acrónimo. |
| Objetivo del experimento (estudio original) | La ficha describe grabaciones EEG/BCI de control motor intencional (comandos mentales; left/right y push/pull) para investigación de interfaces cerebro-computadora. | Ficha Kaggle EEG 25-1 | Parcialmente documentado | Objetivo **del dataset fuente**, no un protocolo experimental con instrucciones versionadas aquí. |
| Objetivo de este repositorio | Publicar salidas técnicas (BANDPOWER, limpieza, modelos, visor) de una corrida. | `README.md` | Confirmado | Distinto del protocolo de adquisición. |
| Tarea de participantes | Etiquetas de evento/clase: `left`, `right`, `pull`, `push`; también `neutral` en TXT. Pruebas reconocidas: `leftRight`, `pushPull`. | `reports/resumen_eventos_txt.csv`; `reports/archivos_eeg_reconocidos.csv`; ficha Kaggle (left/right, push/pull) | Parcialmente documentado | Hay **etiquetas** y tipos de prueba. No hay texto de instrucciones al participante. |
| Condiciones experimentales | No hay documento de condiciones (laboratorio, iluminación, postura, bloqueos, etc.). | Repositorio; ficha Kaggle | No documentado | No reconstruir a partir de costumbre EEG. |
| Instrucciones | No hay texto de consignas. | Repositorio; ficha Kaggle | No documentado | |
| Estímulos | No hay descripción de estímulos (visuales, auditivos, cues). | Repositorio; ficha Kaggle | No documentado | |
| Lateralidad derecha / izquierda | Clases `left` / `right` en reportes. Nombres de archivo fuente `derecha` / `izquierda` para `cano` y `villanueva`. | `reports/pruebas_csv_espanol_eeg.csv`; `reports/resumen_eventos_txt.csv` | Parcialmente documentado | Las clases están confirmadas como etiquetas. La equivalencia motora (mano, imaginación, ejecución) **no** está documentada. `derecha`/`izquierda` = **patrón observado en nombres de archivo**. |
| Reposo / condición neutral | Clase `neutral` en conteos TXT (p. ej. `{'neutral': 1792, 'left': 307, 'right': 88}`). La ficha menciona estado neutral. | `reports/resumen_eventos_txt.csv`; `reports/diagnostico_tiempos_csv_txt.csv`; ficha Kaggle | Parcialmente documentado | `neutral` es una **etiqueta de evento**. No hay protocolo de reposo (ojos abiertos/cerrados, duración prescrita). |
| Repeticiones | En `archivos_eeg_reconocidos.csv`: `unica` (52), `1ra` (4), `2da` (4). | `reports/archivos_eeg_reconocidos.csv`; `reports/pruebas_csv_espanol_eeg.csv` | Parcialmente documentado | `1ra` / `2da` = **patrón observado en nombres de archivo** (solo `cano` 1ra y `villanueva` 2da en el inventario español). No hay protocolo de cuántas repeticiones se pidieron. |
| Sesiones | Unix de captura para 13 sujetos numéricos entre 2026-05-19 y 2026-06-08 UTC. 26 filas (típicamente dos pruebas por sujeto). | `reports/diagnostico_tiempos_csv_txt.csv` | Parcialmente documentado | Datán capturas. No define “sesión experimental” (número planeado, intervalo entre sesiones). `cano` y `villanueva` **no** aparecen en ese archivo. |
| Duración | `duracion_csv_segundos` entre ~82,8 s y ~358,8 s (26 registros; 13 sujetos numéricos). | `reports/diagnostico_tiempos_csv_txt.csv` | Parcialmente documentado | Duración **observada** de archivos fuente alineados CSV–TXT, no un tiempo de tarea prescrito. |
| Número de sujetos | 15 identificadores en evaluación. | `reports/evaluacion_sujetos.csv`; visor (`total_sujetos`: 15) | Confirmado | Códigos institucionales / numéricos; no nombres reales. |
| Dispositivo EEG | Ficha: dispositivos no invasivos EMOTIV, modelos **EMOTIV Insight** y **EMOTIV EPOC X**. | Ficha Kaggle EEG 25-1 | Parcialmente documentado | No hay mapeo dispositivo↔sujeto. No se afirma que todos usaran el mismo modelo. |
| Fabricante / modelo | EMOTIV; Insight y EPOC X. | Ficha Kaggle EEG 25-1 | Parcialmente documentado | Igual que la fila anterior. |
| Número de canales | En el detalle de artefactos de **este** repo aparecen exactamente 14 etiquetas: AF3, AF4, F3, F4, F7, F8, FC5, FC6, O1, O2, P7, P8, T7, T8. | `reports/reporte_artefactos_sospechados_detalle.csv` | Parcialmente documentado | Canales **presentes en características derivadas**. No es un montaje de adquisición certificado. Insight vs EPOC X no se resuelve por este listado. |
| Canales / electrodos | Lista anterior. | Mismo CSV; nombres de topomapas | Parcialmente documentado | Sin sistema de referencia 10-20 documentado ni impedancias. |
| Frecuencia de muestreo | No aparece en reportes, HTML ni ficha consultada. | Repositorio; ficha Kaggle | No documentado | No inferir Hz típicos de EMOTIV. |
| Referencia | No documentada. | Repositorio; ficha Kaggle | No documentado | |
| Resolución (bits / µV) | No documentada. | Repositorio; ficha Kaggle | No documentado | |
| Formato original | Inventario de fuentes reconocidas: `.csv` y `.txt` (60 archivos: 30 leftRight, 30 pushPull). Ficha: archivos CSV (p. ej. `211260561_LeftRight.csv`) y “other”. Unix mencionado para seguimiento cronológico. | `reports/archivos_eeg_reconocidos.csv`; ficha Kaggle | Parcialmente documentado | Los binarios fuente **no** están en este GitHub. Esquema de columnas de esos CSV/TXT no está versionado aquí. |
| Duración de adquisición (protocolo) | Solo duraciones observadas (fila Duración). | `reports/diagnostico_tiempos_csv_txt.csv` | Parcialmente documentado | No hay tiempo de grabación prescrito. |
| Filtros en adquisición | No documentados (no notch/bandpass de hardware/firmware). | Repositorio; ficha Kaggle | No documentado | La ficha dice que el dataset fuente está **pensado** para filtrado posterior; eso no prueba filtros aplicados en esta corrida. |
| EEG crudo en este repo | 0 archivos de señal (EDF/BDF/FIF/MAT/NPY). | Glob del árbol | Confirmado | Clasificación del **repositorio de resultados**: características derivadas. |
| EDF generados en Kaggle | `reports/archivos_generados.csv` lista rutas `*.edf` bajo la corrida. `reporte_mapeo.csv` tiene `edf_ok=True`. | Esos CSV | Confirmado | Los EDF **no** están versionados en GitHub. |
| CSV de este repo: ¿series temporales? | Los CSV versionados son reportes (métricas, inventarios, artefactos). El único con Unix de sesión es `diagnostico_tiempos_csv_txt.csv` (min/max por archivo, no muestras). El detalle de artefactos tiene `fila` + `valor` por canal/banda, no voltaje continuo. | Encabezados de `reports/*.csv` | Confirmado | No hay series EEG crudas en los CSV de este repo. |
| Figuras y BANDPOWER | Tipos: `scroll_promedio_bandas`, `spectral_bandpower`, `topomap_alpha`, `topomap_betaL`, `topomap_betaH`, `topomap_gamma`, `topomap_theta`. | `docs/RESULTADOS.md`; visor | Confirmado | Las figuras derivan de características BANDPOWER, no de qEEG clínico. |
| Bandas disponibles | `theta`, `alpha`, `betal` / `betaL`, `betah` / `betaH`, `gamma`. | Detalle de artefactos; nombres de PNG | Confirmado | Nombres de banda. |
| Rangos de frecuencia (Hz) | La ficha menciona “standard frequency bands (e.g., Alpha, Beta, Gamma)” **sin Hz**. El repo no trae Hz. | Ficha Kaggle; búsqueda en repo | No documentado | No usar rangos estándar de literatura. Escribir “Rango no documentado.” |
| Tipo de medida BANDPOWER | Visor/dashboard: características EEG tipo BANDPOWER por canal y banda. Columna `valor` en artefactos. No dice si es absoluta, relativa, log, PSD, Welch, promedio temporal o por canal como fórmula. | Visor; dashboard; detalle de artefactos | Parcialmente documentado | Se confirma que es **característica derivada por canal y banda**. La fórmula no está. El visor **niega** equivalencia con PSD cruda. |
| Filtrado / notch / bandpass / ICA / Welch / FFT | El dashboard afirma que **no se afirma** ICA, notch, pasa banda ni PSD cruda cuando solo hay BANDPOWER. No hay parámetros de esos métodos. | `dashboard_eeg_neuroaction.html`; visor | No documentado (como procedimientos aplicados) | La **ausencia de afirmación** está confirmada. No equivale a “se aplicó” ni a “no se aplicó” en Kaggle fuera de este repo. |
| Outliers / artefactos (pipeline de resultados) | Columnas `artefactos_robust_z`, `artefactos_saltos`; variantes `noOutliers`, `sinArtefactosConservador`, `sinArtefactosEstricto`; tipos de sospecha nombrados. Visor: outliers por “protocolo TESE” sin umbral. | `reports/reporte_filtrado.csv`; reportes de artefactos; visor `VARIANT_INFO` | Parcialmente documentado | Heurística sobre BANDPOWER. Umbrales y código no están. |
| Segmentación / ventanas / solapamiento | No documentados. | Repositorio | No documentado | `fila` en artefactos no define duración de ventana. |
| Normalización | Variante de archivo `cleanNorm` en mapeo/EDF listados. Algoritmo no descrito. Ficha Kaggle menciona normalización como intención futura del dataset fuente. | `reports/reporte_mapeo.csv`; ficha Kaggle | Parcialmente documentado | Nombre de variante ≠ procedimiento documentado. |
| Suavizado | Variante visual `cleanSmooth`. Algoritmo no descrito. | Visor; `reports/resumen_figuras_kaggle.csv` | Parcialmente documentado | |
| Clasificadores | NaiveBayes, SMO_SVM, MLP, IBk_kNN, RBFNetwork_aprox, J48_C45, RandomForest. | `reports/resultados_modelos_global.csv` (168 filas) | Confirmado | Nombres. Hiperparámetros: **No documentados.** |
| Partición / CV | `cv=bloques` en las 168 filas; `folds` 2–8 (conteos: 3 más frecuente). | `reports/resultados_modelos_global.csv` | Parcialmente documentado | Estrategia nombrada. No hay definición de bloque temporal ni `random_state`. |
| Train/test hold-out | No aparece un split 70/30 u homologable. | Reportes de modelos | No documentado | El visor de balanceo habla de remuestreo **solo en entrenamiento dentro de cada fold**. |
| `random_state` / semillas | No aparecen. | Reportes; HTML | No documentado | |
| Hiperparámetros | Ninguna columna de `n_estimators`, `C`, `k`, capas, etc. | `reports/resultados_modelos_global.csv`; comparación de balanceo | No documentado | No reconstruir defaults de sklearn/Weka. |
| Métricas de modelos | Accuracy, Kappa, MAE, RMSE, RAE_pct, RRSE_pct, AUC, EXITO (global). Balanceo: accuracy, balanced_accuracy, kappa, macro_f1, weighted_f1, recall/precision por clase, auc, min_clase, exito. | CSV de modelos y balanceo | Confirmado | Criterio que convierte `EXITO` en SI/no: no está formulado fuera de la marca tabulada. |
| Balanceo | Seis estrategias nombradas y comparadas. Unidad: sujeto × movimiento × variante × estrategia × modelo. | `reports/comparacion_balanceo_modelos.csv` (6660 filas); visor `BALANCE_INFO` | Confirmado (estrategias presentes) | El CSV `comparacion_balanceo_por_sujeto.csv` **nombra** `mejor_estrategia_balanceo` como campo de ese reporte; muchas `observacion` dicen que la mejora no es confiable. Esta auditoría no declara un método “mejor”. |
| Notebook / kernel fuente | 0 notebooks. `reports/index_kaggle.html` no enlaza un kernel. Búsqueda de URL `kaggle.com/code` en el repo: no encontrada. | Árbol; `reports/index_kaggle.html` | No documentado | **El repositorio de resultados no contiene el notebook o código fuente completo que produjo todos los outputs.** No se inventa URL. |
| Timestamps de sesión | Unix min/max CSV y TXT; duraciones y desfases; 13 sujetos numéricos; no `cano`/`villanueva`. | `reports/diagnostico_tiempos_csv_txt.csv` | Confirmado (existencia) | Decisión de publicación: **CONSERVAR**. Ver `docs/REVISION_PUBLICACION.md`. |
| Identificadores | 15 códigos; `cano` y `villanueva` confirmados como códigos institucionales pseudonimizados. | `docs/IDENTIFICADORES.md`; confirmación de autora ya documentada | Confirmado | No anonimato absoluto. Prohibida la reidentificación. |

## Clasificación del contenido de este repositorio

**C. contiene características derivadas.**

Justificación:

- Extensiones versionadas (además de git): `.png`, `.csv`, `.xlsx`, `.html`, `.md`, `.cff`, `.txt`.
- No hay EDF/BDF/FIF/MAT ni series de voltaje.
- Los CSV son tablas de métricas, inventarios y `valor` BANDPOWER por `fila` × canal × banda.
- Las figuras se titulan/archivan como espectro BANDPOWER y topomapas por banda.

No es **A** (señal EEG cruda) ni se demuestra **B** (señal procesada continua) en GitHub. La ficha Kaggle describe el **dataset fuente** como grabaciones BCI crudas; esos archivos **no** forman parte de este repositorio. Los EDF citados en `archivos_generados.csv` son salidas de Kaggle no versionadas aquí.

## Advertencia permanente

Las visualizaciones corresponden a características EEG BANDPOWER derivadas y no equivalen a qEEG clínico normativo ni a confirmación fisiológica con EEG crudo/EOG/EMG/ECG.
