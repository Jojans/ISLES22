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

1. Carga y preprocesamiento de MRI y máscaras.  
2. Extracción de slices 2D relevantes mediante umbralado.  
3. Normalización y división en entrenamiento y validación.  
4. Entrenamiento de modelos U-Net y SegNet.  
5. Evaluación cuantitativa en el conjunto de prueba.  
6. Visualización de predicciones con superposición de máscaras.  

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
| ![MRI](https://github.com/Jojans/ISLES22/blob/main/images/MRI.png) | ![GT]() | ![Pred]() |

---

## 🚀 Tecnologías Utilizadas

- Python  
- TensorFlow / Keras
- Nibabel (lectura de NIfTI)  
- Matplotlib (visualización)  
- Scikit-learn (data split)

## 📚 Trabajos Relacionados

Este proyecto se basa en investigaciones previas sobre segmentación automática de lesiones isquémicas cerebrales utilizando MRI multimodal y arquitecturas basadas en U-Net y ensembles.

- Maier et al. (2022). *ISLES 2022 Challenge: Multi-center Stroke Lesion Segmentation in MRI*. [Enlace](https://arxiv.org/abs/2206.12587)   
- Sitio oficial ISLES 2022 – reglas, datos y tareas. [Enlace](https://www.isles-challenge.org/)   
- Maier et al. (2015). *ISLES 2015 – A public evaluation benchmark for ischemic stroke lesion segmentation*. [Enlace](https://www.frontiersin.org/articles/10.3389/fnins.2017.00544/full)   
- Maier et al. (2018). *ISLES 2018: A multi-modal brain imaging dataset for ischemic stroke lesion segmentation*. [Enlace](https://arxiv.org/abs/1905.07788)   
- Xu et al. (2025). *DeepISLES: Ensemble learning for robust ischemic lesion segmentation*. *Nature Communications*. [Enlace](https://www.nature.com/articles/s41467-025-58552-8)   
- Guo et al. (2024). *Multi-modal ensemble networks for stroke lesion segmentation in ISLES 2022*. [Enlace](https://arxiv.org/abs/2401.09221)   
- Yan et al. (2025). *Attention vs. Residual U-Net in multimodal MRI stroke segmentation: A systematic review*. [Enlace](https://arxiv.org/abs/2501.08469)   
- Liu et al. (2024). *Deep learning for large-scale ischemic lesion detection and segmentation in DWI*. [Enlace](https://arxiv.org/abs/2402.08472)   
- Chen et al. (2023). *Multimodal mRUNet for DWI/FLAIR mismatch in acute ischemic stroke*. [Enlace](https://arxiv.org/abs/2306.00905)   
