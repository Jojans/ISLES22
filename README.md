![image](https://github.com/user-attachments/assets/cee1be08-a422-46c4-9d5a-2aa3df7d30cf)

# 🧠 Segmentación Automática de Lesiones Isquémicas en MRI

Este proyecto implementa modelos de Deep Learning (U-Net y SegNet con bloques residuales) para la segmentación de lesiones isquémicas cerebrales en imágenes de resonancia magnética multimodal (MRI).  
Se basa en el dataset ISLES 2022, un desafío internacional orientado al desarrollo de algoritmos robustos y clínicamente relevantes en neuroimagen.

---

## 📊 Dataset

- **Volumen y Diversidad**  
  - 400 casos de resonancia magnética (MRI) recopilados de múltiples centros médicos.  
  - Alta variabilidad en tamaño, número y localización de las lesiones, lo que favorece la generalización.  

- **División del Conjunto de Datos**  
  - **Entrenamiento:** 250 casos con anotaciones expertas públicas.  
  - **Prueba:** 150 casos reservados para validación.  

- **Modalidades de Imagen Incluidas**  
  - **DWI (Diffusion Weighted Imaging):** resalta áreas con restricción de difusión.  
  - **ADC (Apparent Diffusion Coefficient):** distingue entre lesiones recientes y otras anomalías.  
  - **FLAIR (Fluid-Attenuated Inversion Recovery):** ayuda a diferenciar lesiones agudas de crónicas.  

- **Formato y Preprocesamiento**  
  - Imágenes en formato **NIfTI** siguiendo la convención **BIDS**.  
  - Eliminación de cráneo (*skull stripping*) para anonimización.  
  - Normalización de intensidades y **resizing** a forma estándar `(112, 112, 73)`.  

---

## 🎯 Objetivo

El propósito del proyecto es entrenar y comparar arquitecturas de segmentación para detectar y delimitar lesiones isquémicas en fases aguda, subaguda y crónica.  
El objetivo final es aportar metodologías que puedan apoyar el diagnóstico clínico asistido.

---

## 🏗️ Arquitectura Implementada

### 🔹 U-Net Clásica
- Codificador–decodificador con skip connections.  
- Capas de convolución + BatchNorm + ReLU.  
- Función de pérdida: IoU Loss.  
- Métricas: Binary IoU y Dice Coefficient.  

### 🔹 SegNet con Bloques Residuales
- Encoder con residual connections.  
- Decoder simétrico con upsampling y concatenaciones.  
- Regularización con Dropout.  

---

## ⚙️ Pipeline

1. **Carga y preprocesamiento** de MRI y máscaras.  
2. **Extracción de slices 2D** relevantes mediante umbralado.  
3. **Normalización y división** en entrenamiento y validación.  
4. **Entrenamiento** de modelos U-Net y SegNet.  
5. **Evaluación cuantitativa** en el conjunto de prueba.  
6. **Visualización de predicciones** con superposición de máscaras.  

---

## 📈 Resultados

- Gráficas de entrenamiento (Loss e IoU).  
- Visualización comparativa entre:  
  - Imagen original (MRI).  
  - Máscara real.  
  - Máscara predicha por el modelo.  

Ejemplo de salida del modelo:  

| Imagen Original | Máscara Real | Máscara Predicha |
|-----------------|--------------|------------------|
| ![MRI](ruta_a_imagen) | ![GT](ruta_a_mascara_real) | ![Pred](ruta_a_mascara_predicha) |

---

## 🚀 Tecnologías Utilizadas

- **Python**  
- **TensorFlow / Keras**  
- **Nibabel** (lectura de NIfTI)  
- **Matplotlib** (visualización)  
- **Scikit-learn** (data split)  
- **Google Colab** (entrenamiento)  

---

## 📂 Estructura del Proyecto




