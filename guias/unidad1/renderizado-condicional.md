## Renderizado condicional

[Regresar](/CodingBootcampsESPOL-FPR/)

En nuestros componentes será muy a menudo el paso de información en base a condiciones. React, nos permite renderizar JSX de forma condicional utilizando las declaraciones if, && y los operadores ? :, que son parte de la sintaxis de JavaScript.

Devolución condicional de JSX
===========

* * *

Ejemplificaremos un componente que muestra varios **Items**, que puede ser empquetados o no.

```js
/* App.js */
function Item({ name, isPacked }) {
  return <li className="item">{name}</li>;
}

export default function PackingList() {
  return (
    <section>
      <h1> Packing List</h1>
      <ul>
        <Item 
          isPacked={true} 
          name="Item 1" 
        />
        <Item 
          isPacked={true} 
          name="Item 2" 
        />
        <Item 
          isPacked={false} 
          name="Item 3" 
        />
      </ul>
    </section>
  );
}

```
Algunos de los componentes Item tiene su prop isPacked asignado como true o false. Debemos añadir una estructura condicional que muestre la verificación  ✔ a los items en la que la variable **isPacked={true}**.

```js
/* App.js */
function Item({ name, isPacked }) {
  if (isPacked) {
    return <li className="item">{name} ✔</li>;
  }
  return <li className="item">{name}</li>;
}

export default function PackingList() {
  return (
    <section>
      <h1> Packing List</h1>
      <ul>
        <Item 
          isPacked={true} 
          name="Item 1" 
        />
        <Item 
          isPacked={true} 
          name="Item 2" 
        />
        <Item 
          isPacked={false} 
          name="Item 3" 
        />
      </ul>
    </section>
  );
}
```

Operador condicional (ternario) (? :) 
===========

* * *

El operador ternario en JavaScript es el único operador que tiene tres operando. Es un atajo para la isntrucción if. A continuación se muestra la sintaxis.

```js
condición ? expr1 : expr2
```
Por eso razón, reemplazaremos el código condicional que habíamos definido:

```js
if (isPacked) {
  return <li className="item">{name} ✔</li>;
}
return <li className="item">{name}</li>;
```
A este código que contiene el operador condicional (ternario):

```js
return (
  <li className="item">
    {isPacked ? name + ' ✔' : name}
  </li>
);
```

Operador lógico AND (&&)
===========

* * *