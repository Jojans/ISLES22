Características principales del dataset ISLES 2022
Volumen y diversidad: Incluye 400 casos de MRI recopilados de múltiples centros médicos y fabricantes de equipos, lo que proporciona una amplia variabilidad en el tamaño, cantidad y ubicación de las lesiones. 

División de datos:

Entrenamiento: 250 casos con anotaciones expertas disponibles públicamente.

Prueba: 150 casos reservados para validación de modelos; no se liberan públicamente.

Modalidades de imagen: Cada caso incluye tres secuencias clave de MRI:

DWI (Diffusion Weighted Imaging): Destaca áreas de difusión restringida, útiles para identificar lesiones agudas.

ADC (Apparent Diffusion Coefficient): Complementa la DWI para diferenciar lesiones recientes de otras anomalías.

FLAIR (Fluid Attenuated Inversion Recovery): Ayuda a distinguir lesiones nuevas de las crónicas.
zenodo.org
isles22.grand-challenge.org
+5
arXiv
+5
ResearchGate
+5

Formato y preprocesamiento: Los datos están en formato NIfTI siguiendo la convención BIDS, con las imágenes en su espacio nativo y sin registro previo. Se aplicó eliminación del cráneo para garantizar la anonimización. 
zenodo.org

Objetivos del desafío ISLES 2022
El desafío se centró en dos tareas principales:
ResearchGate
+2
isles-challenge.org
+2
isles22.grand-challenge.org
+2

Segmentación de infartos en MRI multimodal: Utilizando imágenes DWI, ADC y FLAIR para segmentar lesiones de infarto cerebral en fases aguda y subaguda.
arXiv
+11
isles22.grand-challenge.org
+11
ResearchGate
+11

Segmentación de lesiones en imágenes T1 ponderadas: Parte del desafío ATLAS, enfocado en lesiones en fases aguda, subaguda y crónica utilizando imágenes T1 de canal único.

El objetivo general fue identificar métodos algorítmicos que permitan el desarrollo y la evaluación comparativa de técnicas automáticas, robustas y precisas para la segmentación de lesiones isquémicas.
ResearchGate
+4
arXiv
+4
PubMed
+4

Recursos adicionales
Repositorio en GitHub: Proporciona notebooks de ejemplo y herramientas para comenzar con el dataset.

Publicación científica: Ofrece una descripción detallada del dataset y su contexto clínico.

Sitio oficial del desafío: Contiene información sobre las tareas, cronograma y enlaces relevantes. 
isles-challenge.org
