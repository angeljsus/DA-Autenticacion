# Autenticación con Directorio Activo

### Descripción
Realizar peticiones para la autenticación de usuarios registrados en el directorio activo.

### Parámetros necesarios
* **loginUsr:** el nombre del usuario que va a autenticarse.
* **passUsr:** contraseña que pertenezca al usuario que se autentificará.
* **cveAplicacion**: clave de aplicación proporcionada por su registro para utilizar el servicio.

### Autenticar y obtener CURP
Existe el siguiente método de autenticación para realizar peticiones por medio de `GET` y es necesario realizarla sobre la siguiente ruta, modificando las variables pasadas por el parametro *(user, password, keyApp)*:
```shell
https://intranet.wapp2.inegi.gob.mx/sistemas/informaticos/ws/v2/ldap.asmx/ObtenerUsrCURP?
loginUsr=user&passUsr=password&cveAplicacion=keyApp
```
Con el método de autenticación, es posible recibir una de las siguientes respuestas:
##### Autenticado
```xml
<?xml version="1.0" encoding="utf-8"?>
    <string xmlns="http://tempuri.org/">CURP000000XXXXXX00</string>
```
##### No Autenticado
```xml
<?xml version="1.0" encoding="utf-8"?>
    <string xmlns="http://tempuri.org/">No autenticado</string>
```
