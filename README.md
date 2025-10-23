# Descripción del laboratorio
Creación de servidor con y sin hilos para evidenciar la diferencia de conexiones que puede manejar y como puede escalar un servidor de forma horizontal, sumado a la creación de un microservicio para verificar NRCs para observar como se puede distribuir responsabilidades en diversos nodos de la aplicación.

# Integrantes del grupo
- Rubén Benavides 
- Joan Cobeña 
- Edison Verdesoto 

## Servidor sin hilos
Servidor en Python utilizando sockets que permite el registro, actualización, listado y eliminación de calificaciones recibiendo comandos con el formato de ACCION|JSON_Informacion que persiste la información usada en un archivo 'calificaciones.csv'

## Servidor con hilos
Igual que el servidor sin hilos pero aprovechando la concurrencia con los hilos del paquete threading y que verifica si los registros y actualizaciones se hacen a NRCs válidos conectandose y llamando a la función de otro servidor.

## Cliente
Cliente en Python que a través de sockets y una interfaz de línea de comandos envía los comandos formateados al servidor con la acción y el JSON con la información a utilizar.

# Estructura de directorios

laboratorio2/

├── con_hilos/

│   ├── calificaciones.csv

│   ├── client.py

│   └── server.py

├── sin_hilos/

│   ├── calificaciones.csv

│   ├── client.py

│   └── server.py

├── nrcs_server.py

└── nrcs.csv

# Instrucciones de ejecución

## Para el servidor sin hilos

1. En la terminal acceder a la carpeta sin_hilos
2. Ejecutar el servidor con python server.py
3. Probar las funcionalidades ejecutando el cliente con python client.py

## Para el servidor con hilos

Desde la raíz del proyecto

1. Crear y/o modificar el archivo de nrcs.csv con las materias que serán válidas para el sistema.

2. Ejecutar primero el servidor con el servicio de verificación de NRCs con python nrcs_server.py

3. En la terminal acceder a la carpeta con_hilos
4. Ejecutar el servidor con python server.py
5. Probar las funcionalidades ejecutando el cliente con python client.py

# Ejemplos de uso

## Registro de una calificación en el servidor sin hilos

## Archivo modificado al asignar una calificación en el servidor 

## Listado de las calificaciones igual al archivo

## Bloqueo y espera de los clientes con el servidor sin hilos con múltiples clientes

## Múltiples conexiones abiertas en el servidor con hilos

## Registro de una calificación en el servidor con hilos con un NRC inválido

## Registro de una calificación en el servidor con hilos con un NRC válido

## Actualización de una calificación con una Materia/NRC inválido

## Actualización de una calificación con un NRC válido

## Listado de las calificaciones registradas en los múltiples clientes igual al archivo

