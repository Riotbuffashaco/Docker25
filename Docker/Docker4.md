# Ejemplo 1: Crear una red personalizada en Docker

Utilizaremos el comando docker network create para crear una red personalizada

![image](https://github.com/user-attachments/assets/a787d114-2bf9-41ea-9132-b2df0f6bc4c4)

Vamos a crear dos contenedores conectados a la red
![image](https://github.com/user-attachments/assets/40c61852-617f-4968-90fd-61c9623dc72f)

Ver los contenedores en ejecución: Puedes listar los contenedores en ejecución con el comando:

```
docker ps
```
![image](https://github.com/user-attachments/assets/db02cf7c-b6af-4ad0-a54b-2c4866b84a48)

# Ejemplo 2: Crear un volumen Docker y montar un contenedor

Creamos un volumen llamado volumendocker con el siguiente comando:

```
docker volume create volumendocker
```
Creamos un contenedor que monte el volumen volumendocker y escriba datos en él:

![image](https://github.com/user-attachments/assets/b457019b-133f-4a10-a1b2-034d0347725e)

docker run -d --name contenedor_volumen -v volumendocker:/data alpine sleep 3600
![image](https://github.com/user-attachments/assets/ac12b73c-c254-495f-b3dc-0c0a49168b77)


# Ejemplo 3: Conectar dos contenedores a la red predeterminada bridge

Primero, creamos un contenedor llamado contenedor1 usando la imagen nginx y lo conectamos a la red bridge
Creamos otro contenedor llamado contenedor2 usando la imagen alpine y lo conectamos a la misma red bridge.

```
docker run -d --name contenedor1 --network bridge nginx
docker run -d --name contenedor22 --network bridge alpine ping contenedor12
```

Inspeccionamos los contenedores para verificar que están conectados correctamente a la red bridge con:

![image](https://github.com/user-attachments/assets/aba3eb86-fddf-4a66-b70c-6d95886f4b80)

![image](https://github.com/user-attachments/assets/b4e53ba7-455a-4a3d-b17b-f9156850e896)
