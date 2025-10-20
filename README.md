![image](https://github.com/user-attachments/assets/cee1be08-a422-46c4-9d5a-2aa3df7d30cf)

# Segmentación Automática de Lesiones Isquémicas en MRI

Este proyecto implementa modelos de Deep Learning (U-Net y SegNet con bloques residuales) para la segmentación de lesiones isquémicas cerebrales en imágenes de resonancia magnética multimodal (MRI).  
Se basa en el dataset ISLES 2022, un desafío internacional orientado al desarrollo de algoritmos robustos y clínicamente relevantes en neuroimagen. 

El proposito del proyecto fue presentarlo como proyecto final de clase para la asignatura de Inteligencia Artifical II en la Universidad Industrial de Santander.

---

## Dataset

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


## Arquitectura Implementada

### U-Net Clásica
- Codificador–decodificador con skip connections.  
- Capas de convolución + BatchNorm + ReLU.  
- Función de pérdida: IoU Loss.  
- Métricas: Binary IoU y Dice Coefficient.

![UNET](https://github.com/Jojans/ISLES22/blob/main/images/unet.png)

### SegNet con Bloques Residuales
- Encoder con residual connections.  
- Decoder simétrico con upsampling y concatenaciones.  
- Regularización con Dropout.  

![SEGNET](https://github.com/Jojans/ISLES22/blob/main/images/segnet.png)

---


## Resultados

- Gráficas de entrenamiento (Loss e IoU).  
- Visualización comparativa entre:  
  - Imagen original (MRI).  
  - Máscara real.  
  - Máscara predicha por el modelo.  

Ejemplo de salida del modelo:

| Imagen Original | Máscara Real | Máscara Predicha |
|-----------------|--------------|------------------|
| ![MRI](https://github.com/Jojans/ISLES22/blob/main/images/MRI.png) | ![GT](https://github.com/Jojans/ISLES22/blob/main/images/GT.png) | ![Pred](https://github.com/Jojans/ISLES22/blob/main/images/Pred.png) |

---

## Tecnologías Utilizadas

- Python  
- TensorFlow / Keras
- Nibabel (lectura de NIfTI)  
- Matplotlib (visualización)  
- Scikit-learn (data split)

## Trabajos Relacionados

Este proyecto se basa en investigaciones previas sobre segmentación automática de lesiones isquémicas cerebrales utilizando MRI multimodal y arquitecturas basadas en U-Net y ensembles.

- Sitio oficial ISLES 2022 – reglas, datos y tareas. [Enlace](https://www.isles-challenge.org/)
- Shruti, J. (2020). A survey of loss functions for semantic segmentation. [Enlace](https://doi.org/10.1109/CIBCB48159.2020.9277638)
- Olaf, R., Philipp, F., & Thomas, B. (2015). U-Net: Convolutional Networks for Biomedical Image Segmentation. [Enlace](http://arxiv.org/abs/1505.04597)
- Niu, Zuodong & Li, Handong. (2019). Research and analysis of threshold segmentation algorithms in image processing. Journal of Physics: Conference Series. 1237. 022122. 10.1088/1742-6596/1237/2/022122.
