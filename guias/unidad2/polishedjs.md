## Polished.js

[Regresar](/CodingBootcampsESPOL-FPR/)


Polished es un conjunto de herramientas ligero para escribir estilos en JavaScript. También contempla el uso de funciones auxiliares y mixins de estilo Sass.

<p align="center">
<img src="https://raw.githubusercontent.com/styled-components/brand/master/polished.png" width="30%" alt="Banner"/>
</p>

Para instalar los paquetes correspondientes ejecuta el siguiente comando en tu aplicación React.

```
npm install --save polished
```
Para el uso de los módulos de polished se dbe importar de manera independiente, como se ejemplifica a continuación:

```js
import { clearFix, animation } from 'polished'
```
Existen una serie de funciones que se pueden importar como: lighten(), darken(), complement(), entre otras. En la [documentación](https://polished.js.org/docs/) verifica las funciones que puedes hacer uso en tu proyecto.

Una de las ventajas del uso de polished.js es que está escrito en estilo funcional, siendo así la principal diferencia con Sass. Eso signifuca que con **compose** se puede ir componiendo los estilos en base a su elección. A continuación, se muestra un ejemplo:

```js
import { compose } from 'ramda' 
import { lighten, desaturate } from 'polished'
const tone = compose(lighten(0.1), desaturate(0.1))
```
