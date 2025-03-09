# 1º Parte

## 1. Ejecutamos la imagen "hello-world"
Para verificar que Docker está funcionando correctamente, ejecutamos el comando:
````
docker run hello-world
````
Con esto, descargamos y ejecutamos la imagen hello-world. 

## 2. Mostramos las imágenes Docker instaladas
Para ver qué imágenes tenemos instaladas en nuestro sistema, utilizamos:

````
docker images
````
Nos muestra una lista de todas las imágenes que tenemos disponibles.

## 3. Mostramos los contenedores Docker
Para ver los contenedores que estamos ejecutando, usamos:

````
docker ps
````

## 4. Si queremos ver todos los contenedores, tanto los que están en ejecución como los detenidos, usamos:
````
docker ps -a
````

![image](https://github.com/user-attachments/assets/aa4f4ce3-4dec-42eb-8e92-d8e44b2f2fdd)

![image](https://github.com/user-attachments/assets/deacbe18-6b90-48f0-87e1-f4912c65b570)

![image](https://github.com/user-attachments/assets/cae29cf4-93e1-48cb-98f5-38fc2e5214e9)

![image](https://github.com/user-attachments/assets/ba9f15bc-a881-4e14-80a8-e01181e37fbf)



# 2º Parte.

## 1. Crearemos un dockerfile.

### 1. Clonamos el repositorio getting-started-app de docker:
````
git clone https://github.com/docker/getting-started-app.git
````

### 2. En el directorio que hemos copiado, creamos el dockerfile para editarlo

![image](https://github.com/user-attachments/assets/d38af322-d3b9-43c5-b8fa-8cc5f4f9be5f)

### 3. Añadiremos los parámetros:
```
FROM node:14
WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 8080
CMD ["node", "app.js"]
```

### Construiremos una imagen. En directorio donde está el Dockerfile y ejecutamos:

```
docker build -t nombre_imagen
```

![image](https://github.com/user-attachments/assets/587c2bff-81d8-4634-9cdc-1f0f59a65a09)


# 3º Parte.

## Crearemos una cuenta

![image](https://github.com/user-attachments/assets/39fe4675-b662-45f4-a0e1-32e36c77ff45)

![image](https://github.com/user-attachments/assets/7ef69db5-5e97-4a92-977b-1a062f7aafc9)

![image](https://github.com/user-attachments/assets/e597fb4d-a46e-4461-b895-9fba1ba0a9d3)

Ahora conectaremos la maquina a la cuenta
![image](https://github.com/user-attachments/assets/05a340de-d7e1-4685-b22a-51d5da881814)

![image](https://github.com/user-attachments/assets/af7119f6-75fe-40fb-a585-06cdae2d77ca)

Y subiremos la imagen con el cpmando "push"
![image](https://github.com/user-attachments/assets/a155cb85-1efc-4e50-a47b-e125b7b78b44)

