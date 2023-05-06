## Montaje y desmontaje de componentes

[Regresar](/CodingBootcampsESPOL-FPR/)


Empezaremos esta sección hablando del ciclo de vida de un componente y luego introduciremos el tema de montaje y desmontaje de componentes. 

¿Qué es el ciclo de vida de un componente?
===========

* * *

* El ciclo de vida de un componente de React representa las diferentes fases de la vida útil de un componente.
* Hay diferentes métodos de ciclo de vida que React proporciona en diferentes fases de la vida de un componente.

Fases de los componentes
===========

* * *
Existen tres fases principales del ciclo de vida del componente, pero en este caso mostraremos un fase adicional. 

1. **Inicialización:** esta es la fase en la que se construye el componente con los Props dados y el estado predeterminado. Esto se hace en el constructor de una Clase de Componente.
2. **Montaje:** el montaje es la fase de representación del JSX devuelto por el propio método de representación.
3. **Actualización:** la actualización es la fase en la que se actualiza el estado de un componente.
4. **Desmontar:** como sugiere el nombre, el desmontaje es el paso final del ciclo de vida del componente, donde el componente se elimina de la página. 

El ciclo de vida del componente comienza cuando los componentes se crean o montan en el DOM. Una vez montados, crecen actualizando, y luego mueren o se desmontan en el modelo de objeto de documento o DOM. React llama automáticamente al método responsable según la fase en la que se encuentre el componente.
Estos métodos le brindan un mejor control sobre los componentes, y puedes manipularlos usando los métodos.

<p align="center">
<img src="https://blog.codedthemes.com/wp-content/uploads/2021/01/1_b8CJnHPRZgbB9-pkLk10gQ.png" width="30%" alt="Banner"/>
</p>

Montaje de componentes
===========

* * *

* En la fase de montaje, el componente se agrega al DOM. 
* En esta fase, se crea un nuevo componente y se inserta en el DOM.
* Esta es también la fase en la que se inicializa el componente y renderizado en la página web por primera vez.
* Esta fase consta de dos funciones predefinidas una de ellas es la función componentWillMount().

Actualización de componentes
===========

* * *

* Es la fase en donde cambian los estados y accesorios de un componente, con la ocurrencia de algunos eventos de usuario, como hacer clic o presionar una tecla en el teclado.
* Estos cambios pueden ocurrir dentro del componente o a través del backend. Activan la función de renderizado de nuevo.

Desmontaje de componentes
===========

* * *

* La fase de desmontaje es la tercera y última fase de un componente React.
* En esta fase, el componente se elimina del DOM.
* El desmontaje solo tiene un método de ciclo de vida involucrado: componenteWillUnmount. Esta función se invoca antes de que el componente se elimine de la página, y denota el final del ciclo de vida.
