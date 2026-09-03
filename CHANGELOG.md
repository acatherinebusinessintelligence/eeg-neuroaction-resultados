# Changelog

All notable documentation and packaging changes for EEG NeuroAction Resultados are recorded here.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).
Versioning follows the future convention v1.0.0 / v1.1.0 / v2.0.0.
This file documents the preparation version; it does not create a GitHub Release.

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

### Changed

- Confirmación de la autora: `cano` y `villanueva` son códigos institucionales pseudonimizados (no nombres reales); riesgo documentado como bajo/controlado.
- Redistribución de resultados autorizada, con atribución a la autora y al laboratorio (nombre formal pendiente).
- `CITATION.cff`: campo `license: MIT`; versión **0.9.0** (v1.0.0 diferida).
- Timestamps: riesgo bajo/moderado sujeto a contexto temporal; se conservan.
- Criterios Zenodo: próximo a apto; no plenamente apto.

### Changed (autoría y procedencia)

- Autores según ficha Kaggle EEG 25-1: Griselda Cortés Barrera; Alejandra Catherine Montaña Acevedo; Jesús Manuel Olivares Ceja; Jhacer Kharen Ruiz Garduño.
- TESE = Tecnológico de Estudios Superiores de Ecatepec, México.
- Dataset fuente documentado: https://www.kaggle.com/datasets/griseldacortes/eeg-25-1/data
- Laboratorio (parcial): National Laboratory in Artificial Intelligence and Data Science (biografía pública en Kaggle; sin traducción oficial ni acrónimo inventado).
- `CITATION.cff` y `LICENSE-RESULTS.md` actualizados para atribución múltiple.

### Notes

- No se pasó a v1.0.0: faltan metodología experimental mínima, revisión definitiva de timestamps y release candidate.
- No se modificaron CSV, XLSX, PNG ni HTML de resultados.
- No se creó tag, GitHub Release, Zenodo ni DOI.
