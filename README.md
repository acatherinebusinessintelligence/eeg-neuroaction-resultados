# EEG NeuroAction

## Resultados y visor interactivo

Visor web y archivo de resultados técnicos del pipeline EEG NeuroAction: reportes, figuras y métricas de clasificación sobre características EEG BANDPOWER asociadas a movimientos motores.

**Versión de preparación:** v0.9.0  
**Estado:** candidata a primera versión estable. Aún no hay tag `v1.0.0`, GitHub Release ni DOI de Zenodo.

Las visualizaciones corresponden a características EEG BANDPOWER derivadas. No equivalen a qEEG clínico normativo ni a confirmación fisiológica con EEG crudo/EOG/EMG/ECG.

## Descripción

Este repositorio publica salidas de una corrida Kaggle (`run_20260902_145353`) para explorar, por sujeto y por variante de limpieza:

- figuras de BANDPOWER (scroll, topomapas, espectros);
- sospechas de artefactos sobre características derivadas;
- modelos de clasificación y matrices de confusión;
- comparación controlada de estrategias de balanceo.

No contiene el código del pipeline ni las series EEG crudas.

## Objetivo

Dejar documentadas, trazables y citables las salidas del análisis EEG NeuroAction, de forma que una futura v1.0.0 pueda archivarse en Zenodo sin alterar los resultados computacionales.

## Visor

Página de entrada: [`index.html`](index.html)

Visor interactivo: [`visor_interactivo_eeg.html`](visor_interactivo_eeg.html)

GitHub Pages: <https://acatherinebusinessintelligence.github.io/eeg-neuroaction-resultados/>

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
├── dashboard_eeg_neuroaction.html
├── informe_evaluacion_resultados.html
├── figures/          # PNG por sujeto, topomapas, scroll, spectral, master
├── reports/          # CSV, XLSX, HTML auxiliares, balanceo
└── docs/             # metodología, inventario y revisión de publicación
```

Inventario detallado: [Resultados](docs/RESULTADOS.md)  
Pipeline de la corrida: [PIPELINE.md](docs/PIPELINE.md)

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

**Kaggle (`TESE_pruebas` / `run_20260902_145353`)** → **procesamiento (no versionado aquí)** → **reportes** → **visualizaciones** → **GitHub Pages**

Este repo permite consultar las salidas. No permite reejecutar el experimento.

## Citación

Autora: Alejandra Catherine Montaña Acevedo

Versión de preparación: **0.9.0**

Citar este software con los metadatos de [`CITATION.cff`](CITATION.cff). El DOI de Zenodo se añadirá **solo cuando exista**; no hay DOI en esta versión.

## Licencias y atribución

- **Código:** MIT
- **Documentación:** CC BY 4.0
- **Resultados derivados:** CC BY 4.0

Enlaces:

- [Licencia del código](LICENSE-CODE)
- [Licencia de documentación](LICENSE-DOCS.md)
- [Licencia de resultados](LICENSE-RESULTS.md)

La reutilización de resultados debe reconocer también al laboratorio correspondiente.

Nombre formal del laboratorio: pendiente de incorporar.

La licencia de resultados no otorga derechos adicionales sobre datos fuente de terceros y no autoriza reidentificación de participantes.

Texto oficial CC BY 4.0: <https://creativecommons.org/licenses/by/4.0/>

Detalle de publicación: [Revisión para publicación](docs/REVISION_PUBLICACION.md)

Estado Zenodo: **próximo a apto para depósito permanente** (faltan el nombre del laboratorio y otros checks). No hay tag `v1.0.0` ni DOI.

## Estado del proyecto

| Ítem | Estado |
| --- | --- |
| Documentación metodológica | Añadida en v0.9.0 |
| Inventario de resultados | Añadido en v0.9.0 |
| Revisión de publicación / privacidad | Códigos institucionales confirmados; **próximo a apto para Zenodo** |
| Identificadores | `cano` / `villanueva`: códigos institucionales pseudonimizados (no nombres reales) |
| Licencias | MIT (código); CC BY 4.0 (docs y resultados derivados) |
| `CITATION.cff` | 0.9.0, `license: MIT`, sin DOI |
| Tag / GitHub Release | No creado |
| Zenodo / DOI | No creado |
| Convención futura | v1.0.0, v1.1.0, v2.0.0 |

## Enlaces

- [Metodología](docs/metodologia.md)
- [Pipeline](docs/PIPELINE.md)
- [Identificadores](docs/IDENTIFICADORES.md)
- [Plan de identificadores](docs/PLAN_PSEUDONIMIZACION.md)
- [Revisión para publicación](docs/REVISION_PUBLICACION.md)
- [Inventario de resultados](docs/RESULTADOS.md)
- [CHANGELOG](CHANGELOG.md)
- [Licencia del código](LICENSE-CODE)
- [Licencia de documentación](LICENSE-DOCS.md)
- [Licencia de resultados](LICENSE-RESULTS.md)
