# EEG NeuroAction Resultados v1.0.0

Primera versión estable de resultados derivados, reportes y visualizaciones EEG NeuroAction.

**Estado:** Release Candidate documental. No hay tag `v1.0.0`, GitHub Release ni DOI.

Las visualizaciones corresponden a características EEG BANDPOWER derivadas y no equivalen a qEEG clínico normativo ni a confirmación fisiológica con EEG crudo/EOG/EMG/ECG.

## Alcance

EEG NeuroAction Resultados v1.0.0 es una versión estable de los resultados derivados, reportes, figuras y visualizaciones generadas a partir del análisis EEG asociado al dataset EEG 25-1.

No constituye el repositorio completo del experimento, un pipeline computacional totalmente reproducible, un repositorio de EEG crudo, qEEG clínico, un sistema diagnóstico ni una validación clínica.

Inventario: [RELEASE_SCOPE_v1.0.0.md](RELEASE_SCOPE_v1.0.0.md).

## Dataset fuente

**Dataset:** EEG 25-1  
**Fuente:** Kaggle  
**URL:** https://www.kaggle.com/datasets/griseldacortes/eeg-25-1/data

El dataset fuente **no** se duplica en este release. Este repositorio publica **resultados derivados**, no los CSV/TXT de señal ni EDF.

## Autoría y atribución

Autores del recurso citable EEG NeuroAction Resultados v1.0.0:

- Griselda Cortés Barrera
- Alejandra Catherine Montaña Acevedo
- Jesús Manuel Olivares Ceja
- Jhacer Kharen Ruiz Garduño

El código del repositorio mantiene copyright de Alejandra Catherine Montaña Acevedo bajo MIT; la autoría del recurso científico no implica titularidad conjunta del software.

Afiliación o rol documentado:

- Griselda Cortés Barrera — Tecnológico de Estudios Superiores de Ecatepec (TESE), México
- Alejandra Catherine Montaña Acevedo — Coinvestigadora, Corporación Universitaria Minuto de Dios (Uniminuto). Encargada de la automatización del proceso de datos: transformación, verificación de los procesos de inteligencia artificial y desarrollo de software; código base en Kaggle y GitHub.
- Jesús Manuel Olivares Ceja — Apoyo en proyecto
- Jhacer Kharen Ruiz Garduño — Apoyo en proyecto

Laboratorio (formulación prudente): National Laboratory in Artificial Intelligence and Data Science (denominación tomada de la biografía pública de Griselda Cortés Barrera en la ficha Kaggle). No se inventa acrónimo ni nombre oficial en español.

## Contenido del release

- visor HTML en español y en inglés (mismos resultados; la versión inglesa es traducción de interfaz y narrativa);
- dashboard e informe HTML;
- figuras PNG (BANDPOWER, topomapas, espectros, matrices);
- reportes CSV/XLSX de evaluación, modelos, balanceo, artefactos, inventario y verificación de la corrida `run_20260902_145353`;
- detalle de artefactos sospechados (122 279 filas): **incluido** (características derivadas; códigos pseudonimizados);
- documentación (`docs/`), README, CHANGELOG, CITATION.cff y licencias.

No incluye: dataset fuente EEG 25-1, notebook del pipeline, EEG crudo, EDF, ZIP de Kaggle citados y no versionados.

## Metodología

Documentada en [metodologia.md](metodologia.md) y [EVIDENCIA_METODOLOGICA.md](EVIDENCIA_METODOLOGICA.md).

Protocolo y adquisición: evidencia confirmada, parcial o no documentada, sin invención. BANDPOWER: nombres de banda; rangos en Hz no documentados.

## Modelos

Siete clasificadores en `reports/resultados_modelos_global.csv` (NaiveBayes, SMO_SVM, MLP, IBk_kNN, RBFNetwork_aprox, J48_C45, RandomForest). Seis estrategias de balanceo. Hiperparámetros: no documentados. Detalle: [MODELOS.md](MODELOS.md).

## Privacidad y pseudonimización

Los sujetos se representan con códigos institucionales pseudonimizados. `cano` y `villanueva` no deben interpretarse como nombres reales. No hay autorización para reidentificar. Este repositorio no declara anonimato absoluto. Timestamps de sesión: decisión **CONSERVAR**.

## Licencias

Código:  
MIT

Documentación:  
CC BY 4.0

Resultados derivados:  
CC BY 4.0

Atribución a los autores del proyecto EEG 25-1, a TESE cuando corresponda, a Corporación Universitaria Minuto de Dios (Uniminuto) cuando corresponda, y al laboratorio descrito públicamente. El código permanece bajo MIT con copyright de Alejandra Catherine Montaña Acevedo. La autoría del recurso científico no implica titularidad conjunta del software. La licencia de resultados no otorga derechos adicionales sobre datos fuente de terceros.

## Limitaciones

- no contiene EEG crudo;
- no equivale a qEEG clínico;
- no permite reproducción completa del pipeline;
- no contiene notebook fuente;
- no contiene hiperparámetros completos;
- rangos BANDPOWER Hz no documentados;
- adquisición EEG incompleta;
- protocolo experimental parcialmente documentado.

## Reproducibilidad

Estado:

Resultados preservados con documentación parcial.

## DOI

DOI de esta versión (registro Zenodo **v1.0.1**): [10.5281/zenodo.22286625](https://doi.org/10.5281/zenodo.22286625).  
DOI de concepto: [10.5281/zenodo.22286624](https://doi.org/10.5281/zenodo.22286624).  
Registro: <https://zenodo.org/records/22286625>.

El tag GitHub archivado es `v1.0.0`. El DOI de Kaggle del dataset EEG 25-1 no es el DOI de este visor.
