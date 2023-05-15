## Uso de middleware

[Regresar](/CodingBootcampsESPOL-FPR/)

<span style="color: #188eac"> Introducción a Middleware </span>
===========

* * *

Las aplicaciones React Redux son comunes en la web hoy en día, debido a su versatilidad, potencial de escala e innumerables características.
El uso de acciones y reductores complementa la arquitectura de su aplicación y le permite mantener su código limpio mientras implementa características complejas.
Sin embargo, cuando necesite usar operaciones asincrónicas, como acciones de despacho, después de recibir la respuesta de un servidor, las acciones y los reductores por sí solos no son suficientes.
Puede interactuar con datos asíncronos en su aplicación React Redux usando middleware. Los cambios de estado en la tienda Redux se realizan activando las acciones proporcionadas por la tienda. El middleware que utilice interceptará la acción.
También puede retrasar las acciones si es necesario, soportando operaciones asíncronas.
Y, una vez que se completa el proceso asíncrono, el resto del flujo de Redux continúa como de costumbre, donde el reductor recibe la acción para calcular el nuevo estado.

<p align="center">
<img src="https://d33wubrfki0l68.cloudfront.net/08d01ed85246d3ece01963408572f3f6dfb49d41/4bc12/assets/images/reduxasyncdataflowdiagram-d97ff38a0f4da0f327163170ccc13e80.gif" width="50%" alt="Banner"/>
</p>

<span style="color: #188eac"> Técnicas de middleware </span>
===========

* * *

* Thunk middleware
* Saga middleware
* Promise-based middleware
* Async/Await middleware

### Redux Thunk

* Redux Thunk es una forma muy fácil de introducir un middleware en Redux.
* Redux Thunk le permite pasar funciones dentro de sus creadores de acciones para crear un Redux asíncrono.
* Permite retrasar el despacho de una acción.
* Permite despachar una acción si se cumple una determinada condición.
* Y pasa dispatch y getState como parámetros a la función devuelta por el creador de la acción o la función interna.

### Ventajas y Desventajas de Thunk

| Ventajas | Desventajas |
|----------|----------|
| Es adecuado para aplicaciones simples.   | No puede actuar directamente en respuesta a una acción.   |
| Permite operaciones asíncronas sin mucho código repetitivo.   | También es difícil manejar los problemas de concurrencia que pueden ocurrir.   |
| Es fácil de configurar e implementar y requiere una curva de aprendizaje más pequeña.    | Es imperativo, por lo que no es muy fácil de probar.  |

<p align="center">
<img src="https://redux-saga.js.org//img/Redux-Saga-Logo-Portrait.png" width="40%" alt="Banner"/>
</p>

### Saga Middleware

* El middleware Saga expone un conjunto de funciones auxiliares, o sagas, para crear efectos declarativos que son objetos simples de JavaScript.
* Utiliza generadores para permitir operaciones asincrónicas.

### Ventajas y Desventajas de Saga Middleware

| Ventajas | Desventajas |
|----------|----------|
| Son fáciles de probar porque las funciones son puras.   | El middleware de Saga no es muy adecuado para aplicaciones simples.   |
| Son predecibles, repetibles y los efectos son declarativos.   | Debe tener el conocimiento de los generadores para comprender completamente los conceptos.   |
| Las sagas pueden viajar en el tiempo y permitir un registro de flujo complejo.    | Se requiere una curva de aprendizaje más alta en comparación con otros middlewares.  |

<span style="color: #188eac"> Elegir middleware </span>
===========

* * *

Entonces, dependiendo de la situación, se puede elegir cualquiera de los middleware para su aplicación React, aunque en la mayoría de los casos se ha preferido Thunk para satisfacer todos los requisitos.

* Con Thunk, puedes comunicarte con tus acciones antes de que lleguen a tu Reducer.
* Thunk tiene muchos casos de uso creados en torno a aplicaciones web prácticas que necesitan enviar diferentes acciones. Estas acciones dependen de la respuesta del servidor.
* Thunk es una solución efectiva para aplicaciones con requisitos asíncronos simples.
* Y comprender Thunk es un objetivo accesible para aquellos que están aprendiendo Redux por primera vez. Una vez que se sienta cómodo con Thunks, es una buena idea probar alternativas.