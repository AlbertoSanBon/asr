# Entrega 2

Iniciamos la práctica realizando un gcloud init seleccionando nuestro proyecto:

!["gcloud init"](https://github.com/AlbertoSanBon/asr/blob/105808da0257c6dec7ee74c78fed2d021247aba1/practica6entrega2/imgs/gcloud%20init.png)
!["gcloud init 2](https://github.com/AlbertoSanBon/asr/blob/83f90587066f472159189fce5e112dc8ec87c000/practica6entrega2/imgs/gcloud%20init%20comprobacio.png)

### Creación del Cluster GKE

1. Crearemos un archivo config.ini, para tener las variables de configuración disponibles en nuestro script.
2. Establecemos nuestra zina de procesamiento predeterminada.

![](https://github.com/AlbertoSanBon/asr/blob/83f90587066f472159189fce5e112dc8ec87c000/practica6entrega2/imgs/Introduccion1_Creamos%20config%20y%20zone%20(1).png)

3. Creamos un cluster GKE.

![](https://github.com/AlbertoSanBon/asr/blob/83f90587066f472159189fce5e112dc8ec87c000/practica6entrega2/imgs/Introduccion1_Creamos%20cluster(2).png)
![](https://github.com/AlbertoSanBon/asr/blob/83f90587066f472159189fce5e112dc8ec87c000/practica6entrega2/imgs/Introduccion1_Creamos%20cluster(2)Comprobacion.png)

4. Una vez ha terminado la creación del cluster, hacemos uso de un manifiesto de despliegue, php-apache.yaml para demostrar el autoescalado horizontal de pods. Este lleva a cabo tareas computacionalmente costosas.

![](https://github.com/AlbertoSanBon/asr/blob/83f90587066f472159189fce5e112dc8ec87c000/practica6entrega2/imgs/Introduccion1_Creacion%20y%20aplicacion%20manifiesto%20(3).png)

### Escalado de pods con HPA

1. Comenzamos inspeccionando los despliegues que se encuentran en funcionamiento en nuestro cluster.

![](https://github.com/AlbertoSanBon/asr/blob/83f90587066f472159189fce5e112dc8ec87c000/practica6entrega2/imgs/Introduccion2_Inspeccion%20despliegues%20activos%20en%20el%20cluster%20(4).png)

2. Aplicamos el autoescalado horizontal del pods (HPA). Esto modificará nuestro número de pods en el cluster en función de la carga de trabajo.

![](https://github.com/AlbertoSanBon/asr/blob/83f90587066f472159189fce5e112dc8ec87c000/practica6entrega2/imgs/Introduccion2_Aplicamos%20el%20HPA%20autoescalado%20horizontal%20de%20pods%20(5).png)

3. Comprobamos el estado del HPA.

![](https://github.com/AlbertoSanBon/asr/blob/83f90587066f472159189fce5e112dc8ec87c000/practica6entrega2/imgs/Introduccion2_Comprobamos%20estado%20del%20HPA%20(6).png)

### Autoescalado del cluster

1. Activamos el autoescalado horizontal de cluster.

![](https://github.com/AlbertoSanBon/asr/blob/83f90587066f472159189fce5e112dc8ec87c000/practica6entrega2/imgs/Introduccion3_Activamos%20autoescalado%20horizontal%20del%20cluster%20(7).png)
![](https://github.com/AlbertoSanBon/asr/blob/83f90587066f472159189fce5e112dc8ec87c000/practica6entrega2/imgs/Introduccion3_Activamos%20autoescalado%20horizontal%20del%20cluster%20(7)Comprobacion.png)

2. Comprobamos los nodos disponibles.

![](https://github.com/AlbertoSanBon/asr/blob/83f90587066f472159189fce5e112dc8ec87c000/practica6entrega2/imgs/Introduccion3_Comprobamos%20nodos%20(8).png)

### Test con alta demanda

Para ver como los recursos gestionan un pico de demanda, en una nueva terminal enviaremos un loop infinito de quereis a nuestro servicio php-apache.

![](https://github.com/AlbertoSanBon/asr/blob/83f90587066f472159189fce5e112dc8ec87c000/practica6entrega2/imgs/Introduccion4_Gestion%20pico%20demanda%20(9_1).png)

Mientras en nuestra terminal principal, podremos ver como aumenta el target.

![](https://github.com/AlbertoSanBon/asr/blob/83f90587066f472159189fce5e112dc8ec87c000/practica6entrega2/imgs/Introduccion4_Gestion%20pico%20demanda%20(9_2).png)

## Entrega 2

1. Creamos el siguiente archivo Dockerfile para que tenga instalado el comando "ab".

![](https://github.com/AlbertoSanBon/asr/blob/83f90587066f472159189fce5e112dc8ec87c000/practica6entrega2/imgs/Entrega2_Creamos%20Dockerfile%20(10).png)

2. Generamos la imagen docker y comprobamos que se ha creado correctamente.

![](https://github.com/AlbertoSanBon/asr/blob/bc115350fffeab947e8a0a962a26aa06869fd9f3/practica6entrega2/imgs/Entrega2_Buildeamos%20la%20imagen%20(11).png)
![](https://github.com/AlbertoSanBon/asr/blob/bc115350fffeab947e8a0a962a26aa06869fd9f3/practica6entrega2/imgs/Entrega2_Comprobamos%20imagen%20creada%20(12).png)

3. Tagueamos la imagen a Google.

![](https://github.com/AlbertoSanBon/asr/blob/bc115350fffeab947e8a0a962a26aa06869fd9f3/practica6entrega2/imgs/Entrega2_Tagueamos%20la%20imagen%20a%20google%20(13).png)
![](https://github.com/AlbertoSanBon/asr/blob/bc115350fffeab947e8a0a962a26aa06869fd9f3/practica6entrega2/imgs/Entrega2_Tagueamos%20la%20imagen%20a%20google%20(13)Comprobacion.png)

4. Definiremos un job.yaml el cual lance nuestra imagen. Lo configuraremos de la siguiente manera.

![](https://github.com/AlbertoSanBon/asr/blob/bc115350fffeab947e8a0a962a26aa06869fd9f3/practica6entrega2/imgs/Entrega2_Creamos%20job_yaml%20(14).png)

# RESULTADO

Lanzamos el siguiente comando.

![](https://github.com/AlbertoSanBon/asr/blob/bc115350fffeab947e8a0a962a26aa06869fd9f3/practica6entrega2/imgs/Entrega2_FINAL%20comando%20(15).png)
Vemos como se crea correctamente el mycronjob.

Ahora con ayuda de la herramienta Lens, podemos ver un informe de estos logs.

![](https://github.com/AlbertoSanBon/asr/blob/bc115350fffeab947e8a0a962a26aa06869fd9f3/practica6entrega2/imgs/ComprobacionFunciona1.png)
![](https://github.com/AlbertoSanBon/asr/blob/bc115350fffeab947e8a0a962a26aa06869fd9f3/practica6entrega2/imgs/ComprobacionFunciona2.png)
