# Revisión para publicación permanente

Documento de preparación para una futura versión estable y un posible archivo citable en Zenodo.

**Versión de preparación:** v0.9.0  
**Estado:** próximo a apto para depósito permanente (no plenamente apto).  
**Fecha de revisión:** 2026-09-03  
**Alcance:** inspección de nombres de archivo, encabezados CSV, filas de muestra y texto de reportes/HTML. No se modificó ningún resultado computacional.

Este repositorio **ya es público** en GitHub y se sirve por GitHub Pages:

- Código/resultados: <https://github.com/acatherinebusinessintelligence/eeg-neuroaction-resultados>
- Visor publicado: <https://acatherinebusinessintelligence.github.io/eeg-neuroaction-resultados/>

La revisión siguiente **no declara anonimato absoluto**. Los códigos de sujeto no deben presentarse como nombres reales ni usarse para reidentificar participantes.

## Criterio

- Solo se registra evidencia realmente encontrada.
- No se eliminó ni se reescribió ningún archivo de resultados.
- Si la privacidad no puede determinarse por estructura o contenido, se indica: *Requiere revisión humana antes de publicación permanente.*

## Tabla de revisión

| Recurso | Riesgo aparente | Observación | Acción recomendada |
| --- | --- | --- | --- |
| Identificadores de sujeto `cano` y `villanueva` (carpetas `figures/cano`, `figures/villanueva`; columnas `sujeto` en CSV/HTML) | Bajo / controlado | Son **códigos institucionales ya pseudonimizados**. No deben interpretarse como nombres personales. Su uso público está autorizado en el contexto de redistribución de resultados. No existe autorización para intentar reidentificar participantes. Clasificación basada en confirmación de la autora de que se trata de códigos institucionales pseudonimizados. | Conservar como códigos. No presentarlos como apellidos reales. No intentar reidentificación. |
| Nombres de archivo fuente `derecha 1ra_Cano 1.csv`, `izquierda 1ra_Cano 1.csv`, `empujar 1ra_Cano 1.csv`, `jalar 1ra_Cano 1.csv`, `derecha 2da_Villanueva 1.csv`, `izquierda 2da_Villanueva 1.csv`, `empujar 2da_Villanueva 1.csv`, `jalar 2da_Villanueva 1.csv` | Bajo / controlado | Son formas de aparición de los mismos códigos institucionales `cano` / `villanueva` (capitalización distinta). Clasificación basada en confirmación de la autora de que se trata de códigos institucionales pseudonimizados. | Conservar. No tratarlos como nombres reales ni como base para reidentificar. |
| Códigos de sujeto numéricos (`211260561`, `212260563`, `212260567`, `212260569`, `212260666`, `212260668`, `212260672`, `222260671`, `22260552`, `231260558`, `252260554`, `252260556`, `252260670`) | Medio, no determinado | Identificadores estables. No deben presentarse como nombres reales. Este repositorio aún no documenta su significado formal (matrícula, código interno u otro). | No afirmar anonimato absoluto. No reconstruir identidades. |
| `reports/evaluacion_sujetos.csv` e `informe_evaluacion_resultados.html` | Medio | Contienen métricas, alertas de artefactos y comentarios técnicos por sujeto. No se encontraron correos, documentos de identidad ni diagnósticos clínicos nominativos. Los IDs `cano` y `villanueva` son códigos institucionales pseudonimizados (confirmación de la autora). | Conservar para trazabilidad. No reidentificar. |
| `reports/reporte_artefactos_sospechados_detalle.csv` y `.xlsx` | Medio-alto | 122 279 filas con `sujeto`, `archivo`, `fila`, `canal`, `banda`, `valor` y tipo de artefacto sospechado. Son características BANDPOWER derivadas, no EEG crudo. Siguen siendo datos biométricos derivados por código de sujeto. El XLSX pesa ~8,2 MB. | Redistribución de resultados autorizada; no declarar anonimato absoluto. Valorar si el detalle fila a fila es necesario en Zenodo o si basta el resumen. |
| `reports/diagnostico_tiempos_csv_txt.csv` | Riesgo bajo/moderado sujeto a contexto temporal | Incluye Unix de sesión (`timestamp_min` / `timestamp_max` y equivalentes TXT), entre 2026-05-19 y 2026-06-08 (UTC). No hay evidencia en este repositorio de que permitan reidentificación **directa**. Datán capturas por código de sujeto. | Conservar por ahora (alineación CSV–TXT). Revisión definitiva pendiente. No eliminar automáticamente. Ver sección de timestamps. |
| Columnas `ruta` / `ruta_archivo` en varios CSV (`reports/archivos_generados.csv`, `reports/reporte_figuras_generadas.csv`, `reports/resumen_exportacion_por_usuario.csv`, `reports/validacion_salidas_pipeline.csv`, `reports/verificacion_kaggle_salidas.csv`) | Bajo en lo personal; medio en procedencia | Las rutas encontradas son de Kaggle (`/kaggle/working/outputs/TESE_pruebas/run_20260902_145353/...`). No se encontraron rutas `C:\Users\...`, `/Users/...` ni OneDrive con nombres personales. El segmento `TESE_pruebas` nombra un contexto de corrida no documentado en este repositorio. | No se hallaron rutas locales con nombres personales. Documentar el significado de `TESE_pruebas` antes de archivar. Requiere revisión humana del contexto institucional. |
| `reports/resumen_exportacion_por_usuario.csv` | Medio | El nombre del archivo usa “usuario”. El contenido inspeccionado lista `sujeto`, `archivo`, `tipo`, `filas` y ruta Kaggle. No se vieron correos. | Requiere revisión humana del término “usuario” frente a “sujeto” y de los identificadores contenidos. |
| Visor, dashboard e informe HTML (`visor_interactivo_eeg.html`, `dashboard_eeg_neuroaction.html`, `informe_evaluacion_resultados.html` y copias en `reports/` / `figures/`) | Bajo / controlado en IDs; residual en embebido | Embeden tablas por código de sujeto, incluidas las etiquetas `cano` y `villanueva` (códigos institucionales pseudonimizados). GitHub Pages los hace consultables. | No modificar HTML de resultados. No presentar códigos como nombres reales. |
| Figuras PNG en `figures/` (1 747 PNG en el repositorio, más 612 PNG de matrices de balanceo bajo `reports/balanceo/`) | Bajo / controlado en IDs | Los nombres de archivo y carpetas incluyen códigos de sujeto, no nombres reales confirmados. | Conservar. OCR de cada PNG no realizado. |
| Consentimiento, ética y origen de los datos fuente | Parcialmente resuelto | La autora confirma que **los resultados pueden redistribuirse** con atribución al laboratorio. El nombre formal del laboratorio no está en este repositorio. No hay dictamen ético versionado aquí. | Incorporar el nombre formal del laboratorio. No inventarlo. Redistribución de resultados autorizada; no reidentificar. |
| Archivos XLSX en `reports/` (16 archivos) | No determinado por inspección binaria | Duplican reportes CSV. El detalle de artefactos es especialmente voluminoso. No se abrió el binario XLSX más allá de la correspondencia de nombres con CSV. | Requiere revisión humana antes de publicación permanente. No modificar. |
| Correos electrónicos | No encontrado | Búsqueda en `.csv`, `.html`, `.txt` y `.md`: 0 coincidencias con patrón de correo. | No se encontró evidencia de correos en los archivos de texto inspeccionados. |
| Documentos de identidad (CURP, RFC, DNI u homologables) | No encontrado | No aparecieron columnas ni tokens con esos nombres en los CSV de reporte inspeccionados. | Sin evidencia en esta inspección. No equivale a una auditoría completa de XLSX/PNG. |
| Información clínica individual nominativa | No encontrado como historia clínica | Los comentarios son de calidad de señal y modelado (“no confiable”, “problema de muestra”, “posible componente muscular/no fisiológico residual, no confirmado”). No hay campos de diagnóstico médico, edad, sexo ni historia clínica. | No declarar ausencia absoluta de riesgo clínico. El contenido es técnico sobre BANDPOWER. Revisión humana si el archivo permanente se presenta en contexto clínico. |
| EEG crudo, EOG, EMG, ECG | No presente en este repositorio | No hay `.edf`, `.bdf`, `.fif` ni series crudas. `reports/archivos_generados.csv` lista EDF generados en Kaggle, pero esos archivos no están aquí. | Este repo no publica EEG crudo. Eso no implica anonimato absoluto de los resultados derivados. |

## Hallazgos que no se encontraron

En la inspección de texto de CSV, HTML, TXT y Markdown:

- no hubo correos;
- no hubo rutas locales con nombres de cuenta personal;
- no hubo columnas explícitas de teléfono, CURP, RFC, DNI, edad, sexo o fecha de nacimiento.

Eso **no** permite afirmar anonimato absoluto.

## Condiciones de redistribución

Los resultados derivados pueden redistribuirse con atribución adecuada a la autora y al laboratorio que originó o facilitó el trabajo experimental.

Nombre formal del laboratorio: pendiente de incorporar.

No existe autorización para reconstruir identidades ni para presentar los códigos de sujeto como nombres reales.

## Revisión de licencias

Esquema definido (archivos en la raíz del repositorio):

- **Código:** MIT — [`LICENSE-CODE`](../LICENSE-CODE)
- **Documentación:** CC BY 4.0 — [`LICENSE-DOCS.md`](../LICENSE-DOCS.md)
- **Resultados derivados:** CC BY 4.0 — [`LICENSE-RESULTS.md`](../LICENSE-RESULTS.md)

Texto oficial CC BY 4.0: <https://creativecommons.org/licenses/by/4.0/>

### Distinción de componentes

| Componente | Qué hay en este repositorio | Licencia aplicada |
| --- | --- | --- |
| Código de interfaz | HTML/CSS/JS del visor, dashboard, `index.html` e informe | MIT (`LICENSE-CODE`). Titular: Alejandra Catherine Montaña Acevedo, 2026. |
| Documentación | `README.md`, `CHANGELOG.md`, `docs/` | CC BY 4.0 (`LICENSE-DOCS.md`). |
| Resultados derivados | CSV, XLSX, PNG, HTML de evaluación, matrices, métricas | CC BY 4.0 (`LICENSE-RESULTS.md`). Redistribución autorizada por la autora. Requiere atribución a la autora y al laboratorio correspondiente. No otorga derechos adicionales sobre datos fuente de terceros. No autoriza reidentificación. |
| Datos fuente | CSV/TXT EEG originales **no están** en este repositorio | Fuera de estas licencias. |
| Archivos de terceros | Plotly.js v2.35.2 embebido (MIT de Plotly, Inc.) | Conservar atribución. No relicenciar Plotly. |

**Advertencia:** no hay licencia definitiva única tipo `LICENSE` que cubra todo el árbol. Usar los tres archivos según el tipo de material. El nombre formal del laboratorio sigue pendiente.

## Fechas y timestamps

Archivo de sesión: `reports/diagnostico_tiempos_csv_txt.csv` (26 filas; 13 sujetos numéricos; **no** incluye `cano` ni `villanueva`).

Columnas Unix de calendario: `timestamp_min`, `timestamp_max`, `txt_time_min`, `txt_time_max`. Convertidas a UTC caen entre **2026-05-19 y 2026-06-08**. Datán capturas por sujeto; no son fechas de nacimiento.

Columnas relativas (duración y desfase CSV–TXT): `duracion_csv_segundos`, `duracion_txt_segundos`, `diferencia_inicio_csv_txt`, `diferencia_fin_csv_txt`.

El identificador de corrida `run_20260902_145353` aparece en HTML y rutas Kaggle (reloj de *pipeline*, no de participante).

El detalle de artefactos **no** tiene columnas de tiempo.

No se modificaron fechas en esta auditoría. **No se eliminan automáticamente.**

**Clasificación de riesgo residual:** riesgo bajo/moderado sujeto a contexto temporal.

No hay evidencia en este repositorio de que esos Unix permitan reidentificación **directa** (no hay nombres reales, correos ni documentos de identidad asociados). El riesgo residual es contextual: alguien que ya sepa quién participó en qué día podría cruzar el calendario de sesión con un código numérico. Por eso se conservan (sirven para comprobar duración y alineación CSV–TXT) y podrían generalizarse más adelante si se decide no publicar fechas de calendario, sin cambiar métricas de modelos.

| Clase | Recurso | Clasificación |
| --- | --- | --- |
| A. Necesarias para reproducibilidad | `duracion_csv_segundos`, `duracion_txt_segundos`, `diferencia_inicio_csv_txt`, `diferencia_fin_csv_txt`; `filas_csv`, `eventos_txt`, `conteo_clases` | Permiten comprobar alineación CSV–TXT y duración de registro **sin** fecha de calendario. Se conservan. |
| A. Necesarias para reproducibilidad | Identificador de corrida `run_20260902_145353` | Nombra el lote computacional. No es un ID de sujeto. Se conserva. |
| B. Conservadas; no imprescindibles para citar modelos | `timestamp_min`, `timestamp_max`, `txt_time_min`, `txt_time_max` como Unix absoluto | Riesgo bajo/moderado sujeto a contexto temporal. Se conservan en esta versión. Revisión definitiva pendiente. Podrían generalizarse (p. ej. solo duraciones) sin alterar BANDPOWER ni métricas. |
| C. Inciertas | Si algún PNG o XLSX incrusta la misma marca temporal (no inspeccionado por OCR/binario) | Revisión definitiva pendiente. |

## Criterios previos a Zenodo

Debe cumplirse:

- [x] Identificadores revisados
- [x] Pseudonimización confirmada
- [x] Redistribución autorizada
- [x] Licencia de resultados definida
- [ ] Nombre formal del laboratorio incorporado
- [ ] Timestamps revisados definitivamente
- [ ] Metodología mínima completada
- [ ] Archivos de release revisados
- [x] CITATION.cff validado
- [ ] Release candidate revisada

Estado actual:

**Próximo a apto para depósito permanente.**

No está todavía plenamente apto: faltan el nombre formal del laboratorio, la revisión definitiva de timestamps, metodología experimental mínima y la revisión de una release candidate. `CITATION.cff` está validado (schema 1.2.0, sin DOI).

Esto es una decisión de publicación, no una evaluación científica de los resultados.

El mapa local `docs/MAPA_PSEUDONIMIZACION_LOCAL.md` permanece gitignored y **no** debe ir a Zenodo. `cano` y `villanueva` no requieren recodificación adicional: ya son códigos institucionales pseudonimizados.

## Qué no se hizo en esta revisión

- no se borró ningún archivo;
- no se modificaron CSV, XLSX, PNG ni HTML de resultados;
- no se recodificaron identificadores (no era necesario para `cano`/`villanueva`);
- no se creó tag, GitHub Release ni DOI;
- no se hizo push;
- no se conectó Zenodo;
- no se inventó el nombre del laboratorio.
