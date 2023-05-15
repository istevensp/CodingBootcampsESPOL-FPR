## Reducers & Pure functions

[Regresar](/CodingBootcampsESPOL-FPR/)


<span style="color: #188eac"> Principios básicos de Redux </span>
===========

* * *

* Redux ofrece un sistema de gestión de estado centralizado en su biblioteca de aplicaciones.
* Las propiedades de un componente deben considerarse inmutables.

<p align="center">
<img src="../imagenes/flux.png" width="80%" alt="Banner"/>
</p>

La imagen anterior representa  un usuario cuando interactúa con un componente en una aplicación, la Acción actualiza el estado completo de la aplicación. Esto a su vez, desencadena una nueva representación del componente, actualizando así las propiedades de ese componente. Estas propiedades muestran el resultado al usuario.

<span style="color: #188eac"> Principios de Redux </span>
===========

* * *

Redux se fundamenta en 3 principios:
1. **Acciones:** es lo que aplicación puede hacer.
2. **Store:** es el estado actual de la aplicación Redux que vive en un objeto que se llama la tienda. 
3. **Reducers:** son acciones que devuelven el nuevo estado.

<span style="color: #188eac"> Reducers </span>
===========

* * *

* Los reductores son funciones puras que reciben el estado actual y un objeto Action y devuelven un nuevo estado con las acciones realizadas.
* El reductor realiza los cambios apropiados en el estado.
* Los reducers actúan como un detector de eventos que maneja los eventos en función del tipo de evento aceptado.
* Lee las cargas útiles de la Acción y luego actualiza la Tienda a través del estado correspondiente.
* La función Reducers toma dos parámetros; el estado anterior de la aplicación y la acción que se envía. Devuelve el nuevo estado de la aplicación.

<p align="center">
<img src="https://css-tricks.com/wp-content/uploads/2016/03/redux-article-3-04.svg" width="40%" alt="Banner"/>
</p>

Se puede comenzar con un solo reductor y, a medida que crece su aplicación, dividirlo en reductores más pequeños que administren partes específicas del árbol de estado. Debido a que los reductores son solo funciones, puede controlar el orden en que se llaman, pasar datos adicionales o incluso hacer reductores reutilizables para tareas comunes como la paginación.

```js
function visibilityFilter(state = 'SHOW_ALL', action) {
  switch (action.type) {
    case 'SET_VISIBILITY_FILTER':
      return action.filter
    default:
      return state
  }
}

function todos(state = [], action) {
  switch (action.type) {
    case 'ADD_TODO':
      return [
        ...state,
        {
          text: action.text,
          completed: false
        }
      ]
    case 'COMPLETE_TODO':
      return state.map((todo, index) => {
        if (index === action.index) {
          return Object.assign({}, todo, {
            completed: true
          })
        }
        return todo
      })
    default:
      return state
  }
}

import { combineReducers, createStore } from 'redux'
const reducer = combineReducers({ visibilityFilter, todos })
const store = createStore(reducer)
```

## Referencias

* Three Principles. Retrieved May 13, 2023, from [https://redux.js.org/understanding/thinking-in-redux/three-principles](https://redux.js.org/understanding/thinking-in-redux/three-principles)