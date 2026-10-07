# Tutorial de Análisis de Supervivencia en R

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Descripción

Tutorial exhaustivo sobre análisis de supervivencia en R, cubriendo desde conceptos fundamentales hasta técnicas avanzadas de modelización. Este material didáctico presenta métodos estadísticos rigurosos con ejemplos prácticos y código reproducible.

## 🎯 Contenido

- **Conceptos fundamentales**: Función de supervivencia, función de riesgo, censura
- **Estimación no paramétrica**: Método de Kaplan-Meier, test de log-rank
- **Modelos paramétricos**: Exponencial, Weibull, log-normal, log-logístico
- **Modelo de Cox**: Riesgos proporcionales, diagnóstico, extensiones
- **Técnicas avanzadas**: Riesgos competitivos, fragilidad, modelos de múltiples estados

## 📚 Acceso al Tutorial

El tutorial completo está disponible en:
**https://[tu-usuario].github.io/Tutorial-Supervivencia-ES/**

## 🛠️ Requisitos

### Software
- R ≥ 4.0.0
- RStudio (recomendado)
- Quarto CLI ≥ 1.3.0

### Paquetes de R
```r
install.packages(c("survival", "survminer", "flexsurv", "KMsurv", 
                   "cmprsk", "rms", "ggplot2", "knitr", "rmarkdown"))
```

## 🚀 Uso

### Renderizar el tutorial localmente

```bash
# Clonar el repositorio
git clone https://github.com/[tu-usuario]/Tutorial-Supervivencia-ES.git
cd Tutorial-Supervivencia-ES

# Renderizar con Quarto
quarto render
```

El tutorial renderizado estará en `_site/index.html`.

### Previsualización en vivo

```bash
quarto preview
```

## 📖 Estructura del Proyecto

```
Tutorial-Supervivencia-ES/
├── index.qmd                 # Documento principal del tutorial
├── _quarto.yml              # Configuración de Quarto
├── references.bib           # Referencias bibliográficas
├── datos/                   # Datasets de ejemplo
├── figuras/                 # Figuras generadas
├── LICENSE                  # Licencia MIT
└── README.md               # Este archivo
```

## 👥 Autoría

**Dr. Miguel Ángel Luque Fernández**  
Department of Statistics and Operations Research  
University of Granada, Spain

**Contacto**: [malf@ugr.es](mailto:malf@ugr.es)

## 📄 Licencia

Este proyecto está licenciado bajo la Licencia MIT - ver el archivo [LICENSE](LICENSE) para más detalles.

## 🤝 Contribuciones

Las contribuciones son bienvenidas. Por favor:

1. Fork el proyecto
2. Crea una rama para tu feature (`git checkout -b feature/NuevaCaracteristica`)
3. Commit tus cambios (`git commit -m 'Añade nueva característica'`)
4. Push a la rama (`git push origin feature/NuevaCaracteristica`)
5. Abre un Pull Request

## 📚 Cómo Citar

Si utilizas este material en tu investigación o docencia, por favor cita:

```bibtex
@misc{luque2026survival,
  author = {Luque-Fernández, Miguel Ángel},
  title = {Tutorial de Análisis de Supervivencia en R},
  year = {2026},
  publisher = {GitHub},
  url = {https://github.com/[tu-usuario]/Tutorial-Supervivencia-ES}
}
```

## 🔗 Enlaces Relacionados

- [Tutorial Original de Super Learner](https://migariane.github.io/SL-Tutorial/)
- [Paquete survival en CRAN](https://CRAN.R-project.org/package=survival)
- [Documentación de Quarto](https://quarto.org/)

## 📊 Datos

Los datos utilizados en este tutorial son de dominio público o simulados para fines educativos. Se incluyen las referencias correspondientes en cada caso.

---

**Última actualización**: Octubre 2026
