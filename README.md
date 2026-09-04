# EEG NeuroAction

## Resultados y visor interactivo

Visor web y archivo de resultados técnicos del pipeline EEG NeuroAction: reportes, figuras y métricas de clasificación sobre características EEG BANDPOWER asociadas a movimientos motores.

**Versión:** v1.0.0 Release Candidate  
**Estado:** Release Candidate documental. No hay tag `v1.0.0`, GitHub Release ni DOI de Zenodo.

## Estado de la versión

EEG NeuroAction Resultados v1.0.0 preserva los resultados derivados, reportes y visualizaciones disponibles en el repositorio.

La versión se publica con limitaciones documentadas de reproducibilidad.

[Alcance de v1.0.0](docs/RELEASE_SCOPE_v1.0.0.md)  
[Notas de v1.0.0](docs/RELEASE_NOTES_v1.0.0.md)

Las visualizaciones corresponden a características EEG BANDPOWER derivadas. No equivalen a qEEG clínico normativo ni a confirmación fisiológica con EEG crudo/EOG/EMG/ECG.

## Descripción

Este repositorio publica salidas de una corrida Kaggle (`run_20260902_145353`) para explorar, por sujeto y por variante de limpieza:

- figuras de BANDPOWER (scroll, topomapas, espectros);
- sospechas de artefactos sobre características derivadas;
- modelos de clasificación y matrices de confusión;
- comparación controlada de estrategias de balanceo.

No contiene el código del pipeline ni las series EEG crudas.

**TESE** = Tecnológico de Estudios Superiores de Ecatepec (México). La corrida Kaggle se registró bajo `TESE_pruebas`.

## Dataset fuente

**Dataset:** EEG 25-1  
**Fuente:** Kaggle  
**URL:** <https://www.kaggle.com/datasets/griseldacortes/eeg-25-1/data>

Autores (orden de la ficha Kaggle):

- Griselda Cortés Barrera
- Alejandra Catherine Montaña Acevedo
- Jesús Manuel Olivares Ceja
- Jhacer Kharen Ruiz Garduño

Esta ficha se utiliza como fuente de procedencia y autoría del dataset/proyecto, no como declaración de titularidad conjunta del código de este repositorio.

## Autoría, atribución y derechos

La autoría del recurso citable no implica titularidad conjunta del código fuente.

### Código

Autora:  
Alejandra Catherine Montaña Acevedo

Licencia:  
MIT

Copyright: (c) 2026 Alejandra Catherine Montaña Acevedo (`LICENSE-CODE`). Rol documentado: encargada de la automatización del proceso de datos, transformación, verificación de los procesos de inteligencia artificial y desarrollo de software (código base en Kaggle y GitHub). No hay evidencia en este repositorio de contribución de software de los demás autores del dataset; no se les declara titulares del código.

### Dataset fuente EEG 25-1

Autores:

- Griselda Cortés Barrera
- Alejandra Catherine Montaña Acevedo
- Jesús Manuel Olivares Ceja
- Jhacer Kharen Ruiz Garduño

Fuente: <https://www.kaggle.com/datasets/griseldacortes/eeg-25-1/data>

### Resultados derivados

La reutilización requiere atribución a los autores del proyecto EEG 25-1 y reconocimiento institucional cuando corresponda (TESE; National Laboratory in Artificial Intelligence and Data Science, según la formulación documentada en la ficha Kaggle). Licencia: CC BY 4.0 (`LICENSE-RESULTS.md`).

### Recurso citable (CITATION.cff)

Los cuatro autores anteriores figuran como autores del recurso **EEG NeuroAction: resultados, análisis y visualización interactiva**. Esa lista describe la obra conjunta de resultados. No implica que todos sean titulares del copyright del código.

### Afiliaciones y roles documentados

Fuente de Griselda Cortés Barrera: ficha Kaggle / TESE. Afiliación y rol de Alejandra Catherine Montaña Acevedo, y roles de Jesús Manuel Olivares Ceja y Jhacer Kharen Ruiz Garduño: confirmación de Alejandra Catherine Montaña Acevedo. No se inventan instituciones no dichas.

| Autor | Afiliación o rol documentado |
| --- | --- |
| Griselda Cortés Barrera | Tecnológico de Estudios Superiores de Ecatepec (TESE), México |
| Alejandra Catherine Montaña Acevedo | Coinvestigadora, Corporación Universitaria Minuto de Dios (Uniminuto). Encargada de la automatización del proceso de datos: transformación, verificación de los procesos de inteligencia artificial y desarrollo de software; código base en Kaggle y GitHub. |
| Jesús Manuel Olivares Ceja | Apoyo en proyecto |
| Jhacer Kharen Ruiz Garduño | Apoyo en proyecto |

“Apoyo en proyecto” es un rol, no una afiliación institucional. No implica titularidad del código (el código permanece bajo MIT con copyright de Alejandra Catherine Montaña Acevedo).

Laboratorio (formulación prudente): **National Laboratory in Artificial Intelligence and Data Science**. Denominación tomada de la biografía pública de Griselda Cortés Barrera en la ficha Kaggle del dataset. No se traduce a un nombre institucional oficial en español ni se inventa un acrónimo.

## Objetivo

Dejar documentadas, trazables y citables las salidas del análisis EEG NeuroAction, de forma que una futura v1.0.0 pueda archivarse en Zenodo sin alterar los resultados computacionales.

## Visor

Página de entrada: [`index.html`](index.html)

- Visor en español: [`visor_interactivo_eeg.html`](visor_interactivo_eeg.html)
- Interactive viewer in English: [`visor_interactivo_eeg_en.html`](visor_interactivo_eeg_en.html)

GitHub Pages:

- Español: <https://acatherinebusinessintelligence.github.io/eeg-neuroaction-resultados/visor_interactivo_eeg.html>
- English: <https://acatherinebusinessintelligence.github.io/eeg-neuroaction-resultados/visor_interactivo_eeg_en.html>

Ambos visores contienen los mismos datos, resultados, métricas, figuras y metodología. La versión inglesa es una **traducción de presentación** (interfaz y narrativa); no es un nuevo procesamiento de los datos.

El visor permite filtrar por sujeto, tipo de figura, variante de limpieza/modelado y estrategia de balanceo, y muestra galería, métricas, artefactos sospechados y matrices.

## Dashboard

[`dashboard_eeg_neuroaction.html`](dashboard_eeg_neuroaction.html)

Resumen ejecutivo de la corrida (sujetos, retención, outliers, artefactos sospechados) con gráficos Plotly embebidos.

## Informe de evaluación

[`informe_evaluacion_resultados.html`](informe_evaluacion_resultados.html)

También: [`reports/resumen_ejecutivo_resultados.txt`](reports/resumen_ejecutivo_resultados.txt)

Clasifica la evidencia de modelado por sujeto (aprobado, revisión, no confiable). Esa clasificación no es un diagnóstico médico.

## Estructura de resultados

```text
.
├── index.html
├── visor_interactivo_eeg.html
├── visor_interactivo_eeg_en.html
├── dashboard_eeg_neuroaction.html
├── informe_evaluacion_resultados.html
├── figures/          # PNG por sujeto, topomapas, scroll, spectral, master
├── reports/          # CSV, XLSX, HTML auxiliares, balanceo
└── docs/             # metodología, inventario y revisión de publicación
```

Inventario detallado: [Resultados](docs/RESULTADOS.md)  
Pipeline de la corrida: [PIPELINE.md](docs/PIPELINE.md)  
Matriz de evidencia: [EVIDENCIA_METODOLOGICA.md](docs/EVIDENCIA_METODOLOGICA.md)  
Modelos: [MODELOS.md](docs/MODELOS.md)

## Metodología

[Metodología](docs/metodologia.md)

Las visualizaciones corresponden a características EEG BANDPOWER derivadas. No equivalen a qEEG clínico normativo ni a confirmación fisiológica con EEG crudo/EOG/EMG/ECG.

## Limitaciones

- No hay EEG crudo, EOG, EMG ni ECG en este repositorio.
- No hay scripts ni notebooks que regeneren las métricas.
- Los artefactos son sospechas sobre BANDPOWER, no confirmación fisiológica.
- Los códigos de sujeto (`cano`, `villanueva` y códigos numéricos) no deben interpretarse como nombres reales ni usarse para reidentificar.
- No debe usarse como qEEG clínico, diagnóstico médico ni sustituto de evaluación clínica.

## Reproducibilidad

Cadena observada:

**Kaggle (`TESE_pruebas` / `run_20260902_145353`, dataset [EEG 25-1](https://www.kaggle.com/datasets/griseldacortes/eeg-25-1/data))** → **procesamiento (no versionado aquí)** → **reportes** → **visualizaciones** → **GitHub Pages**

Este repo permite consultar las salidas. No permite reejecutar el experimento. Nivel: **resultados preservados, con documentación parcial** (no es un pipeline totalmente reproducible).

## Citación

La referencia de [`CITATION.cff`](CITATION.cff) corresponde al recurso **EEG NeuroAction: resultados, análisis y visualización interactiva** (resultados derivados, reportes y visualización interactiva), versión **1.0.0** (Release Candidate documental).

Autores del recurso citable (mismo orden que la ficha Kaggle [EEG 25-1](https://www.kaggle.com/datasets/griseldacortes/eeg-25-1/data)):

1. Griselda Cortés Barrera (Tecnológico de Estudios Superiores de Ecatepec, TESE, México)
2. Alejandra Catherine Montaña Acevedo (Coinvestigadora, Corporación Universitaria Minuto de Dios (Uniminuto); automatización del proceso de datos, transformación, verificación de los procesos de inteligencia artificial y desarrollo de software; código base en Kaggle y GitHub)
3. Jesús Manuel Olivares Ceja (apoyo en proyecto)
4. Jhacer Kharen Ruiz Garduño (apoyo en proyecto)

La autoría del recurso citable no implica titularidad conjunta del código fuente.

El DOI de Zenodo se añadirá **solo cuando exista**; no hay DOI en esta versión.

## Licencias y atribución

- **Código:** MIT — sola titular documentada: Alejandra Catherine Montaña Acevedo (`LICENSE-CODE`)
- **Documentación:** CC BY 4.0 — preparada y organizada por Alejandra Catherine Montaña Acevedo (`LICENSE-DOCS.md`)
- **Resultados derivados:** CC BY 4.0 — atribución a los cuatro autores del proyecto EEG 25-1 (`LICENSE-RESULTS.md`)

Enlaces:

- [Licencia del código](LICENSE-CODE)
- [Licencia de documentación](LICENSE-DOCS.md)
- [Licencia de resultados](LICENSE-RESULTS.md)

La reutilización de resultados debe reconocer a los autores del dataset/proyecto EEG 25-1, a Tecnológico de Estudios Superiores de Ecatepec (TESE) cuando corresponda, a Corporación Universitaria Minuto de Dios (Uniminuto) cuando corresponda, y al laboratorio descrito públicamente como National Laboratory in Artificial Intelligence and Data Science.

Denominación del laboratorio tomada de la biografía pública de Griselda Cortés Barrera en la ficha Kaggle del dataset. No se afirma un nombre institucional oficial en español ni se inventa un acrónimo.

La licencia de resultados no transfiere copyright entre autores, no otorga derechos adicionales sobre datos fuente de terceros, no autoriza reidentificación y no implica que todos los autores sean titulares del código.

Texto oficial CC BY 4.0: <https://creativecommons.org/licenses/by/4.0/>

Detalle de publicación: [Revisión para publicación](docs/REVISION_PUBLICACION.md)

Estado: **APTO PARA RELEASE CANDIDATE v1.0.0 CON LIMITACIONES DOCUMENTADAS.** Versión **1.0.0**. No hay tag `v1.0.0` ni DOI. No se ha creado GitHub Release ni depósito Zenodo.

## Estado del proyecto

| Ítem | Estado |
| --- | --- |
| Documentación metodológica | v1.0.0 RC; limitaciones de reproducibilidad explícitas |
| Inventario de resultados | Incluido; alcance en [RELEASE_SCOPE_v1.0.0.md](docs/RELEASE_SCOPE_v1.0.0.md) |
| Revisión de publicación / privacidad | Códigos institucionales confirmados; timestamps **CONSERVAR**; RC documental |
| Identificadores | `cano` / `villanueva`: códigos institucionales pseudonimizados (no nombres reales) |
| Autores | Cuatro autores de la ficha Kaggle EEG 25-1 |
| TESE | Tecnológico de Estudios Superiores de Ecatepec, México |
| Laboratorio | National Laboratory in Artificial Intelligence and Data Science (parcial; ficha Kaggle) |
| Licencias | MIT (código); CC BY 4.0 (docs y resultados derivados) |
| `CITATION.cff` | 1.0.0, `license: MIT`, sin DOI, sin `date-released` |
| Tag / GitHub Release | No creado |
| Zenodo / DOI | No creado |
| Convención futura | v1.0.0, v1.1.0, v2.0.0 |

## Enlaces

- [Alcance de v1.0.0](docs/RELEASE_SCOPE_v1.0.0.md)
- [Notas de v1.0.0](docs/RELEASE_NOTES_v1.0.0.md)
- [Metodología](docs/metodologia.md)
- [Evidencia metodológica](docs/EVIDENCIA_METODOLOGICA.md)
- [Modelos](docs/MODELOS.md)
- [Pipeline](docs/PIPELINE.md)
- [Identificadores](docs/IDENTIFICADORES.md)
- [Plan de identificadores](docs/PLAN_PSEUDONIMIZACION.md)
- [Revisión para publicación](docs/REVISION_PUBLICACION.md)
- [Inventario de resultados](docs/RESULTADOS.md)
- [CHANGELOG](CHANGELOG.md)
- [Licencia del código](LICENSE-CODE)
- [Licencia de documentación](LICENSE-DOCS.md)
- [Licencia de resultados](LICENSE-RESULTS.md)
