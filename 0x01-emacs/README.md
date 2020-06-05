Una visita guiada a Emacs
Pantalla de bienvenida de Emacs

El Manual GNU Emacs llama a Emacs el editor de pantalla en tiempo real extensible, personalizable y autodocumentado , pero esta descripción le dice a los principiantes poco sobre lo que Emacs es capaz de hacer. Para darle una idea, aquí hay una muestra de las cosas que puede hacer con Emacs:

Además de poder editar archivos de texto sin formato, Emacs incluye funciones especiales para ayudarlo a escribir en muchos idiomas humanos y lenguajes de programación / marcado:

'Hola' en varios idiomas
Resaltado de sintaxis en modo látex
Resaltado de sintaxis en modo C
(Haga clic en cualquiera de estas imágenes para ampliarla).
... así como herramientas para compilar, ejecutar y probar programas. Emacs se integra con GDB para proporcionar un IDE ( Mx gdb ):

Captura de pantalla del modo GDB

Emacs puede comparar dos archivos y resaltar sus diferencias ( Mx ediff ):

Captura de pantalla del modo Ediff

Emacs es un administrador de archivos ( Mx dired ):

Vista de primer plano de Dired

Emacs puede leer noticias, correos y canales RSS ( Mx gnus ):

Captura de pantalla de Gnus

Incluso puedes jugar tetris en Emacs ( Mx tetris ):

Captura de pantalla de Tetris

Ahora puede ver por qué algunas personas consideran que Emacs no es simplemente un editor de texto sino casi un sistema operativo completo. Algunos usuarios encuentran que pueden hacer casi todo su trabajo desde Emacs.

¿Por qué Emacs?
Emacs lo ayuda a ser productivo al proporcionar un entorno integrado para muchos tipos diferentes de tareas:

Todos los comandos de edición básicos (y hay muchos) están disponibles sin importar lo que intente hacer: escribir código, leer un manual, usar un shell o redactar un correo electrónico.
Todas las herramientas que Emacs proporciona para abrir, guardar, buscar y procesar texto (y más) están disponibles para usted sin importar lo que esté haciendo.
Esta uniformidad significa que trabajar dentro de Emacs es a menudo más fácil que aprender a usar un programa separado, especialmente cuando ese programa es probable que tenga su propio conjunto de capacidades de edición y accesos directos.

Si Emacs no funciona de la manera deseada , puede usar el lenguaje Emacs Lisp (Elisp) para personalizar Emacs, automatizar tareas comunes o agregar nuevas funciones. Elisp es muy fácil de comenzar y, sin embargo, es notablemente poderoso: puede usarlo para alterar y extender casi cualquier característica de Emacs. Puede hacer Emacs lo que quiera que sea escribiendo código Elisp; Un testimonio de esto es el hecho de que todas las características que se muestran arriba (y muchas más descritas más adelante en este recorrido) están escritas en Elisp.

Emacs también es portátil. Puede usar el mismo editor (con la misma configuración) en muchas plataformas, incluidas GNU / Linux, BSD y otros derivados de Unix, y algunos sistemas operativos propietarios como Microsoft Windows.

Antes de comenzar ...
Si instala Emacs primero, puede seguir junto con los ejemplos presentados aquí. Cada vez que decida comenzar a usar Emacs, debe tomar el tutorial de Emacs. Es una práctica interactiva que lo familiarizará con muchas cosas, que incluyen:

Inicio y salida de Emacs
Movimiento de texto básico y comandos de edición
Abrir y guardar archivos
Conceptos de Emacs: ventanas, marcos, archivos y buffers
Invocar comandos con combinaciones de teclas y con Mx
Para ejecutar el tutorial, inicie Emacs y escriba Ch t , es decir, Ctrl-h seguido de t .

Todas las características descritas en este recorrido funcionan en GNU Emacs 23. Algunas características descritas no se incluyeron en versiones anteriores de Emacs, pero se pueden instalar por separado.

De vez en cuando diré algo como esto:

Consulte (información "(emacs) Uso de la región") para obtener más información.

Esto se refiere a una página en el manual de Emacs que puede leer siguiendo el enlace. Sin embargo, también puede leer dichas páginas directamente en Emacs utilizando el lector de documentación incorporado, llamado Información. Para hacer esto, presione M-:, luego escriba (info "(emacs) Using Region") seguido de RET :

Captura de pantalla del modo de información

El manual de Emacs es un excelente recurso para aprender sobre Emacs; puedes leerlo desde Emacs escribiendo Ch r . También puede leer el manual en la web .

Emacs tiene muchas otras funciones de ayuda, algunas de las cuales se describirán más adelante. Puede ver una lista de todas las funciones de ayuda escribiendo Ch Ch .

El poder de la manipulación de textos.
Emacs le ofrece una gran colección de herramientas para manipular texto, lo que resulta ser una especie de navaja suiza porque Emacs también tiene formas de presentar todo tipo de información en texto. Aquí hay un ejemplo:

Mx dired invoca Dired , el modo administrador de archivos, en un directorio de su elección. Luego, Cx Cq (o Mx wdired-change-to-wdired-mode ) cambia al modo Editable Dired :

Primer plano de una lista de directorios en modo Editable Dired.

En este modo, cambiando los nombres de archivo en la columna de la derecha y luego escribiendo Cx Cs ("guardar") cambia el nombre de los archivos indicados. Renombrar archivos es tan fácil como editar texto. El cambio de nombre por lotes (por ejemplo, cambiar el nombre de cada archivo del formulario icon_ * a backup_icon_ * ) es tan fácil como realizar una búsqueda y reemplazo ( Mx query-replace o M-% ); no es necesario aprender a usar una herramienta de cambio de nombre por lotes separada.

Desde Emacs, puede interactuar no solo con archivos y directorios, sino también con utilidades del sistema, compiladores, depuradores, administradores de información personal, Internet, correo electrónico, chat, otros servicios de Internet y más, y hay un ecosistema de herramientas de terceros. para hacer aún más funcionalidades accesibles. Debido a esta integración, los beneficios de aprender a usar cualquiera de las funciones de edición de Emacs (por ejemplo, buscar y reemplazar) se multiplican muchas veces.

Comandos básicos de edición
Una forma en que Emacs permite a los usuarios trabajar de manera rápida y eficiente es proporcionando comandos de alto nivel para moverse y manipular texto. Hay comandos que operan en caracteres, palabras, líneas, oraciones, párrafos, páginas, definiciones de funciones, espacios en blanco y más. Puede usarlos en cualquier lugar donde lea o edite texto: código fuente, páginas web, shells, listados de directorios, mensajes de correo electrónico, etc.

Moverse en topes
Los comandos de movimiento del búfer más básicos mueven el punto (el cursor) por filas (líneas) o columnas (caracteres):

Cf	Reenviar un personaje
Cn	Proxima linea
Cb	Retrocede un personaje
Cp	Línea anterior
Aquí hay algunas formas de moverse en incrementos mayores:

California	Comienzo de linea
Mf	Reenviar una palabra
Mamá	Oración anterior
Mv	Pantalla anterior
M- <	Comienzo del buffer
Ce	Fin de la línea
megabyte	Retrocede una palabra
Yo	Siguiente oración
CV	Pantalla siguiente
M->	Fin del buffer
Cuando se acostumbra a estas teclas, son más rápidas que sus equivalentes más familiares en otras aplicaciones (Inicio, Fin, Ctrl + Izquierda, etc.) porque no tiene que mover las manos desde la posición de escritura táctil. Y estas teclas son mucho más rápidas que usar un mouse para moverse en un búfer.

Emacs a menudo proporciona comandos adicionales para moverse en formas específicas del contexto (por ejemplo, en el código fuente, comandos para moverse a la definición de función anterior o siguiente).

Muchos de los comandos anteriores se mueven a una ubicación relativa a su posición actual en el búfer, por lo que puede usarlos repetidamente (por ejemplo, Cp Cp Cp para retroceder tres líneas). Puede usar el argumento prefijo para ahorrar tiempo: Cu seguido de un número y un comando de movimiento repite ese comando el número especificado de veces. También puede usar M- [dígito] en lugar de Cu [dígito] . Si usa Cu sin especificar un dígito, el valor predeterminado es 4. Omitir el dígito puede ahorrar tiempo cuando no sabe con precisión cuántas unidades desea saltar de todos modos.

Cu 3 Cp	Volver 3 líneas
Cu 10 Cf	Reenviar 10 caracteres
M-1 M-0 Cf	Reenviar 10 caracteres
Cu Cn	Adelante 4 líneas
Cu Cu Cn	Reenviar 16 líneas
Cu Cu Cu Cn	Adelante 64 líneas
Puede saltar directamente a un número de línea particular en un búfer:

Mg g	Salta a la línea especificada
Buscar texto es una forma práctica de moverse en un búfer. Piense en la búsqueda como solo otra instalación para el movimiento. Cuando busca algo específico, puede usar la búsqueda incremental para llevarlo allí en lugar de escanear por líneas o páginas. Más sobre la búsqueda más tarde.

Cs	Búsqueda incremental hacia adelante
Cr	Búsqueda incremental hacia atrás
Otra forma de moverse en los buffers es mediante el uso de la marca :

marca
Emacs recuerda algo llamado la marca , que es una posición previa del cursor. Puede establecer la marca para indicar un lugar particular en su búfer para que pueda volver a él fácilmente. Cx Cx en un momento posterior devolverá el punto a marcar. En realidad, ese comando también mueve la marca al punto donde estaba anteriormente; por lo tanto, un segundo Cx Cx devuelve el punto a su posición original.

C-SPC	Establecer marca en la ubicación actual
Cx Cx	Intercambiar punto y marcar
Puede establecer la marca explícitamente, pero ciertos comandos establecen la marca para usted, proporcionándole puntos de apoyo convenientes a medida que se mueve alrededor de su búfer:

Cuando usted…	la marca se establece en ...
Tipo C-SPC	Su ubicación actual
Saltar a cualquier extremo del búfer ( M- < o M-> )	tu ubicación anterior
Salir de búsqueda incremental	donde comenzaste a buscar
Texto yanqui	el comienzo de la región arrancada
Insertar un búfer o archivo	el comienzo del texto insertado
Como puede ver, Emacs trata de ser útil: muchos comandos que tienen el potencial de llevarlo a largas distancias establecen la marca para que un simple Cx Cx lo lleve de regreso a donde estaba. Emacs hace que sea difícil perder tu lugar en un búfer : incluso si tomas un desvío, no necesitas desplazarte para volver a donde estabas.

Emacs guarda muchos valores anteriores de la marca para usted. Puede recorrer el anillo de marcas , que contiene las últimas 16 marcas que ha establecido en el búfer actual:

Cu C-SPC	Ciclo a través del anillo de marca
Región
Mark tiene otro propósito: marcar y señalar juntos delinear la región . Muchos comandos operan solo en el texto de la región (es decir, entre la marca y el punto). Puede establecer la región explícitamente estableciendo la marca ( C-SPC ) y luego moviendo el punto a otra parte, o haciendo clic y arrastrando con el mouse. Emacs proporciona algunos comandos que establecen la región para usted moviendo el punto y marcando adecuadamente, por ejemplo:

Cx h	Hacer que la región contenga todo el búfer ("Seleccionar todo")
Mh	Hacer que la región contenga el párrafo actual
Otros comandos ayudan a establecer la región como parte de lo que hacen. Cy (tirar), insertar un archivo e insertar un búfer configuran la región para rodear el texto insertado.

El estrechamiento restringe la vista (y edición) de un búfer a una determinada región. Esto es útil cuando solo está trabajando con una pequeña parte de un búfer (por ejemplo, un capítulo de un libro). Luego, los comandos como búsqueda incremental o principio de búfer o fin de búfer no lo llevan fuera de la región de interés, y los comandos como búsqueda y reemplazo no afectan a todo el archivo.

Cx nn	Búfer estrecho a la región actual
Cx nw	Restaurar ("ensanchar") el búfer
Para obtener más información, consulte (información "(emacs) Narrowing") .

Texto de matanza ("corte")
Al igual que con el movimiento de texto, Emacs proporciona comandos para eliminar texto en varias cantidades.

Ck mata la parte de la línea actual después del punto (o elimina el punto siguiente de nueva línea si el punto está al final de la línea). El argumento del prefijo para Ck se puede usar para eliminar varias líneas:

Ck	Línea de matar
Cu 10 Ck	Mata 10 líneas
Los siguientes comandos operan en la región y son los análogos más cercanos a "cortar" y "copiar" en Emacs:

Cw	Región de muerte ("corte")
Mw	Guardar región para matar el anillo sin eliminarlo ("copiar")
Estos comandos también son útiles:

Maryland	Mata la siguiente palabra
Mk	Matar hasta el final de la oración
Todos los comandos anteriores matan siendo borrado del texto, lo que significa que Emacs elimina el texto y ardillas lejos para su recuperación posterior ( "YanKing"). La mayoría de los comandos que eliminan cantidades significativas de texto lo eliminan en lugar de simplemente eliminarlo, para que pueda usar esos comandos para "eliminar" texto o para "cortarlo" para su uso posterior.

Texto de Yanking ("pegar")
Después de que una pieza de texto ha sido asesinada, va a un lugar llamado el anillo de matar que es análogo al "portapapeles": puedes tirar un elemento para restaurarlo del anillo de matar con Cy . Sin embargo, a diferencia del portapapeles, el anillo de matar es capaz de contener muchos elementos diferentes. Si el elemento que desea tirar no se coloca cuando escribe Cy , escriba My (repetidamente, si es necesario) para recorrer los elementos eliminados anteriormente.

Cy	Yanks último texto asesinado
Mi	Reemplazar texto arrancado con texto eliminado previamente
Recuerde que la mayoría de los comandos que eliminan una gran cantidad de texto de hecho lo matan (es decir, lo colocan en el anillo de matar) para que pueda restaurarlo más tarde. Emacs hace que sea muy difícil perder mucho texto permanentemente : en editores con un solo portapapeles, uno puede borrar accidentalmente una gran parte de texto o golpear el contenido del portapapeles (cortando dos elementos en sucesión). Pero en Emacs, en cualquiera de esos casos, el texto perdido se puede recuperar fácilmente del anillo de matar.

Deshacer
La función de deshacer de Emacs funciona de manera ligeramente diferente a la de otros editores. En la mayoría de los editores, si deshace algunos cambios y luego realiza algunos cambios nuevos, ¡los estados a los que antes se podía acceder con "rehacer" ya no se pueden recuperar! Entonces, cuando se usa "deshacer" y "rehacer" ampliamente, hay que tener mucho cuidado para evitar golpear accidentalmente la lista de rehacer.

Emacs usa un modelo de deshacer diferente que no tiene esta deficiencia. Después de cualquier secuencia consecutiva de deshacer, Emacs hace que todas sus acciones anteriores se puedan deshacer, incluidas las deshacer. (Esto sucederá siempre que cualquier otra orden rompa una secuencia de deshacer).

Si esto suena complicado, solo recuerde que "deshacer" siempre es capaz de devolverlo a cualquier estado anterior en el que se encontraba su búfer (a menos que Emacs se haya quedado sin memoria para almacenar el historial de deshacer). El principio aquí es que Emacs hace que sea muy difícil perder accidentalmente su trabajo .

Deshacer está disponible a través de tres teclas diferentes:

C-/	Deshacer
C-_	Deshacer
Cx u	Deshacer
Entonces, si necesita volver a un estado de búfer anterior, simplemente mueva el cursor (para romper cualquier secuencia existente de deshacer) y presione C- / hasta que encuentre lo que desea.

Para obtener más información sobre deshacer, consulte (información "(emacs) Deshacer") .

Búsqueda incremental
Cs	Búsqueda incremental
Al escribir Cs seguido de algún texto, se inicia la búsqueda incremental. Emacs salta a la siguiente aparición de lo que haya escrito, a medida que lo escribe (es posible que haya visto un comportamiento similar en Mozilla Firefox u otros navegadores web), y se resaltan todas las coincidencias visibles en su pantalla.



Dentro de la búsqueda incremental, puede volver a escribir Cs en cualquier momento para saltar a la próxima aparición.

Cuando haya encontrado lo que está buscando, puede escribir RET (o usar casi cualquier comando de movimiento) para salir de la búsqueda en el caso que haya encontrado, o Cg ("cancelar") para volver al lugar donde comenzó su búsqueda . Si sale de la búsqueda en el momento en que se encuentra, puede volver fácilmente a donde comenzó con Cx Cx, ya que los conjuntos de búsqueda incremental se marcan adecuadamente.

Estos comandos lo ayudan a emitir consultas emitidas anteriormente:

Cs Cs	Buscar el elemento buscado más recientemente
Cs Mp	Elemento anterior en el historial de búsqueda
Cs Mn	Siguiente elemento en el historial de búsqueda
Ch k Cs	Guía de más comandos disponibles en búsqueda incremental
Puede realizar una búsqueda incremental hacia atrás con Cr . (Todos los comandos anteriores se pueden activar de manera similar desde la búsqueda hacia atrás). En cualquier momento durante una búsqueda hacia adelante (o hacia atrás), puede escribir Cr ( Cs ) para cambiar a una búsqueda hacia atrás (hacia adelante).

Cr	Búsqueda incremental hacia atrás
Consulte (información "(emacs) Búsqueda incremental") para obtener más información.

Búsqueda y reemplazo
METRO-%	Consulta reemplazar
El comando query replace le solicita una cadena de búsqueda y un reemplazo. Luego, para cada coincidencia en el búfer, puede elegir si desea reemplazar la cadena de búsqueda. Estas son algunas de las opciones disponibles en cada solicitud:

Escriba y para reemplazar la coincidencia actual.
Escriba n para saltar al siguiente partido sin reemplazar.
Escriba q para salir sin hacer más reemplazos.
Tipo . para reemplazar este partido, luego salga.
Escriba ! para reemplazar todos los partidos restantes con no más preguntas.
Consulte (información "(emacs) Consulta Reemplazar") para obtener más información sobre estas (y otras) opciones. También puedes escribir ? en cualquier momento dentro de una operación de búsqueda y reemplazo para ver una guía.

Búsqueda de expresiones regulares
Emacs le permite buscar expresiones regulares:

CMs	Búsqueda incremental de expresiones regulares
Las expresiones regulares son una forma sucinta de buscar muchas cadenas diferentes a la vez utilizando un lenguaje especial para describir la forma de lo que está buscando. La sintaxis de expresiones regulares está más allá del alcance de este recorrido; ver (info "(emacs) Regexps") para más información.

Si eres nuevo en regexps, o estás construyendo una expresión regular particularmente complicada, puedes usar el generador de expresiones regulares ( Mx re-builder ). Este comando abre una ventana separada en la que puede probar su expresión regular, y cualquier coincidencia en su búfer original se resaltará a medida que edite su expresión regular.

En lugar de saltar a través de los partidos uno por uno, también puede elegir mostrarlos todos a la vez. Mx ocurre le solicita una expresión regular, luego muestra en un búfer separado una lista de todas las líneas en el búfer actual que coinciden con esa expresión regular (así como sus números de línea). Al hacer clic en cualquier ocurrencia, te lleva a esa línea en el búfer.

Búsqueda y reemplazo de expresiones regulares
Las expresiones regulares son aún más poderosas en la búsqueda y reemplazo, porque Emacs permite que el texto de reemplazo dependa del texto encontrado. Puede controlar el reemplazo insertando secuencias de escape especiales en la cadena de reemplazo, y Emacs las sustituirá adecuadamente:

Cuando escribe esto
en una cadena de reemplazo:	Emacs lo reemplaza con:
\ &	el texto original encontrado
\ 1 , \ 2 , etc.	el 1er , 2do , etc. subgrupo entre paréntesis en el texto encontrado
\ #	la cantidad de reemplazos realizados hasta ahora
\?	una cadena obtenida solicitando al usuario en cada partido
\, (expresión-lisp ...)	El resultado de evaluar una función arbitraria
Aquí hay un ejemplo. Supongamos que tenemos un búfer que contiene nombres como este:

George Washington
John Adams
Thomas Jefferson
James Madison
James Monroe
Si ejecutamos Mx replace-regexp y reemplazamos regexp \ (\ w + \) \ (\ w + \) con \, (upcase \ 2), \ 1 , nuestro búfer ahora se ve así:

WASHINGTON, George
ADAMS, John
JEFFERSON, Thomas
MADISON, James
MONROE, James
Como puede ver, el reemplazo de expresiones regulares es capaz de hacer algunas transformaciones bastante sofisticadas. (Aproximadamente, la expresión de búsqueda busca dos palabras; la cadena de reemplazo inserta una versión en mayúscula de la segunda palabra, seguida de una coma, seguida de la primera palabra).

Macros de teclado
Las macros de teclado son una forma de recordar una secuencia fija de teclas para su posterior repetición. Son útiles para automatizar algunas tareas de edición aburridas.

F3	Comience a grabar macro
F4	Deja de grabar macro
F4	Reproduce macro una vez
M-5 F4	Reproduce macro 5 veces
M-0 F4	Reproduzca macro una y otra vez hasta que falle
Por ejemplo, esta secuencia de teclas hace exactamente la misma transformación que hicimos con el reemplazo de expresiones regulares anteriormente, es decir, transforma una línea que contiene George Washington a WASHINGTON, George :

Md Cd Mu, [SPC] Cy Cn Ca

Después de registrar esa secuencia de teclas como una macro, podemos escribir M-0 F4 para transformar el búfer ilustrado anteriormente; en este caso, Emacs ejecuta la macro varias veces hasta que llega al final del búfer.

Consulte (información "(emacs) Macros de teclado") para obtener más información.

Ayuda con comandos
Si has leído hasta aquí, probablemente te sientas intimidado por la idea de tener que recordar un montón de comandos de teclado y nombres de comandos. Afortunadamente, Emacs incluye documentación completa y de fácil acceso. La documentación no es solo para principiantes. Emacs tiene miles de comandos, de los cuales la mayoría de las personas solo usan un pequeño número. Por lo tanto, incluso los expertos de Emacs consultan con frecuencia los documentos para conocer los nuevos comandos o activar su memoria con los antiguos.

Si no recuerda lo que hace una tecla o comando en particular, puede leer una descripción utilizando uno de los siguientes comandos:

Ch k
Muestra documentación para el comando asociado con cualquier tecla en particular.
Ch f
Muestra la documentación de cualquier comando en particular, por nombre (es decir, lo que escribiría después de Mx ).
Por ejemplo, Ch k Cs y Ch f isearch-forward RET muestran una página que describe la búsqueda incremental:



Esto es útil, por ejemplo, si no recuerda lo que hace Cs , o si recuerda que invoca la búsqueda incremental pero quiere saber más sobre esa característica. La documentación proporciona el nombre completo del comando, muestra qué teclas (si las hay) están vinculadas y proporciona una descripción completa de lo que hace el comando.

Por otro lado, si usted no recuerda cómo invocar una característica particular, puede utilizar a propósito para buscarlo:

Ch a
Busque comandos por palabras clave o expresiones regulares
Por ejemplo, si recuerdo que quiero activar el estrechamiento , pero no recuerdo cómo, puedo escribir Ch un RET estrecho que muestra una breve lista de comandos que tienen que ver con estrecho , uno de los cuales es Mx estrecho a región .

Más funciones útiles
Integración con herramientas comunes.
Emacs destaca por su integración con muchas herramientas comunes. No solo puede invocarlos desde el editor, Emacs generalmente lo ayuda a usar su salida de manera más efectiva. Aquí hay unos ejemplos:

Mx shell
Inicia un shell en el búfer llamado * shell * , cambiando a él si ya existe. Use el shell Cu Mx para usar un búfer con un nombre diferente.



Compilación Mx
Invoca make (con objetivos y opciones de su elección) y muestra la salida en un nuevo búfer. Emacs identifica líneas de error que contienen nombres de archivo y números de línea, y puede hacer clic en ellas para saltar directamente al búfer y la línea correspondientes.



Mx gdb
Invoca gdb en un nuevo búfer. Puede usar la línea de comando gdb como de costumbre en ese búfer. Sin embargo, Emacs le permite establecer puntos de interrupción directamente desde sus buffers de origen y muestra la ejecución marcando la línea activa en sus buffers de origen. Emacs también puede mostrar puntos de interrupción, la pila y locales, simultáneamente y cada uno en su propia ventana.



Mx grep
Invoca grep e imprime resultados en un nuevo búfer. Al igual que la compilación Mx , cuando hace clic en una coincidencia, Emacs abre el archivo correcto y lo lleva a la línea correspondiente.



Hombre mx
Muestra hombre páginas.



Aquí hay algunas herramientas más variadas:

Calculadora Mx	Una calculadora simple.
Calendario mx	Un calendario.
Mx fases de luna	Muestra los próximos cuartos de la luna.
Invocar comandos de shell
Si necesita ejecutar un comando de shell simple, estos comandos pueden ahorrarle la molestia de cambiar a un xterm o iniciar un nuevo búfer de shell Emacs:

Mx shell-command o M-!
Ejecuta un comando y muestra la salida en un nuevo búfer.

Mx shell-command-on-region o M- |
Ejecuta un comando, canalizando en la región actual como entrada; muestra la salida en un nuevo búfer.

Para cualquier comando, un prefijo Cu insertará la salida en su búfer actual en lugar de usar un búfer temporal.

Control de versiones
Emacs lo ayuda a manipular y editar archivos almacenados en el control de versiones. Emacs admite CVS, Subversion, bzr, git, hg y otros sistemas, pero ofrece una interfaz uniforme, llamada VC, independientemente del sistema de control de versiones que esté utilizando.

Emacs detecta automáticamente cuándo un archivo que está editando está bajo control de versión y muestra algo como esto en la línea de modo: CVS-1.14 para indicar el sistema de control de versión en uso y la versión actual.

Mx vc-next-action o Cx vv confirma el archivo actual (solicitándole un mensaje de registro) si lo ha modificado. (En los sistemas de control de versiones que requieren bloqueo, este comando también adquiere un bloqueo para usted).

VC proporciona otros comandos para tareas relacionadas con el control de versiones:

Cx v =
Muestra una diferencia que muestra los cambios que ha realizado en el archivo actual.

Cx v ~
Le solicita un número de versión y le muestra esa versión del archivo actual en otra ventana.

Cx vg
Muestra una versión anotada del archivo que muestra, para cada línea, el compromiso donde esa línea fue modificada por última vez y por quién. En cualquier línea, puede presionar L para ver el mensaje de registro de esa confirmación o D para ver el diferencial asociado.

Cx vl
Muestra un registro de cambios anteriores en el archivo. Cuando el cursor está en una entrada de registro en particular, puede pulsar d para ver el diff asociado con ese cambio o f para ver esa versión del archivo.

Vea (info "(emacs) Version Control") para más información.

Algunas características especiales se habilitan cuando mira un archivo diff (ya sea de un archivo o uno producido por VC). Emacs le permite moverse en un archivo de diferencias por trozos o archivos, aplicar trozos individuales a un archivo, revertir un archivo de diferencias y realizar otras operaciones útiles para leer o editar archivos de diferencias manualmente.

Vea (info "(emacs) Diff Mode") para más información.

Editar archivos remotos
Emacs puede editar archivos remotos de forma transparente (como si fueran locales) utilizando una función llamada Tramp. Siempre que Emacs solicite un archivo, puede indicar un archivo remoto así: / myname @ remotehost: / remote / path / to / file . Emacs recupera el archivo a través de SSH, FTP u otro método y se encarga de guardarlo cuando haya terminado. Con Tramp puede editar archivos en diferentes computadoras usando una sola sesión de Emacs, incluso si Emacs no está instalado en el lado remoto.

También puede usar Tramp para editar archivos locales con permisos de otro usuario. Puede editar archivos con privilegios de root a través de sudo: / sudo :: / etc / file , o a través de su: / root @ localhost: / etc / file .

Ver (info "(TRAMP)") para más información.

Servidor Emacs
A algunas personas les gusta mantener abierta una sola instancia de Emacs y editar todos sus archivos allí. Hacer esto tiene algunas ventajas:

Puede eliminar / extraer texto entre buffers en la misma instancia de Emacs.
Emacs recuerda los historiales de argumentos (qué comandos ha utilizado, qué archivos ha abierto, términos que ha buscado, etc.), pero solo dentro de cada instancia.
Si tiene muchas personalizaciones, iniciar nuevas instancias de Emacs es lento.
Por desgracia, cuando escribe emacs en un shell para editar un archivo (o cuando un programa externo invoca $ EDITOR ), se inicia una nueva instancia de Emacs. Puede evitar esto utilizando emacsclient , que en su lugar abre un nuevo marco conectado a una instancia existente de Emacs:

En su instancia actual de Emacs, escriba Mx server-start . O agregue (server-start) a su archivo .emacs para que lo haga automáticamente al inicio.
Para editar un archivo, escriba emacsclient -t FILENAME en el indicador. También puede cambiar su $ EDITOR a emacsclient -t si está utilizando programas que invocan automáticamente $ EDITOR . ( emacsclient -t abre un nuevo marco en el terminal; alternativamente, emacsclient -c abre un nuevo marco X).
Cuando termine de editar, escriba Cx Cc , que cierra el marco.
Para obtener más información, consulte (información "(emacs) Servidor Emacs") .

Ser improductivo con Emacs
Emacs incluso viene con diversiones:

Mx tetris	Tetris
Mx hanoi	Juego de Towers of Hanoi
Doctor mx	Psicoterapeuta de Emacs
Conceptos comunes de Emacs
Argumentos de prefijo
Como hemos visto, los argumentos de prefijo a veces se usan para indicar la repetición:

Cu 10 Cf	Reenviar 10 caracteres
Cu Ma	Atrás 4 oraciones
También hemos visto un argumento prefijo utilizado para modificar el siguiente comando (el argumento numérico, si se proporciona, se ignora):

Mx shell	Cree o cambie al búfer de shell llamado * shell *
Cu Mx shell	Crear o cambiar a búfer de shell con nombre especificado
Si alguna vez se confunde, la documentación de cualquier comando (accesible con Ch f o Ch k ) describe el efecto del argumento prefijo, si lo hay.

Consulte (info "(Argumentos de emacs)") para obtener más información.

Modos principales
Cada búfer tiene un modo principal asociado , que altera ciertos comportamientos, combinaciones de teclas y visualización de texto en ese búfer. La idea es personalizar la apariencia y las características disponibles en función del contenido del búfer.

Emacs viene con docenas de modos principales para editar lenguajes de programación, lenguajes de marcado y formatos de archivos de configuración ampliamente utilizados. Estos modos principales le dicen a Emacs cómo:

Aplicar sangría a su código correctamente (generalmente, simplemente presionando TAB una vez hará que Emacs sangre la línea actual correctamente).
Hacer resaltado de sintaxis
Identificar los límites de las funciones.
Invoque intérpretes, compiladores o depuradores para su código.
Algunos comandos que hemos visto, como Mx dired , Mx compile y Mx shell , de hecho usan sus propios modos principales especiales para hacer que sus buffers brinden ciertas características (como resaltar errores de compilación y hacer que se pueda hacer clic en ellos).

El modo principal actual se muestra en la línea de modo. Lo último en la línea de modo debe ser uno o más elementos entre paréntesis, como (Python Narrow) . El primero de ellos es el nombre del modo principal.

Puede cambiar los modos en un búfer existente utilizando Mx y el nombre del modo:

Mx modo java	Modo para editar archivos Java
Mx python-mode	Modo para editar archivos Python
Mx modo texto	Modo para editar archivos de texto
Mx modo fundamental	Modo sin especializaciones en absoluto
Emacs es muy bueno para determinar el modo correcto para usar cuando abre un archivo, por lo que rara vez tendrá que usar los comandos anteriores.

Estos son ejemplos de los comandos proporcionados por los modos principales de idioma:

Idioma	Algunos comandos especiales disponibles
Ceceo	Manipular s-exps de varias maneras; ejecutar expresiones
Pitón	Sangría, bloques no sangrantes; ejecutar código en el shell de Python
HTML	Insertar y cerrar etiquetas; vista previa en el navegador
En casi todos los casos, los modos principales para formatos no compatibles están disponibles como paquetes de extensión. Puedes encontrar muchos de ellos en EmacsWiki .

Consulte (información "(emacs) Modos principales") para obtener más información.

Modos menores
Cada búfer también puede tener cualquier número de modos menores , que son piezas adicionales de funcionalidad que puede habilitar, independientemente el uno del otro y del modo principal. Los modos menores se enumeran en la línea de modo después del modo mayor dentro de los paréntesis. Aquí hay algunos de uso común:

Mx auto-fill-mode
Envuelve tus líneas automáticamente cuando tienen más de 70 caracteres.

Mx flyspell-mode
Destaca las palabras mal escritas mientras escribe.

Mx modo de seguimiento
Si tiene un búfer visualizado en dos ventanas una al lado de la otra, el modo de seguimiento los obliga a desplazarse juntos de manera que el texto que se muestra en la segunda ventana aparece justo después del texto en la primera ventana, y mueve el cursor fuera de la parte inferior izquierda la ventana hace que aparezca en la parte superior de la ventana derecha:



Algunos modos menores son globales, es decir, afectan el comportamiento de todo el editor, en lugar de solo el de un búfer específico.

Mx icomplete-mode	En el indicador Mx (y en cualquier otro lugar), muestre las finalizaciones a medida que escribe
Mx iswitchb-mode	Mostrar todos los nombres de búfer cuando cambie de búfer con Cx b
Consulte (información "(emacs) Modos menores") para obtener más información.

Si necesita ayuda con un modo particular, Ch m describe los modos activo mayor y menor. La descripción del modo a menudo enumera comandos importantes que son útiles en ese modo, lo que es útil cuando aprende a usar un nuevo modo.

El minibúfer
El minibúfer (el espacio en la parte inferior del marco) es donde Emacs le pide que ingrese en la mayoría de las situaciones: para un comando, cuando escribe Mx ; para un nombre de archivo, dentro de Mx find-file ; para una expresión Elisp, dentro de Mx eval-expression , etc. Estas son algunas de las características comunes a la mayoría de las solicitudes de minibúfer:

Puede usar la mayoría de los comandos de edición de búfer y movimiento. Puede moverse, eliminar texto y tirar texto a minibúferes.
Puede buscar entradas anteriores a la solicitud actual usando Mp y Mn .
La finalización de pestañas suele estar disponible. Por ejemplo, el indicador Mx ofrece la finalización de tabulación, por lo que no debe preocuparse por escribir nombres de comandos largos como Mx wdired-change-to-wdired-mode cuando Mx wdired-ch TAB es suficiente.
Consejos para principiantes.
En caso de emergencia ...
Esto es lo que debe hacer si accidentalmente presionó una tecla incorrecta:

Si ejecutó un comando y Emacs ha modificado su búfer, use C- / para deshacer ese cambio.
Si presionó una tecla de prefijo (por ejemplo, Cx ) o invocó un comando que ahora le solicita que ingrese (por ejemplo, Buscar archivo: ... ), escriba Cg , varias veces si es necesario, para cancelar.
Cg también cancela una operación de larga duración si parece que Emacs se ha congelado.

Configuración de teclado y terminal
Algunos usuarios de Emacs reasignan su tecla Bloq Mayús para actuar como una tecla Ctrl adicional, porque es más fácil de alcanzar. Consulte las instrucciones para mover Ctrl .

Debido a la configuración de su teclado o terminal, puede encontrar que algunas teclas parecen hacer lo incorrecto:

Si su tecla DEL no funciona (a veces, al escribir DEL aparece una pantalla de ayuda, como si hubiera escrito Ch ), pruebe Mx normal-erase-is-backspace-mode .

Si su meta clave no funciona, para escribir una clave que contenga meta, puede escribir ESC , luego las teclas restantes. Por ejemplo, ESC x es lo mismo que Mx , y ESC Cs es lo mismo que CMs .

Preguntas frecuentes
Emacs viene con un FAQ que explica cómo realizar muchas tareas comúnmente solicitadas; presione Ch Cf para leerlo.

Migrar a Emacs
Emacs tiene varias opciones para facilitar la transición de otros entornos de edición.

Emacs para usuarios de Windows
En Windows, los comandos de edición de pan y mantequilla son Cz , Cx , Cc y Cv . Desafortunadamente, estas teclas se usan con frecuencia en Emacs para otros fines (suspensión, tecla de prefijo, tecla de prefijo y página siguiente). Puede recuperar esas teclas para Deshacer, Cortar, Copiar y Pegar activando el "Modo CUA" en el menú Opciones. El modo CUA también le permite hacer una selección usando Shift en combinación con teclas de movimiento, como lo haría en Windows.

Dado que Cx y Cc son tan integrales para la operación de Emacs (son teclas de prefijo para muchos comandos), el modo CUA solo vincula Cx y Cc a Cortar y Copiar, respectivamente, cuando ha seleccionado algún texto.

Puede obtener más información sobre el modo CUA escribiendo Ch f cua-mode RET .

Emacs para usuarios de vi / vim
Viper ( Mx viper-mode ) es un conjunto de modos para emular el comportamiento de edición vi en Emacs. Proporciona diferentes niveles de adherencia vi, dependiendo de cuán parecido a vi desee que sea su Emacs.

Para obtener más información sobre Viper, consulte (información "(viper)") .

Recursos de Emacs
El Manual de GNU Emacs ( Ch r ) es la guía definitiva si desea obtener más información sobre Emacs. Algunas funciones de Emacs tienen sus propios manuales separados ( Id . De canal ).

Las preguntas frecuentes de GNU Emacs ( Ch Cf ) responden muchas preguntas que los principiantes tienen sobre cómo funciona Emacs y cómo configurarlo para hacer cosas particulares.

EmacsWiki contiene información sobre muchas extensiones descargables de Emacs, así como consejos para usar y personalizar Emacs.

Puede hacer preguntas en la lista de correo help-gnu-emacs .