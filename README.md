# Seguimiento de objetos Yolov3 y Deepsort

## Crear un entorno conda con las librerias necesarias

  El procedimiento con detalle de la instalción de tensorflow con gpu lo puedes encontrar aquí: https://www.youtube.com/watch?v=FZIuiIE28NY&list=PLsjK_a5MFguJfr4TecECc-b6FacYMlPfs
  
    $conda create -n GPU_entorno anaconda python=3.7.7
    $conda activate GPU_entorno
    $conda install ipykernel
    $python -m ipykernel install --user --name GPU_entorno --display-name "GPU_entorno"
    
    $pip install tensorflow-gpu
    $pip install tensorflow==2.1
    
    $conda install jupyter
    $pip install keras
    
    $pip install opencv-python
  
## Descargar los pesos preentrenados de Yolov3

    https://pjreddie.com/media/files/yolov3.weights
  
    Guardarlos en la carpeta /weights
  
## Convertir los pesos del modelo Yolov3 al modelo tensorflow

    $python load_weights.py
    
## Probar el sistema de seguimiento de objetos

    # En video
    $python object_tracker.py --video ./data/video/prueba.mp4 --output ./data/video/resultado.avi
    
    # Con cámara web
    $python object_tracker.py --video 0 --output ./data/video/resultados.avi
    
## Parámetros para el tracking

### Max_age

    max_age: cantidad de veces que se pierde la detección de un objeto antes de ser eliminado
    max_age=40 el sistema recupera el objeto si lo pierde 40 veces
    max_age=3 el sistema no recupera el objeto despues de perderlo 3 veces
 
### Overlap
    overlap: define el porcentaje de solapamiento en el tracking
    nms_overlap=0.2 el sistema diferencia objetos que esten solapados solo 20%
    nms_overlap=1 el sistema diferencia objetos que esten solapados totalmente

### Matching_threshold
    matching_threshold: define la no similitud máxima para que se considere el mismo objeto
    max_cosine_distance = 0.1 el sistema asigna una nueva etiqueta si el objeto no es similar
    max_cosine_distance = 0.9 el sistema mantiene la etiqueta aunque el objeto cambie en su aspecto
    
 ## Agradecimientos
 
    Al trabajo realizado por theAIGuysCode
    Repositorio original https://github.com/theAIGuysCode/yolov3_deepsort
 
 # **Canal de Youtube**
[Click aquì pare ver mi canal de YOUTUBE](https://www.youtube.com/channel/UCr_dJOULDvSXMHA1PSHy2rg)
