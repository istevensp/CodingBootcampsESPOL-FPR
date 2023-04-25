## Extending styles

[Regresar](/CodingBootcampsESPOL-FPR/)


Al usar estilos en nuestros componentes existe una forma de extender esos estilos.
A continuación se mostrará el componente con estilo **Button** en el que se han definido algunos estilos css.

```js
import React from 'react';
import styled from 'styled-components';

const Button = styled.button`
  border: 3px solid gray;
  border-radius: 10px;
  font-size: 30px;
`;

const App = () => (
  <>
    <Button>Base Button</Button>
  </>
);

export default App;
```
Ahora si deseas cambiar el font-size del botón y mantener los demás estilos. Entonces, debes crear un componente que este basado en el estilo del botón anterior.

```js
const Button = styled.button`
  border: 1px solid black;
  border-radius: 5px;
  font-size: 20px;
`;

const DangerousButton = styled(Button)`
  font-size: 40px;
`;
```
* Además, se puede mantener el estilo utilizando otras etiquetas. El uso de props nos ayuda en eso, asi que añde "as" para renderizar a otras etiquetas. 

```js
const App = () => (
  <>
    <Button as="a" href="https://dev.to">Base Button</Button>
    <Button as="div">Base Button</Button>
  </>
);
```