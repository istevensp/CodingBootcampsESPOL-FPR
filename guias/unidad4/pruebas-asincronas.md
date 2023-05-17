## Pruebas asíncronas

[Regresar](/CodingBootcampsESPOL-FPR/)

En las aplicaciones de React la mayoría de las funcionalidades son asíncronas. Las pruebas asíncronas suele tener grado de complejidad, sin embargo, existen herramientas que nos ayudarán en este proceso. 

A continuación, se muestra un ejemplo de código.

* El primer componente acepta una función que devuelve una promesa. Dicha función se invoca cuando se hace clic en el botón. 

```js
const DisplayData = ({ get }) => {
  const [display, setDisplay] = React.useState(null);

  const getData = async () => {
    try {
      const data = await get();
      setDisplay(data);
    } catch (err) {
      setDisplay("**** ERROR ****");
    }
  };
  return (
    <>
      <button type="button" onClick={getData} aria-label="get data">
        Get data
      </button>
      {display && (
        <div className="display" aria-label="display">
          {display}
        </div>
       )}
    </>);
};
```
En el botón se define el onClick que llama a la función **getData** y de ah regresa la promesa con el **await**. Luego el **display** establece el resultado o muestra el error.

* Existe un segundo componente que es el Timer para esperar 20 segundos.

```js
const TimerMessage = () => {
  const [message, setMessage] = React.useState(null);

  React.useEffect(() => {
    setTimeout(() => setMessage("Hello"), 20000);
  }, []);

  return (
    <div>
      {message && (
        <div className="message" aria-label="Message">
          {message}
        </div>
      )}
    </div>);
};
```
El código anterior usa el hook Effect. Además, dentro de ese hook se define la llamada a **setTimeout** en la que se establece el mensaje luego de esperar 20 minutos. 

### Pruebas de una función asíncrona

Se procederá a probar el primer componente. Para ello se necesita crear una función simulada que devulebe la promesa. Usando jest.fn que realizarán 2 escenarios uno con el resultado esperado y el otro con la condición de error. 

```js
const successResult = "Some data";
const getSuccess = jest.fn(() => Promise.resolve(successResult));
const getFail = jest.fn(() => Promise.reject(new Error()));
```

Para hacer las pruebas en el temporizador se debe llamar a jest.useFakeTimers() que nos permitirá usar temporizadores falsos. 
Utilizando React Testing Library se procede a crear el componente:

```js
const { queryByLabelText } = render(<TimerMessage />);
```
El temporizador se ejecutará si el componente está montado en el DOM usando la función mount:

```js
const wrapper = mount(<TimerMessage />);
```

Se continua con la parte de forzar el temporizador usando **jest.runAllTimers()**

```js
const afterTimer = queryByLabelText(/message/i);
expect(afterTimer.textContent).toEqual("Hello");
```

