# FakeStore.shop

FakeStore somos comercio en línea con una gran cantidad de productos a comercializar. Estamos por lanzar nuestra implementación y necesitamos resolver los problemas que presenta nuestra aplicación.

FakeStore tiene varios bugs, tareas sin completar y recursos a implementar para su lanzamiento oficial.

### Instalación

```
npm install
```

### Ejecución

```
npm run start
```

### Debug

- http://fakestore.shop
- localhost:8080/public

### Documentación

- Variable llamada $app donde haremos render de nuestra app.
- Elemento del DOM que será Observado.
- Constante 'API': Utilizamos la FakeAPI de Platzi.

```javascript
const $app = document.getElementById("app");
const $observe = document.getElementById("observe");
const API = "https://api.escuelajs.co/api/v1/products";
```

Función llamada 'getData' que se encarga de hacer Fetch a una API y debe de construir un elemento nuevo en el DOM.

```javascript
const getData = (api) => {
  fetch(api)
    .then((response) => response.json())
    .then((response) => {
      const products = response;
    })
    .catch((error) => console.log(error));
};
```

Función encargada de obtener de los Productos.

```javascript
const loadData = () => {
  getData(API);
};
```

Intersection Observer

```javascript
const intersectionObserver = new IntersectionObserver(
  (entries) => {
    // logic...
  },
  {
    rootMargin: "0px 0px 100% 0px",
  }
);

intersectionObserver.observe($observe);
```

### Licencia

js-challenge se lanza bajo la licencia [MIT](https://opensource.org/licenses/MIT).
