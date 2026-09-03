# Pipeline EEG NeuroAction (trazabilidad de salidas)

**Versión de preparación:** v0.9.0  
**Corrida registrada en los HTML y reportes:** `run_20260902_145353`  
**Ruta Kaggle observada:** `/kaggle/working/outputs/TESE_pruebas/run_20260902_145353`

Este documento describe solo lo verificable en este repositorio. No hay notebook ni script de pipeline versionado aquí.

## Identificación de la corrida

| Campo | Evidencia |
| --- | --- |
| Identificador | `run_20260902_145353` |
| Fecha/hora inferida del nombre | 2026-09-02, 14:53:53 (convención del directorio; no hay reloj independiente en el repo) |
| Contexto de carpeta | `TESE_pruebas` (significado no documentado aquí) |
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

Pendiente de documentación.

Lo verificable: los reportes *nombran* 60 archivos fuente CSV/TXT (pruebas `leftRight` y `pushPull`) y 8 CSV de acción individual en español. Esos archivos **no están** en este repositorio. El README indica publicación desde Kaggle. No hay URL de dataset ni licencia de origen en este repo.

### Preprocesamiento

Pendiente de documentación.

Lo verificable por nombres de salida: filtrado, outliers, variantes `noOutliers`, `cleanSmooth`, `sinArtefactosConservador`, `sinArtefactosEstricto`. El visor menciona “protocolo TESE” para outliers. No hay código, umbrales ni cuaderno.

`reports/archivos_generados.csv` lista EDF generados en Kaggle; **0 archivos EDF** en este GitHub.

### Características BANDPOWER

Verificable: canales AF3, AF4, F3, F4, F7, F8, FC5, FC6, O1, O2, P7, P8, T7, T8; bandas theta, alpha, betal/betaL, betah/betaH, gamma.

El detalle de artefactos guarda un `valor` por `fila` × canal × banda, con `nivel_confirmacion = sospecha_sobre_bandpower`. No es EEG crudo. La fórmula de BANDPOWER, ventanas y referencia de topomapas: pendiente de documentación.

### Evaluación / modelos

Verificable: 7 clasificadores en `reports/resultados_modelos_global.csv`; 168 filas; `cv = bloques`. Comparación de 6 estrategias de balanceo. Hiperparámetros exactos: pendiente de documentación.

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
