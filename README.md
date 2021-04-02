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
