# Configuración de ambiente

En este documento se detallan los pasos a seguir para configurar en una máquina con sistema operativo Linux (64 bits) el ambiente necesario para ejecutar los ejemplos introducidos en el curso.

## Instalación de Miniconda

En esta sección listamos los pasos necesarios para instalar el manejador de paquetes Conda por medio de la instalación de Miniconda. Los pasos necesarios serían:

1. **Descargar miniconda**: 
	```user@node:~$ wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh```
2. **Instalar miniconda**:
	1. Ejecutar el archivo descargado: 
	```user@node:~$ bash Miniconda3-latest-Linux-x86_64.sh```
	2. Aceptar los términos de la licencia.
	3. Indicar un directorio donde instalar Miniconda. Se puede omitir la introducción de una ruta haciendo que miniconda se instale en un directorio por defecto dentro del home del usuario.
	4. Indicar si se desea cargar las variables de entorno de Miniconda de forma automática cada vez que se inicie sesión. La recomendación es que no se carguen por defecto.

## Activar Miniconda

En caso de seleccionar la opción de que no se carguen por defecto las variables de entorno de Miniconda, se deberá de activar de forma manual Miniconda. Para realizar esto se debe de ejecutar:

```user@node:~$ source /path/to/env/bin/activate```

Donde **/path/to/env** es el directorio indicado en el paso 2 de la instalación de Miniconda.

## Crear entornos virtuales en Miniconda

Luego de activar Miniconda, es posible crear entornos virtuales que nos permitan instalar los paquetes necesarios para la ejecución de un código fuente en particular.

### Creación de un entorno virtual

Para crear un entorno virtual en miniconda se debe de ejecutar:
```user@node:~$ conda create --name env```

En particular, en este curso se trabajará con una versión específica de python (3.6) la cual no tiene porque utilizarse por defecto en Miniconda. Por esto es que a la hora de crear un entorno existe la posibilidad de indicar la versión de python que se desea instalar. Para crear un entorno virtual con una versión de python se debe de ejecutar: 
```user@node:~$ conda create --name env python=3.6```

En este ejemplo se creará un entorno con la versión 3.6 de python.

### Creación de un entorno virtual desde un archivo de dependencias

Otra posibilidad para crear un entorno virtual es utilizando un archivo de dependencias perteneciente a un entorno virtual existente. Esto nos permitirá crear una réplica exacta del entorno existente. 

Para obtener las librerías instalar en un entorno virtuales se debe de ejecutar:

```user@node:~$ conda list -e > requirements.txt```

Para crear un entorno desde un archivo de dependencias se debe de ejecutar:

```user@node:~$ conda create --name env --file requirements.txt```

## Activar un entorno virtual

Luego de activar Miniconda, se puede activar un entorno existente ejecutando: 

```user@node:~$ conda activate env```

Donde **env** es el nombre del entorno virtual a activar.
