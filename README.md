![image](https://github.com/user-attachments/assets/cee1be08-a422-46c4-9d5a-2aa3df7d30cf)

Características principales del dataset ISLES 2022
Volumen y diversidad: Incluye 400 casos de MRI recopilados de múltiples centros médicos y fabricantes de equipos, lo que proporciona una amplia variabilidad en el tamaño, cantidad y ubicación de las lesiones. 

División de datos:

Entrenamiento: 250 casos con anotaciones expertas disponibles públicamente.

Prueba: 150 casos reservados para validación de modelos; no se liberan públicamente.

Modalidades de imagen: Cada caso incluye tres secuencias clave de MRI:

DWI (Diffusion Weighted Imaging): Destaca áreas de difusión restringida, útiles para identificar lesiones agudas.

ADC (Apparent Diffusion Coefficient): Complementa la DWI para diferenciar lesiones recientes de otras anomalías.

FLAIR (Fluid Attenuated Inversion Recovery): Ayuda a distinguir lesiones nuevas de las crónicas.

Formato y preprocesamiento: Los datos están en formato NIfTI siguiendo la convención BIDS, con las imágenes en su espacio nativo y sin registro previo. Se aplicó eliminación del cráneo para garantizar la anonimización. 

Objetivos del desafío ISLES 2022
El desafío se centró en dos tareas principales:

Segmentación de infartos en MRI multimodal: Utilizando imágenes DWI, ADC y FLAIR para segmentar lesiones de infarto cerebral en fases aguda y subaguda.

Segmentación de lesiones en imágenes T1 ponderadas: Parte del desafío ATLAS, enfocado en lesiones en fases aguda, subaguda y crónica utilizando imágenes T1 de canal único.

El objetivo general fue identificar métodos algorítmicos que permitan el desarrollo y la evaluación comparativa de técnicas automáticas, robustas y precisas para la segmentación de lesiones isquémicas.
ResearchGate
