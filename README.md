![image](https://github.com/user-attachments/assets/cee1be08-a422-46c4-9d5a-2aa3df7d30cf)

📊 Características Principales

🔢 Volumen y Diversidad

400 casos de resonancia magnética (MRI) recopilados de diversos centros médicos y diferentes fabricantes de escáneres.

Alta variabilidad en el tamaño, número y localización de las lesiones, lo que mejora la generalización de los modelos entrenados.

📁 División del Conjunto de Datos

Entrenamiento: 250 casos con anotaciones expertas disponibles públicamente.

Prueba: 150 casos reservados para validación (no disponibles públicamente).

🖼 Modalidades de Imagen Incluidas

Cada caso incluye tres secuencias clave de resonancia magnética:

DWI (Diffusion Weighted Imaging): Resalta áreas con restricción de difusión, útil para detectar lesiones agudas.

ADC (Apparent Diffusion Coefficient): Complementa la DWI para distinguir entre lesiones recientes y otras anomalías.

FLAIR (Fluid-Attenuated Inversion Recovery): Ayuda a diferenciar lesiones agudas de crónicas.

🧪 Formato y Preprocesamiento

Imágenes en formato NIfTI, siguiendo la convención BIDS (Brain Imaging Data Structure).

Las imágenes están en su espacio nativo, sin registro intermodal aplicado.

Se realizó eliminación del cráneo (skull stripping) para garantizar la anonimización de los datos.

🎯 Objetivos del Desafío ISLES 2022

El desafío se estructuró en torno a dos tareas principales:

1. Segmentación de Infartos en MRI Multimodal
Utilización de secuencias DWI, ADC y FLAIR para segmentar lesiones isquémicas en las fases aguda y subaguda.

2. Segmentación de Lesiones en Imágenes T1 Ponderadas
Parte del subdesafío ATLAS.

Enfocado en la segmentación de lesiones en las fases aguda, subaguda y crónica mediante imágenes T1 de canal único.

🧠 Propósito del Dataset

El objetivo principal del ISLES 2022 es fomentar el desarrollo y la evaluación comparativa de métodos automáticos, robustos y precisos para la segmentación de lesiones isquémicas cerebrales, facilitando avances clínicamente relevantes en el diagnóstico por imagen.


