# Activity 6

Crea un fichero de zona para "marisma.intranet", además de la zona de resolución inversa

En la zona se definirán los siguientes FQND:
Servidor DNS: ns1
Servidor fpt: ftp1
Servidores de correo: mail1, mail2
Servidores web: www, departamentos


## Paso 1: Instalación de BIND9:

Primero, instala BIND9 en tu servidor:

```
sudo apt-get update
sudo apt-get install bind9 bind9utils bind9-doc
```


## Paso 2: Configurar el archivo named.conf.local
Editaremos los archivos de configuracion local, dondde configuraremos las zonas Directa e Inversa.

```sudo nano /etc/bind/named.conf.local```

Una vez dentro, definiremos las zonas.

```
zone "marisma.intranet" {
    type master;
    file "/etc/bind/zones/db.marisma.intranet";
};

zone "1.168.192.in-addr.arpa" {
    type master;
    file "/etc/bind/zones/db.192.168.1";
};
```
![image](https://github.com/user-attachments/assets/33f06d43-dc1c-4e46-9712-c5aa22352d8e)

## Paso 3: Creación de Zonas Directa e Inversa.

Crearemos una carpeta para las zonas dentro del directorio bin9 llamado "Zones"

Crearemos además, dentro de la carpeta, los archivos de las zonas.

Z.D --> ```sudo nano /etc/bind/zones/db.marisma.intranet```

Z.I --> ```sudo nano /etc/bind/zones/db.192.168.1```

Según el enunciado definimos la Zona Directa como:

```
;
;
$TTL    604800
@       IN      SOA     ns1.marisma.intranet. admin.marisma.intranet. (
                              2         ; Número de serie
                         604800         ; Refrescar
                          86400         ; Reintentar
                        2419200         ; Expirar
                         604800 )       ; TTL mínimo
;
@       IN      NS      ns1.marisma.intranet.

ns1     IN      A       192.168.1.2
ftp1    IN      A       192.168.1.3
mail1   IN      A       192.168.1.4
mail2   IN      A       192.168.1.5
www     IN      A       192.168.1.6
departamentos   IN      A       192.168.1.7

@       IN      MX      10      mail1.marisma.intranet.

```
![image](https://github.com/user-attachments/assets/d0c53861-fd29-44bd-8825-f323cb42d83a)


Y haremos lo mismo con la Zona Inversa:

```
; 
;
$TTL    604800
@       IN      SOA     ns1.marisma.intranet. admin.marisma.intranet. (
                              2         ; Número de serie
                         604800         ; Refrescar
                          86400         ; Reintentar
                        2419200         ; Expirar
                         604800 )       ; TTL mínimo
;
@       IN      NS      ns1.marisma.intranet.

2       IN      PTR     ns1.marisma.intranet.
3       IN      PTR     ftp1.marisma.intranet.
4       IN      PTR     mail1.marisma.intranet.
5       IN      PTR     mail2.marisma.intranet.
6       IN      PTR     www.marisma.intranet.
7       IN      PTR     departamentos.marisma.intranet.
```

![image](https://github.com/user-attachments/assets/08747547-3e69-4ef0-8dfa-0d733e88a66f)

## Paso 4: Comprobacion:

Reiniciamos los servicios y comprobaremos la creacion de las Zonas.

```
sudo service bind9 restart
sudo named-checkconf 
```

Para la Zona Directa
```
sudo named-checkzone marisma.intranet /etc/bind/zones/db.marisma.intranet
```

Para la Zona Inversa
```
sudo named-checkzone 1.168.192.in-addr.arpa /etc/bind/zones/db.192.168.1
```

![image](https://github.com/user-attachments/assets/ae968a50-75a2-4e6c-8b20-1dd9de5ad20c)

