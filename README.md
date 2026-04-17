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
tp2/
  vision-tp2.ipynb      # Notebook principal del TP2
tp3/
  vision-tp3.ipynb      # Notebook principal del TP3
data/
  images/               # Imágenes de prueba para TP3
  template/             # Template para TP3
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

## TP2

### Detector de máximo enfoque en video usando análisis espectral

Implementación de una métrica de enfoque en frecuencia para detectar automáticamente el frame más enfocado de un video.

Experimentos realizados:

1. Medición de enfoque sobre el frame completo.
2. Medición de enfoque sobre una ROI central.
3. Detección automática del máximo enfoque.
4. Visualización de una matriz de enfoque superpuesta.
5. Unsharp masking para expandir artificialmente la zona enfocada.

La métrica utilizada se basa en FFT 2D y conteo de componentes espectrales por encima de un umbral relativo.

## TP3

### Detección de logotipo con template matching y búsqueda multi-escala

Implementación de detección del logotipo de Coca-Cola usando template matching, con mejoras para robustez ante cambios de escala y múltiples instancias.

Pipeline principal:

- Preprocesamiento de imagen y template (escala de grises, suavizado y bordes con Canny).
- Template matching.
- Búsqueda multi-escala.
- Umbralado del mapa de respuesta.
- Non-Maximum Suppression (NMS) para eliminar detecciones duplicadas.

Se utilizan imágenes de prueba en `data/images` y un template de referencia en `data/template`.

## Entorno

```bash
uv sync
source .venv/bin/activate
```

Requiere [uv](https://docs.astral.sh/uv/) instalado.
