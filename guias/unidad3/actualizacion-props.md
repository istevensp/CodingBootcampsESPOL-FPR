## Actualización de Props

[Regresar](/CodingBootcampsESPOL-FPR/)

Como vimos en la sección de [ciclo de vida de los componentes](./montaje-desmontaje-componentes.md), una de las fases del ciclo es la actualización. 

<p align="center">
<img src="https://www.freecodecamp.org/news/content/images/2021/02/props-1-min.gif" width="35%" alt="Banner"/>
</p>

La actualización es la fase en la que un componente se actualiza cada vez que detecte un cambio en el estado o props del componentes. Una de las funciones usadas en este fase es:

### componentWillReceiveProps(nextProps)

El método de componentWillReceiveProps(nextProps) se ejecuta luego de detectar que el componente tiene nuevos props o propiedades. Para que se refleje la actualización del estado del componente y la actualización de props, se deberá reiniciar el valor inicial. 
Como dato adicional, es posible que React ejecute el método incluso si no han cambiado los props. Por tal razón, se debe validar las nuevas propiedades(nextProps) con las anteriores(this.props), verificando el cambio de props. 

### shouldComponentUpdate(nextProps, nextState)

El método shouldComponentUpdate(nextProps, nextState) es usado antes de iniciar la actualización del componente, es decir cuando llegan las nuevas props(nextProps) y el nuevo estado(nextState). 
Este método devuelve true o false dependiendo si se desea renderizar o no el componente, como se decia anteriormente valida que los datos de **this.props** y **this.state** sean diferentes. 
Una aspecto a considerar es que si al componente que deseamos actualizar props tiene otro componentes como hijos y a su vez tienen sus estados, ya que si está en ese caso el método shouldComponentUpdate(nextProps, nextState) devolverá false lo que hará que los sub-componentes no se actualicen al detectar un cambio. 

### componentWillUpdate(nextProps, nextState)

Una vez que el método anterior shouldComponentUpdate(nextProps, nextState) devuelva true, entonces se ejecutará el metodo componentWillUpdate(nextProps, nextState) que realiza la preparación antes de que se actualice la UI. 

### render()

Con el método render() se va a generar la UI, ya con los componentes actualizados en base a las props. Y finalmente da paso al siguiente método componentDidUpdate(prevProps, prevState).

### componentDidUpdate(prevProps, prevState)

Este método es la parte final de la actualización de un componente y sucede justo después de que se renderiza en el DOM. Cabe recordar que es posible interactuar con el DOM y cualquier API de los navegadores. 

<p align="center">
<img src="https://images.viblo.asia/412485a5-beaf-49c7-b21a-738cb9cbd3c3.png" width="30%" alt="Banner"/>
</p>