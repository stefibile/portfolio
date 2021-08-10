# Observaciones

Stefi, felicitaciones por tu trabajo. Es increible el nivel de atención al detalle que demostras con este trabajo: cada espaciado, cada linea, se nota que está pensada y repensada. Me gusta cómo seguis el modelo pero ademas le das tu estilo con los colores y las imágenes, que lindo toque tu "firma" junto a la foto. El resultado es una web que te refleja y a la vez cumple a la perfección lo solicitado.

Tengo, lamentablmemente, pocos comentarios para hacerte, ya que el nivel de este trabajo es realmente muy alto. Pero siempre hay algo que comentar! :) Como dije en clase, este trabajo no se hace para que constates conocimientos, sino para que aprendas: en ese sentido, mi intencion es que estos comentarios te sirvan para aprender, mejorar tu codigo a futuro e ir apreciando mejor qué se espera de nosotras como desarrolladoras front end.

## Estructura correcta de documento HTML

Tu HTML esta realmente excelente. Claro, prolijo, muy bien comentado e identado.

Algo que me llama la atención es tu `head`, dado que allí repetís innecesariamente el link de google fonts. No es necesario escribilo dos veces

```html
    <link rel="preconnect" href="https://fonts.gstatic.com">
    <link rel="preconnect" href="https://fonts.gstatic.com">
```

Cada uno de esos links hace exactamente lo mismo - traerse el css de google fonts para poder usar los fonts en tu sitio. Quizá estés bajo la impresión de que por cada uno de los fonts de tu web es necesario traerse nuevamente el css, pero no, no es necesario agregarlo más de una vez. Agregar muchos de estos links innecesarios impacta negativamente en la velocidad de carga de tu web, ya que por cada uno de ellos se hace un llamado a un css externo y se lo carga. 

Tenés cierta tendencia a tener divs de más. Algunas estructuras de tu web se podrían resolver con menos divs. Dicho esto, yo prefiero que los divs sobren antes de que falten: un div de más se soluciona muy fácil, un div menos puede ser un gran dolor de cabeza cuando estamos recién arrancando. Este sería un comentario que quizá me reservaría para futuros trabajos, pero veo tan bien tu código que me siento confiada en recomendarte que empieces a ver estas cosas desde ya. 

Si tenés ganas, con tiempo, te diría que valdría la pena recorrer tu html y notar que estructuras como "contenedorfooter" son innecesarias. Te lo comento aquí como un ejemplo, pero esto es algo que se repite a lo largo de tu código. 

## Respeta la consigna

- El portfolio cuenta con las secciones solicitadas
- Al clickear en los links de navegación, debe llevar a la sección correspondiente
- Al clickear en los links de contacto, debe llevar a la página externa
  correspondiente
- El portfolio debe tener un diseño responsivo y verse correctamente en distintos dispositivos
- El portfolio debe estar deployado y ser accesible desde una URL
- El repositorio en GitHub debe tener un readme adecuado

Todos estos puntos están cumplidos. Menciono especialmente tu responsive: es increíble lo bien que solucionaste las distintas resoluciones, siguiendo casi a la perfección el modelo y preocupandote para que todo se vea hermoso, veamos tu web desde cualquier dispositivo. 

El único comentario que te haría al respecto es que en las resoluciones de 400 a 320px (celulares pequeños) tu codigo "rebalsa". Te das cuenta porque hay un scroll horizontal, y una especie de barra blanca que cubre todo el extremo derecho. Esto ocurre normalmente cuando hay un elemento que rebalsa su contenedor, forzando que el body sea más grande que la pantalla. En tu caso, ese elemento es el nav del footer. Prestá atención a este código: 

```css
@media (max-width: 701px)
.navfooter {
    visibility: hidden;
}
```

Visibility hidden hace que el elemento no se vea, pero *continua ocupando espacio*. En tu caso, es mas ancho que el body de los celulares mas pequeños, y eso hace que rebalse. Privilegiá usar display: none para que los elementos desaparezcan, y usá visibility hidden para animaciones. 

### Respeta el diseño dado

Cumplido a la perfección. 

### Buena estructura de proyecto

Cuando tenés más de un archivo de css, es buena práctica ponerlos a todos en una carpeta que se llame styles. Estiloform no se usa, asi que deberias borrarlo. Ahora bien... estilosflex no se usa en absoluto tampoco, no existen esas clases en tu portfolio. Entonces, para que tenes estos archivos de css? 

La imagen del readme debería ir en la carpeta img. 

### Código bien indentado

Tabulas muy bien, lo cual parece un detalle extra cuando una recien comienza pero ayuda un monton a su legibilidad, y que lo hayas logrado en esta etapa es un gran mérito. 

### Comentarios que permiten mejorar la legibilidad del código

Ausentes. Ayudan mucho al lector para encontrar lo que busca, acostumbrate a separar tus secciones con comentarios. 

### Uso correcto de etiquetas semánticas

En general usas bien las etiquetas semánticas. Me llama la atención que hayas usado `div` para las tarjetas de Mis Conocimientos y Mis Proyectos: yo diría que deberían ser `article`. Pero es el único detalle a comentar aquí (y hay quien podría discutirme que deberían ser divs)

Usas mas de un `h1` en tu web. El h1 es el titulo principal, y debería haber sólo uno por página. El resto deberían estar en orden de jerarquía: h2 para los titulos de secciones, h3 para los títulos dentro de cada subsección, etc. En este caso, "Mis conocimientos", "Mis proyectos" etc deberían ser h2 y los títulos de las cards deberían ser h3. 

### Buenos nombres de clases

Si tenes una clase que es "htmlimg", asumo que esa imagen es la de html. Sin embargo, se repite en varias mas. Encontrá un nombre que sirva para todas. 

Cuando quieras separar palabras, como en "buttonpresentation", escribilo con guiones: "button-presentation". 

"proimg" es un nombre que solo vos vas a entender. Trabajamos en equipo: escribi nombres claros. "imagenes-proyectos" es mejor. 

"Hola", "holadiv", "phola", no me dicen nada de la funcion que cumplen estos elementos. Noto algunas clases que tienen identidades confusas y problemas con lo que consideramos "descriptivo". Cuando decimos que un nombre de clase debe ser descriptivo, lo decimos en un sentido funcional: qué rol cumple este elemento en el código. Los colores de los elementos, su forma, su estilo, su posición, todas esas cosas pueden cambiar y efectivamente cambian todo el tiempo en las webs que hacemos. El botón que hoy es violeta mañana será azul; la sección que estaba a la derecha mañana estará arriba, el texto que hoy saluda mañana será una publicidad. Por lo tanto esos factores sos no son buenos descriptores, y no deberían ser parte de nuestros nombres de clases. Deberían cambiarse para representar qué son en tu página: la sección que tiene una cita, el formulario de contacto.

### Código CSS bien estructurado

Cumplido a nivel formal. Noto algunos estilos innecesarios o confusos, que te voy indicando en tu archivo de css.

### Reutilización de estilos

Cumplido en general, pero muchas veces podrias usar dos nombres de clase para el mismo elemento, uno general y otro más específico, para evitar repeticiones innecesarias. 

Repetis muchisimos display: flex que no necesitas, ojo con eso. Display flex sirve para acomodar los hijos de un contenedor: no tiene sentido si el elemento no tiene hijos. Vale la pena que te tomes unas horas para desactivar tus estilos uno por uno, y vas a ver la inmensa cantidad de cosas que agregaste sin sentido. Te menciono la mayoria que encontré. 

### Cumple con criterios básicos de accesibilidad

- Los colores tienen un contraste adecuado

Cumplido. 

- Las imágenes tiene el atributo `alt` que corresponde

Cumplido a medias. "Imagen ilustrativa del proyecto" no está bien, el usuario va a asumir que si ponés una imagen al lado de tu proyecto es porque lo ilustra. En el alt le describimos la imagen tal cual es: "Mujer parada junto a un cuadro", "Gato persiguiendo una pelota". No necesitamos aclarar que es una imagen, eso lo hace el lector de pantalla. 

- Los íconos y elementos que no presentan texto agregan la información correspondiente por otros medios (etiquetas aria, texto oculto)

Cumplido

- Los íconos y elementos que no necesitan ser anunciados por un lector de pantalla tienen la etiqueta aria
  correspondiente

No veo que lo uses, pero tampoco que lo necesites. 

- Commits con mensajes adecuados

Cumplido, noto muchos y buenos commits en tu proyecto, lo que siempre se agradece.

- Cuenta con un favicon

Cumplido, aunque debería ser un archivo .ico en lygar de .png. 

### Nota: 9
