# Informe IIS - Servidor Web avanzado - PHP, MySQL, phpMyAdmin, FTP y Drupal

* Vamos a realizar las instalaciones y configuraciones necesarias para obtener un Servidor Web con soporte PHP y accesos a bases de datos relacionales, acceso FTP y gestor de bases de datos. Sobre este servidor, podremos realizar instalaciones de aplicaciones integradas (CMS, e-commerce, etc)
u
* Siguiendo los pasos detallados en las guías y tutoriales, instala soporte para PHP para tus sitios Web gestionados por IIS. Recomendado PHP 5.x VCx Non Thread-Safe (con IIS Fast CGI).

![imagen](./img/000150.png)

![imagen](./img/000151.png)

![imagen](./img/000152.png)

* Configuramos el servidor

![imagen](./img/000153.png)

![imagen](./img/000154.png)

* Comprobar la instalación correcta de PHP colocando un fichero index.php en el sitio web destinado
a gestionar el CMS Drupal (www.miEmpresa.com ó miEmpresa\principal) con el siguiente código:
`<?php phpinfo(); ?>`

![imagen](./img/000155.png)

* Siguiendo los pasos detallados en las guías y tutoriales, instala el servidor de bases de datos relacionales MySQL para tus sitios Web gestionados por IIS.

  * Descargar e instalar .NET Framework 4.0.
  * Instalar MySQL y complementos necesarios.

![imagen](./img/000156.png)

![imagen](./img/000157.png)

![imagen](./img/000158.png)

![imagen](./img/000159.png)

![imagen](./img/000160.png)

![imagen](./img/000161.png)

![imagen](./img/000162.png)

![imagen](./img/000163.png)

![imagen](./img/000164.png)

* Siguiendo los pasos detallados en las guías y tutoriales, instala PHPMyAdmin para tus sitios Web gestionados por IIS. Para esto debes crear un nuevo sitio web asociado a `phpmyadmin.miEmpresa.com`, recordando crear la correspondiente carpeta (donde descomprimirás los ficheros de phpMyAdmin) y actualizar DNS.

![imagen](./img/000165.png)

![imagen](./img/000166.png)

![imagen](./img/000167.png)

* Siguiendo los pasos detallados en las guías y tutoriales proporcionados:
  * Instalar Servidor FTP FileZilla en Windows 2012 Server.

  ![imagen](./img/000144.png)

  ![imagen](./img/000145.png)

  ![imagen](./img/000146.png)

  ![imagen](./img/000147.png)

  ![imagen](./img/000148.png)

  * Crear un usuario denominado ftpuser en el Servidor FTP y asociarle a este usuario permisos de Control Total sobre la carpeta en la que se va a instalar el CMS de miEmpresa.

  ![imagen](./img/000168.png)

  *  Crear un nuevo registro DNS que permita acceder a nuestro sitio FTP a través de la dirección `ftp.miEmpresa.com`.

  ![imagen](./img/000170.png)

  ![imagen](./img/000172.png)

* A partir de este punto, salvo problemas de difícil solución, todo el trabajo deberá realizarse en modo remoto, desde el cliente Windows 7:
  * Comprobar acceso a phpMyAdmin desde un navegador (phpmyadmin.miEmpresa.com).

  ![imagen](./img/000167.png)  
  * Descargar CMS Drupal de drupal.org.

  * Comprobar el acceso al sitio FTP creado a través de un navegador y con el usuario ftpuser.

  ![imagen](./img/captura1.png)

  ![imagen](./img/captura2.png)
  * Instalar un cliente ftp (p.e.: FileZilla) en Windows 7 para poder realizar todas las operaciones sobre los ficheros y carpetas del servidor web.

  ![imagen](./img/000173.png)

  ![imagen](./img/000174.png)

  ![imagen](./img/000175.png)

  * Descomprimir y subir archivos Drupal a carpeta principal (www.miEmpresa.com).

  ![imagen](./img/000176.png)

  * Crear una nueva base de datos, denominada cms, a través de phpMyAdmin.

    ![imagen](./img/000177.png)

    ![imagen](./img/000178.png)
  * Crear usuario cms y asignar todos los privilegios para la base de datos anterior.

  ![imagen](./img/000179.png)

  ![imagen](./img/000180.png)

  * Instalar CMS Drupal desde el navegador siguiendo los pasos y consultando documentación en Internet.

  ![imagen](./img/000181.png)

  ![imagen](./img/000182.png)

  ![imagen](./img/000183.png)

  * Configuración y creación del sitio Drupal: configurar idioma español; instalar módulo gtranslate y habilitar traducción a varios idiomas;

  ![imagen](./img/000184.png)

  ![imagen](./img/000185.png)

  ![imagen](./img/000186.png)

  ![imagen](./img/000187.png)

  ![imagen](./img/000188.png)

  * Instalar y configurar temas Marinelli, Zen y Fusion.

![imagen](./img/000189.png)

![imagen](./img/000190.png)

![imagen](./img/000191.png)
  * Crear dos o tres páginas de contenido, crear menú Primary Links y colocar como bloque. Otras opciones de configuración que desees.  

  ![imagen](./img/000192.png)

  * Elige una de las siguientes aplicaciones web integradas basadas en software libre y realiza, en grupos de hasta tres alumnos, su instalación y configuración en tu servidor web, siempre en modo remoto, desde el cliente W7.

  * Utilizamos Wordpress.

  ![imagen](./img/000193.png)

  ![imagen](./img/000194.png)

  ![imagen](./img/000195.png)

#### Trabajo Realizado por Sergio de la Barrera García y Adán Pérez García.
