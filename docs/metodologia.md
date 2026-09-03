# EEG NeuroAction

## Metodología de procesamiento, análisis y visualización de resultados EEG

**Versión de preparación:** v0.9.0  
**Estado:** candidata a primera versión estable.  
**Fuente de esta descripción:** archivos del repositorio `acatherinebusinessintelligence/eeg-neuroaction-resultados` (rama `main`) y la ficha Kaggle del dataset [EEG 25-1](https://www.kaggle.com/datasets/griseldacortes/eeg-25-1/data).

Las visualizaciones corresponden a características EEG BANDPOWER derivadas y no equivalen a qEEG clínico normativo ni a confirmación fisiológica con EEG crudo/EOG/EMG/ECG.

No deben presentarse como:

- qEEG clínico normativo;
- diagnóstico médico;
- confirmación fisiológica basada en EEG crudo;
- sustituto de evaluación clínica.

EEG crudo, EOG, EMG o ECG serían necesarios para determinadas verificaciones fisiológicas que este repositorio no demuestra por sí mismo.

---

## Propósito del repositorio

Este repositorio publica un **visor web y resultados técnicos** del pipeline EEG NeuroAction para exploración de gráficas, variantes de limpieza, sujetos, modelos y métricas asociadas al procesamiento de características EEG BANDPOWER de movimientos motores.

La descripción del repositorio en GitHub lo formula así: visor web y resultados técnicos del pipeline EEG NeuroAction para el procesamiento, limpieza, visualización y clasificación de señales EEG asociadas a movimientos motores.

El README original indica que el repositorio fue **publicado desde Kaggle**.

## Dataset fuente

**Dataset:** EEG 25-1  
**Fuente:** Kaggle  
**URL:** <https://www.kaggle.com/datasets/griseldacortes/eeg-25-1/data>

Autores (orden de la ficha oficial):

- Griselda Cortés Barrera
- Alejandra Catherine Montaña Acevedo
- Jesús Manuel Olivares Ceja
- Jhacer Kharen Ruiz Garduño

Esta ficha se utiliza como fuente de procedencia y autoría.

## Autoría y afiliaciones

| Autor | Afiliación |
| --- | --- |
| Griselda Cortés Barrera | Tecnológico de Estudios Superiores de Ecatepec (TESE), México |
| Alejandra Catherine Montaña Acevedo | Afiliación pendiente de confirmación |
| Jesús Manuel Olivares Ceja | Afiliación pendiente de confirmación |
| Jhacer Kharen Ruiz Garduño | Afiliación pendiente de confirmación |

**TESE** = Tecnológico de Estudios Superiores de Ecatepec. País: México.

Laboratorio (formulación prudente): **National Laboratory in Artificial Intelligence and Data Science**. Denominación tomada de la biografía pública de Griselda Cortés Barrera en la ficha Kaggle del dataset. No se traduce a un nombre institucional oficial en español ni se inventa un acrónimo. No se afirma propiedad institucional más allá de lo documentado.

## Naturaleza de los resultados

Reinspección de extensiones en el árbol local (además de `.git`): `.png`, `.csv`, `.xlsx`, `.html`, `.md`, `.cff`, `.txt`. **Cero** archivos `.edf`, `.bdf`, `.fif`, `.set`, `.vhdr`, `.eeg`, `.cnt`, `.mat`, `.npy`, `.npz`, `.h5`. **Cero** `.py` / `.ipynb`.

Lo que hay aquí son **únicamente resultados derivados y agregados**, no EEG crudo:

- reportes tabulares (CSV y XLSX) de métricas, inventarios y sospechas de artefactos;
- figuras PNG (scroll, topomapas, espectros, resúmenes, matrices de confusión) construidas sobre BANDPOWER;
- HTML de visor, dashboard e informe;
- un resumen ejecutivo en texto.

El detalle de artefactos (`fila` × canal × banda × `valor`) es una **matriz de características BANDPOWER derivadas**, no una serie de voltajes. No permite reconstruir EEG crudo, EOG, EMG ni ECG. Los timestamps de sesión están en otro archivo (`reports/diagnostico_tiempos_csv_txt.csv`) y datan capturas; no son muestras de señal.

El dashboard y el visor advierten que los datos visualizados son características EEG tipo BANDPOWER por canal y banda; que los artefactos se reportan como **sospecha metodológica**; y que **no se afirma ICA, notch, pasa banda ni PSD cruda** cuando solo hay características BANDPOWER.

El listado `reports/archivos_generados.csv` menciona EDF generados en la corrida Kaggle; esos binarios **no** están versionados aquí.

Las visualizaciones corresponden a características EEG BANDPOWER derivadas y no equivalen a qEEG clínico normativo ni a confirmación fisiológica con EEG crudo/EOG/EMG/ECG.

## Archivos principales

| Recurso | Función verificable |
| --- | --- |
| `index.html` | Página de entrada del visor (GitHub Pages). |
| `visor_interactivo_eeg.html` | Visor interactivo con filtros por sujeto, tipo de figura, variante y estrategia de balanceo. |
| `dashboard_eeg_neuroaction.html` | Dashboard ejecutivo con métricas globales y gráficos Plotly. |
| `informe_evaluacion_resultados.html` | Informe de evaluación por sujeto. |
| `reports/` | Reportes CSV/XLSX, HTML auxiliares y matrices de balanceo. |
| `figures/` | Figuras PNG por sujeto, por tipo y exploración master. |
| `reports/resumen_ejecutivo_resultados.txt` | Resumen ejecutivo en texto. |

Hay copias de algunos HTML en `reports/` y `figures/` (por ejemplo `reports/visor_interactivo_eeg.html` y `figures/dashboard_eeg_neuroaction.html`).

## Pipeline de resultados (solo lo inferible con seguridad)

La arquitectura **verificable** en este repositorio es de **publicación de salidas**, no de código ejecutable del pipeline.

```text
Corrida Kaggle
  /kaggle/working/outputs/TESE_pruebas/run_20260902_145353
        ↓
Procesamiento (fuera de este repo; no hay scripts Python aquí)
        ↓
Reportes CSV/XLSX/TXT  +  figuras PNG  +  HTML
        ↓
Publicación en GitHub (rama main)
        ↓
GitHub Pages
  https://acatherinebusinessintelligence.github.io/eeg-neuroaction-resultados/
```

Evidencia de la corrida:

- el visor, el dashboard, el informe y `reports/index_kaggle.html` registran `run_20260902_145353`;
- `reports/verificacion_kaggle_salidas.csv` y `reports/validacion_salidas_pipeline.csv` comprueban rutas bajo `/kaggle/working/outputs/TESE_pruebas/...`;
- `reports/index_kaggle.html` se titula “Salidas Kaggle” y enlaza visor, dashboard, informe y ZIP que **no están** en este repositorio.

No hay Actions, notebooks ni scripts en este repo que regeneren las métricas. **No existe aquí una conexión automática documentada** entre Kaggle y GitHub: se observa un depósito de resultados publicados.

Pasos del procesamiento **nombrados por los reportes** (sin reconstruir umbrales no documentados):

1. Reconocimiento de archivos EEG fuente (CSV/TXT) y pares de prueba (`reports/archivos_eeg_reconocidos.csv`, `reports/pares_eeg.csv`).
2. Resumen de eventos de archivos TXT y diagnóstico de tiempos CSV–TXT.
3. Filtrado / detección de outliers y artefactos sospechados sobre BANDPOWER (`reports/reporte_filtrado.csv`, reportes de artefactos).
4. Variantes de limpieza y, cuando el conjunto es modelable, clasificación.
5. Comparación de variantes de limpieza y de estrategias de balanceo.
6. Generación de figuras y empaquetado del visor/dashboard/informe.

### Sujetos y pruebas reconocidas

`reports/evaluacion_sujetos.csv` evalúa **15 sujetos**.

Pruebas reconocidas en reportes: `leftRight` y `pushPull`. Clases motoras reportadas: `left`, `right`, `pull`, `push`. Los TXT de eventos también registran `neutral`.

El dashboard muestra la etiqueta “5 movimientos”; este repositorio no define esa cifra más allá de las clases y el agregado `all` usados en archivos.

### Canales y bandas observados

En `reports/reporte_artefactos_sospechados_detalle.csv` aparecen exactamente estos canales y bandas:

- canales: AF3, AF4, F3, F4, F7, F8, FC5, FC6, O1, O2, P7, P8, T7, T8;
- bandas: theta, alpha, betal, betah, gamma.

El visor y las figuras usan también las etiquetas `betaL` y `betaH` en nombres de topomapas.

### Variantes de limpieza nombradas en el visor

El visor documenta tres variantes de modelado/comparación:

| Variante | Qué declara el visor |
| --- | --- |
| `noOutliers` | Línea base. Conserva artefactos sospechados como trazabilidad porque los datos son BANDPOWER derivado, no EEG crudo continuo. |
| `sinArtefactosConservador` | Limpieza adicional moderada. Elimina `outlier_estadistico_extremo`, `posible_no_fisiologico_salto_o_pico`, `posible_no_fisiologico_canal_plano`. |
| `sinArtefactosEstricto` | Limpieza más agresiva. Añade `salto_brusco_estadistico`, `posible_muscular_beta_gamma`, `posible_ocular_frontal_banda_baja`. |

Existe además la variante visual `cleanSmooth` en figuras y en `reports/resumen_figuras_kaggle.csv`. Este repositorio no documenta el algoritmo de suavizado.

El visor indica que `noOutliers` elimina “outliers estadísticos detectados por el protocolo TESE”. **TESE** = Tecnológico de Estudios Superiores de Ecatepec (México). Eso identifica la institución asociada a la corrida (`TESE_pruebas`); **no** especifica umbrales, fórmulas ni software del protocolo de outliers.

### Tipos de artefacto sospechado

En los reportes de artefactos aparecen:

- `salto_brusco_estadistico`
- `outlier_estadistico_extremo`
- `posible_no_fisiologico_salto_o_pico`
- `posible_muscular_beta_gamma`
- `posible_ocular_frontal_banda_baja`

El visor también nombra `posible_no_fisiologico_canal_plano` como categoría eliminada en variantes de limpieza.

Estos nombres son etiquetas de sospecha sobre BANDPOWER, no confirmación con EEG crudo/EOG/EMG/ECG.

### Modelos

`reports/resultados_modelos_global.csv` lista clasificadores:

- NaiveBayes
- J48_C45
- IBk_kNN
- RandomForest
- MLP
- SMO_SVM
- RBFNetwork_aprox

Métricas tabuladas incluyen Accuracy, Kappa, MAE, RMSE, RAE_pct, RRSE_pct, AUC y una marca `EXITO`. La columna `cv` toma el valor `bloques` con distintos números de folds.

La comparación de balanceo (`reports/comparacion_balanceo_modelos.csv`) usa un subconjunto de modelos (IBk_kNN, MLP, RBFNetwork_aprox, RandomForest, SMO_SVM) y las estrategias:

1. `sin_balanceo`
2. `random_oversampling`
3. `class_weight_balanced`
4. `smote`
5. `smote_tomek`
6. `random_undersampling_controlado`

El visor declara que el remuestreo se plantea en entrenamiento y que SMOTE no se aplica si `min_clase < 10` (experimental si `min_clase < 20`). No hay código aquí que permita reejecutar esas reglas.

## Tipos de reportes

Familias verificables en `reports/`:

- inventario de archivos EEG reconocidos y pares CSV/TXT;
- procesamiento y filtrado;
- artefactos sospechados (detalle y resumen);
- limpieza por variante;
- evaluación por sujetos;
- resultados globales de modelos;
- comparación de variantes de limpieza;
- comparación de balanceo (global, por sujeto, recall por clase, matrices);
- cobertura del visor y de figuras;
- validación/verificación de salidas de la corrida Kaggle.

Detalle de rutas: [RESULTADOS.md](RESULTADOS.md).

## Visualizaciones

Tipos de figura presentes:

- scroll / promedio de bandas;
- espectro BANDPOWER;
- topomapas por banda (alpha, betaL, betaH, gamma, theta);
- resumen visual por sujeto y variante;
- exploración master (`figures/exploracion_master/`);
- matrices de confusión por sujeto/modelo/variante;
- matrices de confusión de la comparación de balanceo;
- dashboard HTML con Plotly.js v2.35.2 embebido.

El visor prioriza: scroll `noOutliers`, scroll `cleanSmooth`, topomapas alpha/betaH/gamma `noOutliers`, espectro `noOutliers` y matrices de confusión.

## Limitaciones

- Este repositorio **no contiene el pipeline computacional** (no hay `.py`, `.ipynb` ni parámetros serializados de entrenamiento).
- No contiene EEG crudo, EOG, EMG ni ECG.
- Las métricas y figuras corresponden a **una corrida** (`run_20260902_145353`) y no deben recalcularse a partir de este repo.
- Varias variantes no son “modelables” según `reports/reporte_visor_interactivo.csv`; en esos casos se muestran figuras diagnósticas.
- El resumen ejecutivo indica 15 sujetos, 0 aprobados fuertes sin restricciones, 2 aprobados moderados, 11 en revisión y 2 no confiables. Esa clasificación es de **calidad de evidencia de modelado**, no un juicio clínico.
- Los códigos de sujeto no deben interpretarse como nombres reales; ver [Pseudonimización y privacidad](#pseudonimización-y-privacidad).

## Pseudonimización y privacidad

Los sujetos se representan mediante **códigos institucionales pseudonimizados**.

- `cano` y `villanueva` son códigos institucionales ya pseudonimizados (confirmación de la autora). **No deben interpretarse como nombres reales.**
- Los códigos numéricos de sujeto tampoco deben presentarse como nombres reales.
- El uso público de estos códigos está autorizado en el contexto de redistribución de resultados.
- **No existe autorización para intentar reidentificar participantes.**
- Este repositorio **no declara anonimato absoluto.**
- Los resultados publicados son **derivados** (BANDPOWER, métricas, figuras), no EEG crudo.

Las visualizaciones corresponden a características EEG BANDPOWER derivadas y no equivalen a qEEG clínico normativo ni a confirmación fisiológica con EEG crudo/EOG/EMG/ECG.

## Reproducibilidad

Reproducible **como archivo de salidas**: los HTML y reportes pueden consultarse tal cual.

No es reproducible **como experimento computacional** desde este repositorio: faltan datos fuente, código, semillas, entorno y el notebook/script de Kaggle.

Trazabilidad de la corrida: [PIPELINE.md](PIPELINE.md).

La cadena observada es:

**fuente computacional (Kaggle, corrida `run_20260902_145353`)** → **procesamiento (no versionado aquí)** → **reportes** → **visualizaciones** → **GitHub / GitHub Pages**.

## Alcance científico

Alcance verificable: exploración y evaluación técnica de características BANDPOWER derivadas y de modelos de clasificación asociados a etiquetas motoras (`left`, `right`, `pull`, `push`), con variantes de limpieza y balanceo.

Fuera de alcance, según las propias advertencias del visor y del dashboard:

- qEEG clínico normativo;
- diagnóstico médico;
- confirmación fisiológica con EEG crudo/EOG/EMG/ECG;
- afirmación de ICA, notch, pasa banda o PSD cruda.

## Advertencias de interpretación

Las visualizaciones corresponden a características EEG BANDPOWER derivadas y no equivalen a qEEG clínico normativo ni a confirmación fisiológica con EEG crudo/EOG/EMG/ECG.

No deben presentarse como:

- qEEG clínico normativo;
- diagnóstico médico;
- confirmación fisiológica basada en EEG crudo;
- sustituto de evaluación clínica.

EEG crudo, EOG, EMG o ECG serían necesarios para determinadas verificaciones fisiológicas que este repositorio no demuestra por sí mismo.

Los artefactos se interpretan como sospechas sobre características BANDPOWER. Las figuras diagnósticas no implican confirmación fisiológica.

## Información metodológica pendiente de documentar

Resuelto o parcialmente resuelto con la ficha Kaggle [EEG 25-1](https://www.kaggle.com/datasets/griseldacortes/eeg-25-1/data):

- TESE = Tecnológico de Estudios Superiores de Ecatepec, México (**resuelto**);
- fuente del dataset y URL (**resuelto**);
- autores del dataset/proyecto (**resuelto**);
- laboratorio: National Laboratory in Artificial Intelligence and Data Science (**parcialmente resuelto**; denominación de la biografía pública de Griselda Cortés Barrera en Kaggle, no un nombre oficial registrado en español).

Este repositorio **aún no documenta**:

- protocolo experimental exacto;
- definición operativa de BANDPOWER;
- hiperparámetros;
- notebook fuente;
- detalles completos de adquisición EEG;
- umbrales y software del “protocolo TESE” de outliers;
- significado formal de los códigos numéricos de sujeto;
- afiliaciones de Alejandra Catherine Montaña Acevedo, Jesús Manuel Olivares Ceja y Jhacer Kharen Ruiz Garduño;
- dictamen ético versionado aquí;
- ORCID.

La redistribución de **resultados derivados** está autorizada, con atribución a los autores, a TESE cuando corresponda y al laboratorio descrito públicamente. `cano` y `villanueva` están confirmados como códigos institucionales pseudonimizados.

Hasta completar los pendientes, cualquier descripción de adquisición EEG que no esté en estos archivos o en la ficha Kaggle citada sería invención y debe evitarse.

Inventario de IDs: [IDENTIFICADORES.md](IDENTIFICADORES.md). Pipeline: [PIPELINE.md](PIPELINE.md).
