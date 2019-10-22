Uso Python Version 3

CREAR UN NUEVO PROYECTO Django-Python
    django-admin startproject xxxxxxx   --"xxxxxxx" representa el nombre del directorio del proyecto                                        --  que vamos a crear.

ESTRUCTURA DE ARCHIVOS
    mysite/                 --Se puede cambiar este nombre de directorio
        manage.py           --Archivo usado para configurar Django
        mysite/             --Directorio donde esta almacenado el proyecto Python. Se
                            --  entiende al nombre como un modulo Python. Esta info es
                            --  importante en caso de que queramos importarlo como modulo
            __init__.py     --Archivo usado como indicador de que esta carpeta tiene un modulo Python
            settings.py     --Configuraciones de Django
            urls.py         --Configuracion de rutas del proyecto
            wsgi.py         --Para uso avanzado de conexion con otros servidores

COMANDO PARA CORRER EL SERVIDOR
    python3 manage.py runserver
    python3 manage.py runserver XXXX         --"XXXX" representa el numero de puerto en el que correra
                                            --  nuestra app.
COMANDO PARA CREAR UNA APLICACION
    python3 manage.py startapp xxxxxxx       --Donde "xxxxxxx" representa el nombre de la app