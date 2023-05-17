## Mock

[Regresar](/CodingBootcampsESPOL-FPR/)

### Mock para aplicaciones React

Por lo general, las aplicaciones en React tienen sus componentes que están anidados a otros componentes. Para probar un único componente se utiliza Mock de Jest. 

A continuación, se muestra un ejemplo:

```js
// example1/ChildComponent.js
function ChildComponent(){
  return(
    <div className="ChildComponent">
      Child component
    </div>
  )
}
```

```js
// example1/ParentComponent.js
function ParentComponent(){
  return(
    <div className="ParentComponent">
      <div>Parent Component</div>
      <ChildComponent />
    </div>
  )
}
```

El objetivo es probar ParentComponent. Se usará **screen.debug()** que imprirá la salida en consola o se puede utilizar otra declaración.

```js
// example1/__tests__/test1.js
import { screen, render } from '@testing-library/react'
import ParentComponent from '../ParentComponent'

test('ParentComponent and ChildComponent render', () => {
  render(<ParentComponent />)
  screen.debug()
  expect(screen.getByText(/Parent Component/i)).toBeInTheDocument()
  expect(screen.getByText(/Child Component/i)).toBeInTheDocument()
})
```

### Simular componentes React

Se reseescribirá la prueba y se agregará la regla `jest.mock('../ChildComponent')` para el componente secundario. 

```js
// example1/__tests__/test2.js
import { screen, render } from '@testing-library/react'
import ParentComponent from '../ParentComponent'

jest.mock('../ChildComponent')

test('ParentComponent renders and ChildComponent does not', () => {
  render(<ParentComponent />)
  expect(screen.getByText(/Parent Component/i)).toBeInTheDocument()
  // notice the .not
  expect(screen.queryByText(/Child Component/i)).not.toBeInTheDocument()
})
```
### Simulacros automáticos con jest.mock()

jest.mock() es una prueba que toma como como primer parámetro la ruta al archivo en el que se encuentra el módulo. Si no existe un segundo párametro entonces Jest realiza el simulacro automático. 

Enresumen, para simular un componente en React utilizamos `jest.mock(path)` lo que hace un mock automático del componnete. Accede a este simulacro llamándolo por su nombre después de importarlo. A continuación, se muestra el código final del **ParentComponent**.

```js
// example1/__tests__/test4.js
import { screen, render } from '@testing-library/react'
import ParentComponent from '../ParentComponent'
import ChildComponent from '../ChildComponent'

jest.mock('../ChildComponent')

test('ParentComponent rendered', () => {
  render(<ParentComponent />)
  expect(screen.getByText(/Parent Component/i)).toBeInTheDocument()
})

test('ChildComponent mock was called', () => {
  render(<ParentComponent />)
  expect(ChildComponent).toHaveBeenCalled()
})
```

## Referencias

* React Router. Retrieved May 09, 2023, from [https://dev.to/peterlidee/mocking-react-components-jest-mocking-react-part-2-2l8j](https://dev.to/peterlidee/mocking-react-components-jest-mocking-react-part-2-2l8j)