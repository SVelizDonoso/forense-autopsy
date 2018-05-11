# Análisis Forense Digital de un caso real con Autopsy
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/autopsy_logo.gif?w=400&zoom=2">

En el Magíster de la universidad Central de Chile, tuvimos un ejercicio bien interesante que me gustaría compartir con ustedes. Se trata de un análisis forense de un caso real, que por medio de una imagen, se obtiene una serie de datos que ayudan a una investigación.

El ejercicio resuelto , difiere un poco de lo que me toco a mí resolver ya que no encontré la imagen con la que yo trabaje en el curso del Magíster, pero encontré el mismo ejemplo en una pagina de desafíos forenses por lo que deberia dar los mismos resultados.

# Herramientas utilizadas
 En el desarrollo práctico de este ejercicio serán utilizadas las siguientes herramientas especializadas para el análisis forense.

- Autopsy
- VMware Workstation 12 Pro
- Kali Linux ver 2.0
- Md5sum
- Archive Manager(Descompresión)

# Desarrollo del Ejercicio

El desafió es analizar un disquete recuperado y contestar algunas preguntas. Para esto tendrás que leer un informe de la policía  simulando una investigación en el mundo real. Además tendrás un poco de información de antecedentes y algunas pruebas.
```sh
wget https://raw.githubusercontent.com/SVelizDonoso/forense-autopsy/master/report.txt
```
A continuación se muestra la imagen del disquete dd recuperado. Esta es la imagen que proporcionará las respuestas del caso.
```sh
wget https://github.com/SVelizDonoso/forense-autopsy/raw/master/image.zip
```
 Descargar: image.zip MD5 = b676147f63923e1f428131d59b1d6a72 (image.zip)
 
 # Preguntas a Resolver en el caso:
 - ¿Quién es el proveedor de marihuana de Joe Jacobs y cuál es su dirección?
-  ¿Qué dato clave está disponible dentro del archivo coverpage.jpg?
-  ¿Qué otras escuelas secundarios (si hay) adicionales a Smith Hill, frecuenta Joe Jacobs?
-  Para cada archivo recuperado, ¿qué proceso fue adelantado por el sospechoso para ocultarlo en el disco?
-  ¿Qué proceso realizó Ud. como investigador para examinar con éxito el contenido completo de cada archivo?
-  ¿Puede decir qué programa fue usado para crear el archivo coverpage.jpg? ¿Cómo lo puede probar?

# DEMOSTRACIÓN PRÁCTICA DEL EJERCICIO FORENSE

El siguiente punto detalla las actividades realizadas paso a paso para obtener las respuestas a las preguntas del punto anterior, nuevamente explico que el nombre del archivo y firma md5 con la que trabajo yo  es distinta, por lo que recomiendo seguir el ejercicio como una guia y ustedes hacer el ejercicio con el archico que les indique descargar.

 Para comenzar con la investigación. Se descarga una imagen con el nombre wetransfer-680dbd.zip<br>
 <img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura114.jpg"><br>
 
 Una vez descargado el archivo se procede a calcular su hash md5<br>
 <img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura213.jpg"><br>

 
 Ahora creamos una copia del archivo para trabajar con él y no contaminar la evidencia principal.<br>
 <img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura33.jpg"><br>

Calculamos el md5 del archivo copiaevidencia.zip para verificar que estamos trabajando con una copia original de la evidencia.<br>
 <img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura42.jpg"><br>

Para trabajar con la imagen, vamos a descomprimir copiaevidencia.zip<br>
 <img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura52.jpg"> <br>
Damos Click en Open With Archive Manager  <br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura61.jpg"><br>
Damos Click en Extract y vemos que tenemos un archivo que se llama image, la cual será la imagen sobre la cual trabajaremos.<br>
 <img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura72.jpg"><br>
Procedemos a calcular su HASH md5<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura82.jpg"><br>

Ahora vamos a trabajar esta imagen sobre una herramienta especializada en análisis forense. Para completar este paso abrimos una terminal y escribimos el comando autopsy.<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura93.jpg"><br>
Copiamos la URL que nos indican el programa y la pegamos en nuestro navegador con el siguiente resultado.<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura103.jpg"><br>
Para iniciar un caso con autopsy damos Click sobre el botón que dice Open Case.<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura115.jpg">  <br>
Una vez realizada esta tarea, nos aparecerá la siguiente pantalla<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura122.jpg"><br>
Ahora damos Click sobre el botón New Case<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura132.jpg"><br>
Y procedemos a llenar los datos del formulario.<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura142.jpg"><br>
Damos Click en New Case nuevamente y nos aparecerá la siguiente pantalla<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura152.jpg"><br>
Ahora vamos a dar Click en ADD HOST<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura162.jpg"><br>
Llenamos los campos del formulario y aceptamos.<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura172.jpg"><br>
Al agregar el nuevo host, nos aparecerá la siguiente pantalla<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura183.jpg"><br>
Ahora nos queda agregar la evidencia a revisar.<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura193.jpg"><br>
Ahora damos Click en Next.<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura202.jpg"><br>
seleccionamos Volume System Type Dos<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura214.jpg"><br>
Damos Ok.

Ahora procedemos a completar el formulario.<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura222.jpg"><br>
Seleccionamos calcular Hash y comprobamos la integridad de nuestra evidencia.<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura242.jpg"><br>
Damos Ok y comienza el inicio del análisis ya que tenemos la evidencia cargada en nuestro sistema con los procedimientos forenses adecuados.

Esta es la pantalla del inicio de análisis.<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura252.jpg"><br>
Para comenzar damos Click en el link Details y procedemos a crear los índices de búsqueda.

Imagen antes de los índices de búsqueda:<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura262.jpg"><br>
Para trabajar con la imagen damos Click sobre los botones Extract String y Extract Unallocated.

Después de este proceso de verificación damos Click sobre el botón Close que se encuentra al final del formulario y nos salimos de esta pantalla.<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura271.jpg"><br>
Ahora volvemos a verificar como quedo la imagen después de trabajar sobre ella.<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura281.jpg"><br>
Si el paso anterior lo seguimos bien deberíamos estar en la siguiente pantalla nuevamente.<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura291.jpg"><br>
Ahora Damos Click sobre el botón Analyze<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura301.jpg"><br>
Y damos Click en el botón Image Details<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura311.jpg"><br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura321.jpg"><br>
Con esto verificamos el tamaño del cluster, direcciones de memoria, metadatos y informacion volumen, FAT contents nos indica los sectores que contienen datos del diskett.

Ahora damos click en el boton que dice File Analyze y nos deberia llegar a la siguiente Pantalla<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura331.jpg"><br><br><br>
# Examinar cada uno de los archivos.
<br>
<br>
Archivo Cover page.jpgc<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura34.jpg"><br>
Damos click en HEX DISPLAY y verificamos que este archivo no es reconocido como un .jpeg , ya que si fuese de esta forma tendría los valores en HEX FF D8.<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura35.jpg"><br>
Ahora Vamos a visualizar los metadatos de esta imagen dando click en Meta<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura36.jpg?w=68&zoom=2"><br>
Tendremos la siguiente información en pantalla.<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura37.jpg"><br>
La evidencia nos señala la siguiente inconsistencia:

El archivo posee un tamaño de 15585 bytes, sin embargo sólo se tiene un sector de 451 bytes asignado sobre 512 bytes correspondiente al tamaño de los sectores en FAT 12.<br>

Procedemos entonces al cálculo del archivo:<br>
- Tamaño archivo 15585 bytes
- Tamaño FAT 12 512 bytes
- Sectores a Ocupar = (Tamaño archivo + Tamaño FAT -1) / Tamaño FAT

Es decir: (15585 + 511) /512= 31<br>

 Por lo tanto, debemos ocupar 31 sectores para reconstruir la imagen.<br>

Ahora procedemos a buscar una firma JPEG JFIF desde el sector 451 en sentido inverso, es decir, primero revisar el sector 451, después 450, después 449 hasta llegar al sector 73 donde encontramos una coincidencia con el contenido JI IF.<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura38.jpg"><br>
Como en el análisis FAT CONTENTS encontramos 31 sectores, significa que desde el inicio de la imagen debemos comenzar de sector 72 + 31 esto nos 103, es decir, del sector 73 al 103.<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura39.jpg"><br>
Damos click en View e inmediatamente el sistema reconoce el conjunto de byte donde se encuentra grabada la imagen en el disco que pertenecen a el archivo JPEG. Ahora procedemos a extraer la imagen dando Click en Export Content<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura40.jpg"><br>
Nos aparecerá la siguiente Imagen.<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura411.jpg"><br>
Damos Click en Save File y Cambiamos la imagen de .raw a .jpeg<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura421.jpg"><br>
Guardamos el archivo y Damos Click sobre la imagen y visualizamos el contenido.<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura43.jpg"><br>
<br>
<br>
Análisis Archivo Jimmy Jungle.doc<br><br>
En la primera visualización Autopsy, reconoce este archivo como eliminado y de extensión .doc<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura44.jpg"><br>
Ahora procedemos a verificar los metadatos del archivo dando Click sobre el link Meta.<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura45.jpg"><br>
Verificamos sus datos para proceder al cálculo del número de bloques necesarios para extraer el archivo<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura46.jpg"><br>
Entonces procedemos al Cálculo del archivo:<br>
Números de sectores del archivo
- Desde sector 32
- Hasta Sector 72

Numero de sectores 72 – 32 = 40<br>

Con los datos obtenidos vamos al bloque 33, completamos el formulario y damos Click a View<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura47.jpg"><br>
La operación anterior debería haber mostrado la siguiente pantalla.<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura48.jpg"><br>
Damos Click en Export Contents<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura49.jpg"><br>
Damos Click en Guardar archivo<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura50.jpg"><br>
Cambiamos de extensión raw a Doc y guardamos<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura511.jpg"><br>
Y damos Click sobre el para verificar el contenido.<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura521.jpg"><br>
<br><br>
Análisis Archivo Schedueld Visits.exe<br><br>
Damos Click sobre el archivo y verificamos los resultados entregados por la aplicación.<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura53.jpg"><br>
Ingresamos a Verificar sus metadatos.<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura54.jpg"><br>
Resultados de la apantalla metadatos<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura55.jpg"><br>
En la pantalla nos indica que el tamaño del archivo es de 1000 y que utiliza dos sectores 104 y 105.<br>

Entonces procedemos al Cálculo del archivo:<br>
Números de sectores del archivo:<br><br>
Desde sector 103 à Hasta Sector 105<br>

Numero de sectores 103 – 105 = 2<br><br>

Con los datos obtenidos vamos al bloque 2, completamos el formulario y damos Click a View<br>

Procedemos a calcular el archivo<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura56.jpg"><br>
Según los datos del bloque 104 y 105 indica que hay un archivo de nombre Scheduled Visits.xls<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura57.jpg"><br>
Ahora damos Click a Export Contents<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura58.jpg"><br>
Guardamos el archivo con extensión .zip y procedemos a extraer contenidos.<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura59.jpg"><br>
La siguiente imagen nos demuestra que el archivo esta corrupto por lo que nos hacen falta más bloques para lograr crear el contenido.<br><br>

Como tuvimos este tipo de problemas al encontrar que el archivo no estaba completo, revisamos la evidencia y descubrimos que desde el bloque 106 a 108 estaban resto de otro archivo y tiene la coincidencia que también lleva adentro el archivo Scheduled Visits.xls<br><br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura60.jpg"><br>
Entonces ya con esta información procedemos a extraer desde el bloque 104 a 108, nuevamente damos Click a Export Contents<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura611.jpg"><br>
el siguiente nombre para diferenciar de la descarga anterior y damos Click a guardar<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura62.jpg"><br>
Procedemos a extraer el contenido y verificamos que adentro de este archivo encontramos un archivo con nombre Scheduled Visits.xls<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura63.jpg"><br>
Lo extraemos y verificamos su contenido.<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura64.jpg"><br>
Nos damos cuenta que para exportar el archivo se necesita una clave.<br><br>

Al no saber dónde encontrar la clave, nuevamente verificamos las evidencias obtenidas. El primer paso es revisar desde el archivo jpeg y luego el doc para ver si pasamos por alto algún dato relevante que nos pueda indicar si la contraseña se encuentra dentro del diskette.<br><br>

Comenzamos revisando el archivo  jpeg y nos dimos cuenta que al final de la imagen existe la palabra pw que hace referencia a password.<br><br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura65.jpg"><br>
Pasamos el contenido de HEX a string para visualizar mejor el contenido y vemos que dice pw=goodtimes<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura67.jpg"><br>
Procedemos a ingresar esta clave, primero ingresaremos en el archivo zip goodtimes y si esta contraseña no sirve, ingresaremos el texto completo pw=goodtimes<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura68.jpg"><br>
Nos indica que la extracción fue realizada con éxito<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura69.jpg"><br>
Y damos doble Click para verificar su contenido.<br>
<img src="https://cybersecuritylaboratory.files.wordpress.com/2016/09/captura70.jpg"><br>
<br>

# Respuestas al Caso
<br><br>

¿Quién es el proveedor de marihuana de Joe Jacobs y cuál es su dirección?<br>

El proveedor es Jimmy Jungle. La dirección es 626 Jungle Ave, Apt 2, Jungle, NY 11111.<br><br>

 ¿Qué dato clave está disponible dentro del archivo coverpage.jpg?<br>

Dentro del archivo “coverpage.jpg”, en la parte final de las unidades de asignación del archivo se encuentra el texto “pw=gootimes” el cual corresponde a la contraseña del archivo protegido “Scheduled Visit.exe”.<br><br>

¿Qué otras escuelas secundarios (si hay) adicionales a Smith Hill, frecuenta Joe Jacobs? Frecuenta los siguientes establecimientos <br>secundarios adicionales:<br>

- Key High School (B)
- Leetch High School (C)
- Birard High School (D)
- Richter High School (E)
- Hull High School (F)

Para cada archivo recuperado, ¿qué proceso fue adelantado por el sospechoso para ocultarlo en el disco?<br>

Borrado de archivo “Jimmy Jungle.doc” Compresión, protección por contraseña y cambio de extensión del archivo  “Schedule Visits.exe”.<br><br>

 ¿Qué proceso realizó Ud. como investigador para examinar con éxito el contenido completo de cada archivo?<br>

Recuperación y visualización directa con herramienta Autopsy del archivo “Jimmy Jungle.doc” Extracción con la herramienta Archive Manager a partir de la correcta estructura del directorio FAT12 del archivo “Scheduled Visits.exe”. Descompresión mediante herramienta Winzip y utilización de Excel para visualizar la planilla.<br><br>

 ¿Puede decir qué programa fue usado para crear el archivo coverpage.jpg? ¿Cómo lo puede probar?<br>

 Se puede deducir que el archivo fue creado mediante una aplicación de Microsoft que maneje conversión de formatos gráficos o escaneo de imágenes. Esta hipótesis se puede probar (en parte para descartar), convirtiendo un archivo BMP a JPG con cualquier otra herramienta distinta a las mencionadas, corroborando así que no es posible generar bloques de comentarios.<br><br>
 
 
# Autor
@svelizdonoso https://github.com/SVelizDonoso/
 
 
 
  
 
 
 
 
 
 
 
 
