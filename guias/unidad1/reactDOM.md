## ReactDOM

[Regresar](/CodingBootcampsESPOL-FPR/)


Básicamente ReactDOM.render() usa un nodo DOM perteneciente al HTML de tu aplicación para reemplazarlo con JSX. Así es como puedes integrar fácilmente React a cualquier aplicación externa. No está prohibido utilizar ReactDOM.render() varias veces en una aplicación. Puedes utilizarlo en varios lugares para iniciar la sintaxis JSX simple, un componente React, múltiples componentes React o una aplicación completa. El ejemplo se encuentra en el archivo src/index.js de la aplicación incial que habíamos realizado en la sección de [nodeJs-npm](./nodeJs-npm.md).

```js
import React from 'react';
import ReactDOM from 'react-dom';
import App from './App';
import './index.css';

ReactDOM.render(
  <App />,
  document.getElementById('root')
);
```