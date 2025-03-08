
# Activity 5

Instala y configura bin9 en primer lugar como servidor caché y por último como forwarding. 

En ambos casos debes:
Comprueba la sintaxis del archivo de configuración (named-checkconf)
Visualiza el archivo log y comprueba que responde adecuadamente (/var/log/syslog)


## Paso 1: Instalar BIND9:

```
sudo apt update
sudo apt install bind9 bind9utils bind9-doc
```

![image](https://github.com/user-attachments/assets/26712e58-f734-4041-8b6c-dd246c4b773a)

## Paso 2: Configuración de BIND9 Caching:

Accedemos a la configuracion de BIN9 con:

```
/etc/bind/named.conf.options
```

Una vez dentro, añadiremos los siguientes parametros:

```
acl goodclients {
    	192.0.2.0/24;
        localhost;
        localnets;
};

options {
        directory "/var/cache/bind";

        recursion yes;
        allow-query { goodclients; };

        dnssec-validation auto;

        auth-nxdomain no;    
        listen-on-v6 { any; };
};

```
![image](https://github.com/user-attachments/assets/ef7d5ade-b566-4340-a64d-5fe40aa38cd2)

Comprobaremos la sintaxis con:
```
sudo named-checkconf
```

No da error

![image](https://github.com/user-attachments/assets/c23b3412-b500-4202-8e79-d52825fad1c2)

## Paso 2: Configuración de BIND9 Forwarding:

Para que funcione como foerwarding, debemos añadir:


```
forwarders {
                8.8.8.8;
                8.8.4.4;
        };
forward only;

```

Cambiaremos los parametros de dnssec para evitar problemas. Por lo que pondremos la validación en "yes"

![image](https://github.com/user-attachments/assets/a8b99699-66bc-4e54-a5fb-0f5d2780c7b9)


volvemos a vomprobar con 
```
sudo named-checkconf
```
![image](https://github.com/user-attachments/assets/6baebab4-3b71-4724-9cc9-210cea3c7cba)

## Paso 3: Syslog:

Para ver el syslog, reinicaremos el servicio y le permitiremos el firewall

```
sudo systemctl restart bind9
sudo ufw allow Bind9
```
Luego, usaremos:

```
sudo tail -f /var/log/syslog
```

![image](https://github.com/user-attachments/assets/43309c7f-b028-4978-9cca-52f57db88b2e)

Vemos que no da Fallos.
