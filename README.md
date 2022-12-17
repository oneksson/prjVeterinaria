
## Instalación de dependencias
Requirements.txt = Archivo que gestiona todas las dependencias y en que versiones se necesitan.

Generar el archivo con el siguiente comando:

````sh
pip3 freeze > requirements.txt
````

Revisar lo que hay dentro del archivo:
````sh
cat requirements.txt
````
Instalar las dependencias necesarias para contribuir más rápido en proyectos:
````sh
pip3 install -r requirements.txt
````

# Informiación de Django
````sh
https://django-allauth.readthedocs.io/en/latest/installation.html
````

# Primer proyecto

````sh
django-admin startproject myproject
````
Ingresar a la carpeta "myprojecto" y levantar el servidor local:

````sh
cd myproject
````
````sh
python manage.py runserver
````

El proyecto ya está listo. Ahora se le dará un poco
de funcionalidad creando una nueva aplicación.
Para eso, se deberá apagar el servidor web
presionando en la terminal CTRL + C (Windows)
o CTRL + D (Linux) y luego escribir:

````sh
python manage.py startapp myapp
````

El comando anterior creará la carpeta myapp con varios
archivos en su interior. Para indicarle a Django que
la aplicación myapp es parte del proyecto myproject,
debemos editar el archivo de configuración del proyecto
myproject/myproject/settings.py y agregar nuestra
aplicación así:

````sh
INSTALLED_APPS = [
'django.contrib.admin' ,
'django.contrib.auth' ,
'django.contrib.contenttypes' ,
'django.contrib.sessions' ,
'django.contrib.messages' ,
'django.contrib.staticfiles' ,
"myapp.apps.MyappConfig" # <-- Agregamos este elemento.
]
````

Como se puede observar, el proyecto creado vía
django-admin startproject incluye, por defecto,
algunas aplicaciones (django.contrib.admin ,
django.contrib.auth , etc.).
Lo importante es agregar la aplicación indicando
la clase MyappConfig dentro del archivo
myapp/apps.py (creada automáticamente por
el comando python manage.py startapp).
Por último, habrá que iniciar nuevamente el
servidor, que debe estar corriendo para que
el sitio responda.

````sh
python manage.py runserver
````

Nota: El servidor web iniciado con el comando
runserver se ocupará de recargar el código
cada vez que se hacen cambios en los archivos de Python del proyecto o de la aplicación.
No obstante, en algunas ocasiones, particularmente cuando ocurren errores de sintaxis,
será necesario volver a iniciarlo de manera
manual escribiendo nuevamente el comando
anterior.