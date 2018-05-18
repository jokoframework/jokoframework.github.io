Joko Security
*************

Introducción
============
Es una extensión de spring-security que provee la capacidad de realizar autenticación y autorización por medio de JSON Web Tokens (JWT). Permite trabajar con tokens de actualización (Refresh Token) y de acceso (Access Token), se puede utilizar de dos formas:
 
- Como un componente separado actuando de emisor de tokens
- Incluido en una aplicación web como una librería

**Repositorio:** https://github.com/jokoframework/security

**Versiones:** https://github.com/jokoframework/security/releases

**Javadoc:** https://jokoframework.github.io/security

|
|
|

Conceptos de Token
============
Un token es un permiso particular que garantiza al poseedor acceso a ciertos recursos. Los tokens son firmados por joko-security con una clave secreta, por lo tanto no pueden ser alterados. Esto permite a Joko-security realizar la validación en memoria de los tokens. Por ejemplo: un token extemporáneo se rechaza sin mayor chequeo.

Realizar las validaciones en memoria sin tener que tocar la base de datos permite a los sistemas que utilizan joko-security escalar con mayor rapidez al ser en gran medida stateless.

Los tokens en Joko siguen el standard `JWT (JSON Web Tokens) <https://jwt.io/introduction/>`_ .


Tipos de Token
============

Existen dos tipos de token:

----------------------------------
Refresh Token
----------------------------------

Cuando un usuario se autentica al sistema recibe un refresh token. Este token permite al usuario acceder al sistema por un tiempo prolongado pero con pocos permisos de acceso. #### Un refresh token tiene información necesaria para obtener un nuevo access token. #### Un access token sirve para realizar operaciones.

Dependiendo del security profile el sistema devolverá un refresh token con mayor o menor tiempo de vida. Por ejemplo si el usuario accede desde una aplicación web se podría dar un token de una semana, y si accede desde la web en términos de horas. Si el usuario no utiliza la aplicación por 1 (una) semana, entonces necesitará realizar un nuevo login (esto es aceptable desde el punto de vista UX). Los refresh token son especialmente útiles para las aplicaciones móviles en las cuales es molesto pedir el usuario en cada momento la autenticación.


**Guardar el token de refresh de manera segura**

En el caso de una aplicación móvil se tendría que guardar en el key store, y en el caso de una aplicación Web en los :term:cookies (NO guardarlos en WEB storage)


----------------------------------
Access Token
----------------------------------

Permite al usuario realizar todas las operaciones que su perfil permita.

Un token de acceso tiene un tiempo de vida corto, y la aplicación tendrá que renovar el token de acceso antes de que este fenezca. Esto crea la sensación al usuario de estar siempre conectado, mientras que también brinda un mayor nivel de seguridad.

Para mayor seguridad el token de acceso se debería de sostener solo en memoria.
