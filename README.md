# App Apache

Ver Dockerfile para la creacion y despliegue de la App

## Formatear y montar un volumen en un directorio a elección

Para crear y montar un volumen en un directorio a elección, usa el siguiente comando:

```
docker volume create mi_appapache
```

## Para lanzar un contenedor utilizando la imagen 'ubuntu/apache2' y montar el directorio /var/www/html con el directorio asociado al volumen creado, usa el siguiente comando:

```
docker run -d -p 8080:80 -v mi_appapache:/var/www/html --name app-apache ubuntu/apache2
```

## Desplegar el contenedor con Docker Compose: 

```
docker-compose up -d 
```

## Para clonar el repositorio y copiar el fichero index.html de la rama main al punto de montaje del contenedor, sigue estos pasos:

```
git clone https://github.com/CharlosBrother/Final.git
cd Final
git checkout main
cp index.html /var/lib/docker/volumes/mi_appapache/_data/
```

## Configuración del Proxy Reverso (Nginx)
Para configuracion de proxy reverso ver Proxy.conf
