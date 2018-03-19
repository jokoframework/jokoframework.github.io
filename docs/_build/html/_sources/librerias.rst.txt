*********
Librerias
*********

joko-utils
==========
Introducción
^^^^^^^^^^^^
**joko-utils** es una librería para Java que contiene *clases* con utilidades varias de modo a facilitar el trabajo a la hora de trabajar sobre el *Backend* de un proyecto.

Instalación o Actualización
^^^^^^^^^^^^^^^^^^^^^^^^^^^
Descargar el proyecto en Github:
	https://github.com/jokoframework/joko-utils

Clases
^^^^^^
JokoConstants
-------------

CsvUtils (CSV - Comma Seperated Values)
---------------------------------------

DateTimeUtils
-------------
Esta clase contiene un montón de utilidades para trabajar con fechas

+-------------------+-------+--------------------------+
|       Método      | Input | Output                   |
+===================+=======+==========================+
|       now()       | n/a   | Devuelve la fecha actual |
+-------------------+-------+--------------------------+
|      today()      | n/a   | Devuelve el dia actual   |
+-------------------+-------+--------------------------+
| getCurrentMonth() | n/a   | Devuelve el mes actual   |
+-------------------+-------+--------------------------+
|  getCurrentYear() | n/a   | Devuelve el año actual   |
+-------------------+-------+--------------------------+

Continuaria hasta tener todos!


DTOUtils (Data Transfer Object)
-------------------------------

EncodeUtils
-----------

EncryptUtils
------------

ExcelUtils
----------

IpUtils
-------

JokoUtilsException
------------------

LocationUtils
-------------

LoggingUtils
------------

NumberUtils
-----------

PdfGenerator
------------

ReflectionUtils
---------------

TXUUIDGenerator (Universally Unique IDentifier)
-----------------------------------------------


Seccion de TO DO y TO FIX
^^^^^^^^^^^^^^^^^^^^^^^^^
Lista de cosas por hacer o que se deben mejorar

--------------------------------------------------------------------------

joko-security
=============
Introducción
^^^^^^^^^^^^
Que es, para que se hizo, etc.

--------------------------------------------------------------------------

Instalación o Actualización
^^^^^^^^^^^^^^^^^^^^^^^^^^^
**joko-security** necesita un repositorio de datos en el cual se almacenan datos para realizar el proceso de autorización. El sistema utiliza JPA (Java Persistence API) de una manera bastante agnóstica a la BD. Sin embargo, actualmente solamente está probado con PostgreSQL 9.3

**Observación**: Favor referir a la guia de upgrade para actualizar desde la versión 0.1.4. Y primero leer los cambios que se introdujeron a partir de la versión 0.1.5.
Inicio desde .sql

El inicio mas sencillo es correr el script .sql correspondiente a la BD que utiliza. Estos scripts se encuentran en /db/sql-initialization

--------------------------------------------------------------------------

Clases
^^^^^^
Clases y Funcionalidades
