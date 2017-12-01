# Informe IIS - Servidor Web avanzado - PHP, MySQL, phpMyAdmin, FTP y Drupal

* Vamos a realizar las instalaciones y configuraciones necesarias para obtener un Servidor Web con soporte PHP y accesos a bases de datos relacionales, acceso FTP y gestor de bases de datos. Sobre este servidor, podremos realizar instalaciones de aplicaciones integradas (CMS, e-commerce, etc)
u
* Siguiendo los pasos detallados en las guías y tutoriales, instala soporte para PHP para tus sitios Web gestionados por IIS. Recomendado PHP 5.x VCx Non Thread-Safe (con IIS Fast CGI).

![imagen](./img/000150.PNG)

![imagen](./img/000151.PNG)

![imagen](./img/000152.PNG)

* Configuramos el servidor

![imagen](./img/000153.PNG)

![imagen](./img/000154.PNG)

* Comprobar la instalación correcta de PHP colocando un fichero index.php en el sitio web destinado
a gestionar el CMS Drupal (www.miEmpresa.com ó miEmpresa\principal) con el siguiente código:
`<?php phpinfo(); ?>`

![imagen](./img/000155.PNG)

* Siguiendo los pasos detallados en las guías y tutoriales, instala el servidor de bases de datos relacionales MySQL para tus sitios Web gestionados por IIS.

  * Descargar e instalar .NET Framework 4.0.
  * Instalar MySQL y complementos necesarios.

![imagen](./img/000156.PNG)

![imagen](./img/000157.PNG)

![imagen](./img/000158.PNG)

![imagen](./img/000159.PNG)

![imagen](./img/000160.PNG)

![imagen](./img/000161.PNG)

![imagen](./img/000162.PNG)

![imagen](./img/000163.PNG)

![imagen](./img/000164.PNG)

* Siguiendo los pasos detallados en las guías y tutoriales, instala PHPMyAdmin para tus sitios Web gestionados por IIS. Para esto debes crear un nuevo sitio web asociado a `phpmyadmin.miEmpresa.com`, recordando crear la correspondiente carpeta (donde descomprimirás los ficheros de phpMyAdmin) y actualizar DNS.

![imagen](./img/000165.PNG)

![imagen](./img/000166.PNG)

![imagen](./img/000167.PNG)

* Siguiendo los pasos detallados en las guías y tutoriales proporcionados:
  * Instalar Servidor FTP FileZilla en Windows 2012 Server.

  ![imagen](./img/000144.PNG)

  ![imagen](./img/000145.PNG)

  ![imagen](./img/000146.PNG)

  ![imagen](./img/000147.PNG)

  ![imagen](./img/000148.PNG)

  * Crear un usuario denominado ftpuser en el Servidor FTP y asociarle a este usuario permisos de Control Total sobre la carpeta en la que se va a instalar el CMS de miEmpresa.

  ![imagen](./img/000168.PNG)

  *  Crear un nuevo registro DNS que permita acceder a nuestro sitio FTP a través de la dirección `ftp.miEmpresa.com`.

  ![imagen](./img/000170.PNG)

  ![imagen](./img/000172.PNG)

* A partir de este punto, salvo problemas de difícil solución, todo el trabajo deberá realizarse en modo remoto, desde el cliente Windows 7:
  * Comprobar acceso a phpMyAdmin desde un navegador (phpmyadmin.miEmpresa.com).

  ![imagen](./img/000167.PNG)  
  * Descargar CMS Drupal de drupal.org.

  * Comprobar el acceso al sitio FTP creado a través de un navegador y con el usuario ftpuser.

  ![imagen](./img/captura1.PNG)

  ![imagen](./img/captura2.PNG)
  * Instalar un cliente ftp (p.e.: FileZilla) en Windows 7 para poder realizar todas las operaciones sobre los ficheros y carpetas del servidor web.

  ![imagen](./img/000173.PNG)

  ![imagen](./img/000174.PNG)

  ![imagen](./img/000175.PNG)

  * Descomprimir y subir archivos Drupal a carpeta principal (www.miEmpresa.com).

  ![imagen](./img/000176.PNG)

  * Crear una nueva base de datos, denominada cms, a través de phpMyAdmin.

    ![imagen](./img/000177.PNG)

    ![imagen](./img/000178.PNG)
  * Crear usuario cms y asignar todos los privilegios para la base de datos anterior.

  ![imagen](./img/000179.PNG)

  ![imagen](./img/000180.PNG)

  * Instalar CMS Drupal desde el navegador siguiendo los pasos y consultando documentación en Internet.

  ![imagen](./img/000181.PNG)

  ![imagen](./img/000182.PNG)

  ![imagen](./img/000183.PNG)

  * Configuración y creación del sitio Drupal: configurar idioma español; instalar módulo gtranslate y habilitar traducción a varios idiomas;

  ![imagen](./img/000184.PNG)

  ![imagen](./img/000185.PNG)

  ![imagen](./img/000186.PNG)

  ![imagen](./img/000187.PNG)

  ![imagen](./img/000188.PNG)

  * Instalar y configurar temas Marinelli, Zen y Fusion.

![imagen](./img/000189.PNG)

![imagen](./img/000190.PNG)

![imagen](./img/000191.PNG)
  * Crear dos o tres páginas de contenido, crear menú Primary Links y colocar como bloque. Otras opciones de configuración que desees.  

  ![imagen](./img/000192.PNG)

  * Elige una de las siguientes aplicaciones web integradas basadas en software libre y realiza, en grupos de hasta tres alumnos, su instalación y configuración en tu servidor web, siempre en modo remoto, desde el cliente W7.

  * Utilizamos Wordpress.

  ![imagen](./img/000193.PNG)

  ![imagen](./img/000194.PNG)

  ![imagen](./img/000195.PNG)

#### Trabajo Realizado por Sergio de la Barrera García y Adán Pérez García.
