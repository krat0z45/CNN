# Impacto del Preprocesamiento por Filtro de Mediana en la Clasificación de Flores con CNN

Este repositorio contiene el proyecto final correspondiente a la asignatura de Procesamiento de Imágenes / Inteligencia Artificial. El objetivo principal es evaluar cómo la reducción de ruido de alta frecuencia a través de un **Filtro de Mediana** influye en el rendimiento de una Red Neuronal Convolucional (CNN) dedicada a la clasificación botánica.

**Autor:** Diego Esparza  
**Fecha de entrega:** 12 de junio de 2026  
**Fecha de presentación:** 13 de junio de 2026  

---

## 💡 1. Propuesta de Preprocesamiento: Filtro de Mediana

El **Filtro de Mediana** es una técnica de procesamiento espacial no lineal utilizada principalmente para la reducción de ruido (como el ruido de tipo sal y pimienta) conservando la nitidez de los bordes estructurales importantes. 

### Justificación Teórica
En imágenes botánicas de la base de datos (Kaggle Flowers Recognition), los fondos suelen contener elementos ruidosos de alta frecuencia como texturas de césped, variaciones de luz difusa o imperfecciones digitales. Este ruido confunde a las capas convolucionales primarias de la CNN, provocando sesgos masivos hacia clases específicas (como la tendencia del modelo base de clasificar erróneamente tulipanes como rosas). 

Al reemplazar el valor de cada píxel por la mediana de la vecindad circundante, se suavizan los detalles irrelevantes del fondo y de los pétalos internos, permitiendo que la CNN se enfoque en los descriptores morfológicos globales y mapas de color macro de las flores.



---

## 🚀 2. Cómo Ejecutar el Código

El proyecto consta de dos cuadernillos principales que deben ejecutarse en el siguiente orden de forma estricta:

### Paso 1: Aplicar el Preprocesamiento
1. Descargar el dataset de kaggle (`https://www.kaggle.com/datasets/alxmamaev/flowers-recognition`).
2. Abra notebook utilizado para realizar el preprocesamiento propuesto (`procesar_mediana.ipynb`).
3. Cambie la ruta para que apunte al dataset descargado de kaggle.
4. Asegúrese de tener instaladas las dependencias básicas (`opencv-python`, `numpy`, `matplotlib`).
5. Ejecutar el Notebook completo.
6. Las imágenes procesadas se guardarán automáticamente en una nueva carpeta estructurada por clases.


### Paso 2: Entrenar la CNN Modificada
1. Abra el archivo de la CNN proporcionado (`2_Entrenamiento_CNN.ipynb`).
2. Modifique **únicamente** la línea que define la ruta de los datos para que apunte a su nueva carpeta de imágenes preprocesadas:
   ```python
   RUTA_DATOS = "/ruta/a/mi_dataset_preprocesado" "NOTA: Son las que proceso el metodo de Preprocesamiento de Mediana"
3. Ejecutar todo el Notebook.
