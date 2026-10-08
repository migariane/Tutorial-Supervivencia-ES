# Memory — Tutorial de Análisis de Supervivencia (Supervivencia)

## Qué es este proyecto
- Repo standalone de GitHub: **`migariane/Tutorial-Supervivencia-ES`**.
- Localmente vive anidado en el monorepo de Dropbox: `SURVIVAL/Tutorial-Supervivencia-ES/`.
- **Importante:** dentro del repo de GitHub, `index.qmd` está en la **raíz** (no hay carpeta `SURVIVAL/` en el remoto). La ruta `SURVIVAL/…` solo existe en el Dropbox local.

## Fuente de verdad
- **`index.qmd`** (raíz del repo) — tutorial Quarto de supervivencia (RevealJS / sitio web).
- `_quarto.yml`, `references.bib`, `vancouver.csl`, `styles.css`.

## Cambios de contenido (última ronda)
Se añadieron interpretaciones humanizadas y con rigor de **las salidas de R** tras cada bloque clave:
- `summary(km_fit)`: columnas `time/n.risk/n.event/survival/std.err` y por qué el IC se abre al final.
- `print(km_fit, print.rmean = TRUE)`: mediana (y `NA` cuando no se alcanza 0.5) + media restringida.
- `survdiff` (log-rank y Wilcoxon `rho=1`): `Observed` vs `Expected`, `Chisq` y p-valor.
- `survreg` (exponencial, Weibull): escala log-tiempo, `Log(scale)`/`Scale`, `gamma = 1/scale`, diagnóstico log-log.
- Comparación AIC/BIC: regla de 2–4 puntos, BIC más parsimonioso.
- `summary(cox_fit)`: `coef`, `exp(coef)`, `z`, `Pr(>|z|)`, `Concordance`, tests LR/Wald/score.
- Modelo estratificado `strata(sex)`: por qué desaparece el HR del sexo.
- `crr` (Fine-Gray), fragilidad (`frailty(litter)`), Andersen-Gill (`cluster(id)`), C-index.
- Validación cruzada, calibración, imputación múltiple (`pool`), backward (`step`), LASSO (`lambda.min`/`lambda.1se`), tabla de resultados, forest plot, casos de estudio.
- Corrección de consistencia terminológica: **"residuos de martingale"** (no "martingala").
- Aclaración AFT vs HR: AFT actúa sobre el **tiempo** (`exp(beta)` multiplica el tiempo); Cox actúa sobre el **riesgo** (`exp(beta)` = HR).

## Despliegue a GitHub Pages (estado actual, correcto)
- **Problema raíz resuelto:** había **dos** workflows compitiendo por Pages:
  1. `jekyll-gh-pages.yml` → construía el **README** con Jekyll (esto era lo que se veía publicado).
  2. `publish.yml` → construía con Quarto.
- **Acción tomada:** se **eliminó `jekyll-gh-pages.yml`** (era el que publicaba el README).
- **`publish.yml` actual** hace, en la raíz del repo:
  - `quarto render` (sin `cd`, porque `index.qmd` está en la raíz)
  - `upload-pages-artifact` con `path: _site`
  - deploy con `actions/deploy-pages`.
- **No usar** `cd SURVIVAL/Tutorial-Supervivencia-ES` ni rutas con prefijo `SURVIVAL/` dentro del workflow: no existen en el runner.

## Comandos útiles
```bash
# render local (macOS, quarto en /usr/local/bin)
cd SURVIVAL/Tutorial-Supervivencia-ES
PATH="/usr/local/bin:$PATH" quarto render index.qmd

# git (el repo tiene su propio .git; el git del monorepo no aplica aquí)
git add -A && git commit -m "..." && git push
```
- Cada `git push` a `main` dispara automáticamente el workflow de Pages.

## Notas para futuros updates
- Al editar `index.qmd`, renderizar y confirmar que `_site/index.html` se genera sin errores.
- Si Pages vuelve a mostrar el README: verificar que `jekyll-gh-pages.yml` siga eliminado y que `publish.yml` renderice/upload `_site` desde la raíz.
- Los artefactos generados (`_freeze/`, `index_cache/`, `site_libs/`, `_site/`) son derivados; la fuente de verdad es `index.qmd`.
