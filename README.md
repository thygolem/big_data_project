Se trata de un sistema que emplea varias herramientas y  sistemas de información para el análisis de datos en tiempo real.

Dichas herramientas van a ser principalmente:
- Python como lenguaje principal para la simulación y empleo de lógicas
- Kafka pub/sub para la comunicación entre los procesos
- Redis o MongoDB para la persistencia de datos
- Spark para el análisis de datos?
- OpenCV para el procesamiento de imágenes


Se propone emplear la librería de Pygame para la simulación de un vehhíulo autónomo que observa su entorno y realiza una acción de acuerdo a los datos recibidos.

El algoritmo principal será NEAT. El motivo de la elección es que será una introducción simple a las redes neuronales cuyo funcionamiento ya he contrastado en varios desarrollos. Además pythoncuenta con una librería que permite el empleo de éstas redes neuronales.

El proceso de desarrollo se basa en videos de YouTube que explican el funcionamiento de estas redes neuronales y de la propia librería NEAT.

El objetivo es meramente académico y se dará constancia de los proyectos en los que se basa.


Dividiremos el proyecto en dos pruebas diferentes, en ambos se trata de usar vehículos autónomos:

- Sistema detección de señalización o adversidades en el terreno.
    - Subida y etiquetado de imágenes a modo de señal de tráfico u obstáculo en el terreno. Es una simulación de reacción ante las características de la calzada.
    - Para realizar esta operación, se facilitará la imagen del terreno de simulación y se podrá etiquetar puntos en el espacio con un tipo de etiqueta(STOP, 120, 50, presencia de piedras).
    - El vehículo tendrá preprogramadas las actuaciones ante dichos elementos.
        - STOP: parar el vehículo durante 2 segundos.
        - 120: aumentar max_vel a 120 km/h (probar cuál sería la velocidad máxima para averigual qué coeficiente es el óptimo para la máxima velo en esta simulación).
        - 50: disminuir la velocidad del vehículo para que no se salga de las curvas.
        - presencia de piedras: deterner vehículo y enviar aviso de alerta (KafkaPubSub?)
        

- Sistema de aprendizaje automático con algoritmo NEAT en entrono Pygame.
    - Se trata de emplear un sistema ya desarrollado para construir un sistema de envío de información en tiempo real de parámetros que pudieran estar generando sensores.


# Sistema detección de señalización o adversidades en el terreno.
## FASE 1
Reproducción del desarrollo de un juego básico con Pygame:
- Pygame Car Racing Tutorial #1 - Moving The Car: https://www.youtube.com/watch?v=L3ktUWfAMPg&list=PLzMcBGfZo4-kmY7Nh4kI9kPPnxJ5JMRPj&index=1&t=0s

- Pygame Car Racing Tutorial #2 - Pixel Perfect Collision: https://www.youtube.com/watch?v=WfqXcyF0_b0&list=PLzMcBGfZo4-kmY7Nh4kI9kPPnxJ5JMRPj&index=2

- Pygame Car Racing Tutorial #3 - Computer Car And Path Following: https://www.youtube.com/watch?v=V_B5ZCli-rA&list=PLzMcBGfZo4-kmY7Nh4kI9kPPnxJ5JMRPj&index=3

## RECURSOS OBTENIDOS:
- Uso de Pygame:
    - Mostrar imágenes
    - Mostrar texto
    - Mover el vehículo con asdw
    - Detectar colisiones
    - Creación de vehículo autónomo mediante un 'path' (coordenadas de los puntos que seguirá el vehículo).


# Sistema de aprendizaje automático con algoritmo NEAT en entrono Pygame.
## FASE 1
