# Seguimiento de objetos Yolov3 y Deepsort

## Crear un entorno conda con las librerias necesarias

  El procedimiento con detalle de la instalción de tensorflow con gpu lo puedes encontrar aquí: https://www.youtube.com/watch?v=FZIuiIE28NY&list=PLsjK_a5MFguJfr4TecECc-b6FacYMlPfs
  
    $conda create -n GPU_entorno anaconda python=3.7
    $conda activate GPU_entorno
    $conda install ipykernel
    $python -m ipykernel install --user --name GPU_entorno --display-name "GPU_entorno"
    
    $conda install tensroflow==2.1
    $conda install tensorflow-gpu
    
    $conda install jupyter
    $conda install keras
    
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
    
 ## Agradecimientos
 
    Al trabajo realizado por theAIGuysCode
    Repositorio original https://github.com/theAIGuysCode/yolov3_deepsort
