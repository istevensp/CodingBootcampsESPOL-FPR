## Manejadores de eventos

[Regresar](/CodingBootcampsESPOL-FPR/)

Para manejar los eventos en React consideremos los siguientes aspectos en cuánto a sintaxis:
* Los eventos de React se nombran usando camelCase, en vez de minúsculas.
* Con JSX pasas una función como el manejador del evento, en vez de un string.

```js
<button onClick={activateLasers}>
  Activate Lasers
</button>
```

* No se puede retornar false, para ello se debe usar la función **preventDefault**. A continuación, se mostrará un ejemplo para retornar el comportamiento por defecto al enviar un formulario.

```js
function Form() {
  function handleSubmit(e) {
    e.preventDefault();
    console.log('You clicked submit.');
  }

  return (
    <form onSubmit={handleSubmit}>
      <button type="submit">Submit</button>
    </form>
  );
}
```

* En react, no necesitas usar la función de addEventListener. Más bien hacer uso de un manejador de eventos para renderizar el elemento inicialmente.

* Cuando se usa un componente definido con la clase ES6, por lo general, el manejador de evento será un método de clase. A continuación, se muestra un código en el que se define un componente **Toggle** permitiendo el renderizado de un botón para que el usuario realice un cambio de estado entre "encendido" y "apagado".

```js
class Toggle extends React.Component {
  constructor(props) {
    super(props);
    this.state = {isToggleOn: true};

    // Este enlace es necesario para hacer que `this` funcione en el callback
    this.handleClick = this.handleClick.bind(this);
  }

  handleClick() {
    this.setState(prevState => ({
      isToggleOn: !prevState.isToggleOn
    }));
  }

  render() {
    return (
      <button onClick={this.handleClick}>
        {this.state.isToggleOn ? 'ON' : 'OFF'}
      </button>
    );
  }
}
```

Paso de argumentos a manejadores de eventos
===========

* * *

En varias ocasiones resultará común querer enviar un parámetro extra a un manejador de eventos. A continuación, se muestra un ejemplo para el paso de un **id** que representa el ID de una fila.

```js
<button onClick={(e) => this.deleteRow(id, e)}>Delete Row</button>
<button onClick={this.deleteRow.bind(this, id)}>Delete Row</button>
```
* Las dos líneas que se mostraron anteriormente son equivalentes. La primera línea hace uso de función flecha y la segunda usa Function.prototype.bind.
* Como se puede apreciar en el código, el argumento **e** es la representación del evento que es pasado como segundo parámetro. Note la diferencia en que la función flecha se pasa el evento explícitamente. En cambio, con **bind** los argumentos adicionales son pasados automáticamente.