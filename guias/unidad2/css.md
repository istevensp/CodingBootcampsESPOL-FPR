## Repaso css

[Regresar](/CodingBootcampsESPOL-FPR/)


CSS
===========

* * *

CSS significa hojas de estilo en cascada. Permite describir cómo se deben mostrar los elementos html en el pantalla. Además, existen hojas de estilo que se almacenan en archivo CSS.

<p align="center">
<img src="https://cdn-icons-png.flaticon.com/512/919/919826.png" width="30%" alt="Banner"/>
</p>

A continuación se mostrará un ejemplo de código CSS.

```css
body {
  background-color: green;
}

h1 {
  color: white;
  text-align: center;
}

p {
  font-family: verdana;
  font-size: 18px;
}
```

Sintaxis css
===========

* * *

<p align="center">
<img src="https://hablacode.org/static/media/selector.bc73474e.png" width="30%" alt="Banner"/>
</p>

En el sintaxis, el selector apunta al elemento html que desea aplicarle nuevos estilos. El bloque de declaración está compuesto por uno o más declaraciones que están entre el símbolo de punto y coma y a la vez encerradas en llaves.

A continuación, visualizaremos el ejemplo de aplicarle estilo a todos los elementos `<p>`.

```css
p {
  color: green;
  text-align: center;
}
```
En el código anterior vemos que existe **color** y **text-align** que son propiedades y lo que se encuentra después de los dos puntos son los valores correspondientes a esa propiedad.

Selectores css
===========

* * *

En css, los selectores se usan para seleccionar los elementos html que desea diseñar. Existen 5 categorías de los selectores css:

1. **Selectores simples:** seleccionan el elemento basado en nombre, id o clase.
2. **Selectores combinadores:** seleccionan elementos en función de una relación específica.
3. **Selectores pseudoclase:** seleccionan elementos en función de un determinado estado.
4. **Selectores de atributos:** seleciionan elementos basados en un atributo o valor del atributo.

#### Selector por ID

El selector de id usa el atributo id de un elemento HTML para seleccionar un elemento específico. Para encontrar dicho elemento se usa el carácter numeral # seguido del id con las propiedades a utilizar.
Por ejemplo si tenemos un elemento html con id="elemento", se utiliza la siguiente regla css.

```css
#elemento{
    text-align: center;
    color: blue;
}
```
**Nota:** recuerda que un nombre de identificación(id) no puede comenzar con un número.

#### Selector de clases

El selector de clase usa un atributo de clase para seleccionar el elemento html que este en esa clase. Para encontrar dicho elemento se usa el carácter de punto (.) seguido del nombre de la clase.
A continuación, se muestra un ejemplo en que se seleccionan los elementos cuya clase sea **texto**.

```css
.texto{
    text-align: center;
    color: green;
}
```

#### Selector universal

El selector universal hace referencia a que seleccionamos todos los elementos html de la página. Se usa el carácter (*) para especificación universal.

```css
.texto{
    text-align: center;
    color: gray;
}
```

#### Selector de agrupación

El selector de agrupación permite seleccionar todos los elementos html con las definiciones de estilo. A continuación, se muestra que tanto los elementos `<h1>` y `<p>` tendrán las mismas definiciones de estilo.

```css
h1 {
  text-align: center;
  color: purple;
}

p {
  text-align: center;
  color: orange;
}
```

¿Cómo agregar css?
===========

* * *

Existen 3 formas de insertar una hoja de estilo:
1. CSS externo
Para incluir una hoja de estilo externo, dentro de la página html deberás incluir el elemento <link> en la sección de encabezado.

```html
<!DOCTYPE html>
<html>
<head>
<link rel="stylesheet" href="mystyle.css">
</head>
<body>
</body>
</html>
```
La hoja de estilo externa tiene extensión .css, además no debe contener ninguna etiqueta html.
```css
/* mystyle.css*/
body {
  background-color: lightblue;
}

h1 {
  color: green;
  margin-left: 50px;
}
```
2. CSS interno
Si nuestra página tiene un estilo único la agregamos en una hoja de estilo interna, se la define dentro del elemento `<style>` en la cabecera.

```html
<!DOCTYPE html>
<html>
<head>
<style>
body {
  background-color: lightblue;
}

h1 {
  color:purple;
  margin-left: 40px;
}
</style>
</head>
<body>

<h1>CSS interno</h1>
<p>Esta es una prueba de hoja de estilo interna.</p>

</body>
</html>
```
3. CSS por línea

Para un solo elemento se aplica el estilo en la misma línea.

```html
<!DOCTYPE html>
<html>
<body>

<h1 style="color:blue;text-align:center;">CSS por línea</h1>
<p style="color:white;">Esto es una prueba.</p>

</body>
</html>
```