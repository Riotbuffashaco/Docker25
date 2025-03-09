Para instalar docker

Paso 1.  Instalaremos dependencias necesarias usando:

```
sudo apt install apt-transport-https ca-certificates curl software-properties-common -y
```

![image](https://github.com/user-attachments/assets/d19ff2b7-5704-4db8-9d04-2d440a644dca)


Paso 2. Docker necesita una clave GPG para asegurarse de que el software descargado es legítimo. Usaremos el comando:

```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

Y agregaremos el repositorio de Docker.

```
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```

Paso 3. Instalamos Docker y comprobaremos su instalación. 

```
sudo apt install docker-ce -y
```

Para comprobar su instalacion escribiremos:

```
sudo docker --version
```

![image](https://github.com/user-attachments/assets/cd1cf83e-72c5-4403-bbff-1d2302181bd9)

Obtendremos la versión 28.0 de Docker
