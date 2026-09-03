# Revisión para publicación permanente

Documento de preparación para una futura versión estable y un posible archivo citable en Zenodo.

**Versión:** v1.0.0  
**Estado:** APTO PARA RELEASE CANDIDATE v1.0.0 CON LIMITACIONES DOCUMENTADAS.  
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
| `reports/diagnostico_tiempos_csv_txt.csv` | Riesgo bajo/moderado sujeto a contexto temporal | Incluye Unix de sesión (`timestamp_min` / `timestamp_max` y equivalentes TXT), entre 2026-05-19 y 2026-06-08 (UTC). No hay evidencia en este repositorio de que permitan reidentificación **directa**. Datán capturas por código de sujeto numérico. **Decisión: CONSERVAR.** | Conservar valores. No modificar. Ver sección de timestamps. |
| Columnas `ruta` / `ruta_archivo` en varios CSV (`reports/archivos_generados.csv`, `reports/reporte_figuras_generadas.csv`, `reports/resumen_exportacion_por_usuario.csv`, `reports/validacion_salidas_pipeline.csv`, `reports/verificacion_kaggle_salidas.csv`) | Bajo en lo personal | Las rutas encontradas son de Kaggle (`/kaggle/working/outputs/TESE_pruebas/run_20260902_145353/...`). **TESE** = Tecnológico de Estudios Superiores de Ecatepec (México). No se encontraron rutas locales con nombres personales. | Conservar. TESE identifica la institución de la corrida, no un laboratorio con acrónimo inventado. |
| `reports/resumen_exportacion_por_usuario.csv` | Medio | El nombre del archivo usa “usuario”. El contenido inspeccionado lista `sujeto`, `archivo`, `tipo`, `filas` y ruta Kaggle. No se vieron correos. | Requiere revisión humana del término “usuario” frente a “sujeto” y de los identificadores contenidos. |
| Visor, dashboard e informe HTML (`visor_interactivo_eeg.html`, `dashboard_eeg_neuroaction.html`, `informe_evaluacion_resultados.html` y copias en `reports/` / `figures/`) | Bajo / controlado en IDs; residual en embebido | Embeden tablas por código de sujeto, incluidas las etiquetas `cano` y `villanueva` (códigos institucionales pseudonimizados). GitHub Pages los hace consultables. | No modificar HTML de resultados. No presentar códigos como nombres reales. |
| Figuras PNG en `figures/` (1 747 PNG en el repositorio, más 612 PNG de matrices de balanceo bajo `reports/balanceo/`) | Bajo / controlado en IDs | Los nombres de archivo y carpetas incluyen códigos de sujeto, no nombres reales confirmados. | Conservar. OCR de cada PNG no realizado. |
| Consentimiento, ética y origen de los datos fuente | Parcialmente resuelto | Resultados redistribuibles. Fuente: dataset Kaggle [EEG 25-1](https://www.kaggle.com/datasets/griseldacortes/eeg-25-1/data). Autores documentados en esa ficha. No hay dictamen ético versionado aquí. | Conservar atribución a autores, TESE cuando corresponda y el laboratorio descrito en la ficha. No reidentificar. |
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

## Autoría y procedencia

Se distinguen capas. La autoría del recurso citable no implica titularidad conjunta del código fuente.

- **Código:** MIT; copyright (c) 2026 Alejandra Catherine Montaña Acevedo (`LICENSE-CODE`).
- **Dataset fuente EEG 25-1:** ficha Kaggle <https://www.kaggle.com/datasets/griseldacortes/eeg-25-1/data>. Autores (mismo orden): Griselda Cortés Barrera; Alejandra Catherine Montaña Acevedo; Jesús Manuel Olivares Ceja; Jhacer Kharen Ruiz Garduño.
- **Resultados derivados:** atribución a esos cuatro autores (`LICENSE-RESULTS.md`).
- **Recurso citable:** los mismos cuatro autores en `CITATION.cff` para *EEG NeuroAction: resultados, análisis y visualización interactiva*.

Afiliaciones:

1. Griselda Cortés Barrera — Tecnológico de Estudios Superiores de Ecatepec (TESE), México
2. Alejandra Catherine Montaña Acevedo — Coinvestigadora, Corporación Universitaria Minuto de Dios (Uniminuto). Encargada de la automatización del proceso de datos: transformación, verificación con inteligencia artificial y desarrollo de software; código base en Kaggle y GitHub.
3. Jesús Manuel Olivares Ceja — Apoyo en proyecto
4. Jhacer Kharen Ruiz Garduño — Apoyo en proyecto

Los ítems 3–4 son roles confirmados por Alejandra Catherine Montaña Acevedo, no nombres de institución. “Apoyo en proyecto” no implica titularidad del código. El ítem 2 combina afiliación institucional (Uniminuto) y rol técnico, ambos confirmados por la autora.

**TESE** = Tecnológico de Estudios Superiores de Ecatepec. País: México.

Laboratorio: **National Laboratory in Artificial Intelligence and Data Science**. Denominación tomada de la biografía pública de Griselda Cortés Barrera en la ficha Kaggle del dataset. No se traduce a un nombre institucional oficial en español ni se inventa un acrónimo. No se afirma propiedad institucional más allá de lo documentado.

## Dataset fuente

- **Dataset:** EEG 25-1
- **Fuente:** Kaggle
- **URL:** <https://www.kaggle.com/datasets/griseldacortes/eeg-25-1/data>
- **Autores:** Griselda Cortés Barrera; Alejandra Catherine Montaña Acevedo; Jesús Manuel Olivares Ceja; Jhacer Kharen Ruiz Garduño

Esta ficha se utiliza como fuente de procedencia y autoría del dataset/proyecto, no como titularidad conjunta del código.

## Condiciones de redistribución

Los resultados derivados pueden redistribuirse con atribución adecuada a:

- los autores del dataset/proyecto (lista anterior);
- Tecnológico de Estudios Superiores de Ecatepec (TESE), México, cuando corresponda;
- Corporación Universitaria Minuto de Dios (Uniminuto), cuando corresponda (afiliación documentada de Alejandra Catherine Montaña Acevedo como coinvestigadora);
- el laboratorio descrito públicamente como National Laboratory in Artificial Intelligence and Data Science (con la salvedad de procedencia de esa denominación).

No existe autorización para reconstruir identidades ni para presentar los códigos de sujeto como nombres reales. `cano` y `villanueva` son códigos institucionales pseudonimizados (riesgo **Bajo / controlado**). Este repositorio **no declara anonimato absoluto**.

## Revisión de licencias

Esquema definido (archivos en la raíz del repositorio):

- **Código:** MIT — [`LICENSE-CODE`](../LICENSE-CODE)
- **Documentación:** CC BY 4.0 — [`LICENSE-DOCS.md`](../LICENSE-DOCS.md)
- **Resultados derivados:** CC BY 4.0 — [`LICENSE-RESULTS.md`](../LICENSE-RESULTS.md)

Texto oficial CC BY 4.0: <https://creativecommons.org/licenses/by/4.0/>

### Distinción de componentes

| Componente | Qué hay en este repositorio | Licencia aplicada |
| --- | --- | --- |
| Código de interfaz | HTML/CSS/JS del visor, dashboard, `index.html` e informe | MIT (`LICENSE-CODE`). Copyright (c) 2026 Alejandra Catherine Montaña Acevedo. Los demás autores del dataset **no** se declaran titulares de este código. |
| Documentación | `README.md`, `CHANGELOG.md`, `docs/` | CC BY 4.0 (`LICENSE-DOCS.md`). Preparada y organizada por Alejandra Catherine Montaña Acevedo, incorporando procedencia de EEG 25-1. No altera derechos del dataset fuente. |
| Resultados derivados | CSV, XLSX, PNG, HTML de evaluación, matrices, métricas | CC BY 4.0 (`LICENSE-RESULTS.md`). Atribución a los cuatro autores del proyecto EEG 25-1, TESE cuando corresponda y el laboratorio descrito públicamente. No transfiere copyright entre autores. No otorga derechos adicionales sobre datos fuente de terceros. No autoriza reidentificación. No implica titularidad conjunta del código. |
| Datos fuente | CSV/TXT EEG originales **no están** en este repositorio | Fuera de estas licencias. |
| Archivos de terceros | Plotly.js v2.35.2 embebido (MIT de Plotly, Inc.) | Conservar atribución. No relicenciar Plotly. |

**Advertencia:** no hay un único archivo `LICENSE` que cubra todo el árbol. Usar los tres archivos según el tipo de material. No se afirma propiedad institucional más allá de lo documentado. El campo `license: MIT` de `CITATION.cff` identifica la licencia del software de interfaz; no afirma que los cuatro autores del recurso sean titulares del código.

## Fechas y timestamps

Archivo de sesión: `reports/diagnostico_tiempos_csv_txt.csv` (26 filas; 13 sujetos numéricos; **no** incluye `cano` ni `villanueva`).

### Campos y granularidad

| Campo | Granularidad | Relación con sujetos |
| --- | --- | --- |
| `timestamp_min`, `timestamp_max` | Unix (segundos con fracción) de sesión CSV | 13 códigos numéricos; una o dos pruebas (`leftRight` / `pushPull`) por sujeto en este archivo |
| `txt_time_min`, `txt_time_max` | Unix de eventos TXT | Mismos 13 códigos |
| `duracion_csv_segundos`, `duracion_txt_segundos` | Segundos relativos | Útiles para comprobar duración **sin** calendario |
| `diferencia_inicio_csv_txt`, `diferencia_fin_csv_txt` | Segundos de desfase | Alineación CSV–TXT |
| `filas_csv`, `eventos_txt`, `conteo_clases` | Conteos | No son reloj |
| `run_20260902_145353` | Identificador de corrida | Reloj de *pipeline*, no de participante |

Convertidos a UTC, los Unix de calendario caen entre **2026-05-19 y 2026-06-08**. Datán capturas; no son fechas de nacimiento.

El detalle de artefactos **no** tiene columnas de tiempo.

### Utilidad científica

Las columnas relativas permiten verificar duración y alineación CSV–TXT. Los Unix absolutos documentan cuándo se dató cada captura de los 13 códigos numéricos. No se usaron para recalcular BANDPOWER ni modelos.

### Riesgo de reidentificación

Los identificadores ya están pseudonimizados. No se encontró vínculo directo con identidades (nombres reales, correos, documentos). El riesgo residual es **contextual**: alguien que ya sepa quién participó en qué día podría cruzar el calendario con un código numérico. `cano` y `villanueva` no están en este archivo.

### Decisión explícita: CONSERVAR

**CONSERVAR** los timestamps tal como están. No se modifican los valores.

Justificación:

1. No hay evidencia de reidentificación directa en este repositorio.
2. Los IDs no se presentan como nombres reales; está prohibido reidentificar.
3. Las duraciones y desfases son necesarias para interpretar el diagnóstico CSV–TXT.
4. Generalizar o excluir los Unix absolutos reduciría el calendario de captura sin cambiar métricas, pero no es exigido por la evidencia de riesgo **directo** hallada.
5. EXCLUIR el archivo entero perdería la única tabla de alineación temporal.

No se elige GENERALIZAR ni EXCLUIR en esta versión. Una generalización futura (solo duraciones) seguiría siendo posible sin tocar BANDPOWER ni métricas de modelos.

| Clase | Recurso | Clasificación |
| --- | --- | --- |
| A. Necesarias para trazabilidad de resultados | `duracion_csv_segundos`, `duracion_txt_segundos`, `diferencia_inicio_csv_txt`, `diferencia_fin_csv_txt`; `filas_csv`, `eventos_txt`, `conteo_clases` | CONSERVAR |
| A. Necesarias para trazabilidad de resultados | Identificador de corrida `run_20260902_145353` | CONSERVAR |
| B. Calendario de captura | `timestamp_min`, `timestamp_max`, `txt_time_min`, `txt_time_max` | CONSERVAR (decisión cerrada; riesgo residual contextual) |
| C. Inciertas | Si algún PNG o XLSX incrusta la misma marca temporal (no inspeccionado por OCR/binario) | Sin evidencia de columnas de tiempo en PNG; no se modifican archivos de resultados |

## CRÍTICO PARA PUBLICACIÓN vs. DESEABLE PARA REPRODUCCIÓN COMPLETA

Este repositorio es un **archivo de resultados**, no el estudio experimental completo. No es obligatorio tener todos los detalles del estudio original para publicar resultados **si se declara su ausencia**.

### Crítico para publicación (archivo de resultados)

- procedencia (dataset Kaggle EEG 25-1 y URL);
- autoría (cuatro autores de la ficha);
- privacidad (códigos pseudonimizados; no reidentificación; timestamps CONSERVAR documentado);
- derechos de redistribución de resultados derivados;
- descripción clara de **qué son** los resultados (características BANDPOWER derivadas, no EEG crudo ni qEEG clínico);
- limitaciones y nivel de reproducibilidad;
- licencias (MIT código; CC BY 4.0 docs y resultados).

Estado de esos ítems: **cumplidos en documentación v1.0.0 RC**, con laboratorio solo parcialmente nombrado (biografía Kaggle). Afiliación de Alejandra Catherine Montaña Acevedo: coinvestigadora, Corporación Universitaria Minuto de Dios (Uniminuto), más rol técnico. Jesús Manuel Olivares Ceja y Jhacer Kharen Ruiz Garduño: apoyo en proyecto.

### Deseable para reproducción completa (no necesariamente bloqueante)

- hiperparámetros completos;
- notebook original y URL de kernel;
- protocolo experimental exhaustivo;
- fs, referencia, dispositivo por sujeto, rangos Hz de BANDPOWER;
- umbrales del protocolo de outliers.

Estos faltantes están **declarados** en [EVIDENCIA_METODOLOGICA.md](EVIDENCIA_METODOLOGICA.md), [MODELOS.md](MODELOS.md) y [metodologia.md](metodologia.md).

## Criterios previos a publicación permanente / Zenodo

- [x] Identificadores revisados
- [x] Pseudonimización confirmada
- [x] Redistribución autorizada
- [x] Autores documentados
- [x] Fuente Kaggle documentada
- [x] Licencias definidas
- [x] TESE identificado
- [~] Laboratorio identificado parcialmente
- [x] Timestamps revisados
- [x] Protocolo mínimo documentado con limitaciones
- [x] Adquisición EEG documentada con limitaciones
- [x] BANDPOWER documentado con limitaciones
- [x] Modelos documentados
- [x] Pipeline documentado con limitaciones
- [x] Alcance del release definido
- [x] CITATION.cff validado (`version: 1.0.0`, sin DOI, sin `date-released`)
- [x] Detalle de artefactos (122 279 filas): **INCLUIR** en v1.0.0 (derivados; códigos pseudonimizados)
- [ ] Release candidate revisada humanamente
- [ ] GitHub Release creada
- [ ] Zenodo archivado
- [ ] DOI incorporado

### Decisión de release readiness

**APTO PARA RELEASE CANDIDATE v1.0.0 CON LIMITACIONES DOCUMENTADAS.**

La versión documental es **1.0.0**. No se crea tag, GitHub Release, Zenodo ni DOI en esta pasada.

Alcance: [RELEASE_SCOPE_v1.0.0.md](RELEASE_SCOPE_v1.0.0.md). Notas: [RELEASE_NOTES_v1.0.0.md](RELEASE_NOTES_v1.0.0.md).

Pendiente para una publicación posterior (no ejecutado aquí):

1. Revisión humana de la Release Candidate.
2. Crear tag `v1.0.0` y GitHub Release **solo cuando se decida publicar**.
3. Archivar en Zenodo e incorporar DOI **solo cuando exista**.
4. Opcional: notebook/URL si aparecen con evidencia verificable.

Estado actual:

**APTO PARA RELEASE CANDIDATE v1.0.0 CON LIMITACIONES DOCUMENTADAS.** Versión **1.0.0**. Tag / GitHub Release / Zenodo / DOI: no creados.

Esto es una decisión de publicación, no una evaluación científica de los resultados.

El mapa local `docs/MAPA_PSEUDONIMIZACION_LOCAL.md` permanece gitignored y **no** debe ir a Zenodo. `cano` y `villanueva` no requieren recodificación adicional: ya son códigos institucionales pseudonimizados.

## Qué no se hizo en esta revisión

- no se borró ningún archivo;
- no se modificaron CSV, XLSX, PNG ni HTML de resultados;
- no se recodificaron identificadores;
- no se alteraron timestamps (decisión CONSERVAR);
- no se creó tag, GitHub Release ni DOI;
- no se conectó Zenodo;
- no se añadió `date-released` ni badge Zenodo;
- no se inventaron ORCID, correos, URL de notebook, rangos Hz, hiperparámetros, acrónimo de laboratorio ni un nombre institucional oficial en español para el laboratorio.
