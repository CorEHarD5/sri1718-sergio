# Informe FTP - Prácticas Windows y Linux Tarea (2.2)

## 1.Instalación y Configuración del Servicio FTP en Windows 2012 Server

* Instalar Servicio FTP en Windows 2012 Server, a través de Agregar roles y características (IIS).

![imagen](./img/Windows/captura1.PNG)

![imagen](./img/Windows/captura2.PNG)

![imagen](./img/Windows/captura3.PNG)

![imagen](./img/Windows/captura4.PNG)

![imagen](./img/Windows/captura5.PNG)

![imagen](./img/Windows/captura6.PNG)

![imagen](./img/Windows/captura7.PNG)

* Acceder a la creación y configuración de Sitios FTP por medio de la Administración de IIS.

![imagen](./img/Windows/captura8.PNG)

* Crear tres nuevos sitios FTP (en todos ellos se debe poder acceder a través de las IPs del servidor y, en algún caso, de un nombre DNS ftp.tudominio.ext):

![imagen](./img/Windows/captura9.PNG)

  * Uno asociado a la unidad C: completa. No debe permitir accesos anónimos. Sin uso de SSL. Sólo el usuario Administrador podrá acceder al sitio. Modos lectura y escritura.  

![imagen](./img/Windows/captura10.PNG)

![imagen](./img/Windows/captura11.PNG)

![imagen](./img/Windows/captura12.PNG)
  Ahora realiza las siguientes acciones:

  * Trata de acceder al sitio ftp desde el propio servidor a través de un navegador y un explorador de archivos.

  * Comprueba accesos permitidos y denegados. Comprueba también permisos asignados.

![imagen](./img/Windows/captura13.PNG)

  * Accede ahora desde un cliente Windows de la misma forma. Realiza comprobaciones.

![imagen](./img/Windows/captura14.PNG)

![imagen](./img/Windows/captura15.PNG)

  * Instala el software WinSCP en el cliente Windows, configura la conexión a tu sitio ftp y trata de establecer conexión y realizar comprobaciones.
![imagen](./img/Windows/captura16.PNG)

![imagen](./img/Windows/captura17.PNG)

![imagen](./img/Windows/captura18.PNG)

![imagen](./img/Windows/captura19.PNG)

  * El segundo asociado al directorio wwwroot de Inetpub. Se permitirá el acceso a todos los usuarios de Active Directory en modo lectura y escritura. No permitimos acceso anónimo y habilitamos en este caso la posibilidad (permitir, no requerir) de conexiones SSL asociadas a uno de los certificados que poseas en IIS. Realizar diferentes comprobaciones válidas e inválidas de conexión y operaciones, tanto desde el servidor como desde el cliente. Realizar una configuración de conexión SSL desde WinSCP.

![imagen](./img/Windows/captura20.PNG)

![imagen](./img/Windows/captura21.PNG)

![imagen](./img/Windows/captura22.PNG)

> hacemos lo siguiente para que pueda funcionar y no se acople con el otro posteriormente lo arreglamos cambiando el puerto de acceso.

![imagen](./img/Windows/captura23.PNG)

![imagen](./img/Windows/captura24.PNG)

![imagen](./img/Windows/captura26.PNG)

![imagen](./img/Windows/captura25.PNG)
  * El tercer sitio FTP debe asociarse a una carpeta cualquiera del servidor que contenga información (archivos y carpetas), pero que no sea importante. Permitiremos acceso anónimo y sólo se podrá consultar y leer. Comprobar desde servidor y cliente.

![imagen](./img/Windows/captura27.PNG)

![imagen](./img/Windows/captura28.PNG)

![imagen](./img/Windows/captura29.PNG)

* En un principio es posible que debas detener un sitio web para que pueda iniciarse otro. Tras comprobar el funcionamiento por separado de los sitios, encontrar una solución para que nuestro servidor ofrezca varios sitios FTP simultáneamente.

> modificamos los puertos de los sitios para que se pueda acceder simultáneamente.

![imagen](./img/Windows/captura32.PNG)

![imagen](./img/Windows/captura33.PNG)

![imagen](./img/Windows/captura31.PNG)

 > los iniciamos todos y comprobamos su acceso indicando el puerto adecuado.

![imagen](./img/Windows/captura34.PNG)

![imagen](./img/Windows/captura35.1.PNG)

![imagen](./img/Windows/captura35.2.PNG)

![imagen](./img/Windows/captura35.PNG)

## 2.Instalación y Configuración de un Servidor FTP en Linux

* Instalar Servicio SSH en el servidor Linux.

![imagen](./img/Linux/captura1.PNG)
* Crear dos usuarios en el sistema, con diferentes privilegios y niveles de acceso al filesystem.

![imagen](./img/Linux/captura2.PNG)

![imagen](./img/Linux/captura3.PNG)
* Comprobar, desde una máquina cliente, acceso de los usuarios mediante ssh.

![imagen](./img/Linux/captura4.PNG)

![imagen](./img/Linux/captura5.PNG)

* Tratar de ejecutar una aplicación gráfica del servidor de forma remota, desde el cliente, mediante ssh.
> Daba un error y comprobastes que estaba todo bien solo que no ejecutaba

![imagen](./img/Linux/captura6.PNG)
* Acceder, también desde el cliente, mediante sftp (ftp seguro, incluido en el paquete ssh) al sistema de ficheros del servidor y probar acceso, carga y descarga de archivos con ambos usuarios.

![imagen](./img/Linux/captura7.PNG)
* Realizar varias copias de archivos hacia / desde el servidor mediante scp, utilizando también los dos usuarios creados anteriormente.

![imagen](./img/Linux/captura8.PNG)

![imagen](./img/Linux/captura9.PNG)

![imagen](./img/Linux/captura10.PNG)

![imagen](./img/Linux/captura11.PNG)

![imagen](./img/Linux/captura12.PNG)
* Instalar el paquete proftpd.

![imagen](./img/Linux/captura13.PNG)

![imagen](./img/Linux/captura14.PNG)
* Investigar y editar el fichero de configuración /etc/proftpd/proftpd.conf buscando información en Internet.

![imagen](./img/Linux/captura15.PNG)

![imagen](./img/Linux/captura16.PNG)
* Tratar de conectar al servicio ftp gestionado por proftpd tanto desde el servidor como desde un cliente.

![imagen](./img/Linux/captura17.PNG)
* Desde la máquina cliente, probar el acceso al ftp mediante los usuarios creados y realizando diferentes operaciones de listado, subida y descarga de archivos.

![imagen](./img/Linux/captura19.PNG)

![imagen](./img/Linux/captura20.PNG)

![imagen](./img/Linux/captura21.PNG)
