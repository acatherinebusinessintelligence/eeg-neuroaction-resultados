# Modelos e hiperparámetros

**Versión:** v1.0.0 Release Candidate  
**Corrida:** `run_20260902_145353`  
**Alcance:** solo lo tabulados en reportes de este repositorio. No se reconstruyen defaults de sklearn, Weka ni de ningún otro framework.

Las visualizaciones corresponden a características EEG BANDPOWER derivadas y no equivalen a qEEG clínico normativo ni a confirmación fisiológica con EEG crudo/EOG/EMG/ECG.

## Tarea observada

Clasificación de etiquetas motoras (`left`, `right`, `pull`, `push`) a partir de características BANDPOWER derivadas, por sujeto y por variante de limpieza. Los datasets en `reports/resultados_modelos_global.csv` tienen la forma `sujeto_all_variante` (p. ej. `211260561_all_noOutliers`).

No hay en este repositorio una descripción de si la unidad de cada ejemplo es una ventana, una época o una fila de características más allá de las columnas de esos CSV.

## Validación tabulada

| Campo | Valor encontrado | Fuente |
| --- | --- | --- |
| `cv` | `bloques` (168/168 filas) | `reports/resultados_modelos_global.csv` |
| `folds` | 2, 3, 4, 5, 6, 7 u 8 (el valor 3 es el más frecuente) | mismo CSV |
| Hold-out train/test | No documentado | — |
| `random_state` / semilla | No documentados | — |
| Criterio de la marca `EXITO` | Valores `SI` (61) y `no` (107); el visor solo muestra “Modelo exitoso” / “no exitoso” | mismo CSV; `visor_interactivo_eeg.html` |

Cómo se construyen los “bloques” temporales: **No documentados.**

## Tabla de modelos (evaluación global)

Fuente de métricas: `reports/resultados_modelos_global.csv` (168 filas; 15 sujetos; 7 clasificadores). Columnas de métrica: Accuracy, Kappa, MAE, RMSE, RAE_pct, RRSE_pct, AUC, EXITO.

| Modelo | Tarea | Hiperparámetros encontrados | Métrica | Fuente |
| --- | --- | --- | --- | --- |
| NaiveBayes | Clasificación de clases motoras sobre BANDPOWER (`*_all_*`) | No documentados. | Accuracy, Kappa, MAE, RMSE, RAE_pct, RRSE_pct, AUC, EXITO | `reports/resultados_modelos_global.csv` |
| SMO_SVM | Igual | No documentados. | Igual | Igual |
| MLP | Igual | No documentados. | Igual | Igual |
| IBk_kNN | Igual | No documentados. | Igual | Igual |
| RBFNetwork_aprox | Igual | No documentados. | Igual | Igual |
| J48_C45 | Igual | No documentados. | Igual | Igual |
| RandomForest | Igual | No documentados. | Igual | Igual |

Los nombres recuerdan implementaciones tipo Weka (SMO, IBk, J48, RBFNetwork) o aproximaciones (`RBFNetwork_aprox`). **No** se afirma el software ni la versión: no está versionado aquí.

`reports/validacion_salidas_pipeline.csv` cita XLSX `*_Comparativa_Modelos_Final.xlsx` por sujeto en Kaggle; **no** están en este GitHub.

## Comparación de balanceo

Archivos:

- `reports/comparacion_balanceo_modelos.csv` / `.xlsx` (6660 filas)
- `reports/comparacion_balanceo_por_sujeto.csv` / `.xlsx`
- `reports/recall_por_clase_balanceo.csv` / `.xlsx`
- matrices en `reports/balanceo/`

### Estrategias que aparecen (no se declara un ganador)

1. `sin_balanceo`
2. `random_oversampling`
3. `class_weight_balanced`
4. `smote`
5. `smote_tomek`
6. `random_undersampling_controlado`

Texto del visor (`BALANCE_INFO`), como descripción de lo que **ese visor declara**, no como código reejecutable:

- `sin_balanceo`: no aplica remuestreo ni pesos; compara sin modificar el test.
- `random_oversampling`: duplica minoritarias solo en entrenamiento dentro de cada fold.
- `class_weight_balanced`: pesos de clase en modelos compatibles; no aplica a todos los clasificadores.
- `smote`: sintéticos solo en entrenamiento; no se aplica si `min_clase < 10`; experimental si `min_clase < 20`.
- `smote_tomek`: SMOTE + Tomek en entrenamiento.
- `random_undersampling_controlado`: reduce mayoritarias de forma limitada.

Hiperparámetros de SMOTE, k de undersampling, etc.: **No documentados.**

### Modelos en la comparación de balanceo

Subconjunto: IBk_kNN, MLP, RBFNetwork_aprox, RandomForest, SMO_SVM.  
No aparecen NaiveBayes ni J48_C45 en `comparacion_balanceo_modelos.csv`.

### Unidad de análisis

Fila = `sujeto` × `movimiento` (`all`, `left`, `pull`, `push`, `right`) × `variante_limpieza` (`noOutliers`, `sinArtefactosConservador`, `sinArtefactosEstricto`) × `estrategia_balanceo` × `modelo`.

### Métricas utilizadas (balanceo)

`accuracy`, `balanced_accuracy`, `kappa`, `macro_f1`, `weighted_f1`, `recall_left`, `recall_pull`, `recall_push`, `recall_right`, `precision_*`, `auc`, `min_clase`, `problema_muestra`, `exito`, `observacion`, y en algunas filas `cv` / `folds`.

### Resultados comparados (sin interpretar “el mejor”)

`reports/comparacion_balanceo_por_sujeto.csv` incluye columnas `mejor_estrategia_balanceo`, `mejor_modelo`, deltas vs base y `mejora_confiable`. Esas columnas son **salidas del reporte de la corrida**. En las filas inspeccionadas, `observacion` califica varios casos como exploratorios o no confiables (`mejora_confiable=False`). Esta documentación **no** selecciona una estrategia ganadora.

## Variantes de limpieza cruzadas con modelos

`reports/comparacion_variantes_limpieza_modelos.csv`: `noOutliers`, `sinArtefactosConservador`, `sinArtefactosEstricto`, con campos `modelable`, `motivo_no_modelable`, `mejor_modelo`, Accuracy, Kappa, EXITO.

Umbrales que hacen un conjunto “no modelable”: aparecen como texto en esa columna cuando aplica; no hay código de umbral versionado aquí.

## Lo que falta para reproducir el entrenamiento

- notebook o script;
- hiperparámetros;
- semilla;
- definición operativa de `cv=bloques`;
- librería y versión;
- matriz de diseño exacta (qué columnas BANDPOWER entran al clasificador).
