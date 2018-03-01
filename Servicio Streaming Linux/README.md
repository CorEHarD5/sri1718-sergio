* Descargar e instalar el paquete IceCast (Servidor de Audio): `apt-get install icecast2`

![imagen](./img/captura1.PNG)

* Editar el fichero `/etc/icecast/icecast2.xml` y modificar las siguientes líneas:

![imagen](./img/captura2.PNG)

* Editar el fichero `/etc/default/icecast` y modificar la siguiente línea:
 *ENABLE=true*

![imagen](./img/captura3.PNG)

* Iniciar el servicio correspondiente a Icecast:

![imagen](./img/captura4.PNG)

* Instalar el codificador vorbis ices2:

![imagen](./img/captura5.PNG)

* Crear el directorio para el codificador y copiar el fichero de configuración por
defecto:

![imagen](./img/captura6.PNG)

* Editamos el fichero de configuración del codificador y establecemos los
parámetros de nuestra emisora mediante las siguientes etiquetas:

![imagen](./img/captura7.PNG)

![imagen](./img/captura8.PNG)

![imagen](./img/captura9.PNG)

* Recopilar unos cuantos ficheros de audio en formato ogg y copiarlos en el
directorio /tmp/música

* Generar la lista de reproducción:

![imagen](./img/captura10.PNG)

* Crear el directorio log de ices2:

![imagen](./img/captura11.PNG)

* Ejecutar el codificador en background:

![imagen](./img/captura12.PNG)

* o Procedemos a acceder al entorno web de información y administración de nuestro
servidor de audio Icecast, a través de la IP (o nombre DNS) del servidor y el puerto
configurado anteriormente (8000). Acceder con el nombre de usuario y
contraseña que establecimos en la configuración.

![imagen](./img/captura13.PNG)


* Comprobar estado del servicio, configuración y propiedades. Comprobar asimismo
punto de montaje (Mountpoint) asociado a la lsita de reproducción creada y
propiedades

![imagen](./img/captura14.PNG)

![imagen](./img/captura15.PNG)

* Acceder vía web a la lista de reproducción (mountpoint) desde el propio servidor
(IPServidor:puerto/mountpoint).

![imagen](./img/captura16.PNG)

* Acceder desde un posible cliente (Linux o Windows), a través de un navegador,
tanto al entorno de administración como a la reproducción de la lista.

![imagen](./img/captura17.PNG)

![imagen](./img/captura19.PNG)

![imagen](./img/captura20.PNG)

* Tratar de realizar una reproducción del streaming de audio creado utilizando un
software reproductor multimedia desde el cliente (URL-> IP:puerto/mountpoint).

![imagen](./img/captura18.PNG)
