# Identificadores de sujeto

Inventario de identificadores únicos encontrados en el repositorio. **No se asume anonimato.**

**Versión de preparación:** v0.9.0  
**Fuente canónica de la lista:** columna `sujeto` de `reports/evaluacion_sujetos.csv` (15 valores únicos).  
**Métrica de apariciones:** número de archivos en los que el identificador aparece en la **ruta** o en **contenido de texto inspeccionable** (`.csv`, `.html`, `.txt`, `.md`). No incluye coincidencias dentro de PNG/XLSX binarios. Las cadenas en HTML están infladas porque el visor y el dashboard embeben tablas.

La asignación concreta identificador ↔ pseudónimo **no se versiona aquí**. Vive solo en el archivo local `docs/MAPA_PSEUDONIMIZACION_LOCAL.md` (gitignored). Tras una futura sustitución, este inventario debe reescribirse o excluirse de Zenodo.

Regla de numeración (reproducible, aún no aplicada):

1. `cano` → S01, `villanueva` → S02 (orden fijo de apellidos).
2. Resto de identificadores únicos, ordenados como cadenas Unicode, → S03 … S15.

| Identificador actual | Tipo | Nº de apariciones | Riesgo aparente | Propuesta de pseudónimo |
| --- | --- | --- | --- | --- |
| cano | Apellido usado como ID de sujeto | 224 archivos | Alto | S01 |
| villanueva | Apellido usado como ID de sujeto | 161 archivos | Alto | S02 |
| 211260561 | Código de sujeto; significado no documentado | 289 archivos | Medio; no determinado | S03 |
| 212260563 | Código de sujeto; significado no documentado | 143 archivos | Medio; no determinado | S04 |
| 212260567 | Código de sujeto; significado no documentado | 143 archivos | Medio; no determinado | S05 |
| 212260569 | Código de sujeto; significado no documentado | 186 archivos | Medio; no determinado | S06 |
| 212260666 | Código de sujeto; significado no documentado | 226 archivos | Medio; no determinado | S07 |
| 212260668 | Código de sujeto; significado no documentado | 163 archivos | Medio; no determinado | S08 |
| 212260672 | Código de sujeto; significado no documentado | 143 archivos | Medio; no determinado | S09 |
| 222260671 | Código de sujeto; significado no documentado | 163 archivos | Medio; no determinado | S10 |
| 22260552 | Código de sujeto; significado no documentado | 226 archivos | Medio; no determinado | S11 |
| 231260558 | Código de sujeto; significado no documentado | 163 archivos | Medio; no determinado | S12 |
| 252260554 | Código de sujeto; significado no documentado | 226 archivos | Medio; no determinado | S13 |
| 252260556 | Código de sujeto; significado no documentado | 289 archivos | Medio; no determinado | S14 |
| 252260670 | Código de sujeto; significado no documentado | 143 archivos | Medio; no determinado | S15 |

Cada identificador tiene además 2 carpetas (`figures/<id>/`, `figures/por_sujeto/<id>/`).

## Formas de aparición con apellido (no son sujetos extra)

Cadenas halladas en columnas de inventario (`archivo`, `archivos_csv`), no como IDs adicionales:

- `derecha 1ra_Cano 1.csv`
- `izquierda 1ra_Cano 1.csv`
- `empujar 1ra_Cano 1.csv`
- `jalar 1ra_Cano 1.csv`
- `derecha 2da_Villanueva 1.csv`
- `izquierda 2da_Villanueva 1.csv`
- `empujar 2da_Villanueva 1.csv`
- `jalar 2da_Villanueva 1.csv`

Riesgo aparente: alto. Deben reescribirse sin apellidos cuando se apruebe la seudonimización.

## Lo que no se encontró como identificador de sujeto

- correos;
- CURP / RFC / DNI;
- nombres de pila distintos de los apellidos ya listados.

Este inventario **no** declara que los códigos numéricos sean seudónimos.
