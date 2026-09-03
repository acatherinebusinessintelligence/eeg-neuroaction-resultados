# Pipeline EEG NeuroAction (trazabilidad de salidas)

**Versión de preparación:** v0.9.0  
**Corrida registrada en los HTML y reportes:** `run_20260902_145353`  
**Ruta Kaggle observada:** `/kaggle/working/outputs/TESE_pruebas/run_20260902_145353`

Este documento describe solo lo verificable en este repositorio. No hay notebook ni script de pipeline versionado aquí.

**El repositorio de resultados no contiene el notebook o código fuente completo que produjo todos los outputs.** No se encontró una URL de kernel/notebook Kaggle en este árbol; no se inventa.

Esto es un **registro de resultados**, no un **pipeline totalmente reproducible**.

## Identificación de la corrida

| Campo | Evidencia |
| --- | --- |
| Identificador | `run_20260902_145353` |
| Fecha/hora inferida del nombre | 2026-09-02, 14:53:53 (convención del directorio; no hay reloj independiente en el repo) |
| Contexto de carpeta | `TESE_pruebas`. **TESE** = Tecnológico de Estudios Superiores de Ecatepec (México) |
| Sujetos en evaluación | 15 (`reports/evaluacion_sujetos.csv`) |
| ZIP de origen citado | `run_20260902_145353_resultados_TESE.zip` (~427 MB según `reports/verificacion_kaggle_salidas.csv`) — **no está** en este GitHub |

## Diagrama

```text
Fuente de datos
        ↓
Preprocesamiento
        ↓
Características BANDPOWER
        ↓
Evaluación / modelos
        ↓
Reportes
        ↓
Figuras
        ↓
Dashboard / visor
        ↓
Publicación GitHub / GitHub Pages
```

### Fuente de datos

Dataset **EEG 25-1** en Kaggle: <https://www.kaggle.com/datasets/griseldacortes/eeg-25-1/data>

Autores de esa ficha: Griselda Cortés Barrera; Alejandra Catherine Montaña Acevedo; Jesús Manuel Olivares Ceja; Jhacer Kharen Ruiz Garduño.

Los CSV/TXT de señal **no están** versionados en este GitHub; los reportes nombran 60 archivos fuente (pruebas `leftRight` y `pushPull`) y 8 CSV de acción individual. Esta ficha se usa como procedencia y autoría, no como notebook ejecutable.

### Preprocesamiento

Nombres de salida verificables: filtrado, outliers, variantes `noOutliers`, `cleanSmooth`, `sinArtefactosConservador`, `sinArtefactosEstricto`. El visor menciona “protocolo TESE” para outliers. No hay código, umbrales ni cuaderno. Notch, ICA, bandpass, Welch y FFT: **no documentados** como procedimientos aplicados.

`reports/archivos_generados.csv` lista EDF generados en Kaggle; **0 archivos EDF** en este GitHub.

### Características BANDPOWER

Verificable: canales AF3, AF4, F3, F4, F7, F8, FC5, FC6, O1, O2, P7, P8, T7, T8; bandas theta, alpha, betal/betaL, betah/betaH, gamma. Rangos en Hz: **Rango no documentado.** Tipo (absoluta/relativa/log/PSD): no consta más allá de “característica derivada por canal y banda”.

El detalle de artefactos guarda un `valor` por `fila` × canal × banda, con `nivel_confirmacion = sospecha_sobre_bandpower`. No es EEG crudo.

### Evaluación / modelos

Verificable: 7 clasificadores en `reports/resultados_modelos_global.csv`; 168 filas; `cv = bloques`. Comparación de 6 estrategias de balanceo. Hiperparámetros: **No documentados.** Detalle: [MODELOS.md](MODELOS.md).

### Reportes

Verificable y presente: familia CSV/XLSX bajo `reports/` (evaluación, filtrado, artefactos, modelos, balanceo, verificación Kaggle). Inventario: `docs/RESULTADOS.md`.

### Figuras

Verificable: scroll, spectral, topomapas, resumen, exploración master, matrices de confusión, 612 PNG de balanceo. El visor declara 528 figuras generadas en métricas globales; el árbol Git contiene copias adicionales por carpeta.

### Dashboard / visor

Verificable: `index.html`, `visor_interactivo_eeg.html`, `dashboard_eeg_neuroaction.html`, `informe_evaluacion_resultados.html`, con copias en `reports/` y `figures/`.

GitHub Pages: `https://acatherinebusinessintelligence.github.io/eeg-neuroaction-resultados/` (rama `main`, raíz).

No hay Actions en este repositorio que regeneren esas páginas. La conexión Kaggle → GitHub no está automatizada aquí.

## Outputs principales de la corrida (presentes en GitHub)

- Visor, dashboard e informe HTML
- Evaluación de 15 sujetos
- 122 279 filas de artefactos sospechados (derivados)
- Resultados de modelos y comparación de limpieza/balanceo
- Figuras PNG por sujeto y por tipo

## Outputs citados y ausentes

- EDF por sujeto/variante
- `*_Comparativa_Modelos_Final.xlsx` por sujeto
- ZIP `run_20260902_145353_resultados_TESE.zip` y ZIP “por usuario”
- Código / notebook de Kaggle

---

## Nivel de reproducibilidad

**Resultados preservados, con documentación parcial.** No es un pipeline completamente reproducible. Ver [metodologia.md](metodologia.md#nivel-de-reproducibilidad).

### Corrida reproducida / registrada

**`run_20260902_145353`**

| Distinción | Aplicación a esta corrida |
| --- | --- |
| Registro de resultados | **Sí.** HTML, reportes y figuras de GitHub corresponden a esta corrida. |
| Pipeline totalmente reproducible | **No.** Falta el código fuente en este repositorio. |

#### Qué archivos pertenecen a esa corrida

Evidencia de pertenencia: el visor, el dashboard, el informe y `reports/index_kaggle.html` imprimen la ruta `/kaggle/working/outputs/TESE_pruebas/run_20260902_145353`. `reports/verificacion_kaggle_salidas.csv` y `reports/validacion_salidas_pipeline.csv` listan artefactos de esa ruta (reportes, figuras, ZIP).

Presentes en este GitHub (mismo lote, reorganizados en la raíz / `reports/` / `figures/`):

- visor, dashboard, informe HTML (y copias);
- familia CSV/XLSX de `reports/` (evaluación, filtrado, artefactos, modelos, balanceo, inventario, verificación);
- `reports/resumen_ejecutivo_resultados.txt`;
- PNG en `figures/` y matrices de `reports/balanceo/`.

Citados para esa corrida y **ausentes** de GitHub:

- ZIP `run_20260902_145353_resultados_TESE.zip` (~427 MB) y ZIP “por usuario”;
- directorio `processed_data/EDF/` (`*.edf`);
- `*_Comparativa_Modelos_Final.xlsx` por sujeto;
- notebook/script.

#### Timestamps de la corrida (pipeline)

El identificador `20260902_145353` es convención de directorio (2026-09-02, 14:53:53). No hay reloj independiente en el repo.

Los Unix de **sesión de sujeto** están en `reports/diagnostico_tiempos_csv_txt.csv` (13 códigos numéricos; no `cano`/`villanueva`) y datan capturas, no el reloj del pipeline.

#### Resultados, figuras, sujetos, modelos

- 15 sujetos en `reports/evaluacion_sujetos.csv`.
- Dashboard de esa corrida (texto embebido): 16 578 registros originales, 13 561 `noOutliers`, retención media 82.62 %, 3 009 outliers removidos, 122 279 artefactos sospechados.
- Figuras: visor declara 528 generadas; el árbol Git incluye copias y 612 PNG de balanceo.
- Modelos: 7 clasificadores en resultados globales; 6 estrategias de balanceo. Hiperparámetros no documentados.

Matriz de evidencia: [EVIDENCIA_METODOLOGICA.md](EVIDENCIA_METODOLOGICA.md).
