<<<<<<< HEAD

Puede agregar un archivo README a su repositorio para decirle a otras personas por qué su proyecto es útil, qué pueden hacer con su proyecto y cómo pueden usarlo.

En este articulo
Enlaces de sección en archivos README y páginas de blob
Enlaces relativos y rutas de imágenes en archivos README
Otras lecturas
Un archivo README, junto con una licencia de repositorio , pautas de contribución y un código de conducta , lo ayuda a comunicar las expectativas y administrar las contribuciones a su proyecto.

A menudo, un archivo README es el primer elemento que verá un visitante cuando visite su repositorio. Los archivos README generalmente incluyen información sobre:

Que hace el proyecto
Por qué es útil el proyecto
Cómo los usuarios pueden comenzar con el proyecto
Donde los usuarios pueden obtener ayuda con su proyecto
Quién mantiene y contribuye al proyecto.
Si coloca su archivo README en el directorio raíz docso oculto de su repositorio .github, GitHub reconocerá y mostrará automáticamente su README a los visitantes del repositorio.

Página principal del repositorio github / scientist y su archivo README

Enlaces de sección en archivos README y páginas de blob
Muchos proyectos usan una tabla de contenido al comienzo de un archivo README para dirigir a los usuarios a diferentes secciones del archivo. Puede vincular directamente a una sección en un archivo renderizado al pasar el cursor sobre el encabezado de la sección para exponer el enlace:

Enlace de sección dentro del archivo README para el repositorio github / scientist

Enlaces relativos y rutas de imágenes en archivos README
Puede definir enlaces relativos y rutas de imágenes en sus archivos renderizados para ayudar a los lectores a navegar a otros archivos en su repositorio.

Un enlace relativo es un enlace relativo al archivo actual. Por ejemplo, si tiene un archivo README en la raíz de su repositorio y tiene otro archivo en docs / CONTRIBUTING.md , el enlace relativo a CONTRIBUTING.md en su README podría verse así:

[Contribution guidelines for this project](docs/CONTRIBUTING.md)
GitHub transformará automáticamente el enlace relativo o la ruta de la imagen en función de la rama en la que se encuentre actualmente, de modo que el enlace o la ruta siempre funcionen. Puede usar todos los operandos de enlace relativos, como ./y ../.

Los enlaces relativos son más fáciles para los usuarios que clonan su repositorio. Es posible que los enlaces absolutos no funcionen en clones de su repositorio; le recomendamos que utilice enlaces relativos para hacer referencia a otros archivos dentro de su repositorio.

Otras lecturas
" Agregar un archivo a un repositorio "
18F's " Haciendo legibles los READMEs "
CReditos:
Luisa Arboleda.
=======
Markdown hoja de referencia rápida

	Reducción	Procesado
Énfasis	
* Enfatizar * _ enfatizar_
**Fuerte fuerte__
Enfatizar
fuerte
Algunos temas de WordPress.com pueden tener un formato diferente para estos estilos

Enlaces en linea	
Un [enlace] (http://example.com "Título").
La mayoría de los navegadores muestran el texto del título al pasar el mouse sobre un enlace.

Tenga en cuenta que los códigos cortos de WordPress, como [video] o [audio], tendrán prioridad sobre los enlaces de Markdown y no deben usarse para el texto del enlace.

Un enlace .
Enlaces referenciados	
Algún texto con [un enlace] [1] y
otro [enlace] [2].

[1]: http://example.com/ "Título"
[2]: http://example.org/ "Título"
La sección de referencia puede estar en cualquier parte del documento.

Algún texto con un enlace y otro enlace .
Imágenes en línea	
Logotipo:! [Alt] (/ wp.png "Título")
El texto "Alt" (texto alternativo) hace que las imágenes sean accesibles para personas con discapacidad visual

Logo: Alt
Imágenes referenciadas	
Logotipo más pequeño:! [Alt] [1]

[1]: /wp-smaller.png "Título"
Logotipo más pequeño: texto alternativo
Imágenes vinculadas	
Logotipo vinculado: [! [Texto alternativo] (/ wp-bigger.png)]
(http://wordpress.com/ "Título")
Logotipo vinculado: texto alternativo
Notas al pie	
Tengo más [^ 1] para decir aquí.

[^ 1]: Para decir aquí abajo.
Se agregarán notas al pie de página al final del documento, con un enlace de regreso a la referencia original

Tengo más 1 para decir aquí.
Para decir aquí abajo. ↩
Saltos de línea	No admitimos el doble espacio típico de Markdown para generar un salto de línea debido a nuestra función integrada de salto automático de línea. Un salto de línea regular generará un salto de línea en la salida.	
Listas de viñetas	
* Articulo
* Articulo
- Articulo
- Articulo
Articulo
Articulo
Articulo
Articulo
Listas Numeradas	
1 articulo
2. Artículo
Articulo
Articulo
Listas Mixtas	
1 articulo
2. Artículo
   * Mezclado
   * Mezclado  
3. Artículo
Articulo
Articulo
Mezclado
Mezclado
Articulo
Blockquotes	
> Texto citado.
>> Presupuesto citado.

> * Citado 
> * Lista
Texto citado

Presupuesto citado

Citado
Lista
Preformateado	
  Comience cada línea con 
  dos espacios o más para 
  hacer que el texto se vea
  exactamente 
  como si escribieras i
  t.
Comience cada línea con 
dos espacios o más para 
hacer que el texto se vea
exactamente 
como si escribieras i
t.
Código	
`Este es el código`
This is code
Bloque de código	
~~~~
Esto es un 
pieza de código 
en un bloque
~~~~

`` `
Esto también
`` `
1
2
3
4 4
<br>
This is a<br>
piece of code<br>
in a block<br>
1
2
<br>
This too<br>
Resaltado de sintaxis	
`` `css
# botón {
    borde: ninguno;
}
`` `
Consulte Publicar código fuente para conocer los idiomas compatibles.

1
2
3
4 4
<br>
#button {<br>
    border: none;<br>
}<br>
Encabezados	
# Encabezado 1
## Encabezado 2
### Encabezado 3 
#### Encabezado 4 ####
##### Encabezado 5 #####
###### Encabezado 6 ######
Las marcas hash de cierre son opcionales en todos los niveles

Encabezado 1

Encabezado 2

Encabezado 3

Encabezado 4

Encabezado 5

Encabezado 6

Listas de definiciones	
WordPress
: Una plataforma semántica de publicación personal 

Reducción
: Herramienta de conversión de texto a HTML
WordPress
Una plataforma semántica de publicación personal.
Reducción
Herramienta de conversión de texto a HTML
El formato para las listas de definición puede variar entre los temas.

Abreviaturas	
Markdown convierte texto a HTML.

* [HTML]: lenguaje de marcado de hipertexto
Las definiciones pueden estar en cualquier parte del documento

Markdown convierte texto a HTML .

Creditos
Desarrolladora
Luisa Arboleda
>>>>>>> 1a5911c9ef592c1da4dc23a5293cc0f344f6093a
