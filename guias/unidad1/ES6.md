## JavaScript ES6, JSX

[Regresar](/CodingBootcampsESPOL-FPR/)

Con create-react-app habíamos inicializado una aplicación estándar.
Dentro del archivo src/App.js se encuentra un React ES6 class component o componente de clase React ES6 con el nombre App. Esto es una declaración de componente.

ES6
===========

* * *

* ES es la abreviatura de EcmaScript. Ecma es una organización de estándares que crea una amplia gama de información y comunicaciones globales.

* JavaScript se adhiere a la especificación ES6 de Ecma, que salió en 2015. Las versiones más nuevas de ES llevan el nombre del año de lanzamiento.

* ES6 es una versión con cambios que tuvieron un gran impacto.

* En JavaScript, los cambios principales son let, const, funciones de flecha, promesas y clase.

* En ES6, usa let y const además de var.

### Funciones flecha

* ES6 también hace uso de funciones flecha que permiten declarar funciones de la misma manera que declara variables. Usar esta sintaxis es una forma más corta y limpia de trabajar con funciones.

```js
const sayHello = ()=> console.log("ES6 function - Hello World!")
```
### LLamando a funciones flecha

* Las funciones de flecha se llaman como funciones normales.
* También se pueden pasar como parámetros para devoluciones de llamada.

```js
const sayHello = ()=> console.log("Hello World!");
setTimeout(sayHello,1000);
```
Aquí, la función de flecha, sayHello, se pasa como un parámetro de devolución de llamada a setTimeout.

* Las funciones flecha también toman parámetros como funciones normales. Pueden devolver un tipo de datos o un objeto.

```js
const twoParamsArrowFunc = (first, last)=> {
    const greeting = "Hello";
    return greeting + " " + first + " " + last;
}
```

### Promesas

* El objeto de promesa representa la eventual finalización de una operación asíncrona y su valor de retorno.
* Cuando invoca una operación asincrónica, una promesa está en estado pendiente.
* Cuando la operación se ejecuta con éxito, se dice que la promesa se cumplió.
* Cuando la operación falla, se dice que la promesa es rechazada.

En este primer ejemplo, tiene una función de flecha, PromiseArgument, que toma dos parámetros (resolver y rechazar). Si el tiempo actual en milisegundos es divisible por 2, esta función de flecha invoca resolver con "Éxito" como parámetro; si no, invoca el rechazo con "Error" como parámetro. Esta función se pasa al constructor del objeto de promesa.

```js
let promiseArgument = (resolve, reject) =>{
    setTimeout(() => {
        let currTime = new Date().getTime();
        if (currTime % 2 === 0){
            resolve("Éxito!")
        }else {
            reject("Error!!!")
        }
    },2000)
};
let myPromise = new Promise(promiseArgument);
```
En el segundo ejemplo, en lugar de crear promiseArgument, está creando directamente la función a tiempo con el constructor de la promesa.

```js
let myPromise = new Promise ((resolve, reject) =>{
    setTimeout(() => {
        let currTime = new Date().getTime();
        if (currTime % 2 === 0){
            resolve("Éxito!")
        }else {
            reject("Error!!!")
        }
    },2000)
})

```

### Clases

* La clase es una plantilla o modelo para crear objetos.
* Las clases en JavaScript se basan en prototipos.

```js
function Person(name, age) {
    this.name = name;
    this.age = age;
    return this;
}

let person1 = Person("Jason",20)
console.log(person1)
```

* La clase puede tener un constructor, que es un método que se llama cuando desea crear un objeto de clase. El cuerpo de la clase es la parte que está entre llaves, después del constructor.

```js
class Rectangle{
    constructor(height, width){
        this.height = height;
        this.width = width;
        console.log("Rectangle Created");
        console.log("Height" + this.height);
        console.log("Widht" + this.width);
    }
};
let myRectangle = new Rectangle(10,5)
```

### Herencia

* En JavaScript ES6, una clase puede heredar de otra clase.
* La clase que hereda otra clase se llama subclase.
* La superclase es la clase que hereda la subclase.
* La subclase hereda todos los atributos y métodos de la superclase.

Ahora es momento de dar una introducción sobre JSX, que es la sintaxis empleada por React. 

Introducción a JSX
===========

* * *

### ¿Qué es JSX?

* JSX o JavaScript Syntax Extension o JavaScript XML es una extensión de JavaScript.
* Proporciona una forma más fácil de crear una interfaz de usuario o componentes de interfaz de usuario en React.
* JSX produce "elementos" de React que se pueden usar para representar el componente en el DOM.

### Sintaxis del JSX

La sintaxis JSX es como una sintaxis similar a XML o HTML utilizada por React que extiende ECMAScript que es un estándar utilizado para secuencias de comandos del lado del cliente. Esto permite que el texto similar a XML o HTML coexista con código JavaScript o React.
La sintaxis JSX está destinada a ser utilizada por preprocesadores, por ejemplo, transpiladores o compiladores como Babel, para transformar el texto similar a HTML que se encuentra en archivos JavaScript en JavaScript estándar objetos. Estos objetos luego pueden ser analizados por un motor de JavaScript. A continuación mostraremos un ejemplo:

```js
const el1 = <h1> Este es un fragmento de código JSX de muestra</h1> 
```
El código muestra una construcción 'el1' que muestra el encabezado 'Este es un fragmento de código JSX de muestra'. El fragmento de código se parece a HTML, pero también usa una variable similar a JavaScript que no es ni
HTML ni JavaScript, es JSX.

Lenguaje JSX
===========

* * *

* JSX es básicamente una extensión de sintaxis de JavaScript normal y se usa para crear elementos React. Luego, estos elementos se procesan en el modelo de objetos de documento de React o DOM.
* JSX es un lenguaje declarativo que combina JavaScript con HTML.
* JSX hace que el código React sea mucho más fácil de leer, escribir y comprender.

Beneficios de usar JSX
===========

* * *

* Las personas menos técnicas pueden entender y modificar las partes requeridas.
* Los desarrolladores y diseñadores de CSS encontrarán que JSX es más familiar que solo JavaScript.
* También puede aprovechar todo el poder de JavaScript en HTML y evitar el aprendizaje o el uso de plantillas.
* JSX promueve la idea de estilos en línea.
* Al escribir grandes piezas de código, JSX lo ayuda a mantener su código simple y elegante.
* JSX se ocupa de los problemas habituales de saneamiento de salida para evitar ataques como secuencias de comandos entre sitios.