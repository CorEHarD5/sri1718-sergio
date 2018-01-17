# Informe FTP - Prácticas Windows y Linux Tarea (2.2)

## 1.Instalación y Configuración del Servicio FTP en Windows 2012 Server

* Instalar Servicio FTP en Windows 2012 Server, a través de Agregar roles y características (IIS).

![imagen](./img/Windows/captura1.png)

![imagen](./img/Windows/captura2.png)

![imagen](./img/Windows/captura3.png)

![imagen](./img/Windows/captura4.png)

![imagen](./img/Windows/captura5.png)

![imagen](./img/Windows/captura6.png)

![imagen](./img/Windows/captura7.png)

* Acceder a la creación y configuración de Sitios FTP por medio de la Administración de IIS.

![imagen](./img/Windows/captura8.png)

* Crear tres nuevos sitios FTP (en todos ellos se debe poder acceder a través de las IPs del servidor y, en algún caso, de un nombre DNS ftp.tudominio.ext):

![imagen](./img/Windows/captura9.png)

  * Uno asociado a la unidad C: completa. No debe permitir accesos anónimos. Sin uso de SSL. Sólo el usuario Administrador podrá acceder al sitio. Modos lectura y escritura.  

![imagen](./img/Windows/captura10.png)

![imagen](./img/Windows/captura11.png)

![imagen](./img/Windows/captura12.png)
  Ahora realiza las siguientes acciones:

  * Trata de acceder al sitio ftp desde el propio servidor a través de un navegador y un explorador de archivos.

  * Comprueba accesos permitidos y denegados. Comprueba también permisos asignados.

![imagen](./img/Windows/captura13.png)

  * Accede ahora desde un cliente Windows de la misma forma. Realiza comprobaciones.

![imagen](./img/Windows/captura14.png)

![imagen](./img/Windows/captura15.png)

  * Instala el software WinSCP en el cliente Windows, configura la conexión a tu sitio ftp y trata de establecer conexión y realizar comprobaciones.
![imagen](./img/Windows/captura16.png)

![imagen](./img/Windows/captura17.png)

![imagen](./img/Windows/captura18.png)

![imagen](./img/Windows/captura19.png)

  * El segundo asociado al directorio wwwroot de Inetpub. Se permitirá el acceso a todos los usuarios de Active Directory en modo lectura y escritura. No permitimos acceso anónimo y habilitamos en este caso la posibilidad (permitir, no requerir) de conexiones SSL asociadas a uno de los certificados que poseas en IIS. Realizar diferentes comprobaciones válidas e inválidas de conexión y operaciones, tanto desde el servidor como desde el cliente. Realizar una configuración de conexión SSL desde WinSCP.

![imagen](./img/Windows/captura20.png)

![imagen](./img/Windows/captura21.png)

![imagen](./img/Winpngs/captura22.png)

> hacemos lo siguiente para que pueda funcionar y no se acople con el otro posteriormente lo arreglamos cambiando el puerto de acceso.

![imagen](./img/Windows/captura23.png)

![imagen](./img/Windows/captura24.png)

![imagen](./img/Windows/captura26.png)

![imagen](./img/Windows/captura25.png)
  * El tercer sitio FTP debe asociarse a una carpeta cualquiera del servidor que contenga información (archivos y carpetas), pero que no sea importante. Permitiremos acceso anónimo y sólo se podrá consultar y leer. Comprobar desde servidor y cliente.

![imagen](./img/Windows/captura27.png)

![imagen](./img/Windows/captura28.png)

![imagen](./img/Windows/captura29.png)

* En un principio es posible que debas detener un sitio web para que pueda iniciarse otro. Tras comprobar el funcionamiento por separado de los sitios, encontrar una solución para que nuestro servidor ofrezca varios sitios FTP simultáneamente.

> modificamos los puertos de los sitios para que se pueda acceder simultáneamente.

![imagen](./img/Windows/captura32.png)

![imagen](./img/Windows/captura33.png)

![imagen](./img/Windows/captura31.png)

 > los iniciamos todos y comprobamos su acceso indicando el puerto adecuado.

![imagen](./img/Windows/captura34.png)

![imagen](./img/Windows/captura35.1.png)

![imagen](./img/Windows/captura35.2.png)

![imagen](./img/Windows/captura35.png)

## 2.Instalación y Configuración de un Servidor FTP en Linux

* Instalar Servicio SSH en el servidor Linux.

![imagen](./img/linux/captura1.png)
* Crear dos usuarios en el sistema, con diferentes privilegios y niveles de acceso al filesystem.

![imagen](./img/linux/captura2.png)

![imagen](./img/linux/captura3.png)
* Comprobar, desde una máquina cliente, acceso de los usuarios mediante ssh.

![imagen](./img/linux/captura4.png)

![imagen](./img/linux/captura5.png)

* Tratar de ejecutar una aplicación gráfica del servidor de forma remota, desde el cliente, mediante ssh.
> Daba un error y comprobastes que estaba todo bien solo que no ejecutaba

![imagen](./img/linux/captura6.png)
* Acceder, también desde el cliente, mediante sftp (ftp seguro, incluido en el paquete ssh) al sistema de ficheros del servidor y probar acceso, carga y descarga de archivos con ambos usuarios.

![imagen](./img/linux/captura7.png)
* Realizar varias copias de archivos hacia / desde el servidor mediante scp, utilizando también los dos usuarios creados anteriormente.

![imagen](./img/linux/captura8.png)

![imagen](./img/linux/captura9.png)

![imagen](./img/linux/captura10.png)

![imagen](./img/linux/captura11.png)

![imagen](./img/linux/captura12.png)
* Instalar el paquete proftpd.

![imagen](./img/linux/captura13.png)

![imagen](./img/linux/captura14.png)
* Investigar y editar el fichero de configuración /etc/proftpd/proftpd.conf buscando información en Internet.

![imagen](./img/linux/captura15.png)

![imagen](./img/linux/captura16.png)
* Tratar de conectar al servicio ftp gestionado por proftpd tanto desde el servidor como desde un cliente.

![imagen](./img/linux/captura17.png)
* Desde la máquina cliente, probar el acceso al ftp mediante los usuarios creados y realizando diferentes operaciones de listado, subida y descarga de archivos.

![imagen](./img/linux/captura19.png)

![imagen](./img/linux/captura20.png)

![imagen](./img/linux/captura21.png)
