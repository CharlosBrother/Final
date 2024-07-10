# App Apache

Ver Dockerfile para la creacion y despliegue de la App

## Formatear y montar un volumen en un directorio a elección

Para crear y montar un volumen en un directorio a elección, hacemos los siguientes pasos:

```
sudo mkfs.ext4 /dev/sdX
sudo mkdir -p /mnt/mi_volumen
sudo mount /dev/sdX /mnt/mi_volumen
```

## Para lanzar un contenedor utilizando la imagen 'ubuntu/apache2' y montar el directorio /var/www/html con el directorio asociado al volumen creado, usamos los siguientes comando:

```
docker pull ubuntu/apache2
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
sudo cp index.html /mnt/mi_volumen/
```

## Configuración del Proxy Reverso (Nginx)
Para configuracion de proxy reverso ver Proxy.conf
