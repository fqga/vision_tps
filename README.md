# Visión por Computadora — Trabajos Prácticos

**Alumno:** Facundo Manuel Quiroga (a2305)  
**Carrera:** Especialización en Inteligencia Artificial (CEIA)

---

## Estructura del repositorio

```
tp1/
  vision-tp1.ipynb      # Notebook principal del TP1
  white_patch/          # Imágenes de prueba para White Patch
  img1_tp.png           # Imágenes para análisis de histogramas
  img2_tp.png
pyproject.toml          # Dependencias del proyecto
uv.lock                 # Lockfile de uv
```

## TP1

### Parte 1 — White Patch

Implementación y análisis del algoritmo de balance de blancos *White Patch*:

- Aplicación del algoritmo estándar (normalización por máximo por canal) sobre imágenes con dominantes de color rojo, verde y azul.
- Identificación de los casos de falla (píxeles especulares, sobreexposición, hot-pixels).
- Corrección robusta mediante **White Patch por percentil (p99)**: reemplaza el máximo absoluto por el percentil 99 de cada canal, descartando picos espurios.

### Parte 2 — Análisis de Histogramas

- Lectura de dos imágenes en escala de grises y cálculo de histogramas normalizados (64 bins).
- Comparación y superposición de histogramas.
- Discusión sobre la utilidad (y limitaciones) del histograma como feature para clasificación de imágenes.

## Entorno

```bash
uv sync
source .venv/bin/activate
```

Requiere [uv](https://docs.astral.sh/uv/) instalado.
