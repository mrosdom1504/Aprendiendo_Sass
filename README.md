# ¿Por qué usar Sass en el desarrollo FrontEnd?
Este repositorio utiliza Sass (Syntactically Awesome Style Sheets) para mejorar la eficiencia y mantenibilidad del código CSS. Sass es un preprocesador de CSS que permite escribir estilos de manera más rápida, organizada y escalable. 
A continuación, te explicaré por qué creo que Sass es una herramienta esencial para el desarrollo FrontEnd moderno.
# 1. Variables: Reutilización y consistencia
Sass permite definir variables para almacenar valores que se repiten en tu CSS, como colores, fuentes, tamaños, etc. Esto facilita la reutilización y garantiza la consistencia en todo el proyecto.
````css
$primary-color: #3498db;
$font-stack: 'Helvetica', sans-serif;

body {
  font-family: $font-stack;
  color: $primary-color;
}
````

# 2. Anidamiento: Estructura clara y legible
Con Sass, puedes anidar selectores para reflejar la estructura HTML, lo que hace que el código sea más legible y organizado.
````css
nav {
  ul {
    margin: 0;
    padding: 0;
    list-style: none;

    li {
      display: inline-block;
    }
  }
}
````
# 3. Mixins: Reutilización de bloques de código
Los mixins son bloques de código reutilizables que pueden incluirse en diferentes partes del CSS. Son ideales para estilos complejos o repetitivos.
````css
@mixin border-radius($radius) {
  -webkit-border-radius: $radius;
     -moz-border-radius: $radius;
      -ms-border-radius: $radius;
          border-radius: $radius;
}

.button {
  @include border-radius(10px);
}
````
# 4. Herencia: Evita la duplicación de estilos
Sass permite la herencia de estilos usando @extend, lo que ayuda a evitar la duplicación de código.
````css
%message-shared {
  padding: 10px;
  border: 1px solid #ccc;
}

.message {
  @extend %message-shared;
}

.success {
  @extend %message-shared;
  border-color: green;
}
````
# 5. Modularización: Dividir código
Sass permite dividir el código en múltiples archivos y luego importarlos en un archivo principal. Esto mejora la organización y mantenibilidad del proyecto.
````css
// _variables.scss
$primary-color: #3498db;

// styles.scss
@import 'variables';

body {
  color: $primary-color;
}
````
# 6. Funciones y operaciones: CSS dinámico
Sass incluye funciones y operaciones que permiten realizar cálculos y manipular valores directamente en el CSS.
````css
.container {
  width: 100% / 3;
  padding: 10px * 2;
}
````
