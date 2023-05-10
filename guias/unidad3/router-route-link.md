## Uso de Router, Route y Link

[Regresar](/CodingBootcampsESPOL-FPR/)

<span style="color: #188eac"> Componentes primarios de React Router </span>
===========

* * *

React router consta de 3 tipos:
1. **Enrutadores**: Browserouter, HashRouter
2. **Comparadores de ruta**: Switch, Route
3. **Navegadores**: Link, NavLink, Redirect

### Enrutadores

La aplicación que use React router tiene un componente enrutador:

* **Browserouter:**
Usa las rutas `URL` normales como www.url.com/about. El servidor debe estar configurado correctamente, create-react-app nos garantiza aquello.

* **HashRouter:**
No requiere una configuración especial del lado del servidor. Usa hash # para almacenar la ubicación en el URL, como www.url.com/#/about.

### Comparadores de ruta

* **Switch:**
Se encarga de buscar la URL que sea igual o parecida y así mostrar su contenido. Si no se encuentra devueleve null. A partir de la versión 6 de React Router usa Routes en vez de Switch.

* **Route:**
Route es el componente que va a tener la URL y así mostrar el contenido.

### Navegadores

* **Link:**
Link es un componente que permite crear enlaces en la aplicación.

* **NavLink:**
NavLink es un componente especial usado para cambiar el estilo del enlace.

* **Redirect:**
Redirect fuerza la navegación a la URL que se le específica.


En resumen, React Router tiene un componente llamado `Routes` (para versiones anteriores Switch) que es el encargado de buscar en los componentes hijos `Route` la URL correspondiente y asi mostrar el contenido. 

<p align="center">
<img src="https://miro.medium.com/v2/resize:fit:1100/format:webp/1*_lGk1_TyPUk2kNhi0nV93w.png" width="35%" alt="Banner"/>
</p>



## Referencias

* React Router. Retrieved May 09, 2023, from [https://mauriciogc.medium.com/react-react-router-db391b3def2a](https://mauriciogc.medium.com/react-react-router-db391b3def2a)