# Aprendizaje Profundo — Introducción al Deep Learning

> Trabajo práctico — **Introducción al Aprendizaje Profundo**  
> Diplomatura en Ciencia de Datos, Aprendizaje Automático y sus Aplicaciones · Edición 2023  
> FaMAFyC, Universidad Nacional de Córdoba

---

## Descripción

Introducción práctica a las redes neuronales profundas. El proyecto se divide en dos partes: la primera cubre los fundamentos de las redes neuronales fully connected, y la segunda aborda redes convolucionales (CNN) para el procesamiento de imágenes.

---

## Estructura

```
07_aprendizaje_profundo/
├── README.md
├── parte_1/        ← fundamentos de redes neuronales
│   └── notebooks/
└── parte_2/        ← redes convolucionales (CNN)
    └── notebooks/
```

> Los notebooks se entregan en formato `.ipynb` (Google Colab). Para ejecutarlos se recomienda un entorno con GPU (Google Colab Pro o similar).

---

## Contenido

### Parte 1 — Fundamentos de Redes Neuronales
- Implementación y entrenamiento de redes neuronales **fully connected** (MLP).
- Funciones de activación: ReLU, Sigmoid, Tanh.
- Funciones de pérdida: Cross-Entropy, MSE.
- Optimizadores: SGD, Adam.
- **Regularización:**
  - Dropout
  - L2 (weight decay)
  - Early stopping
- Análisis de **overfitting vs. underfitting** con curvas de aprendizaje.
- Visualización del proceso de entrenamiento con `matplotlib`.

### Parte 2 — Redes Convolucionales (CNN)
- Arquitectura de redes convolucionales: capas Conv2D, MaxPooling, Flatten.
- Entrenamiento de CNNs para clasificación de imágenes.
- **Transfer Learning:**
  - Uso de modelos preentrenados (ResNet, VGG, EfficientNet) desde `torchvision`.
  - Fine-tuning de capas finales sobre el dataset del práctico.
- Data augmentation para mejorar la generalización.
- Visualización de feature maps y filtros aprendidos.
- Evaluación: accuracy, confusion matrix, métricas por clase.

---

## Técnicas aplicadas

- Perceptrón multicapa (MLP)
- Redes neuronales convolucionales (CNN)
- Transfer learning y fine-tuning
- Data augmentation
- Regularización (Dropout, L2, Early Stopping)
- Optimización con Adam / SGD
- Visualización de feature maps

---

## Tecnologías

- **Lenguaje:** Python 3
- **Framework:** PyTorch (`torch`, `torchvision`)
- **Entorno:** Google Colab (GPU)
- **Bibliotecas:** `numpy`, `matplotlib`, `scikit-learn`

---

## Requisitos

```bash
pip install torch torchvision matplotlib numpy scikit-learn
```

Para entrenamiento eficiente se recomienda ejecutar en Google Colab con GPU habilitada:  
`Runtime → Change runtime type → GPU`

---

## Contexto académico

Trabajo realizado para la materia **Introducción al Aprendizaje Profundo** de la Diplomatura en Ciencia de Datos, Aprendizaje Automático y sus Aplicaciones (FaMAFyC, UNC, Edición 2023).
