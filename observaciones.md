# Observaciones

Querida Tati, felicitaciones por tu trabajo. Tu portfolio se ve muy lindo y se nota muchísimo el esfuerzo por hacer que se asemeje al modelo de Ada. Hay muchos detalles que lo mejoran - los efectos en el hover por ejemplo - y recorriendolo se ve el esmero que pusiste.

El mayor problema en tu portfolio es que el responsive no funciona, lo que afecta negativamente tu nota a pesar de que se nota que pusiste esfuerzo. Una web sin responsive no está completa: la mayoría de nuestros usuarios van a ver nuestra web desde el celular, por lo que es absolutamente necesario poder ofrecerles la misma experiencia a ellos. Noto el interés por hacer que tu web sea lo mas responsive posible, en el sentido de que las secciones se mueven y en algunas resoluciones todo funciona de manera aceptable (600px por ejemplo), por lo que no sé si te faltó tiempo o no lo pudiste resolver. Si es el segundo caso, me escribirías? Asi podemos verlo juntas más en detalle.

Te dejo varios comentarios para mencionar cositas puntuales. Como comentamos en clase, este trabajo no se hace para que constates conocimientos, sino para que aprendas: en ese sentido, mi intencion es que estos comentarios te sirvan para aprender, mejorar tu codigo a futuro e ir apreciando mejor qué se espera de nosotras como desarrolladoras front end.

## Estructura correcta de documento HTML

Tu HTML esta muy bien. Claro, prolijo, sin elementos de más, muy bien comentado.

El lenguaje de tu documento de HTML está en inglés, por lo que un lector de pantalla va a tratar de leer todos tus textos en inglés. El efecto es muy feo y confuso: pronuncian en inglés las palabras en español, así que si ven "generador de memes" van a leer "yiniradour di mims". Siempre tratá de que el atributo `lang` de tu HTML refleje el idioma de los textos en tu página.

El titulo es "Document", lo que no es correcto, debería ser uno que refleje tu portfolio.

## Respeta la consigna

- El portfolio cuenta con las secciones solicitadas

Cumplido

- Al clickear en los links de navegación, debe llevar a la sección correspondiente

Cumplido.

- Al clickear en los links de contacto, debe llevar a la página externa
  correspondiente

No cumplido a fines practicos. Esta el codigo, pero es asi: 

```html
<div class="twitter">
    <i class="fab fa-twitter" aria-label="Twitter icono" id="icon-fotter"></i>
    <a href="https://twitter.com/"></a>
</div>
```

La etiqueta `a`, debe rodear a un elemento para que el link funcione. En este caso el div rodea a la etiqueta a, asi que el link no sirve. Por otro lado, noto que los iconos estan corridos: el div "twitter" por ejemplo deberia ser el que tiene el color de fondo blanco, y el icono solo ser un icono. De ese modo te va a ser mucho mas facil centrarlo. 

- El portfolio debe tener un diseño responsivo y verse correctamente en distintos dispositivos

No cumplido. Comenté en clase que la guia de bootstrap para las media queries me parece la mejor, te la dejo acá. Esto nos permite enfocarnos en los tamaños mas habituales, y a la vez asegurarnos de que no dejamos afuera a ningún dispositivo.

```css
/* Celulares */
@media (max-width: 576px) {
  ...;
}

/* Celulares en modo horizontal y tablets pequeñas */
@media (max-width: 768px) {
  ...;
}

/* Tablets  */
@media (max-width: 992px) {
  ...;
}

/* Monitores pequeños */
@media (max-width: 1200px) {
  ...;
}

/* Monitores grandes */
@media (max-width: 1400px) {
  ...;
}
```

- El portfolio debe estar deployado y ser accesible desde una URL

Cumplido, pero esta URL debe estar en el readme.

- El repositorio en GitHub debe tener un readme adecuado

Cumplido raspando, necesita si o si link a tu portfolio y no te dañaría hacerlo un poco más extenso y amable :)

### Respeta el diseño dado

Cumplido, excepto por las tarjetas de Mis Proyectos. Tienen muchisimo padding los contenedores asi que las tarjetas no entran, en mi pantalla se ven una debajo de la otra incluso en desktop.

Fijate que a container-columns-one le diste un padding horizontal de 250px, y luego a column-boxes le diste un padding horizontal de 150px. En una pantalla que mide 1440px, eso significa que tenemos 400px a la derecha y 400px a la izquierda solo en padding: nos quedan libres solo 600px para las tarjetas. No entran. Saca ese padding, cuando quieras centrar las cosas tenes que usar `flex`.

### Buena estructura de proyecto

Usás muchas imágenes en tu proyecto, y viéndolo a primera vista en github no es tan fácil ver cuáles son los archivos principales. Siempre que uses imágenes locales, como en este caso, agregalas a una carpeta que se llame por ejemplo "imgs", "imagenes" o "assets". De esta manera solo los archivos principales - html, readme y css - son los que están en la carpeta principal. La excepción a esta regla es el favicon, que siempre debería ir en la carpeta principal.

Tenes una carpeta dentro que se llama "portfolio" que por lo que veo tiene duplicado el css - pero en tu HTML no linkeas a ese CSS sino al que tenes en la carpeta principal. Para qué esta esa carpeta?

### Código bien indentado

No cmplido para CSS basicamente porque hay muchisima indentacion, al nivel que tengo que hacer scroll a la derecha para poder verlo. Que paso ahi? Tu codigo debe estar prolijo, especialmente en un trabajo a entregar.

### Comentarios que permiten mejorar la legibilidad del código

No cumplido. Es algo que ayuda mucho al lector para encontrar lo que busca. Minimo indica cada seccion con un comentario, tanto en HTML como en CSS. 

### Uso correcto de etiquetas semánticas

Cumplido. 

### Buenos nombres de clases

Cumplido en general. 

Cuando quieras separar palabras, como en "myPerson", escribilo con guiones: "my-person". 

"myPerson" es un nombre que solo vos vas a entender. Trabajamos en equipo: escribi nombres claros. "seccion-welcome-descripcion" es mejor. 

"container-fotter-two", "conocimientos-one", no me dicen la funcion que cumplen estos elementos. Noto algunas clases que tienen identidades confusas y problemas con lo que consideramos "descriptivo". Cuando decimos que un nombre de clase debe ser descriptivo, lo decimos en un sentido funcional: qué rol cumple este elemento en el código. Los colores de los elementos, su forma, su estilo, su posición, todas esas cosas pueden cambiar y efectivamente cambian todo el tiempo en las webs que hacemos. El botón que hoy es violeta mañana será azul; la sección que estaba a la derecha mañana estará arriba, el texto que hoy saluda mañana será una publicidad. Lo que hoy llamamos "dos" mañana puede ser "cinco". Por lo tanto esos factores sos no son buenos descriptores, y no deberían ser parte de nuestros nombres de clases. Deberían cambiarse para representar qué son en tu página: la sección que tiene una cita, el formulario de contacto.

### Código CSS bien estructurado

Cumplido. Noto muchos estilos innecesarios o confusos, que te voy indicando en tu archivo de css.

### Reutilización de estilos

Cumplido la mayoría de las veces, noto muchos intentos por reutilizar los estilos. La clase "flex" esta muy bien usada. A veces parecés olvidarlo, como en el siguiente caso:

```css
.container-forms-one,
.container-forms-two {
    height: 500px;
    width: 500px;
    display: flex;
    flex-direction: column;
    align-items: center;
    border-radius: 10px;
}
```

Si estos elementos tienen exactamente los mismos estilos, por que tienen distintos nombres de clase? La idea de las clases es justamente que todos los elementos que son iguales tengan el mismo nombre de clase. Podrías haberle dado a cada uno de esos elementos el mismo nombre, "container-forms" por ejemplo, y sólo tendrías una clase. Lo mismo para las redes sociales de tu footer: de que sirve tener la clase "twitter", "git", etc, si son todos iguales? No repetirnos a nosotras mismas es un principio muy importante en programación, porque en la repetición se encuentran buena parte de nuestros errores. Reutilizá tus clases siempre que puedas.

### Cumple con criterios básicos de accesibilidad

- Los colores tienen un contraste adecuado

No cumplido cuando el fondo es #5C9794 y el color de texto es blanco (tus botones). Siempre recordá chequear estas cosas con herramientas del tipo https://webaim.org/resources/contrastchecker/

- Las imágenes tiene el atributo `alt` que corresponde

Cumplido. 

- Los íconos y elementos que no presentan texto agregan la información correspondiente por otros medios (etiquetas aria, texto oculto)

Cumplido. 

- Los íconos y elementos que no necesitan ser anunciados por un lector de pantalla tienen la etiqueta aria correspondiente

No veo ejemplos en tu portfolio, pero tampoco veo que sea necesario.

- Commits con mensajes adecuados

Cumplido, noto muchos y buenos commits en tu proyecto, lo que siempre se agradece.

- Cuenta con un favicon

No cumplido. 

### Nota: 7
