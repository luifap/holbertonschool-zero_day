
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
