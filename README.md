# DJANGO-MVT-API-

## Realizar instalaciones de dependencias con el entorno activado (.venv): 
# pip install django, pymysql, python-dotenv

## Crear el proyecto: django-admin startproject apiDemo .
## Crear una app llamada empleadoApp:  python manage.py startapp empleadoApp 

## ir a models de empleado y crear los modelos de la base de datos

from django.db import models

# Create your models here.

class Empleado(models.Model):
    id = models.AutoField(primary_key=True)
    nombre = models.CharField(max_lenght=100)
    email = models.EmailField(unique=True)
    telefono = models.CharField(max_length=20,blank=True)


    def __str__(self):
        return f"{self.nombre}({self.email})"

## configurar el admin: 

from django.contrib import admin
from .models import Empleado
# Register your models here.

@admin.register(Empleado)
class EmpleadoAdmin(admin.ModelAdmin):
    list_display = ('id','nombre', 'emil','telefono')
    search_fields = ('nombre', 'email')
    list_filter = ('nombre',)
    ordering = ('nombres',)


##https://www.alwaysdata.com/en/ base de datos y sitio

## VictorGarcia
## cc: 

Crear la base de datos dentro de always. 
Crear el archivo .env para los parametros 

empleadoApp / .env

MYSQL_HOST = mysql-victorgarcia.alwaysdata.net
MYSQL_PORT = 3306
MYSQL_DATABASE = victorgarcia_db
MYSQL_USER = victorgarcia_user
MYSQL_PASSWORD = 4PROGRAMACIONINACAP@2026v

