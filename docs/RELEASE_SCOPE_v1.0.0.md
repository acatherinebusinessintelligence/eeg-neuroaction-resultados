# Alcance de EEG NeuroAction Resultados v1.0.0

**Estado:** Release Candidate documental  
**Versión:** 1.0.0  
**Corrida de resultados:** `run_20260902_145353`  
**No hay tag, GitHub Release, Zenodo ni DOI en esta preparación.**

## Qué representa esta versión

EEG NeuroAction Resultados v1.0.0 es una versión estable de los resultados derivados, reportes, figuras y visualizaciones generadas a partir del análisis EEG asociado al dataset EEG 25-1.

Preserva las salidas ya versionadas en este repositorio (visor, dashboard, informe, reportes tabulares y figuras) y la documentación de procedencia, autoría, privacidad, licencias y limitaciones.

## Qué no constituye

No constituye:

- repositorio completo del experimento;
- pipeline computacional totalmente reproducible;
- repositorio de EEG crudo;
- qEEG clínico;
- sistema diagnóstico;
- validación clínica.

Las visualizaciones corresponden a características EEG BANDPOWER derivadas y no equivalen a qEEG clínico normativo ni a confirmación fisiológica con EEG crudo/EOG/EMG/ECG.

## Dataset fuente vs. resultados derivados

| Capa | Qué es | Dónde está | ¿En este release? |
| --- | --- | --- | --- |
| Dataset fuente | EEG 25-1 (ficha: EEG OF NEUROACTION LABELED) | https://www.kaggle.com/datasets/griseldacortes/eeg-25-1/data | **No.** No se duplica. No forma parte del árbol de este repositorio. |
| Resultados derivados | Reportes, figuras, HTML y métricas de la corrida Kaggle | Este GitHub | **Sí.** Es el objeto de v1.0.0. |

No se copian CSV/TXT de señal ni EDF del dataset fuente ni de Kaggle Working.

## Inventario del release

| Recurso | Incluir en release | Justificación |
| --- | --- | --- |
| `README.md` | **Sí** | Punto de entrada, estado RC, procedencia y límites. |
| `CITATION.cff` | **Sí** | Metadatos de citación; `version: 1.0.0`; sin DOI ni `date-released`. |
| `CHANGELOG.md` | **Sí** | Historial; sección `[1.0.0] - Unreleased`. |
| `LICENSE-CODE` | **Sí** | MIT para HTML/CSS/JS de interfaz. |
| `LICENSE-DOCS.md` | **Sí** | CC BY 4.0 para documentación. |
| `LICENSE-RESULTS.md` | **Sí** | CC BY 4.0 para resultados derivados. |
| `docs/` (versionado) | **Sí** | Metodología, evidencia, modelos, pipeline, privacidad, alcance y notas de release. |
| `docs/MAPA_PSEUDONIMIZACION_LOCAL.md` | **No** | Gitignored; no debe entrar en tag, Release ni Zenodo. |
| `index.html` | **Sí** | Entrada de GitHub Pages. |
| `visor_interactivo_eeg.html` | **Sí** | Visor de la corrida. No se modifica. |
| `dashboard_eeg_neuroaction.html` | **Sí** | Dashboard de la corrida. No se modifica. |
| `informe_evaluacion_resultados.html` | **Sí** | Informe por sujeto. No se modifica. |
| `figures/` | **Sí** | Figuras PNG derivadas (BANDPOWER, topomapas, matrices). No se modifican. |
| `reports/` (familias abajo) | **Sí** | Reportes de la corrida. No se modifican. |
| Dataset EEG 25-1 (archivos fuente) | **No** | Alojado en Kaggle; no está en este repo. |
| `.py` / `.ipynb` / EEG crudo / EDF | **No** | No existen en este repositorio. |

`.gitignore`, `.github` (si existiera) y metadatos git no se listan como “contenido científico”; no se altera el conjunto de resultados.

## Familias en `reports/`

Todas las familias siguientes **se incluyen** en v1.0.0. No se exige un listado archivo por archivo.

| Familia | Ejemplos | Incluir | Justificación |
| --- | --- | --- | --- |
| Evaluación de sujetos | `evaluacion_sujetos.csv` / `.xlsx`; `informe_evaluacion_resultados.html`; `resumen_ejecutivo_resultados.txt` | Sí | Resumen de calidad de evidencia de modelado (15 sujetos). |
| Modelos | `resultados_modelos_global.csv` / `.xlsx`; `comparacion_variantes_limpieza_modelos.csv` / `.xlsx` | Sí | Métricas de clasificadores. Hiperparámetros no están en estos archivos. |
| Balanceo | `comparacion_balanceo_modelos.csv` / `.xlsx`; `comparacion_balanceo_por_sujeto.csv` / `.xlsx`; `recall_por_clase_balanceo.csv` / `.xlsx`; `reports/balanceo/` | Sí | Comparación de seis estrategias; no declara un método “mejor” fuera de columnas del propio reporte. |
| Artefactos (resumen) | `reporte_artefactos_sospechados_resumen.csv` / `.xlsx`; `reporte_filtrado.csv`; `reporte_limpieza_artefactos.csv` | Sí | Conteos y tipos de sospecha por sujeto. |
| Artefactos (detalle, 122 279 filas) | `reporte_artefactos_sospechados_detalle.csv` / `.xlsx` | **Sí (INCLUIR)** | Ver decisión más abajo. |
| Diagnóstico temporal | `diagnostico_tiempos_csv_txt.csv`; `resumen_eventos_txt.csv` | Sí | Timestamps **CONSERVAR**; alineación CSV–TXT. |
| Archivos reconocidos | `archivos_eeg_reconocidos.csv`; `pares_eeg.csv`; `pares_txt_csv_eeg.csv`; `pruebas_csv_espanol_eeg.csv`; `resumen_procesamiento_eeg.csv` | Sí | Inventario de fuentes **nombradas**, no las series. |
| Figuras / visor (metadatos) | `reporte_figuras_generadas.csv`; `resumen_figuras_kaggle.csv`; `resumen_figuras_master.csv`; `reporte_visor_interactivo.csv` | Sí | Trazabilidad de PNG y cobertura del visor. |
| Corrida `run_20260902_145353` | `verificacion_kaggle_salidas.csv`; `validacion_salidas_pipeline.csv`; `archivos_generados.csv`; `reporte_mapeo.csv`; `resumen_exportacion_por_usuario.csv`; `index_kaggle.html` | Sí | Registro de la corrida. Los ZIP/EDF citados **no** están en GitHub. |
| Copias HTML | `reports/visor_interactivo_eeg.html` y homologables | Sí | Duplicados de interfaz ya versionados; no se borran. |

## Decisión: artefactos detallados (122 279 filas)

**INCLUIR** en v1.0.0.

Archivos: `reports/reporte_artefactos_sospechados_detalle.csv` y `reports/reporte_artefactos_sospechados_detalle.xlsx`.

| Criterio | Evaluación |
| --- | --- |
| Privacidad | Códigos de sujeto pseudonimizados (`cano` / `villanueva` institucionales; códigos numéricos no son nombres reales). No hay correos ni documentos de identidad en las columnas. Son características BANDPOWER derivadas, no EEG crudo. Redistribución de resultados autorizada. No se declara anonimato absoluto. Prohibida la reidentificación. |
| Utilidad científica | Es la tabla fila × canal × banda que sostiene el conteo 122 279 del dashboard y las sospechas por tipo. El resumen (365 filas) no sustituye el detalle. |
| Volumen | ~122 279 filas; el XLSX es voluminoso. Ya está en `main`; no se recalcula ni se recorta. |
| Redundancia | CSV y XLSX duplican el mismo reporte; **ambos se incluyen** porque ya existen. No se elimina ninguno. |
| Capacidad de interpretación | Heurística (`sospecha_sobre_bandpower`; `removido=no`). No es confirmación fisiológica ni qEEG clínico. |
| Necesidad para entender resultados | Alta, si se quiere inspeccionar las sospechas que citan el visor y el informe. |

Son **resultados derivados asociados a códigos institucionales pseudonimizados**. No se modifican.

## Limitaciones que permanecen en v1.0.0

- notebook / código fuente completo no incluido;
- hiperparámetros no documentados;
- rangos Hz de BANDPOWER no documentados;
- adquisición EEG incompleta;
- protocolo experimental parcialmente documentado;
- no hay EEG crudo, EOG, EMG ni ECG;
- no es pipeline totalmente reproducible.

Notas de publicación: [RELEASE_NOTES_v1.0.0.md](RELEASE_NOTES_v1.0.0.md).
