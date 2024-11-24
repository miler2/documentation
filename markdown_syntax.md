[*Go back to the index*](README.md)  

# Index
- [Títulos](#títulos)
- [Resaltar palabras o frases](#resaltar-palabras-o-frases)
    - [Cursiva](#cursiva)
    - [Negrita](#negrita)
    - [Negrita y cursiva](#negrita-y-cursiva)
    - [Resaltar una frase](#resaltar-una-frase)
    - [Subrayar](#subrayar)
    - [Cambiar el color](#cambiar-el-color)
- [Comentarios](#comentarios)
- [Indentación](#indentación)
- [Escribir palabras de forma literal](#escribir-palabras-de-forma-literal)
- [Mostrar texto para copiar](#mostrar-texto-para-copiar)
- [Imágenes](#imágenes)
- [Enlaces](#enlaces)
    - [Enlaces indexados](#enlaces-indexados)
    - [Enlaces de directorios](#enlaces-de-directorios)
- [Símbolos](#símbolos)


# Títulos
Si queremos usar títulos podemos usar "#".

> \# Titulo 1
> # Titulo 1
> \## Titulo 2
> ## Titulo 2
> \### Titulo 3
> ### Titulo 3

Después de "Titulo 1" también muestra una línea de separación directamente debajo del título.

# Resaltar palabras o frases
## Cursiva:
Asterisco.

>\*Texto sin editar*
>
>*Texto editado*

## Negrita:
Doble asterisco.

>\*\*Texto sin editar**
> 
>**Texto editado**

## Negrita y cursiva:
Triple asterisco.

>\*\*\*Texto sin editar***
>
>***Texto editado***

**Nota:**
Todo esto se puede hacer también si sistituimos los asteriscos por barra baja.

Ej: 

>\_Texto sin editar_
>
>_Texto editado_

## Resaltar una frase
Si quieres resaltar un ```texto como este``` es tan simple como escribirlo de la siguiente manera:

>\```texto```

Son comillas hacia atrás, y hacen falta tres en cada lado.


## Subrayar

Para subrayar una palabra o frase es tan simple como usar el tag de HTML ```<u>```.

>Cómo se escribe:  
>&nbsp;&nbsp;&nbsp;&nbsp;\<u>texto subrayado\</u>  
>
>Cómo se vería:  
>&nbsp;&nbsp;&nbsp;&nbsp;<u>texto subrayado</u>

Nota: Hay que tener en cuenta que esta forma para subrayar no se acepta en todos los editores de markdown.

## Cambiar el color
Para cambiar el color podemos usar los tags de html y darles color así:

>Cómo se escribe:  
>&nbsp;&nbsp;&nbsp;&nbsp;\<font color="red">Este texto es rojo\</font>  
>
>Cómo se vería:  
>&nbsp;&nbsp;&nbsp;&nbsp;<font color="red">Este texto es rojo</font>

El método con font está depreciado oficialmente, a si que podemos usar css como alternativa así si está soportado:

>Cómo se escribe:  
>\<p style="color:green">Este texto es verde\</p>  
>
>Cómo se vería:
><p style="color:green">Este texto es verde</p>

# Comentarios
Un comentario es algo que solo podríamos ver en el código de markdown, pero no podríamos ver en la visualización final. Es especialmente útil si tenemos que usar el mismo código con varias personas o recordarnos algo a nosotros mismos más adelante.

Para escribir comentarios en markdown tendremos que escribir el texto entre corchetes, luego dos puntos y luego un hashtag de esta manera:

```[Esto no se muestra]: #```

# Indentación
Para indentar líneas normalmente sirve simplemente con escribir tabulador, pero no siempre es así. Por ejemplo, cuando queremos usar un "block quote" como este:

>"build": {  
>&nbsp;&nbsp;&nbsp;&nbsp;"builder": "@angular-devkit/build-angular:application",  
>&nbsp;&nbsp;&nbsp;&nbsp;"options": {  
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"outputPath": "dist",  
>}}

Por defecto, aunque usemos tabulador, se muestra así:

>"build": {  
>"builder": "@angular-devkit/build-angular:application",  
>"options": {  
>"outputPath": "dist",  
>}}

Para hacer indentación tendremos que usar un workaround. En este caso le vamos a decir a markdown que escriba sí o sí un espacio, escribiendo esto:

```
&nbsp;
```
Es el equivalente a escribir un espacio, pero con esto le decimos de forma implícita que escriba un espacio sí o sí, de esta forma, para escribir tabulador tendremos que usar esto cuatro veces más o menos, dependiendo de la indentación que queramos.

Para escribir lo que mostré antes, tendría que hacerse de esta manera:

>"build": {  
>\&nbsp;\&nbsp;\&nbsp;\&nbsp;"builder": "@angular-devkit/build-angular:application",  
>\&nbsp;\&nbsp;\&nbsp;\&nbsp;"options": {  
>\&nbsp;\&nbsp;\&nbsp;\&nbsp;\&nbsp;\&nbsp;\&nbsp;\&nbsp;"outputPath": "dist",  
>}}

Recordemos que queda así:

>"build": {  
>&nbsp;&nbsp;&nbsp;&nbsp;"builder": "@angular-devkit/build-angular:application",  
>&nbsp;&nbsp;&nbsp;&nbsp;"options": {  
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"outputPath": "dist",  
>}}

# Escribir palabras de forma literal
Si queremos mostrar por pantalla lo que tenemos que escribir para hacer un comando, por ejemplo, cómo escribir lo siguiente sin que me lo convierta en una imágen automáticamente:

> !\[](Captura1.png)    #Este mostraría la imágen
>
> !\\[]\(Captura1.png)  #Este no muestra la imágen y muestra el texto de arriba

Tendremos que escribir "\\" antes del caracter especial para que markdown lo escriba de forma literal y no le de formato.

# Mostrar texto para copiar
Si queremos mostrar un comando que queremos permitir que sea copiado de una forma fácil, podemos usar lo siguiente:

>\```  
>Texto a copiar  
>\```

Ejemplo de cómo se vería:

```
Texto a copiar
```

También es posible usarlo escribiendo 4 espacios, o haciendo tabulador delante de la frase que queremos.

# Imágenes
Si quieres utilizar imágenes puedes hacerlo usando esta sintaxis:

    ![]()

Dentro del paréntesis tendrás que escribir la ruta del archivo de la imágen:

> !\[](imagen.png)
>
> !\[](/home/ubuntu/imagen.png)

Dentro de los corchetes se puede escribir texto de descripción para la imágen.

# Enlaces
Si quieres mostrar un enlace solo hace falta escribir esto:

```
[]()
```

Ejemplo:

> \[enlace](https://direccion.del.enlace)

## Enlaces indexados
También se puede guardar el enlace en una cadena de carácteres, por ejemplo, si quieres guardar todos los links internos en una lista como esta:

>\[1]: https://hola.com  
>\[2]: https://google.com  
>\[3]: https://github.com

Se usarían así:

>La página \[hola]\[1] es muy buena.
>
>\[1]: https://hola.com

Solo la palabra "hola" será mostrada junto a la frase, y si clicamos en ella nos llevará al enlace.

## Enlaces de directorios
También es posible usar enlaces para llevar a una ruta en específico.

Por ejemplo, si tenemos un readme con un conjunto de prácticas, y estamos listandolas, podemos añadir un enlace que lleve a su directorio correspondiente.

Ejemplo:

>\[practica_1](practicas/practica_1/)

Esto mostrará la palabra entre corchetes, y lo unirá al link entre paréntesis.

# Símbolos
Aquí hay una lista parcial de los símbolos en HTML que podemos usar en markdown:

- Copyright (©) — \&copy;
- Registered trademark (®) — \&reg;
- Trademark (™) — \&trade;
- Euro (€) — \&euro;
- Left arrow (←) — \&larr;
- Up arrow (↑) — \&uarr;
- Right arrow (→) — \&rarr;
- Down arrow (↓) — \&darr;
- Degree (°) — \&#176;
- Pi (π) — \&#960;

Para una lista completa de los símbolos posibles en markdown, ir al artículo de wikipedia [HTML entities](https://en.wikipedia.org/wiki/List_of_XML_and_HTML_character_entity_references).

# Tablas
En markdown también se pueden hacer tablas como esta:

| Primera columna   | Segunda columna                                          | Otra columna |
| ----------------- | -------------------------------------------------------- | ------------ |
| Header            | Title                                                    | No se        |
| Lista dentro      | Una lista: <ul><li>Item one.</li><li>Item two.</li></ul> | No se        |

Se declaran así:

```
| Primera columna   | Segunda columna                                          | Otra columna |
| ----------------- | -------------------------------------------------------- | ------------ |
| Header            | Title                                                    | No se        |
| Lista dentro      | Una lista: <ul><li>Item one.</li><li>Item two.</li></ul> | No se        |
```

No hace falta que estén indentadas, es solo para que se vea mejor. Pueden ser unas filas más cortas que otras así:

```
| Primera columna | Segunda columna | Otra columna |
| - | ---------------------------------- | --------- |
| Header | Title | No se |
| Lista dentro | Una lista: <ul><li>Item one.</li><li>Item two.</li></ul> | No se |
```

___
[*Go back to the index*](README.md) 