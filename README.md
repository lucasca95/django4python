Uso Python Version 3

CREAR UN NUEVO PROYECTO Django-Python
    django-admin startproject xxxxxxx   --"xxxxxxx" representa el nombre del directorio del proyecto                                        --  que vamos a crear.

ESTRUCTURA DE ARCHIVOS
    nombre_del_proyecto/        --Se puede cambiar este nombre de directorio
        manage.py               --Archivo usado para configurar Django
        nombre_del_proyecto/    --Directorio donde esta almacenado el proyecto Python. Se
                                --  entiende al nombre como un modulo Python. Esta info es
                                --  importante en caso de que queramos importarlo como modulo
            __init__.py         --Archivo usado como indicador de que esta carpeta tiene un modulo                          --  Python
            settings.py         --Configuraciones de Django
            urls.py             --Configuracion de rutas del proyecto
            wsgi.py             --Para uso avanzado de conexion con otros servidores

COMANDO PARA CORRER EL SERVIDOR
    python3 manage.py runserver
    python3 manage.py runserver XXXX         --"XXXX" representa el numero de puerto en el que correra
                                            --  nuestra app.
COMANDO PARA CREAR UNA APLICACION
    python3 manage.py startapp xxxxxxx       --Donde "xxxxxxx" representa el nombre de la app


------------------------------- YA DENTRO DE LA APLICACION ---------------------------------------
nombre_de_la_app/
    __init__.py
    admin.py
    apps.py
    migrations/
        __init__.py
    models.py
    tests.py
    views.py                --Controla las vistas de la app

Se recomienda tener un archivo de configuracion de rutas dentro de cada app, por lo que para crearla corremos
    touch urls.py
Es importante asociar en nombre_del_proyecto/urls.py al arhivo de rutas dentro de la app.

En nombre_de_la_app/models.py se guardan los modelos de la app.
    Se escriben en Python. Los constructores reciben como argumento "models.Model"
    Para referenciar a la base de datos usamos los tipos de datos que vienene en el módulo "models":
    - models.CharFiels(max_length=xxx)
    - models.DateTimeField('xxx')
    - models.IntegerFiled(default=xxx)
    - models.ForeignKey("Clase", on_delete=models.TipoDeAcción)

Para poder hacer administrable la aplicación debemos modificar el archivo
    nombre_de_la_app/admin.py

------------------------------- Uso de la shell ---------------------------------------
Se abre con 
    python3 manage.py shell
Las consultas se hacen escribiendo el nombre de la tabla con mayúscula. Algunos ejemplos:
    Tabla1.objects.all()                            --Trae todo
    Tabla1.objects.filter(id=xxx)                   --Trae elemento con id "xxx"
    Tabla1.objects.filter(campo1__startswith='xxx') --Trae los elementos cuyo atributo "campo1" empiece con "xxx"