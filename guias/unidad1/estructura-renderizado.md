## Estructuras y renderizado

[Regresar](/CodingBootcampsESPOL-FPR/)

En React tendremos los elementos que son los bloques más pequeños de las aplicaciones. Un elemento describe lo que deseas visualizar en la pantalla, como se muestra en el ejemplo:

```js
const element = <h1>Hola Mundo!</h1>;
```

Los elementos de React son objetos planos y por ello su creación es de bajo costo. React DOM se encarga de actualizar el DOM para igualar los elementos de React.

Renderizado de un elemento en el DOM
===========

* * *

Supongamos que tenemos un archivo HTML que contiene un "<div>". React DOM sera el encargado de manejar todo lo que está dentro del nodo "root". 

```html
<div id="root"></div>
```

En React, para renderizar un elemento, iniciamos pasando el elemento del DOM a ReactDOM.createRoot(), después pasamos el elemento de React a root.render():

```js
const root = ReactDOM.createRoot(
  document.getElementById('root')
);
const element = <h1>Hola mundo!</>;
root.render(element);
```

Actualizando un elemento renderizado
===========

* * *
En React, los elementos son inmutables. Es decir, una vez que se crean, no puedes cambiar sus hijos o atributos. En base a esta sección, sabemos que la forma de actualizar la interfaz de usuario seria creando un nuevo elemento que tendría que ser pasado al render. 
A continuación veremos un ejemplo que llama a root.render() cada segundo desde un callback del setInterval() y así actualiza el elemento.

```js
const root = ReactDOM.createRoot(
  document.getElementById('root')
);

function tick() {
  const element = (
    <div>
      <h1>Hola mundo!</h1>
      <h2>La hora es {new Date().toLocaleTimeString()}.</h2>
    </div>
  );
  root.render(element);
}

setInterval(tick, 1000);
```