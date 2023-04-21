## Props & Protypes

[Regresar](/CodingBootcampsESPOL-FPR/)

En una aplicación de React detrás de la interfaz de usuario se encuentran varios componentes comunicados entre si, lo que implica el paso de información entre cada componente.

Protypes es el mecanismo mediante el cuál se pasa información de los componentes asegurandose de que se utilizen el tipo de dato correcto y a su vez se pasen los datos correctamente.

Props
===========

* * *

Los props nos permiten pasar información a los componentes de React. Como ya hemos mencionado las aplicaciones de React consta de varios componentes y props nos ayuda a compartir los mismo datos entre los componentes que requieren dicha información. 

Los datos puede ser: números, cadenas, matrices, funciones, objetos, etc. Por tal razón, se puede pasar cualquier prop a un componente, además podemos declarar atributos en cualquier etiqueta HTML. A continuación, se muestra un ejemplo:

```js
<PostList posts={postsList} />
```
En la línea de código anterior, se está pasando un props llamado posts a un componente PostList. Dicho props tiene una valor de postList.

PropTypes
===========

* * *

Tanto props como propsTypes son un mecanismo para el paso de información entre los componentes de React. Como mencionabamos anteriormente, con props podemos pasar y acceder la información a cualquier componente que use dicho props. Sin embargo, por buena práctica es necesario validar los datos que pasamos usando PropTypes.

Los propTypes a menudo se usan después de la finalización de un componente y comienza con el nombre del otro componente como se muestra a continuación:


```js
import React from 'react';
import { PropTypes } from "prop-types";
 
const Count = (props) => {
  return (
    <>
      .........
    </>
  )
};
 
Count.propTypes = {
  //// key is the name of the prop and
// value is the PropType
}
export default Count;
```