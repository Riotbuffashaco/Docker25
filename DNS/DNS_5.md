
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

        auth-nxdomain no;    # conform to RFC1035
        listen-on-v6 { any; };
};

```

![image](https://github.com/user-attachments/assets/137dcb1c-b248-48d9-932c-83edc6b1331d)


Comprobaremos la sintaxis con:
```
sudo named-checkconf
```

No da error

![image](https://github.com/user-attachments/assets/c23b3412-b500-4202-8e79-d52825fad1c2)


```
sudo systemctl status bind9

```
















![image](https://github.com/user-attachments/assets/137dcb1c-b248-48d9-932c-83edc6b1331d)

![image](https://github.com/user-attachments/assets/ef7d5ade-b566-4340-a64d-5fe40aa38cd2)




## Paso 2: Configuración de BIND9 Forwarding:


![image](https://github.com/user-attachments/assets/a8b99699-66bc-4e54-a5fb-0f5d2780c7b9)






## Paso 3: Syslog:


![image](https://github.com/user-attachments/assets/43309c7f-b028-4978-9cca-52f57db88b2e)


