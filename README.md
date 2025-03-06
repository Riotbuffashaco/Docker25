# Actividades DNS
# DNS
Se debe documentar debidamente las actividades del tema DNS (5, 6 y 8) 

# Práctica 1: AWS


## Creación de la VPC

Vamos a crear un VPC con las siguientes condiciones:
Se trata de montar una infraestructura para una empresa que va a tener dos subredes, una pública y otra privada. 
La zona pública deberá tener salida a Internet a través de un Gateway propio creado ad-hoc para el VPC.

El rango de direcciones del VPC será el CIDR 10.0.0.0/16 y cada una de las dos subredes pública y privada tendrán los CIDR 10.0.1.0/24, 10.0.2.0/24 respectivamente.
Las subredes públicas se llamarán publica_vpc y privada_vpc.

## Creación de EFS, RDS e instalación de wordpress
Sigue las instrucciones de las actividades correspondientes y documentales en Github. La instancia ECS debe crearse en una subred pública y conectarse correctamente con los servicios EFS y RDS para completar la instalación de WordPress.


# Práctica 2: DOCKER

## Despliegue de aplicaciones con Docker
Se propone la realización de de las actividades incluidas en el tema sobre Docker
