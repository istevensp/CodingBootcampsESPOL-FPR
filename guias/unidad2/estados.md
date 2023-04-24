## Administración de estados

[Regresar](/CodingBootcampsESPOL-FPR/)


¿Qué es un estado?
===========

* * *

* Los estados le permiten cambiar datos en una aplicación.
* Se define como un objeto que te ayuda a incluir pares clave-valor que especifican diferentes tipos de datos que desea rastrear en la aplicación.
* Los componentes de React tienen un objeto de estado incorporado.

Tipos de estados en React
===========

* * *

* **Estado compartido:**
El estado compartido es compartido por múltiples componentes.  Un ejemplo de estado compartido es la lista de todos los pedidos en una aplicación de pedidos.
* **Estado local:**
El estado local vive en un solo componente y no se usa en otros componentes. Un ejemplo de estado local es ocultar y mostrar información.

Estados para los componentes en React
===========

* * *

* State es un objeto de JavaScript simple utilizado por React para representar información sobre la situación actual del componente.
* El corazón de cada componente de React es su "estado".
* El estado determina cómo se representa y se comporta un componente.
* Un estado le permite crear componentes dinámicos e interactivos.
* El estado es una instancia de la clase de componente React que puede definirse como un objeto con un conjunto de propiedades observables. Estos controlan el comportamiento del componente.
* El estado se administra y conserva en el componente React.

Ejemplo de un estado
===========

* * *

Este ejemplo de código muestra cómo puede crear un Testcomponent que contiene el estado con atributos como id, nombre y edad.
La función de representación del componente devuelve el nombre y la edad del atributo de estado.
El estado que contiene los atributos cambiará según los requisitos del componente.

```js
//component
class Testcomponent extends React.Component{
    constructor() {
        this.state = {
            id:1,
            name: "Jhon",
            age: 28
        };
    }
render(){
    return(
        <div>
        <p> {this.state.name}</p>
        <p> {this.state.age}</p>
        </div>
    )
}
}

```

Props en React
===========

* * *

* Props es la abreviatura de propiedades, y se utilizan para pasar datos entre los componentes de React.
* El flujo de datos de React entre los componentes es unidireccional solo de padre a hijo.
* Son objetos que almacenan el valor de los atributos de un
etiqueta y funciona como los atributos HTML.
* Son como argumentos de función que se pueden pasar al componente.
* Los accesorios son inmutables y no se pueden modificar desde el interior del componente.
* Los accesorios nunca deben cambiarse en un componente secundario.

Veamos un ejemplo de props. El ejemplo crea una clase, TestComponent, que amplía el componente React. Representa accesorios que aceptan el nombre del atributo. Luego, puede pasar accesorios al componente Prueba que acepta diferentes nombres como John y Jill. 


```js
//component
class TestComponent extends React.component{
    render(){
        return <div> Hola {this.props.name}</div>
    }
}
//pasando los props como ejemplos al TestComponent
<TestComponent name="Julia"/>
<TestComponent name="Jack"/>
```

Veamos las diferencias entre estado y props.

* Un estado solo se puede usar en componentes de clase de forma nativa.
En los componentes funcionales, debe aceptar el uso de Statehook para incluir características con estado. Los props, por otro lado, le permiten reutilizar el componente dándole la capacidad de recibir datos como entrada del componente principal.
* Estado es el estado local del componente que no se puede
accedido o modificado fuera del componente. Los props, por otro lado, hacen que los componentes sean reutilizables al darles la capacidad para recibir datos del componente principal en forma de accesorios.
* Los componentes pueden crear y administrar sus propios datos con estado,
mientras que reciben datos del exterior con props.

Componentes de clase
===========

* * *

En React, estos componentes de clase son clases simples que están compuestas por múltiples funciones que agregan funcionalidad a la aplicación.

```js
class Person extends React.Component { 
  render() { 
    return <h2>¡Hola, soy una Persona!</h2>; 
  } 
}
```


Componentes funcionales
===========

* * *
Los componentes funcionales son algunos de los componentes más comunes cuando se trabaja con React. Estas son simplemente funciones de JavaScript. Se puede crear un componente funcional escribiendo una función de JavaScript.

```js
const Person=()=> {
  return <h2>¡Hola, yo también soy una persona!</h2>;
}
```

| Componentes funcionales | Componentes de clase |
|----------|---------- |
| No se utiliza ningún método de renderizado.   | Debe tener el método render() devolviendo JSX. |
| También conocidos como componentes sin estado.   | También conocidos como componentes con estado. |
| No se utilizan constructores.   | El constructor se usa ya que necesita almacenar el estado.  |
