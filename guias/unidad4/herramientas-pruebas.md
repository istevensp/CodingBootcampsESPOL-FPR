## Herramientas para pruebas unitarias

[Regresar](/CodingBootcampsESPOL-FPR/)

<span style="color: #188eac"> ¿Qué es testing? </span>
===========

* * *

* Testing es una revisión línea por línea de cómo se ejecutará su código.
* Se puede realizar utilizando un conjunto de pruebas para una aplicación que comprende varios bits de código para verificar si una aplicación se ejecuta correctamente y sin errores.

<span style="color: #188eac"> Ventajas del testing </span>
===========

* * *

* Previene regresiones inesperadas.
* Además, permite la construcción modular de una aplicación que de otro modo sería demasiado compleja de construir.
* Reduce la necesidad de verificación manual.

<span style="color: #188eac"> Desventajas del testing </span>
===========

* * *

* Necesita escribir más código, así como depurar y mantener el código y
las fallas de prueba no críticas pueden causar que la aplicación sea rechazada en términos de integración continua.

<span style="color: #188eac"> ¿Por qué hacer testing en los componentes de React? </span>
===========

* * *

* Las pruebas de los componentes de React se realizan para garantizar que su aplicación funcionará según lo previsto para sus usuarios finales. 
* La prueba verifica el código preparado por los desarrolladores para comprobar que se ejecuta sin errores. 
* Las pruebas también prueban la funcionalidad de la aplicación replicando las acciones de los usuarios finales.
* También debe realizar pruebas para verificar que las actualizaciones realizadas en la aplicación no afectar el funcionamiento general de la aplicación.

Para elegir las herramientas de prueba considera el siguiente criterio:

**Velocidad vs. entorno:** algunas herramientas ofrecen un ciclo de retroalimentación rápido entre hacer un cambio y ver el resultado, pero no modelar el precisamente el comportamiento del navegador. Otras herramientas pueden usar un entorno de navegador real, pero reducen la velocidad de iteración y no son confiables en un servidor de integración continua.

<span style="color: #188eac"> Bibliotecas de testing para componentes React </span>
===========

* * *

* Mocha se utiliza como corredor de prueba. 
* Chai puede ser la biblioteca de afirmaciones.
* Sinon se puede usar opcionalmente para probar su lógica de JavaScript con objetos como espías, talones y simulacros.
* Enzyme que se agrega para renderizar sus componentes React.
* Jest trae el poder combinado de Mocha, Chai, Sinon y más.

<p align="center">
<img src="https://miro.medium.com/v2/resize:fit:839/1*8IBBim-Fx_wQzN5va0UHqA.png" width="80%" alt="Banner"/>
</p>
