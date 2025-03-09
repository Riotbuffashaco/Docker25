


## Descargar la imagen de Ubuntu:


```
docker pull ubuntu
```

![image](https://github.com/user-attachments/assets/fdb80d4f-68d6-4f89-9c6b-21bafd53eb0b)

## Descargar la imagen de hello-world:

```
docker pull hello-world
```

![image](https://github.com/user-attachments/assets/8628fcd5-4a19-4697-ac85-c25c33652799)

## Descargar la imagen de nginx:

```
docker pull nginx
```

![image](https://github.com/user-attachments/assets/b9f44b8a-b249-4f86-9e45-08cfbe1589a2)

## Mostrar un listado de todas las imágenes:

```
docker images
```

![image](https://github.com/user-attachments/assets/2c80f17b-a59d-429f-af78-39214adb9a38)

## Ejecutar un contenedor hello-world y darle el nombre “myhello1”:

```
docker run --name myhello1 hello-world
```

![image](https://github.com/user-attachments/assets/2b5b1865-880d-4887-9793-e5573871dd8b)

## Ejecutar un contenedor hello-world y darle el nombre “myhello2”:

```
docker run --name myhello2 hello-world
```

![image](https://github.com/user-attachments/assets/b2631179-ce48-4686-8017-935043079e02)

## Ejecutar un contenedor hello-world y darle el nombre “myhello3”:

```
docker run --name myhello3 hello-world
```

![image](https://github.com/user-attachments/assets/0a107da5-7a49-49ad-9119-991f74ba33c2)

## Mostrar los contenedores que se están ejecutando:

```
docker ps
```

![image](https://github.com/user-attachments/assets/4160bc37-3e67-4522-93de-51a01eb0e6dd)

## Parar el contenedor myhello1:

```
docker stop myhello1
```

## Parar el contenedor myhello2:

```
docker stop myhello2
```

## Borrar el contenedor “myhello1”:

```
docker rm myhello1
```

## Borrar todos los contenedores detenidos:

```
docker rm $(docker ps -a -q)
```

