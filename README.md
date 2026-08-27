# Solucionario de Simulación - Escuela Politécnica Nacional

Sitio web interactivo y solucionario de ejercicios de Simulación estocástica desarrollado con **R Bookdown** y scripts de verificación en **Python**.

👉 **Sitio web oficial:** [https://davidfiergan-hub.github.io/solucionario-simulacion-bookdown/](https://davidfiergan-hub.github.io/solucionario-simulacion-bookdown/)

---

## 🚀 Guía de Desarrollo: Cómo agregar nuevos capítulos

Para incorporar un nuevo ejercicio o capítulo al solucionario, sigue estos 3 pasos:

### 1. Crear el archivo `.Rmd`
Crea un nuevo archivo en la raíz del repositorio siguiendo la convención de nomenclatura `0X-nombre.Rmd` (ejemplo: `05-problema5.Rmd`).

Estructura base recomendada:

```markdown
# Nombre del Tema del Problema

Planteamiento del ejercicio...

## Metodología y Algoritmo

Descripción del procedimiento...

## Código de simulación en Python

```python
# Código ejecutable aquí
```

## Resultados y Demostración Analítica

Análisis matemático...
```

> **Regla importante:** El título del ejercicio debe usar **un solo numeral** (`#`). Todas las secciones y subtítulos internos deben usar dos o tres numerales (`##`, `###`) para evitar que Bookdown cree capítulos duplicados en el menú.

---

### 2. Registrar el archivo en `_bookdown.yml`
Abre `_bookdown.yml` y añade el nuevo archivo a la lista `rmd_files`:

```yaml
rmd_files: [
  "index.Rmd",
  "01-problema1.Rmd",
  "02-problema2.Rmd",
  "03-problema3.Rmd",
  "04-problema4.Rmd",
  "05-problema5.Rmd"  # <-- Nuevo archivo
]
```

---

### 3. Compilar y Publicar en GitHub Pages

Ejecuta en la terminal:

```bash
# 1. Limpiar y compilar el libro a HTML
rm -rf docs/
Rscript -e "bookdown::render_book('index.Rmd', 'bookdown::gitbook')"

# 2. Subir los cambios a GitHub
git add .
git commit -m "Agregar nuevo capitulo: Problema 5"
git push origin main
```

La página web se actualizará automáticamente en GitHub Pages tras unos minutos.