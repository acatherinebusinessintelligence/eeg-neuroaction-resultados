# Revisión para publicación permanente

Documento de preparación para una futura versión estable y un posible archivo citable en Zenodo.

**Versión de preparación:** v0.9.0  
**Estado:** candidata a primera versión estable.  
**Fecha de revisión:** 2026-09-03  
**Alcance:** inspección de nombres de archivo, encabezados CSV, filas de muestra y texto de reportes/HTML. No se modificó ningún resultado computacional.

Este repositorio **ya es público** en GitHub y se sirve por GitHub Pages:

- Código/resultados: <https://github.com/acatherinebusinessintelligence/eeg-neuroaction-resultados>
- Visor publicado: <https://acatherinebusinessintelligence.github.io/eeg-neuroaction-resultados/>

La revisión siguiente no declara que los datos sean anónimos. Varios recursos requieren revisión humana antes de un archivo permanente.

## Criterio

- Solo se registra evidencia realmente encontrada.
- No se eliminó ni se reescribió ningún archivo de resultados.
- Si la privacidad no puede determinarse por estructura o contenido, se indica: *Requiere revisión humana antes de publicación permanente.*

## Tabla de revisión

| Recurso | Riesgo aparente | Observación | Acción recomendada |
| --- | --- | --- | --- |
| Identificadores de sujeto `cano` y `villanueva` (carpetas `figures/cano`, `figures/villanueva`; columnas `sujeto` en CSV/HTML) | Alto | Los identificadores son apellidos. Aparecen de forma reiterada en reportes, figuras, el visor y el informe de evaluación. | Requiere revisión humana antes de publicación permanente. Valorar seudonimización o recodificación antes de Zenodo, sin borrar el histórico si hace falta trazabilidad interna. |
| Nombres de archivo fuente `derecha 1ra_Cano 1.csv`, `izquierda 1ra_Cano 1.csv`, `empujar 1ra_Cano 1.csv`, `jalar 1ra_Cano 1.csv`, `derecha 2da_Villanueva 1.csv`, `izquierda 2da_Villanueva 1.csv`, `empujar 2da_Villanueva 1.csv`, `jalar 2da_Villanueva 1.csv` | Alto | Evidencia en `reports/archivos_eeg_reconocidos.csv` y `reports/pruebas_csv_espanol_eeg.csv`. Los nombres originales combinan apellido, repetición (`1ra`/`2da`) y acción motora. | Requiere revisión humana antes de publicación permanente. No eliminar. Decidir si el archivo permanente puede conservar estos nombres o debe documentar un mapeo seudonimizado. |
| Códigos de sujeto numéricos (`211260561`, `212260563`, `212260567`, `212260569`, `212260666`, `212260668`, `212260672`, `222260671`, `22260552`, `231260558`, `252260554`, `252260556`, `252260670`) | Medio, no determinado | Son identificadores estables y repetidos en rutas, CSV, XLSX, PNG y HTML. Este repositorio no documenta si son seudónimos internos o códigos institucionales. | Requiere revisión humana antes de publicación permanente. No afirmar que sean anónimos. |
| `reports/evaluacion_sujetos.csv` e `informe_evaluacion_resultados.html` | Medio | Contienen métricas, alertas de artefactos y comentarios técnicos por sujeto. No se encontraron correos, documentos de identidad ni diagnósticos clínicos nominativos. Sí hay identificadores de sujeto, incluidos apellidos. | Conservar para trazabilidad. Revisión humana de identificadores antes de archivo permanente. |
| `reports/reporte_artefactos_sospechados_detalle.csv` y `.xlsx` | Medio-alto | 122 279 filas con `sujeto`, `archivo`, `fila`, `canal`, `banda`, `valor` y tipo de artefacto sospechado. Son características BANDPOWER derivadas, no EEG crudo. Siguen siendo datos biométricos derivados por persona. El XLSX pesa ~8,2 MB. | Requiere revisión humana antes de publicación permanente. No declarar anonimato. Valorar si el detalle fila a fila es necesario en Zenodo o si basta el resumen. |
| `reports/diagnostico_tiempos_csv_txt.csv` | Medio | Incluye `timestamp_min` / `timestamp_max` y equivalentes TXT. Los valores Unix inspeccionados caen entre 2026-05-19 y 2026-06-08 (UTC). Son marcas de sesión, no fechas de nacimiento, pero datan capturas por sujeto. | Requiere revisión humana antes de publicación permanente. Confirmar si esas marcas temporales pueden reidentificar participantes. |
| Columnas `ruta` / `ruta_archivo` en varios CSV (`reports/archivos_generados.csv`, `reports/reporte_figuras_generadas.csv`, `reports/resumen_exportacion_por_usuario.csv`, `reports/validacion_salidas_pipeline.csv`, `reports/verificacion_kaggle_salidas.csv`) | Bajo en lo personal; medio en procedencia | Las rutas encontradas son de Kaggle (`/kaggle/working/outputs/TESE_pruebas/run_20260902_145353/...`). No se encontraron rutas `C:\Users\...`, `/Users/...` ni OneDrive con nombres personales. El segmento `TESE_pruebas` nombra un contexto de corrida no documentado en este repositorio. | No se hallaron rutas locales con nombres personales. Documentar el significado de `TESE_pruebas` antes de archivar. Requiere revisión humana del contexto institucional. |
| `reports/resumen_exportacion_por_usuario.csv` | Medio | El nombre del archivo usa “usuario”. El contenido inspeccionado lista `sujeto`, `archivo`, `tipo`, `filas` y ruta Kaggle. No se vieron correos. | Requiere revisión humana del término “usuario” frente a “sujeto” y de los identificadores contenidos. |
| Visor, dashboard e informe HTML (`visor_interactivo_eeg.html`, `dashboard_eeg_neuroaction.html`, `informe_evaluacion_resultados.html` y copias en `reports/` / `figures/`) | Medio | Embeden tablas por sujeto, incluidas etiquetas `cano` y `villanueva`. GitHub Pages los hace consultables sin clonar el repo. | Requiere revisión humana antes de publicación permanente. No modificar HTML de resultados en esta preparación. |
| Figuras PNG en `figures/` (1 747 PNG en el repositorio, más 612 PNG de matrices de balanceo bajo `reports/balanceo/`) | Medio | Los nombres de archivo y carpetas incluyen identificadores de sujeto. Las imágenes son topomapas, scroll, espectros y matrices sobre BANDPOWER derivado. | Requiere revisión humana de identificadores en nombres de archivo. No se inspeccionó OCR de cada PNG. |
| Archivos XLSX en `reports/` (16 archivos) | No determinado por inspección binaria | Duplican reportes CSV. El detalle de artefactos es especialmente voluminoso. No se abrió el binario XLSX más allá de la correspondencia de nombres con CSV. | Requiere revisión humana antes de publicación permanente. No modificar. |
| Correos electrónicos | No encontrado | Búsqueda en `.csv`, `.html`, `.txt` y `.md`: 0 coincidencias con patrón de correo. | No se encontró evidencia de correos en los archivos de texto inspeccionados. |
| Documentos de identidad (CURP, RFC, DNI u homologables) | No encontrado | No aparecieron columnas ni tokens con esos nombres en los CSV de reporte inspeccionados. | Sin evidencia en esta inspección. No equivale a una auditoría completa de XLSX/PNG. |
| Información clínica individual nominativa | No encontrado como historia clínica | Los comentarios son de calidad de señal y modelado (“no confiable”, “problema de muestra”, “posible componente muscular/no fisiológico residual, no confirmado”). No hay campos de diagnóstico médico, edad, sexo ni historia clínica. | No declarar ausencia absoluta de riesgo clínico. El contenido es técnico sobre BANDPOWER. Revisión humana si el archivo permanente se presenta en contexto clínico. |
| EEG crudo, EOG, EMG, ECG | No presente en este repositorio | No hay `.edf`, `.bdf`, `.fif` ni series crudas. `reports/archivos_generados.csv` lista EDF generados en Kaggle, pero esos archivos no están aquí. | Este repo no publica EEG crudo. Eso no hace anónimos los identificadores ni las características derivadas que sí están. |
| Consentimiento, ética y origen de los datos fuente | No documentado aquí | Este repositorio no contiene consentimiento informado, dictamen ético, contrato de datos ni licencia del dataset fuente. | Requiere revisión humana antes de publicación permanente. No aplicar licencia automática a datos o resultados. |

## Hallazgos que no se encontraron

En la inspección de texto de CSV, HTML, TXT y Markdown:

- no hubo correos;
- no hubo rutas locales con nombres de cuenta personal;
- no hubo columnas explícitas de teléfono, CURP, RFC, DNI, edad, sexo o fecha de nacimiento.

Eso **no** permite afirmar que el conjunto sea anónimo.

## Revisión de licencias

Este repositorio **no tiene** `LICENSE` ni declaración de licencia en el README original. No se crea `LICENSE` en v0.9.0 porque hay incertidumbre sobre origen, consentimiento y derechos de datos y resultados.

### Distinción de componentes

| Componente | Qué hay en este repositorio | Evidencia de procedencia / derechos | Propuesta (no aplicada) |
| --- | --- | --- | --- |
| Código de interfaz | HTML/CSS/JS del visor, dashboard, `index.html` e informe | Generado/publicado desde Kaggle; un único commit en `main`. No hay código Python del pipeline. | **MIT** para el código de interfaz propio, si la autora confirma autoría y ausencia de restricciones. |
| Documentación | `README.md` y, a partir de v0.9.0, `docs/` y `CHANGELOG.md` | Redactada para este repositorio. | **CC BY 4.0**. |
| Resultados derivados | CSV, XLSX, PNG, HTML de evaluación, matrices, métricas | Derivados de un pipeline Kaggle (`run_20260902_145353`). El dataset fuente, el consentimiento y la licencia de origen **no están documentados aquí**. | **CC BY 4.0 solo si** no existen restricciones de origen, consentimiento o licencia. En caso contrario, no licenciar todavía o usar una nota de “all rights reserved / revisión pendiente”. |
| Datos fuente | CSV/TXT EEG originales **no están** en este repositorio; solo nombres y metadatos | Nombres de archivo y pares CSV/TXT aparecen en reportes. | No licenciar datos fuente desde este repo. Resolver en el dataset de origen. |
| Archivos de terceros | Plotly.js v2.35.2 embebido en `dashboard_eeg_neuroaction.html` (comentario de licencia MIT de Plotly, Inc.) | Licencia de terceros ya declarada en el propio bundle. | Conservar atribución. No relicenciar Plotly. El HTML contenedor propio puede ir bajo MIT si se confirma. |

### Propuesta resumida (no aplicada todavía)

- **Código:** MIT
- **Documentación:** CC BY 4.0
- **Resultados derivados:** CC BY 4.0 **solamente si** no existen restricciones de origen, consentimiento o licencia.

Hasta esa confirmación humana, **no se añade archivo `LICENSE`**.

## Qué no se hizo en esta revisión

- no se borró ningún archivo;
- no se modificaron CSV, XLSX, PNG ni HTML de resultados;
- no se creó tag, GitHub Release ni DOI;
- no se conectó Zenodo.
