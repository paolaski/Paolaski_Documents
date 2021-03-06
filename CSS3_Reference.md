##### *Paolaski (cc) 2016*

# CSS3 - Cascade Style Sheets REFERENCE GUIDE
Guía basada en la documentación que ofrece [W3Schools](http://www.w3schools.com/css) sobre las hojas de estilo en cascada.  

## Herramientas online:  
- [CSSMinifer](www.cssminifier.com)
- [CSS3 Cheatsheet - By EMEZETA](http://i.emezeta.com/weblog/css3-cheatsheet/css3-cheatsheet-emezeta.pdf)
- [Learn Layouts](http://es.learnlayout.com)

## Index  
- [Introducción](#introducción)  
- [Sintaxis](#sintaxis)  
  - *[Identificadores](#identificadores), [Pseudo-Clases](#pseudo-clases), [Colores](#colores), [Unidades de medida](#unidades-de-medida).*  
- [Background - Fondos](#background---fondos-de-la-página)  
- [Border - Bordes del contenido](#border---bordes-del-contenido)  
- [Margin - Márgenes](#margin---márgenes)  
- [Padding - Relleno](#padding---margen-internorelleno)  
- [Height x Width](#height-x-width---altura-x-anchura)  
- [Box Model - Modelo de Cajas](#box-model---modelo-de-cajas)  
- [Outline - Contorno](#outline---contorno)  
- [Text - Textos](#text---textos)  
- [Fonts - Fuentes](#font---fuentes)  
- [Icons & SVG - Iconos y Gráficos Vectoriales](#icons--svg---iconos-y-gráficos-vectoriales)  
- [Posicionamiento](#position---posicionamiento)  
- [Float - Clear](#float-y-clear) 
- [Layout: Horizontal - Vertical align](#layout-horizontal---vertical-align)

-----

### Introducción
Para ubicar los estilos, existen tres formas:  

   Forma    |     Estilo    |    Ejemplo  
 -----------|---------------|---------------   
  En línea  | En elementos html |  `<p style="color: red"></p>`
  Interno   | En las etiquetas `<style></style>` del head | `<head><style> * { color: red; } </style></head>`  
  Externo   | Link enlazando al documento externo | `<head><link rel="stylesheet" type="text/css" href="mystyle.css"></head>`  
  
Se suele utilizar la forma externalizada, es la forma de dividir lo máximo posible el código html del css.  
  
#### Sintaxis:
La sintaxis para definir elementos css, es:  
  **nombre_elemento { atributo: propiedades; }**  
Si usaramos los tres estilos, el orden por el que prevalecerían los cambios sería: **en linea, interno, externo, y el explorador**.  
`/* ejemplo de comentarios */` - Definición de comentarios.  

#### Identificadores
Se puede hacer referencia a los elementos html id y class mediante dos elementos: **. para class y # para id**.  
*Ejemplo: .nomclass { color: red }*  

#### Selectores  
Los selectores unen o especifican los elementos a los que se les va a aplicar el estilo. Existen varios selectores:  

   Selector    |    Descripción  
---------------|-------------------------------
  (espacio)    |    Selector de descendiente   
      >        |    Selector de hijo (child)
      +        |    Selector de adjacente(hermano) 
      ~        |    Selector general  

El `(space)` seleccionará todos los descendientes de un elemento específico. Ejemplo: **div p** haría referencia a todos los elemeptos **p** contenidos dentro de **div**.  
El elemento `(>)` seleccionará todos los hijos inmediatos de un elemento específico. Ejemplo: **div > p**  
``` html
  <div>
  <p>Paragraph 1 in the div.</p> <!-- hijo directo -->
  <p>Paragraph 2 in the div.</p> <!-- hijo directo -->
  <span><p>Paragraph 3 in the div.</p></span> <!-- no es hijo pero sí descendiente -->
```  
El elemento `(+)` hace referencia a los elementos adjacentes de un elemento específico. Ejemplo `div + p` haría referencia al elemento **p** que está declarado después de **div**.  
El elemento `(~)` hace referencia a todos los elementos adjacentes de un elemento específico. Ejemplo `div ~ p` haría referencia a todos los elementos **p** que van declarados después de **div**.  

#### Pseudo-Clases:
Las pseudo-clases hacen referencia a estados temporales de los elementos, a estados por los que pasan al ser por ejemplo seleccionados, vistos (como los enlaces, etc). Las clases que existen son: 

Clase         |   Ejemplo      |    Descripción  
--------------|----------------|-----------------------------------------------  
:active	      |   a:active	   |    Selecciona el link activo (tras hacer click)  
:checked	    | input:checked  |  	Selecciona todos los `<input>` utilizados  
:disabled	    | input:disabled |	  Selecciona todos los `<input>` desactivados  
:empty	      |   p:empty	     |    Selecciona todos los `<p>` que no tienen hijos  
:enabled	    | input:enabled  |  	Selecciona todos los `<input>` que están activados  
:first-child  | p:first-child  |	  Selecciona todos los `<p>` que son los primer hijo de su padre  
:first-of-type| p:first-of-type|    Selecciona todos los `<p>` que son los primer hijo de `<p>` de su padre  
:focus	      |   input:focus  |   	Selecciona todos los `<input>` que están con el foco (siendo utilizados-seleccionados)  
:hover      	|     a:hover    |  	Selecciona el link mientras está el cursor encima  
:in-range	    | input:in-range |  	Selecciona todo elemento `<input>` sin un rango específico  
:invalid	    | input:invalid	 |    Selecciona todos los `<input>` que tengan un valor inválido  
:lang         | 	p:lang(it)   |	  Selecciona todos los `<p>` con el atributo lang que tiene value comenzando en "it"  
:last-child	  |  p:last-child  |    Selecciona todo `<p>` que sea el último hijo de su padre  
:last-of-type |	p:last-of-type |    Selecciona todos los `<p>` que sea el ultimo `<p>` de su padre  
:link	        |     a:link     |   	Selecciona el enlace sin visitar  
:not(selector)| 	  :not(p)    |  	Selecciona todos los elementos que no sean `<p>`  
:nth-child(n)	| p:nth-child(2) |	  Selecciona todos los `<p>` que sean el segundo hijo de su padre  
:nth-last-child(n) |  p:nth-last-child(2) |	Selecciona todos los `<p>` que sean el segundo hijo de su padre, contando desde el último hijo  
:nth-last-of-type(n) |	p:nth-last-of-type(2) |	Selecciona todos los `<p>` que sean el segundo `<p>` de su padre, contando desde el ultimo hijo  
:nth-of-type(n) | p:nth-of-type(2)  |	Selecciona todo elemento `<p>` que sea el segundo `<p>` de su padre   
:only-of-type	|  p:only-of-type | 	Selecciona todo elemento `<p>` que es el único `<p>` de su padre  
:only-child 	|  p:only-child   |  	Selecciona todo elemento `<p>` que sea el único hijo de su padre  
:optional   	|  input:optional | 	Selecciona todo  `<input>` que no tengan el atributo "required"  
:out-of-range	|input:out-of-range|	Selecciona todo `<input>` con un valor específico fuera de rango  
:read-only	  | input:read-only | 	Selecciona todo `<input>` con el atributo específico "readonly"  
:required	    | input:required  | 	Selecciona todo `<input>` con el atributo "required" especificado
:root	        |       root      |	  Selecciona el elemento root del documento  
:target	      |   #news:target  |	  Selecciona el activo elemento #news (tras hacer click en un enlace que contiene ese nombre de ancla)  
:valid	      |   input:valid   | 	Selecciona todos los `<input>` con un valor válido  
:visited      |	    a:visited   | 	Selecciona el link que está visitado previamente  

#### Pseudo-Elementos
Selector    | 	Ejemplo   |  	Descripción
------------|-------------|--------------------------------------------------------------
::after	    |   p::after	|   Instertar contenido despues de cada elemento `<p>` 
::before	  |   p::before	|   Insetar contenido antes de cada elemento `<p>`
::first-letter|p::first-letter| Selecciona la primera letra de cada elemento `<p>` 
::first-line | p::first-line | Selecciona la primera línea de cada elemento `<p>`  
::selection |	p::selection |	Selecciona un fragmento del elemento definido por el usuario  

**Sintaxis:**  
``` css
selector::pseudo-element {
    property:value;
}
```

#### Colores:
Existen tres formas de definir los colores en CSS:  

   Forma          |         Ejemplo  
------------------|---------------------------  
   Nombre válido  | `red, black, white, gray`  
   valor RGB      | `rgb(255, 0, 0)`  
   Hexadecimal    | `#FAFAFA`  

#### Unidades de medida:
##### Unidades Absolutas:
Su valor no depende de otro de referencia.

Unidad | Definición  
-------|------------ 
in     | pulgadas  
cm     | centímetros  
mm     | milímetros  
pt     | puntos  
pc     | picas  
  
##### Unidades relativas:
Su valor depende de otro absoluto.  

Unidad | Definición  
-------|----------------------------------------------------------------- 
em     | respectiva al tamaño por defecto del inicio  
rem    | respectiva al tamaño del elemento padre  
ex     | respectiva a la altura de la letra `x` del tipo y tamaño de la letra  
px     | píxeles, relativa respecto a la resolución del monitor  
vh     | height, relativa a la resolución del monitor  

  
### Background - Fondos de la Página
``` css
  *{
    background-color: /*color válido explicado antes*/;
    background-image: url("ruta/imagen.png");
    background-repeat: [repeat-x | repeat-y | no-repeat];
    background-attachment: scroll | fixed ;
    background-position: left top | left center | left bottom | right top | right center | right bottom |
    center top | center center | center bottom;
  }
```
Además podrán agruparse en una misma propiedad, `background:` en la que asignarle varios atributos.  

`background-color` establece un color de fondo según las formas explicadas antes.  
`background-image` establece como fondo una imagen según la ruta elegida.  
`background-repeat` establece la forma en la que se repetirá el fondo.  
**repeat-x** repite en horizontal la imagen.  
**repeat-y** repite en vertical la imagen.  
 **no-repeat** no repite la imagen.  
 `background-attachment` Define si el fondo será dinámico con la página.  
 **scroll** se moverá al hacer scrolling en la página.  
**fixed** se quedará fijo y solo se moverá el contenido de la página.  

### Border - Bordes del contenido
``` css
  *{
    border-style: dotted | dashed | solid | double | groove | ridge | inset | outset | none | hidden;
    border-width: 5px;
    border-color: red;
    border-right | border-top | border-bottom | border-left: solid red 1px;
    border-radius: 10px;
  }
```
Además se puede agrupar en una misma propiedad, `border:` en la que asignarle varios atributos.  
Si quisiéramos agregar un estilo distinto para cada lado del borde, hay distintas formas:  
Cuatro atributos: **arriba, derecha, izquierda, abajo**. *Ejemplo: border: dotted dashed solid inset red 2px;*  
Tres atributos: **arriba, derecha+izquierda, abajo**. *Ejemplo: border: dotted solid dotted;*  
Dos atributos: **arriba+abajo, izquierda+derecha**. *Ejemplo: border: dotted solid;*  
Un atributo: **todos**. *Ejemplo: border: dotted*.  
  
`border-style` asigna un estilo de borde.  
`border-width` asigna un grosor al borde.  
`border-color` asigna un color al borde.  
`border-radius` establece un borde redondeado para las esquinas del borde, pues por defecto establece un rectángulo perfecto.  
`border-right | border-top | border-bottom | border-left` establece un estilo para el borde derecho, superior, inferior o izquierdo.  

### Margin - Márgenes
``` css
  *{
    margin: 10px 10px | auto;
    margin-left: 10px;
    margin-right: 10px;
    margin-top: 10px;
    margin-bottom: 10px;
  }
```
`margin` asigna un margen externo, podemos asignarlo simplemente con las propiedades añadiendo cuatro, tres, dos o un atributo con la simple etiqueta o definirlos de forma individual.  
Admite valores negativos, porcentajes (medida relativa que escala en relación a la resolución del monitor) e incluso la ausencia de borde.  

### Padding - Margen interno/relleno
``` css
*{
  padding: 10px;
  padding-left:10px;
  padding-top:10px;
  padding-bottom:10px;
  padding-right:10px;
}
```
`padding` corresponde al relleno, al margen interno del elemento, podemos asignarlo al igual que el margen con más de un atributo mediante esta etiqueta o definirlos de forma individual. Admite porcentajes.  

### Height x Width - Altura x Anchura
``` css
  *{
    height: 500px;
    max-height: 500px;
    max-width: 500px;
    min-height: 200px;
    min-width: 500px;
    width: 500px;
   }
```
Tanto `width` como `height` no establecen un margen o un padding, solo establecen un tamaño al contenedor o elemento al que hacen referencia. Admite cualquier unidad de medida y porcentajes.  

Al agregar un `max-width` establece la máxima anchura del elemento o contenedor.  
Esto quiere decir que al redimensionar el explorador, este elemento no variará su tamaño.  
Lo equivalente a la altura sería `max-height` siendo justo lo contrario con `min-width` y `min-width`.  

### Box Model - modelo de cajas
El modelo de cajas es el método por el cual diferenciamos los elementos y los disponemos con css. Se compone de varios niveles:
`outline - margin - border - padding - contenido`.  

### Outline - Contorno
``` css
  *{
    outline: inherit;
    outline-color: blue;
    outline-style:  dotted | dashed | solid | double | groove | ridge |
    inset | outset | none | hidden;
    outline-offset: 10px;
    outline-width: thin |thick | medium;
   }
```
`outline` establece un contorno por fuera del margen del elemento al que hacen referencia. Es una forma de hacer que el elemento al que hacen referencia *destaque* de alguna forma.  
La principal diferencia del outline con border es que el primero no forma parte del elemento en sí, puesto que no afecta a sus dimensiones.
**outline-offset** establece un espacio entre el outline y el borde.  

### Text - Textos
``` css
  *{
      color: /*color válido*/;
      text-align: center | left | right | justify;
      text-decoration: overline | underline | line-through;
      text-transform: capitalize | lowercase | uppercase | full-width;
      text-shadow: 2px 2px 4px black;
      text-indent: 50px;
      letter-spacing: 3px;
      line-height: 10px;
      direction: ltr | rtl;
      white-space: normal | pre-line | pre-wrap | nowrap;
      word-break: normal | break-all | keep-all;
      word-spacing: 10px;
      vertical-align: baseline | length(50px) | sub | super | top | text-top |
      middle | bottom | text-bottom;
   }
```
`text-align` permite alinear el texto según se elija, centrado, justificado a la derecha o izquierda.  
`text-decoration` permite decorar el texto con una linea superior, una linea de subrayado o una linea de tachado.  
`text-transform` permite un cambio en el texto, capitalizado, todo a minúscula, todo a mayúscula o que compartan el mismo tamaño cada letra.  
`text-shadow`: Establece una sombra para el texto, con valores positivos, *el ejemplo correspondería al margen inferior-derecha el difuminado (en píxeles) y el color*.  
`text-indent` Establece la sangría de la primera línea del párrafo.  
`letter-spacing` Establece el espaciado entre letras.  
`line-height` Establece el espacio del interlineado.  
`direction` Establece la dirección del texto para determinados idiomas.  
Sus atributos: **ltr** izq hacia der. **rtl** der hacia izq.  
`white-space` Establece el espacio superior al texto.  
`word-break` Establece si al final del texto en el límite izquierdo se separan las palabras rompiendo la palabra o manteniendo juntas las letras antes del salto de línea.  
**break-all** romper en cualquier momento la palabra.  
**keep-all** mantener las palabras juntas previo al salto de línea.  
`word-spacing` Establece el espacio entre las palabras.  
`vertical-align` Establece un margen vertical al texto.  

### Font - Fuentes
``` css
  @font-face {
    font-family: 'name';
    src: url('ruta o enlace');
  }

  *{
    font-family: serif, sans-serif, monospace;
    font-style: italic | normal |  oblique;
    font-size: 2.0em;
    font-weight: bold | bolder | lighter;
    font-variant: normal | small-caps;
 }
```
Podemos encontrar dos tipos de fuentes:  
  - por familia genérica: **serif, sans-serif, monospace**
  - por una fuente concreta: **georgia, arial, courier new**

`font-family` Establece el tipo de familia de fuentes que se usará en el texto, se pueden añadir varias unidas por **,**. Si la fuente tiene espacios, irá entre comillas **"**.  
`font-style` Establece el texto como oblicuo o cursivo.  
`font-size` Establece el tamaño de la fuente, tanto en texto como en fuente se pueden usar la medida relativa **em**.  
`font-weight` Establece el grosor de la tipografía. **bold** sería negrita, y **lighter** mas clara.  
`font-variant` Establece que todo el texto sea en mayúsculas aunque diferenciará en tamaño las letras que correspondan a las mayúsculas.  

`@font-face` establece una ruta para agregar familias de fuentes ajenas a las predefinidas, con **font-family** elegimos el nombre asignado para llamarle después, y con **src: url()** la ruta del archivo que contiene la fuente.  

### Icons & SVG - Iconos y gráficos vectoriales
``` html
<!DOCTYPE html>
<html>
<head>
  <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.6.3/css/font-awesome.min.css">
</head>
<body>
  <i class="fa fa-cloud"></i> <br/> <i class="fa fa-heart"></i>
  <svg width="400" height="100">
    <rect width="400" height="100" style="fill:rgb(0,0,255);stroke-width:10;stroke:rgb(0,0,0)" />
  </svg>
</body>
</html>
```
Existe la posibilidad de agregar iconos mediante las etiquetas `<i>` o `<span>`, con enlaces a librerías de iconos mediante los cuales basta con agregar clases a las etiquetas ya mencionadas. *(Un ejemplo serían los octicons de GitHub o los iconos de bootstrap)*.  
`SVG` significa gráficos vectoriales, ocupan mucho menos espacio que una imagen y aunque pueden ser importados como imagen, HTML permite la posibilidad de generarlos mediante la etiqueta `<svg></svg>`.

### Links - Enlaces
```css
a:link{ text-decoration: none; }
a:hover{ text-decoration: underline; }
a:active{ text-decoration: underline;}
a:visited{ color: black;}
```

Para agregar estilos a un enlace, se tendrá que hacer referencia a los estados por los que pasa cada uno de estos.  
`:link` es el enlace sin propiciar ningún evento en él.  
`:hover` cuando el cursor está encima.  
`:active` mientras se está pulsando el enlace.  
`:visited` enlace ya visitado previamente.  

### Lists - Listados
```css
  *{
    list-style-type: circle | disc | square | lower-alpha | lower-greek | lower-latin | upper-alpha | none;
    list-style-image: url('image.png');
    list-style-position: inside | outside;
  }
```
`list-style-type` Elige el tipo de indentificación para los elementos de la lista, algunos de los más usados son los que aparecen en el ejemplo.  
`list-style-image` Selecciona una imagen para que haga de identificador de cada elemento de la lista.  
`list-style-position` Establece la sangría del listado. **inside** establecerá mayor sangría que **outside**.  

### Tables - Tablas
``` css
*{
  border: /*propiedades ya vistas sobre los bordes*/
  border-collapse: collapse | separate;
  caption-side: bottom | top;
  empty-cells: hide | show;
  table-layout: auto | fixed;
  text-align: /*visto previamente*/;
  width: auto;
  height: auto;
}
tr:nth-child(even | odd){
  background-color: lightgray;
}
```
Por defecto las tablas tienen dos bordes, uno que contiene la tabla y otro interno para cada celda.  
`border-collapse` Establece la unión de los dos bordes que se agregan por defecto de la tabla.  
`caption-side` Establece la ubicación del `caption` o título de la tabla.  
`empty-cells` Establece la visibilidad de una celda vacía. De dejarlas ocultas, respetaría el hueco de estas.  
`table-layout` Establece que el texto dependerá del tamaño de la celda.  
El atributo **:nth-child(even | odd)** sirve para diferenciar las filas pares o impares, en caso de querer diferenciar unas filas de otras.  
Si quisieramos hacer una tabla responsive tendríamos que agregar a la etiqueta `<table>` o al `<div>` contenedor el estilo **overflow-x: auto**.   Eso agregaría una barra de desplazamiento horizontal bajo la tabla.  

### Display, Visibility & Opacity
```css
*{
  display: block | inline | inline-block | flex | grid | inline-flex;
  visibility: visible | hidden;

  opacity: 0.5;
  filter: alpha(opacity=50);
}
```
La propiedad `display` cambia la forma en la que se dispone el elemento al que hace referencia, en **block** significa que no admite nada a su izquierda o derecha, **inline** que forma parte de la línea con otros elementos. **flex** permite colocar los elementos de una página para que se comporten de forma predecible cuando el diseño de la página debe acomodarse a diferentes tamaños de pantalla y diferentes dispositivos. **inline-block** es cuando un elemento inline queremos que se comporte como bloque, un ejemplo equivalente al antigulo `float:left + clear:left;` a cajas de contenido.
La propiedad `visibility` establece si un elemento es visible o no.  
La propiedad `opacity` establece la transparencia del elemento al que hacen referencia. El 0% de transparencia sería 1. El 50% sería 0.5. `filter` es el equivalente para algunos exploradores.  

## Position - Posicionamiento
``` css
*{
  position: static | relative | fixed | absolute;
  top: auto;
  left: auto;
  right: auto;
  bottom: auto;
}
```
`position` establece el tipo de posicionamiento que tendrá en relación a la página.  
**static** define que el elemento al que hace referencia está pùesto según el flujo normal de la página.  
**relative** define que el elemento tendrá cierta dependencia de posición en función del contenido de la izquierda y derecha. Se necesita una posición relativa para que funcione el posicionamiento **top, left, bottom, right**.  

## Overflow - Desplazamiento 
``` css
  *{
    overflow: visible | hidden | scroll | auto;
    overflow-x: ;
    overflow-y: ;
   }
```
`Overflow` corresponde al desplazamiento vertical y horizontal de la página. `overflow-x` y `overflow-y` se refieren a la barra horizontal y vertical respectivamente.  
**hidden** ocultará las barras de desplazamiento.  
**visible** no se recortará tamaño para agregar las barras de desplazamiento, aparecerán cuando sea necesario.  
**scroll** aparecen permanentemente las barras de desplazamiento.  

Si un elemento es más alto que el elemento que lo contiene, y que se hace flotar, se desborde fuera de su recipiente. Para evitarlo, podemos añadir `overflow: auto;` al elemento que contiene para solucionar este problema.
  
## Float y Clear
``` css
  *{
    float: none | left | right | initial;
    clear: right | left;
  }
```  
El elemento `float` en su uso mas sencillo, es que flota alrededor del contenido. Un ejemplo sencillo sería aplicar float a las imágenes para que estas ajusten el texto a las mismas.  
La propiedad `clear` sirve para que el elemento al que hace referencia se quede en la misma sin ningún elemento al lado al que hace referencia, puede ser **right, left, both**.  

## Layout: Horizontal - Vertical align
``` css
  /* Para posicionar un elemento centrado + texto centrado */ 
  .center {
    margin: auto;
    text-align: center;
  }
  
  /* Para centrar una imagen usar display:block + margin:auto */
  img{
    display: block;
    margin: auto;
  }
  
  /* Usando left and right align */ 
  .right {
    position: absolute;
    right: 0px;
    width: 300px;
    border: 3px solid #73AD21;
    padding: 10px;
  }
  
  /*Centrado vertical*/
  .center {
    padding: 70px 0;
  }
  
  /* Usando line-height */
  .center {
    line-height: 200px;
    height: 200px;
    border: 3px solid green;
    text-align: center;
  }

  /* Si el texto tiene múltiples líneas: */
  .center p {
      line-height: 1.5;
      display: inline-block;
      vertical-align: middle;
  }
```




