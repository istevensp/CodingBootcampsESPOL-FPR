## Métodos de ciclo de vida de los componentes

[Regresar](/CodingBootcampsESPOL-FPR/)

Continuando con el tema del ciclo de vida de los componentes, es necesario conocer los métodos que son usados en los componentes con el objetivo de seguir buenas practicas, mejorar rendimiento y obtener calidad en los componentes creados. 
A continuación se describen los métodos por cada fase del ciclo de vida de los componentes.

1. **Montado**:

* constructor()
* static getDerivedStateFromProps(nextProps, prevState)
* render()
* componentDidMount()

2. **Actualización**:

* static getDerivedStateFromProps(nextProps, prevState)
* shouldComponentUpdate(nextProps, nextState)
* getSnapshotBeforeUpdate(prevProps, prevState)
* render()
* componentDidUpdate(prevProps, prevState, snapshot)

3. **Desmontado**:

* componentWillUnmount()

De forma ordenada los métodos tendrían el siguiente orden secuencial en el ciclo de vida de los componentes. 

1. constructor()

En los distintos lenguajes de programación se utiliza el constructor que es un método para crear las instancias de una clase. En React, se utilizará el constructor para crear la instancia del componente.

2. static getDerivedStateFromProps(nextProps, prevState)

Es un método estático, usado después de crear la instancia del componente, o en caso de receptar cambios en las propiedades del componente. 

3. shouldComponentUpdate(nextProps, nextState)

El retorno de este método es true o false. Su incidencia está en el renderizado del componente, ya que se ejecuta ese método en el que se decide si los cambios en las **props** o en el **state** requieren una nueva renderización. 

4. getSnapshotBeforeUpdate(prevProps, prevState)

Este método se ejecuta después de render() y antes de componentDidUpdate(). El retorno del método luego se usará en la función de componentDidUpdate(prevProps, prevState, snapshot).

5. render()

El método render() es de suma importancia ya que permitirá que los componentes se visualizen en el navegador. 

6. componentDidUpdate(prevProps, prevState, snapshot)

El método recibe las props y el state para verificar la comparacoón actual y anterior. Se ejecuta luego de que el componente ha sido actualizado y se vea reflejado en el DOM. 

7. componentWillUnmount()

Este método permite liberar recursos y memoria, este proceso se da antes de desmontar el componente en el DOM. 

<p align="center">
<img src="https://codingfactsblog.files.wordpress.com/2017/07/react-lifecycle.png" width="50%" alt="Banner"/>
</p>