# Springboot-Kubernetes-Ingress
En este repo encontraran los archivos necesarios para levantar 2 instancias de una Spring Boot App con Kubernetes y usar el balanceador Ingress de Kubernetes con SSL en el port 443.

En primer instancia, en la Carpeta Docker encontraran los Dockerfiles que crean las Instancias de Docker, el mismo esta subido al HUB publico mio el cual se utiliza en el Deployment.yml que crea las instancias en Kubernetes.

En los archivos Deployment.yml, Service.yml esta la definicion como comente de las SpringBoot App, la configuracion del Service con 2 Instancias y por ultimo esta el Balanceador.yml que contiene la configuracion de Ingress en el port 443 y por ultimo el Secrets.txt que contiene la linea para crear la entrada de configuracion del certificado generado para el SSL del Ingress, que tambien estan incluidos dentro del repositorio.

De todos modos si no quieren abrir el archivo, con esta linea se agrega el certificado creado y cargado en el repo:
 - #kubectl create secret tls examen-tls --key tls.key --cert tls.crt

Por ultimo, hicimos una edicion del /etc/hosts, colocando la IP del Kubernetes: https://192.168.99.100 para que abra como https://minikube/

El Hosts tiene esta linea:

192.168.99.100 minikube

Saludos
Santiago Rollheiser
