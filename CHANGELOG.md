# Changelog

All notable documentation and packaging changes for EEG NeuroAction Resultados are recorded here.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).
Versioning follows the convention v1.0.0 / v1.0.1 / v1.1.0 / v2.0.0.
This file does not create a GitHub Release.

## [1.0.1] - 2026-09-03

### Added

- DOI de Zenodo del recurso citable: [10.5281/zenodo.22286625](https://doi.org/10.5281/zenodo.22286625) (concepto: [10.5281/zenodo.22286624](https://doi.org/10.5281/zenodo.22286624)).
- ORCID de Alejandra Catherine Montaña Acevedo en `CITATION.cff` y README: <https://orcid.org/0009-0004-5991-2861>.
- Enlace de GitHub de la investigadora en README: <https://github.com/acatherinebusinessintelligence>.

### Changed

- `CITATION.cff` y README alineados con el registro Zenodo **v1.0.1**.
- No se recalcularon métricas ni se modificaron CSV, XLSX, PNG ni resultados científicos.

### Notes

- El depósito Zenodo versiona el registro como v1.0.1; el archivo archivado corresponde al tag GitHub `v1.0.0`.
- El DOI de Kaggle del dataset EEG 25-1 no se presenta como DOI de este visor.

## [1.0.0] - 2026-09-03

### Added

- documentación formal de metodología;
- documentación de procedencia;
- autores y afiliaciones verificadas disponibles;
- revisión de privacidad;
- revisión de pseudonimización;
- esquema de licencias;
- inventario de resultados;
- auditoría metodológica;
- documentación de modelos;
- visor interactivo en español (`visor_interactivo_eeg.html`);
- visor interactivo in English (`visor_interactivo_eeg_en.html`): traducción de presentación de los mismos resultados;
- documentación de pipeline;
- selector de idioma Español \| English en ambos visores;
- portada (`index.html`) con acceso a las dos versiones y aviso de que no hay un nuevo procesamiento.

### Changed

- aclaración de autoría y derechos: código (MIT, Alejandra Catherine Montaña Acevedo); dataset EEG 25-1 (cuatro autores); resultados derivados (atribución a los cuatro); recurso citable (cuatro autores, sin titularidad conjunta del código).
- roles documentados: Alejandra Catherine Montaña Acevedo (coinvestigadora, Corporación Universitaria Minuto de Dios (Uniminuto); automatización de datos, verificación de los procesos de inteligencia artificial y desarrollo de software); Jesús Manuel Olivares Ceja y Jhacer Kharen Ruiz Garduño (apoyo en proyecto).

### Known limitations

- notebook fuente no incluido;
- hiperparámetros incompletos;
- frecuencias BANDPOWER no documentadas;
- adquisición EEG incompleta;
- protocolo experimental parcialmente documentado.

### Notes

- Esta incorporación bilingüe forma parte de v1.0.0; no se cambia el número a v1.1.0. No se añade DOI ni `date-released`. Esta pasada no crea GitHub Release ni depósito Zenodo.
- El detalle de artefactos (122 279 filas) **se incluye** en v1.0.0 como resultados derivados con códigos pseudonimizados.
- No se modificaron CSV, XLSX, PNG ni HTML de resultados científicos (dashboard, informe, reportes). El visor español solo recibió el selector de idioma; el visor inglés replica los mismos datos embebidos.

## [0.9.0] - 2026

### Added

- `docs/metodologia.md`: metodología restringida a lo verificable en el repositorio, con advertencia BANDPOWER y sección de información pendiente.
- `docs/RESULTADOS.md`: inventario de familias de resultados (HTML, CSV, XLSX, figuras, reportes, modelos, balanceo) sin reinterpretar métricas.
- `docs/REVISION_PUBLICACION.md`: revisión de privacidad con evidencia encontrada y propuesta de licencias no aplicada.
- `CITATION.cff` (schema 1.2.0, tipo software, versión 0.9.0), sin DOI.
- Este `CHANGELOG.md`.
- README ampliado (visor, dashboard, informe, estructura, citación, estado v0.9.0).
- Auditoría de publicación: `docs/IDENTIFICADORES.md`, `docs/PLAN_PSEUDONIMIZACION.md`, `docs/PIPELINE.md`, criterios previos a Zenodo, clasificación de timestamps, `.gitignore` para el mapa local de identidad.
- Aclaración estructural del detalle de 122 279 artefactos (BANDPOWER derivado, sin EEG crudo).
- `LICENSE-CODE` (MIT), `LICENSE-DOCS.md` (CC BY 4.0), `LICENSE-RESULTS.md` (CC BY 4.0).
- `docs/EVIDENCIA_METODOLOGICA.md`: matriz de evidencia (confirmado / parcialmente documentado / no documentado).
- `docs/MODELOS.md`: clasificadores, métricas, balanceo; hiperparámetros no documentados.
- Secciones de protocolo experimental, adquisición EEG, BANDPOWER y nivel de reproducibilidad en `docs/metodologia.md`.
- Registro de corrida `run_20260902_145353` en `docs/PIPELINE.md` (registro de resultados ≠ pipeline reproducible).

### Changed

- Confirmación de la autora: `cano` y `villanueva` son códigos institucionales pseudonimizados (no nombres reales); riesgo documentado como bajo/controlado.
- Redistribución de resultados autorizada, con atribución a la autora y al laboratorio (nombre formal pendiente).
- `CITATION.cff`: campo `license: MIT`; versión **0.9.0** (v1.0.0 diferida en esa etapa).
- Timestamps: decisión cerrada **CONSERVAR**; riesgo residual contextual; valores no modificados.
- Criterios de publicación: **B. listo para v1.0.0 con limitaciones documentadas**.

### Changed (autoría y procedencia)

- Autores según ficha Kaggle EEG 25-1: Griselda Cortés Barrera; Alejandra Catherine Montaña Acevedo; Jesús Manuel Olivares Ceja; Jhacer Kharen Ruiz Garduño.
- TESE = Tecnológico de Estudios Superiores de Ecatepec, México.
- Dataset fuente documentado: https://www.kaggle.com/datasets/griseldacortes/eeg-25-1/data
- Laboratorio (parcial): National Laboratory in Artificial Intelligence and Data Science (biografía pública en Kaggle; sin traducción oficial ni acrónimo inventado).
- `CITATION.cff` y `LICENSE-RESULTS.md` actualizados para atribución múltiple.

### Notes

- Decisión B: limitaciones (notebook ausente, hiperparámetros no documentados, Hz de BANDPOWER no documentados, protocolo experimental incompleto) están declaradas y no se inventan.
- No se modificaron CSV, XLSX, PNG ni HTML de resultados.
- No se creó tag, GitHub Release, Zenodo ni DOI.
