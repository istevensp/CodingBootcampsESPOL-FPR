## Vistas y Acciones

[Regresar](/CodingBootcampsESPOL-FPR/)


Como se mencionaba en la sección anterior uno de los principios de Redux son las acciones.

<span style="color: #188eac"> Acciones en Redux </span>
===========

* * *

* Entonces, cuando un evento es disparado desde cualquier vista por seleccionar un botón de opción, hacer clic en una casilla de verificación o hacer clic en un botón se denomina acción.
* Las acciones son objetos JSON que contienen información sobre los cambios que deben realizarse en el estado.
* Las acciones son producidas por funciones llamadas creadores de acciones. Es un objeto puro creado para almacenar la información del evento del usuario, y describe un cambio de estado.
* Contiene el tipo de Acción, el tiempo de ocurrencia y qué estados pretende cambiar.

<span style="color: #188eac"> Comportamiento de las acciones </span>
===========

* * *

* Varias partes de su aplicación pueden enviar acciones y la tienda las recibe. Son cargas útiles de información que envían datos de la aplicación a la tienda.
* Son objetos simples de JavaScript que describen QUÉ sucedió, pero no describe cómo cambiará el estado de la aplicación.
* Las acciones se envían a la instancia de su tienda cada vez que desea actualizar el estado de su aplicación.
* Redux requiere que todos los objetos de acción contengan un campo de tipo. Este campo se usa para describir qué tipo de acción se envía y es una constante que exporta desde un archivo.


<p align="center">
<img src="https://3363665679-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-LgMQu802me2gEI8E8bY%2F-Ljo7IWjiQFkcB05xPYH%2F-Ljo7aKNQDeQ9HqgPE5w%2Fkkk.gif?alt=media&token=bb451fcd-f386-45fc-baff-0ef46058008f" width="50%" alt="Banner"/>
</p>