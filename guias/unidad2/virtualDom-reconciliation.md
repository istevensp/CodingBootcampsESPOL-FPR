## VirtualDOM Reconciliation

[Regresar](/CodingBootcampsESPOL-FPR/)

¿Qué es el DOM?
===========

* * *
 El DOM es la forma en que los navegadores estructuran las páginas web para que se pueda interactuar con los elementos. 

El DOM tiene el siguiente funcionamiento en el que el navegador crea el objeto cuando recibe un documento HTML desde un servidor. De ahí, el navegador crea una estructura en forma de árbol conocida como DOM, que es la representación del contenido y la estructura de la página web. Este DOM luego puede ser manipulado con el fin de brindar funcionalidad dinámica e interactiva.

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>My HTML Page</title>
</head>
<body>
  <h1> heading </h1>
  <p> paragraph </p>
  <div>
    Div content
  </div>
</body>
</html>
```

<p align="center">
<img src="https://media.licdn.com/dms/image/D4D12AQF5zAh2WujYfw/article-inline_image-shrink_1500_2232/0/1678537802484?e=1688601600&v=beta&t=HRuCIV83RX_kxRGC5MRjtXVYnJdShY_vY9UFYonhHh8" width="35%" alt="Banner"/>
</p>

Virtual DOM
===========

* * *

* El virtual DOM es una abstracción del DOM. 
* Es una copia ligera del DOM, lo que significa que tiene menos propiedades que el DOM.
* El virtual DOM es liviano, rápido y eficiente. En cada renderización, se crea un nuevo virtual DOM.

Reconciliation
===========

* * *

El proceso de reconciliation se basa en cuando se cambia el estado de un componente, eso quiere decir que se crea un nuevo virtual DOM con un estado actualizado y se comprara con el anterior virtual DOM para que sean actualizadas las partes que requieran el cambio.

La diferenciación es uno de los procesos que utiliza React para hacer la comparación entre el nuevo virtual Dom y el antiguo virtual DOM. 

Algoritmo de diferenciación
===========

* * *

1. Diffing es un algoritmo recursivo simple para comparar la data entre los nodos de los dos árboles. 
2. La comparación inicia en el nodo raíz de los árboles. 
3. Si React detecta cambios desde el nodo raíz, entonces, asume que todo ha cambiado y reconstruye todo el subárbol. 
4. Si no detecta el cambio pasa al siguiente nivel de nodos en el arbol en la que realiza la comparación y sigue con el proceso recursivamente.

Elementos DOM de diferentes tipos
===========

* * *
Como se mencionaba anteriormente, si en el nodo raíz existe diferentes elementos React construirá un nuevo árbol. Por ejemplo que el árbol antiguo se encuentre ```<a>``` y en el nuevo árbol ```<img>```, o de o de ```<Article>``` a ```<Comment>```, o de ```<Button>``` a ```<div>```. Cualquiera de los casos anteriores producirá un nuevo árbol. A continuación, se mostrará un ejemplo en la que se deberá destruir el antiguo Counter y reconstruirlo con el nuevo elemento.

```html
<div>
  <Counter />
</div>

<span>
  <Counter />
</span>
```

Elementos DOM del mismo tipo
===========

* * *

Si en el proceso de comparación, React detecta que ambos elementos del DOM son del mismo tipo. Entonces, mantiene el mismo nodo y el único cambio que hace es actualizar sus atributos. A continuación, se muestra un ejemplo en la que solo se modificaría el **className** dado que son elementos del mismo tipo.

```html
<div className="before" title="stuff" />

<div className="after" title="stuff" />
```
En el caso de **style** al comparar los elementos solo modifica el atributo que ha cambiado. En el siguiente ejemplo React detecta que solo modificará el color y no el fontWeight ya que es el mismo para ambos. 

```html
<div style={{color: 'red', fontWeight: 'bold'}} />

<div style={{color: 'green', fontWeight: 'bold'}} />
```