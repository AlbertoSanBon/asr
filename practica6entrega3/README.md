# Entrega 3

Enlace al github: https://github.com/AlbertoSanBon/asr/tree/main/practica6entrega3

Antes de comenzar habilitamos los servicios cloud.

![](https://github.com/AlbertoSanBon/asr/blob/10e946d0ae84d11da58f8fa3352a962c3bf50458/practica6entrega3/imgs/Habilitamos%20servicios%20cloud%20(1).png)

1. Utilizando un cluster existente, creado como en la entrega 2. Creamos la imagen docker y la guardamos en el contenedor del proyecto.

![](https://github.com/AlbertoSanBon/asr/blob/f4b4cd273cf89e1a9449f0c1e90a2e53647623b1/practica6entrega3/imgs/Creamos%20imagen%20docker%20y%20la%20guardamos%20en%20el%20contenedor%20del%20proyecto%20(2).png)

3. Modificamos en los archivos locust_master-controller.yaml y locust-worker-controller.yaml los parámetros [TARGET_HOST] y [PROJECT_ID].

Archivo locust-master-controller.yaml:
![](https://github.com/AlbertoSanBon/asr/blob/f4b4cd273cf89e1a9449f0c1e90a2e53647623b1/practica6entrega3/imgs/Modificamos%20locust-master-controller_yaml%20(3).png)

Archivo locust-worker-controller.yaml:
![](https://github.com/AlbertoSanBon/asr/blob/f4b4cd273cf89e1a9449f0c1e90a2e53647623b1/practica6entrega3/imgs/Modificamos%20locust-worker-controller_yaml%20(4).png)

5. Desplegamos los nodos Locust master y Locust worker.

![](https://github.com/AlbertoSanBon/asr/blob/f4b4cd273cf89e1a9449f0c1e90a2e53647623b1/practica6entrega3/imgs/Deploy%20locust%20master%20and%20worker%20nodes%20(5).png)

6. Y obtenemos la IP externa del Locust master service para conectarnos.

![](https://github.com/AlbertoSanBon/asr/blob/f4b4cd273cf89e1a9449f0c1e90a2e53647623b1/practica6entrega3/imgs/Obtenemos%20IP%20externa%20del%20locust%20master%20service%20para%20conectarnos%20(6).png)

Si accedemos a esa direccion IP con el protocolo http y añadiendo el puerto 8089. Podemos comprobar los resultados.

![](https://github.com/AlbertoSanBon/asr/blob/f4b4cd273cf89e1a9449f0c1e90a2e53647623b1/practica6entrega3/imgs/Comprobacion%20funcionamiento.png)
![](https://github.com/AlbertoSanBon/asr/blob/f4b4cd273cf89e1a9449f0c1e90a2e53647623b1/practica6entrega3/imgs/Comprobacion%20funcionamiento_2.png)
![](https://github.com/AlbertoSanBon/asr/blob/f4b4cd273cf89e1a9449f0c1e90a2e53647623b1/practica6entrega3/imgs/Comprobacion%20funcionamiento_3.png)

Si repitieramos el proceso aumentando el número de réplicas de pods, observaríamos como aumentaría el número de requests por segundo. También, disminiría la tasa de error.
