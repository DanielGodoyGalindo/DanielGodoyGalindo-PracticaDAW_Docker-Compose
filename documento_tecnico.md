## Documento técnico de configuración de contenedores Docker usando Compose

Este documento contiene los pasos a realizar para instalar y configurar contenedores Docker usando Compose.
La instalación de Docker se realiza en una máquina virtual Ubuntu Server y se accede a ella por medio de SSH con Visual Studio Code.
A continuación se indican todos los pasos por orden para poder levantar tres contenedores de mySQL, phpMyAdmin y Wordpress.
En el repositorio se incluyen los archivos de configuración docker-compose.yml y el fichero de variables de entorno .env


## 0. Actualizar los paquetes del sistema en Ubuntu Server
```bash
sudo apt update
sudo apt upgrade -y
```

## 1. Instalar ssh en Ubuntu server y configurar una clave 
## (a partir de aqui se puede conectar por ssh a Ubuntu Server por medio de Visual Studio Code)
```bash
sudo apt-get install ssh
sudo ssh-keygen
```
Instalar la extensión de SSH en Visual Studio Code para poder crear una conexión con Ubuntu Server

## 2. Instalar docker y docker compose
```bash
sudo apt update
sudo apt install -y docker.io
sudo apt install -y docker-compose
sudo apt install -y docker-compose-v2
```

## 3. Verificar la instalacion
```bash
sudo docker version
sudo docker-compose version
```

## 4. Crear carpeta y ficheros para docker compose
```bash
sudo mkdir practicaDocker
sudo cd practicaDocker
sudo touch docker-compose.yml
sudo touch .env
```
Este paso se podría obviar si se utilizan los ficheros del repositorio, que ya están configurados para levantar los contenedores.
Si se quisieran crear, se podrían configurar desde cero.

## 5. Levantar contenedores despues de configurar los ficheros
```bash
sudo docker-compose up -d
```

## 6. Dar de baja contenedores para reiniciarlos
```bash
sudo docker-compose up -d
```

## 7. Mostrar los contenedores y su estado con la configuración
```bash
sudo docker-compose ps
```

## 8. Mostrar la configuración de redes
```bash
sudo docker network ls
```

## 9. Mostrar la configuración de los volumenes
```bash
sudo docker volume ls
```