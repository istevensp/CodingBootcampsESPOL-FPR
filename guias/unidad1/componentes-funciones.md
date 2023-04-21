## Componentes y funciones

[Regresar](/CodingBootcampsESPOL-FPR/)


¿Qué es un componente?
===========

* * *

* Un componente es uno de los componentes básicos de React. En otras palabras, cada aplicación que desarrolles en React estará compuesta por piezas llamadas componentes.
* Los componentes facilitan la tarea de crear una interfaz de usuario.
* Puede dividir la interfaz de usuario en varias piezas individuales denominadas componentes y fusionarlos todos en un componente principal que forma la interfaz de usuario final.

<p align="center">
<img src="https://www.freecodecamp.org/news/content/images/2019/07/final-multiple.gif" width="30%" alt="Banner"/>
</p>

¿Cuál es el estado de un componente?
===========

* * *

* State es un objeto que describe cómo se comportará y renderizará el componente actualmente.
* Un componente React puede ser "con estado" o "sin estado".
* Un componente con estado actualiza su interfaz de usuario con respecto a su estado.
* Los componentes "con estado" son del tipo de clase, mientras que los componentes "sin estado" son del tipo de función.

Tipos de componentes en React
===========

* * *

Los componentes en React son:
* Funcionales
* Clase
* Puros
* Alto orden

### Componente Funcional

* Los componentes funcionales se pueden crear escribiendo una función de JavaScript.
* Estas funciones pueden o no recibir datos como parámetros.
* Los componentes funcionales son funciones que toman accesorios y devuelven JSX.
* No tienen métodos nativos de estado o ciclo de vida, pero esta funcionalidad se puede agregar implementando React Hooks que es una nueva característica en React.

```js
const Democomponent = () => {
    return <h1> Bienvenidos! </h1>;
}
```

### Componente de clase

* Los componentes de clase son un poco más complejos que los componentes funcionales.
* Puede pasar datos de un componente de clase a otros componentes de clase.
* Puede usar clases de JavaScript ES6 para crear componentes basados en clases en React.
* Los componentes de clase se utilizan con más frecuencia que otros tipos de componentes.
* Los componentes de clase tienen estado.

```js
class Democomponent extends React.Component{
    render() {
        return <h1> Bienvenidos! </h1>;
    }
}
```
### Componente puro

* Los componentes puros son mejores que los componentes funcionales.
* Los componentes puros se utilizan principalmente para proporcionar optimizaciones.
* Son los componentes más simples y rápidos de escribir.
* No dependen ni modifican el estado de las variables fuera de su alcance.

### Componente de alto orden

* Un componente de orden superior (HOC) es una técnica avanzada en React para reutilizar la lógica de componentes.
* Este componente no es un componente de React que esté disponible en la API.
* Es un patrón que surgió de la naturaleza compositiva de React.
* Básicamente, los HOC son funciones que devuelven un componente que se utiliza para compartir la lógica con otros componentes.

```js
import React from 'react';
import { Text } from 'react-native';

const Helloworld = () => {
    return (
        <Text> Hola mundo! </Text>
    );
}

export default Helloworld;
```