# Ejemplo 1: Despliegue de la aplicación guestbook


Paso 1: Crear y navegar al directorio del proyecto

Crea un directorio para tu proyecto

mkdir guestbook-app
cd guestbook-app

Crear el archivo docker-compose.yml:

```
version: '3.1'
services:
  app:
    container_name: guestbook
    image: iesgn/guestbook
    restart: always
    environment:
      REDIS_SERVER: redis
    ports:
      - 8080:5000
  db:
    container_name: redis
    image: redis
    restart: always
    command: redis-server --appendonly yes
    volumes:
      - redis:/data
volumes:
  redis:

```
![image](https://github.com/user-attachments/assets/8e768138-4dea-492a-9384-25654fe5a3ba)

Paso 2: Ejecutar el comando para levantar los contenedores

```
docker compose up -d
```
![image](https://github.com/user-attachments/assets/5ab302ff-e830-4896-b940-1441c02d832b)

Paso 3: Acceder a la aplicación
Accede a la aplicación:

Abre un navegador web y dirígete a:
````http://localhost:8080````

![image](https://github.com/user-attachments/assets/f01cb29c-a3ce-4079-90cf-575cf3eb1eca)


# Ejemplo 2: Despliegue de la aplicación Temperaturas

Paso 1. Crear el directorio para el proyecto
````
mkdir temperaturas-app
cd temperaturas-app
````
Crear el archivo docker-compose.yml:
````
version: '3.1'
services:
  frontend:
    container_name: temperaturas-frontend
    image: iesgn/temperaturas_frontend
    restart: always
    ports:
      - 8081:3000
    environment:
      TEMP_SERVER: temperaturas-backend:5000
    depends_on:
      - backend
  backend:
    container_name: temperaturas-backend
    image: iesgn/temperaturas_backend
    restart: always
````

![image](https://github.com/user-attachments/assets/01223599-fe6a-4655-ae1f-ad37b65cbc8d)

Paso 2: Levantar los contenedores


````
docker compose up -d
````


![image](https://github.com/user-attachments/assets/2b4572da-37d3-4276-adf8-f006f6faa826)

Paso 3: Acceder a la aplicación
Accede a la aplicación:

Abre un navegador web y dirígete a:
````http://localhost:8081````

![image](https://github.com/user-attachments/assets/9a3e948d-c657-4073-9640-d9967ec9006a)


# Ejemplo 3: Despliegue de WordPress + Mariadb
Paso 1:Crear el directorio para el proyecto
````
mkdir wp
cd wp
````
Crear el archivo docker-compose.yml:

![image](https://github.com/user-attachments/assets/71b695bf-230c-452c-bea8-c09ffbf145f3)

Paso 2: Levantar los contenedores


````
docker compose up -d
````
![image](https://github.com/user-attachments/assets/f858143c-c812-4fd3-bd64-bdc61e747154)

Paso 3: Acceder a la aplicación
Accede a la aplicación:

Abre un navegador web y dirígete a:
````http://localhost````

Una vez dentro, podemos continuar para instaalr wordpress
![image](https://github.com/user-attachments/assets/54107954-764c-4867-9770-bb4d107295c0)


![image](https://github.com/user-attachments/assets/0f92a671-7925-4f38-bf36-10201268a4f2)
