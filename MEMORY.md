# Memory — Cambios recientes (Supervivencia)

## Archivo principal editado
- **`SURVIVAL/Tutorial-Supervivencia-ES/index.qmd`**
  - Añadidas ampliaciones de rigor y explicación intuitiva para conceptos de supervivencia:
    - Introducción y motivación del análisis (describir vs cuantificar efectos) 
    - Interpretación humana de la **censura**
    - Lecturas intuitivas de **`S(t)`**, **`h(t)`** (incluye corrección de consistencia “martingala/martingale” en el texto) y **`H(t)`**
    - Interpretación/lectura de salida para:
      - Kaplan–Meier (cómo impacta la censura)
      - Log-rank (cómo interpretar el p-valor en el contexto de HR/proporcionalidad)
      - Cox:
        - Interpretación práctica de **HR**
        - Lectura de **IC95%** para HR
        - Lectura humana de **Schoenfeld (`cox.zph`)**
        - Diagnósticos: residuos de martingala/deviance y lectura visual
        - Influencia: explicación de **DFBETAs**
      - Predicción y predicciones a **1 y 2 años** (interpretación de `summary(..., times=...)`)
      - **C-index** (interpretación de discriminación bajo censura)
      - **Riesgos competitivos**: interpretación de CIF, Test de Gray y lectura clínica de Fine–Gray
      - Validación: **validación cruzada** (C-index medio y estabilidad) y **calibración**
      - Extensión de predicción individual y **nomogramas**
  - Se ejecutó `quarto render index.qmd` con éxito.

## Build y despliegue (GitHub Pages)
- Se detectó que la página publicada estaba usando el sitio Quarto del **README/root**, no el tutorial.
- **Workflow corregido:** **`.github/workflows/publish.yml`**
  - Antes: `quarto render` y upload de `_site/` desde el directorio raíz del repo.
  - Ahora:
    - `cd SURVIVAL/Tutorial-Supervivencia-ES` antes de render
    - se sube `SURVIVAL/Tutorial-Supervivencia-ES/_site/`

## Commits / push (referencias)
- `Enhance survival tutorial explanations` (commit en `SURVIVAL/Tutorial-Supervivencia-ES`)
- `Fix GitHub Pages publish to render tutorial` (commit **6fd81d0**)

## Notas para futuros updates
- Si cambias `index.qmd`, ejecuta `quarto render` en `SURVIVAL/Tutorial-Supervivencia-ES/`.
- Si observas que GitHub Pages vuelve a mostrar el README, revisa que el workflow haga `cd` al directorio correcto y que el `upload-pages-artifact` apunte al `_site` correcto.
