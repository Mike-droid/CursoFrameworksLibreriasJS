# Curso de Frameworks y librerías de JavaScript

## Fundamentos del Desarrollo Web Profesional

### Cuándo necesitas un framework de JavaScript

Los frameworks ayudan a los desarrolladores a hacer aplicaciones web de manera más rápida. Casi podemos usar completamente JS para hacer esto. Pero usar solo JS es contraintuitivo.

Ejemplos de sitios web: Landing page. páginas estáticas

Ejemplos web apps: Cosas más complejas, las páginas son dinámicas

No hay un mejor framework, depende del caso particular.

### Qué son los componentes: historia y evolución del desarrollo web

En un principio HTML, CSS y JS eran diferentes para cada navegador, hasta que se fueron volvieron estándares. Pero jQuery fue la tecnología que hacía que JS fuese compatible en todos los navegadores.

jQuery ya murió, es inútil.

JS está tan bien que ya empieza a reemplazar a HTML. Cada vez escribimos más JS que HTML.

Los componentes son aplicar un concepto muy parecido a las funciones pero para maquetar.

**Composición de componentes:** Es poder crear componentes que estén hechos de otros componentes.

### Cómo estructurar un componente

```html
<header>
  <nav>
    <section>
      <section>
        <img src="logo-platzi.png"/>
        <img src="live.png"/>
      </section>
      <section>
        <ul>
          <li><a>Cursos</a></li>
          <li><a>Blog</a></li>
          <li><a>Foro</a></li>
          <li><a>Agenda</a></li>
          <li><a>TV</a></li>
          <li><a>Contáctanos</a></li>
        </ul>
      </section>
    </section>
    <section>
      <nav dropdown>Iniciar mi plan</nav>
      <button>Iniciar sesión</button>
      <div>
        <input type="text" placeholder="Buscar en Platzi"></input>
        <button><img src="search-icon.png"/></button>
      </div>
    </section>
  </nav>
</header>
```

```html
<header-platzi>
  <logo-plazti></logo-plazti>
  <enlaces-platzi></enlaces-platzi>
  <sesion-platzi></sesion-platzi>
  <busqueda-platzi></busqueda-plazti>
</header-platzi>
```

Quizás tener 1 componente para muchísimas formas distintas no sea lo mejor.

### Componentes: reactividad, estrategias de render, estado y ciclo de vida

*Reactividad:* Es un paradigma, una forma de pensar nuestras aplicaciociones. Deben seguir 2 reglas:

1. Responsive, es decir, deben ser *resilientes* (siempre sabe qué hacer) y *escalables* (no importa con cuánta información debemos trabajar o cuántos usuarios entran a la aplicación, la aplicación debe poder seguir funcionando sin problemas).
2. Message Driven (Arquitectura basada en mensajes). Deben de haber emisores y receptores de mensajes. Los mensajes se entregan de manera asíncrona.

*Recuerda:* La arquitectura no es ajena a la programación.

*Estado:* Es el lugar donde vamos a guardar la información reactiva de nuestros componentes. Son variables a las que nos suscribimos para recibir una notificación cada vez que cambian sus valores.

*Render*: o renderizado, es el proceso por el cual nuestro HTML, pasan a ser información visual en el DOM.

Estrategias de render: Virtual DOM y No Virtual DOM. Ninguna es mejor, depende del caso en particular.

Componente -> Estado -> Render -> Usuario (y vuelve a "Estado")

### Librerías vs. frameworks

*Framework*: Una manera de trabajar y hacer las cosas, incluye librerías.

*Librería*: Un código que tiene una función muy en particular.

### Ecosistema de frameworks y librerías JavaScript

*Empaquetadores*: Webpack, Parcel, Rollup. Tenemos muchos archivos que no podemos simplemente mandarlos al navegador. Hay que minificarlos para que pesen menos y estén optimizados. Webpack usa `webpack.config.js` en el que especificaremos cómo queremos que empaquete nuestros archivos. Parcel por su lado lo hace todo de manera automática, pero si podemos ser específicos es mejor usar Webpack.

*Compiladores*: Babel y TypeScript: Transforman código a lenguaje JS. Babel nos permite escribir JS moderno y lo transforma a JS no moderno para que todos los navegadores lo entiendan. TS por su lado es como JS orientado a objetos.

*Herramientas para UI*: React, Vue, Svelte, y otros más xD. Conforman componentes en render.

*CSS y prepocesadores*: CSS3, Sass, Less, Stylus, etc.

*CSS-in-JS*: Usamos JS para escribir CSS.

*Routers*: React Router, Vue Router, Svelte Router, LitElemet Router, bla bla bla ... es la forma en que hacemos la navegación de nuestro sitio web.

*Frameworks*: todo en uno. Angular.

*Entornos de desarrollos* (todo en uno): Create React App, Vue CLI, Svelte CLI, Poylemer CLI, bla bla bla...

*Manejo del estado*: Redux, XState, MobX

*Consulta de datos*: API REST, GraphQL

## Contexto y funcionamiento de los Frameworks JavaScript

### Cómo construyeron React.js

Ecmascript es el estándar de JavaScript.

Facebook creó React.

React busca cumplir con ser:

- Declarativo: Que sea muy fácil de leer
- Basado en componentes
- Multiplataforma: Learn Once, Write Anywhere

*React DOM* es la herramienta de Facebook oficial para hacer render.

La manera de trabajar ahora con React es usando React Hooks.

### Cómo funciona un componente en React

Los componentes en React funcionan como bloques de lego, juntamos algo y podemos hacer algo más grande.

*Montaje*: Primer paso del ciclo de vida de un componente.

*Actualización*: Cuando los componentes pasan por el método `render()`

Cuando vamos a otra sección de la página, los componentes se eliminan. React eliminará código del DOM.

### Manipulación del DOM y flujo de trabajo al estilo React

Todo lo que empiece por "on" en React es un evento.

Form.js:

```javascript
import React from "react";

export default function Form(props) {
  const [quantity, setQuantity] = React.useState(0);
  const { movie } = props;
  return (
    <form>
      <h3>{movie.name}</h3>
      <button
        type="button"
        onClick={() => setQuantity(quantity - 1)}
        disabled={quantity <= 0}
      >
        -
      </button>
      {quantity}
      <button
        type="button"
        onClick={() => setQuantity(quantity + 1)}
        disabled={quantity >= movie.available}
      >
        +
      </button>
    </form>
  );
}

```

App.js:

```javascript
import Form from "./Form";

const movies = [
  {
    name: "Avengers",
    available: 5
  },
  {
    name: "Terminator",
    available: 3
  }
];

export default function App() {
  return (
    <div>
      <h2>Películas</h2>
      {movies.map((movie) => (
        <Form movie={movie} />
      ))}
    </div>
  );
}

```

### Cómo construyeron Angular

Angular JS se volvió open source en el 2010 y es patrocinado por Google.

Angular tiene a Angular Ivy para renderizar los componentes en el navegador y usa Incremental DOM.

### Manipulación del DOM y flujo de trabajo al estilo Angular

```html
<h2>{{ title }}</h2>

<form *ngFor="let movie of movies">
  <h3>{{ movie.name }}</h3>

  <button
    type="button"
    (click)="removeMovieQuantity(movie.name)"
    [disabled]="movie.quantity <= 0"
  >
    -
  </button>
  {{ movie.quantity }}
  <button
    type="button"
    (click)="addMovieQuantity(movie.name)"
    [disabled]="movie.quantity >= movie.available"
  >
    +
  </button>
</form>

```

```typescript
import { Component } from "@angular/core";

type Movie = {
  name: String;
  available: Number;
  quantity: Number;
};

type Movies = Array<Movie>;

@Component({
  selector: "app-root",
  templateUrl: "./app.component.html"
})
export class AppComponent {
  title: String = "Películas";
  movies: Movies = [
    {
      name: "Avengers",
      available: 3,
      quantity: 0
    },
    {
      name: "Terminator",
      available: 5,
      quantity: 0
    }
  ];

  addMovieQuantity(movieName) {
    const movieIndex = this.movies.findIndex(
      (movie) => movie.name === movieName
    );

    this.movies[movieIndex].quantity += 1;
  }

  removeMovieQuantity(movieName) {
    const movieIndex = this.movies.findIndex(
      (movie) => movie.name === movieName
    );

    this.movies[movieIndex].quantity -= 1;
  }
}
```

### Cómo construyeron Vue

Vue es progresivo, escalable, pero flexible. Se integra bien con cualquier app (no como angular). Vue es completamente reactivo (no como React).
Podrás usar HTML al principio pero poco a poco usarás más JS.

[Documental de Vue JS](https://www.youtube.com/watch?v=OrxmtDw4pVI)

### Manipulación del DOM y flujo de trabajo al estilo Vue

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Static Template</title>
  </head>
  <body>
    <div id="root">
      <h2>Películas</h2>
      <form v-for="movie in movies">
        <h3>{{ movie.name }}</h3>

        <button
          type="button"
          v-on:click="movie.quantity -= 1"
          :disabled="movie.quantity <= 0"
        >
          -
        </button>
        {{ movie.quantity }}
        <button
          type="button"
          v-on:click="movie.quantity += 1"
          :disabled="movie.quantity >= movie.available"
        >
          +
        </button>
      </form>
    </div>
    <script src="https://unpkg.com/vue@3.0.5/dist/vue.global.js"></script>
    <script>
      const { createApp } = Vue;

      const app = createApp({
        data() {
          return {
            movies: [
              {
                name: "Avengers",
                available: 3,
                quantity: 0
              },
              {
                name: "Terminator",
                available: 5,
                quantity: 0
              }
            ]
          };
        }
      });
      app.mount("#root");
    </script>
  </body>
</html>
```

### Cómo construyeron Svelte

No crea intermadiarios entre tu código y el DOM.

Svelte es buenísimo para sitios web y no tan bueno para aplicaciones web.

Svelte es un compilador y necesita hacer un AST (Abstract Syntax Tree).

### Manipulación del DOM y flujo de trabajo al estilo Svelte

```html
<script>
  import Form from "./Form.svelte";
</script>

<main>
  <h2>Películas</h2>

  <Form/>
</main>
```

```html
<script>
  const movies = [
    {
      name: "Avengers",
      available: 3,
      quantity: 0
    },
    {
      name: "Terminator",
      available: 5,
      quantity: 0
    }
  ];
</script>

{#each movies as movie}
<form>
	<h3>{movie.name}</h3>

	<button type="button"
  on:click={() => movie.quantity -= 1}
  disabled={movie.quantity <= 0}
  >
		-
	</button>

	{movie.quantity}

	<button type="button"
  on:click={() => movie.quantity += 1}
  disabled={movie.quantity >= movie.available}
  >
		+
	</button>
</form>
{/each}
```

## Estilos con CSS, preprocesdaores y CSs-in-JS

### Qué es CSS-in-JS

Es la forma de escribir CSS desde JavaScript. Aumenta la ventaja de usarlo en componentes.

Ejemplo de React Components:

```javascript
const Title = styled.h2`
	color: ${props =>
	props.error
	? 'red'
	: 'white'
	)};
`;
```

```html
<Title>¡Título blanco!</Title>
<Title error>¡Título rojo!</Title>
```
Los estilos globales no son una desventaja de CSS-in-JS.

## Cómo escalar sitios o aplicaciones web

### Tipos de aplicaciones según su router: SPAs vs SSR
