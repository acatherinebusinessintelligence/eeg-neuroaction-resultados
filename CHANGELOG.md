# Changelog

All notable documentation and packaging changes for EEG NeuroAction Resultados are recorded here.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).
Versioning follows the convention v1.0.0 / v1.1.0 / v2.0.0.
This file does not create a GitHub Release.

## [1.0.0] - Unreleased

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
- documentación de pipeline;
- definición del alcance del release.

### Changed

- aclaración de autoría y derechos: código (MIT, Alejandra Catherine Montaña Acevedo); dataset EEG 25-1 (cuatro autores); resultados derivados (atribución a los cuatro); recurso citable (cuatro autores, sin titularidad conjunta del código).

### Known limitations

- notebook fuente no incluido;
- hiperparámetros incompletos;
- frecuencias BANDPOWER no documentadas;
- adquisición EEG incompleta;
- protocolo experimental parcialmente documentado.

### Notes

- Release Candidate documental. No hay tag, GitHub Release, Zenodo, DOI ni `date-released`.
- El detalle de artefactos (122 279 filas) **se incluye** en v1.0.0 como resultados derivados con códigos pseudonimizados.
- No se modificaron CSV, XLSX, PNG ni HTML de resultados.

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
