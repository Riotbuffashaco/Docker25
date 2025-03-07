# 1. Creación de la VPC

## Paso 1: Crear la VPC y subredes

![imagen](https://github.com/user-attachments/assets/3a7d8631-4de0-46d4-8da3-d1baaeafcdc2)

## Paso 2: Crear y Asociar un Internet Gateway

En la sección Internet Gateways, creamos un nuevo IGW:

![imagen](https://github.com/user-attachments/assets/ee0c1e6b-aa0a-42b3-bf12-c02fab265471)

La conectamos a la vpc

![imagen](https://github.com/user-attachments/assets/11b4b9b2-d872-414c-a76f-ca0a8205d6d4)

## Paso 3: Configurar la Tabla de Enrutamiento:

Creamos la tabla. Es importante conectarla a la vpc

![imagen](https://github.com/user-attachments/assets/8a4a38b3-a2b9-4dad-974e-e760e312e50b)


# 2. Configuración de RDS

## Paso 1: Accedemos a RDS y creamos una nueva base de datos.

seleccionamos mysql
![imagen](https://github.com/user-attachments/assets/cb9b34ba-4466-43be-9019-fd9016045f64)

La configuracion debe quedar así:

![imagen](https://github.com/user-attachments/assets/670b22c6-594a-4ecb-92d0-c3ba8d923ef4)
![imagen](https://github.com/user-attachments/assets/e7cca03b-b61b-4a52-8799-2d26491320f8)
![imagen](https://github.com/user-attachments/assets/bbd7f438-587e-43ef-b748-16c2d7db12bf)
![imagen](https://github.com/user-attachments/assets/520bbe56-3a7e-47f1-b615-0b1833aab258)

## Paso 2: Creación de EFS

En EFS, creamos un nuevo sistema de archivos. Es importante conectarlo a la vpc

![imagen](https://github.com/user-attachments/assets/15ff15a5-8651-4968-8800-1e1bfaf2c3fa)

# 3. Crear la Instancia EC2

## Paso 1: Lanzar una nueva instancia

![imagen](https://github.com/user-attachments/assets/6615882c-2765-43ff-b483-72df6c6de051)

![imagen](https://github.com/user-attachments/assets/f633a223-51b1-4f6e-8b5d-18e7c26b851b)

![imagen](https://github.com/user-attachments/assets/b7f08405-f295-44f6-9587-f0aab5c86e9c)

## Paso 2: Conectar con putty

![imagen](https://github.com/user-attachments/assets/f18480e6-a2ab-4d05-8572-5938c7fe4ab8)

Pegamos esa direccion en Putty

 ![imagen](https://github.com/user-attachments/assets/13b4dd1e-ba3e-466d-bdad-9cf4236c6b8c)

Agregamos la clave PPK

 ![imagen](https://github.com/user-attachments/assets/fd8d612a-ce71-41bc-bdcb-7e3ec82ad3ff)

 y nos logueamos como root.


 # 4. Instalación Wordpress

Dentro de la instancia, usaremos los comandos:

```
sudo apt update
sudo apt install apache2
```

![imagen](https://github.com/user-attachments/assets/d7a9d170-f196-4117-9bf2-9228dbe91fba)


sudo systemctl start apache2
sudo systemctl enable apache2
sudo apt install php7.4 libapache2-mod-php7.4 php7.4-cli php7.4-mysql
sudo systemctl restart apache2
```

Para instalar PHP y Apache 


![imagen](https://github.com/user-attachments/assets/c22de3d7-5606-4daa-9a4c-f347cd45f4c0)



