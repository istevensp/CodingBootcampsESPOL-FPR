## Instalación y Configuración Jest

[Regresar](/CodingBootcampsESPOL-FPR/)

Con npm que es el administrador de paquete instalaremos Jest. 

```
npm install --save-dev jest
```

Para realizar una prueba tendremos una función que sume dos números. Para ello cree el archivo suma.js.

```js
function sum(x, y) {
  return x + y;
}
module.exports = sum;
```
Ahora se creará la prueba en el archivo suma.test.js con el siguiente código.

```js
const sum = require('./sum');

test('adds 5 + 5 to equal 10', () => {
  expect(sum(5, 5)).toBe(10);
});
```

En el archivo package.json agregue la siguiente sección:

```js
{
  "scripts": {
    "test": "jest"
  }
}
```

Se ejecuta la prueba utilizando el comando `npm Jest`. 

```
PASS  ./suma.test.js
✓ adds 5 + 5 to equal 10 (5ms)
```

La prueba anterior usó **expect** y **toBe** para probar que ambos valores sean iguales. 

### Ejecución desde la línea de comandos

Se puede ejecutar Jest directamente desde la CLI y así obtener una variedad de opciones útiles.
A continuación, se muestra cómo ejecutar Jest en archivos que coincidan con `my-test`. Por tal razón, se muestra el archivo de configuración de config.json en él que se mostrará una notificación después de la ejecución:

```
jest my-test --notify --config=config.json
```

### Configuración adicional

Para generar un archivo de configuración básica ejecute el siguiente comando:

```
jest --init
```

### Configuración para una aplicación React

Si se tiene una aplicación React ya creada, se instalará algunos paquetes para que todo funcione correctamente. Se estará utilizando el paquete `babel-jest`.

```
npm install --save-dev jest babel-jest @babel/preset-env @babel/preset-react react-test-renderer
```
A continuación, el archivo **package.json** tiene la siguiente estructura. En la que "<current-version>" es el número de versión mas reciente del paquete. 

```json
{
  "dependencies": {
    "react": "<current-version>",
    "react-dom": "<current-version>"
  },
  "devDependencies": {
    "@babel/preset-env": "<current-version>",
    "@babel/preset-react": "<current-version>",
    "babel-jest": "<current-version>",
    "jest": "<current-version>",
    "react-test-renderer": "<current-version>"
  },
  "scripts": {
    "test": "jest"
  }
}
```

El archivo babel.config.js tiene la siguiente estructura:

```js
module.exports = {
  presets: [
    '@babel/preset-env',
    ['@babel/preset-react', {runtime: 'automatic'}],
  ],
};
```