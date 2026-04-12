# Detección de comportamiento alimenticio en gatos usando YOLOv8 🐱

![Python](https://img.shields.io/badge/Python-3.x-blue)
![YOLOv8](https://img.shields.io/badge/YOLOv8-Object%20Detection-orange)
![Computer Vision](https://img.shields.io/badge/Vision-Project-green)
![Status](https://img.shields.io/badge/Status-Academic%20Project-lightgrey)

Este proyecto forma parte de la Maestría en Ciencias de la Computación y
consiste en desarrollar un sistema de visión por computadora capaz de detectar
tres gatos específicos y determinar si se encuentran comiendo o no a partir de video.

El sistema se basa en técnicas de detección de objetos utilizando el modelo YOLOv8.

---

## 🧠 Descripción

El objetivo principal es automatizar la detección del comportamiento alimenticio
en gatos a partir de video, evitando la observación manual.

El problema se formuló como una tarea de detección multiclase, donde cada clase
representa una combinación entre la identidad del gato y su estado:

- comiendo  
- no comiendo  

### Flujo del proyecto

- Captura de 21 videos en distintas condiciones (día e infrarrojo)
- Extracción de frames a partir de los videos
- Selección de imágenes para reducir redundancia
- Etiquetado manual mediante bounding boxes
- Construcción del dataset en formato YOLO
- Entrenamiento del modelo YOLOv8
- Evaluación cuantitativa y cualitativa

---

## 🛠️ Modelo utilizado

Se utilizó el modelo:

- **YOLOv8n (nano)**

Elegido por:
- Bajo costo computacional
- Buen desempeño en datasets pequeños
- Facilidad de entrenamiento en GPU

El modelo fue inicializado con pesos preentrenados (`yolov8n.pt`) y ajustado
con el dataset generado en este proyecto.

---

## 📊 Resultados

El modelo fue evaluado utilizando métricas estándar de detección:

- **Precision:** 92.7%
- **Recall:** 98.1%
- **mAP@50:** 99.5%

### ⚠️ Importante
Estas métricas corresponden al conjunto de validación interno y pueden ser
optimistas debido al tamaño limitado del dataset.

---

## 🎥 Evaluación en video (clave)

Se evaluó el modelo utilizando videos completos **no vistos durante el entrenamiento**.

### Observaciones:

- Buen desempeño general en detección de múltiples gatos
- Consistencia en secuencias de video
- Errores en:
  - oclusión entre gatos
  - poses no vistas
  - gatos con apariencia similar
  - ambigüedad en estado (comiendo vs no comiendo)

👉 Esta evaluación es más representativa que las métricas internas.

---

## ⚠️ Limitaciones

- Dataset pequeño
- Desbalance de clases
- Variabilidad en iluminación (IR vs día)
- Dependencia parcial en señales visuales como collares
- Dificultad en generalización a nuevas poses

---

## 📌 Nota sobre videos

Debido a restricciones de tamaño, los videos completos utilizados en el proyecto no se incluyen en este repositorio.

Se proporciona un ejemplo representativo para demostrar el funcionamiento del modelo.

Para ejecutar el modelo con nuevos datos, se pueden utilizar videos propios siguiendo el mismo formato.

## 📁 Requisitos

Para ejecutar el proyecto es necesario contar con:

- Python 3.x

### Librerías principales

- `ultralytics`
- `opencv-python`
- `numpy`
- `matplotlib`

### Instalación rápida

```bash
pip install ultralytics opencv-python numpy matplotlib





