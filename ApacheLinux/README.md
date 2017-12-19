# Práctica Servidor Web Apache - Linux - Pasos e indicaciones



---

* Configurar MV Ubuntu o similar en adaptador Puente (acceso a Internet)

---

* Apache:
  * Instalar Apache: sudo apt-get install apache2

![img](./img/captura1.PNG)

  * Comprobar carpeta raíz sitio web: /var/www

![img](./img/captura2.PNG)

  * Comprobar acceso a localhost //It works!

![img](./img/captura3.PNG)

  * Añadir línea www.miempresa.com asociada a IP servidor en /etc/hosts o servidor DNS. Comprobar acceso

![img](./img/captura4.PNG)

![img](./img/captura5.PNG)

* Reiniciar apache: sudo /etc/init.d/apache2 restart ó reload

![img](./img/captura6.PNG)

* Error + Access logs: /var/log/apache2

![img](./img/captura7.PNG)

![img](./img/captura8.PNG)

![img](./img/captura9.PNG)

![img](./img/captura10.PNG)

---


* PHP
  * Instalar php: sudo apt-get install php5

![img](./img/captura10.PNG)

  * Comprobar acceso a index.php -<?php phpinfo(); ?>-

![img](./img/captura11.PNG)

![img](./img/captura14.PNG)

  * sudo apt-get install libapache2-mod-php5 //No debe ser necesario

![img](./img/captura13.PNG)

---


* Crear Hosts Virtuales en Apache, es decir, asociar carpetas con sitios web (ej: empleados.miempresa.com --> /var/www/empleados) y establecer configuración (/etc/apache2/sites-available/000-default.conf)

![img](./img/captura15.PNG)

  * Configuración Hosts Virtuales (sitios web independientes) en este enlace:
    * Ejemplo:
```cmd
<VirtualHost *:80>

ServerAdmin webmaster@miempresa.com

ServerName empleados.miempresa.com //Añadir también a hosts o serviodor DNS

DocumentRoot /var/www/empleados

<Directory /var/www/empleados> // No es necesario para VirtualHost sencillos

Opciones típicas...

</Directory>

</VirtualHost>
```

![img](./img/captura16.PNG)

![img](./img/captura17.PNG)



---

* Configurar sitio web seguro pagos:
  * Al instalar Apache, se instala también SSL
  * Generar certificado autofirmado:
      * § openssl genrsa -des3 -out server.key 1024

      * § openssl rsa -in server.key -out server.pem

![img](./img/captura19.PNG)

      * § openssl req -new -key server.key -out server.csr
      * § openssl x509 -req -days 360 -in server.csr -signkey server.key -out server.crt

![img](./img/captura20.PNG)

  * Modificar /etc/apache2/sites-available/000-default.conf según indicaciones PDF para crear host virtual seguro

![img](./img/captura30.PNG)

  * Habilitar módulo SSL apache: sudo a2enmod ssl

![img](./img/captura23.PNG)

  ---

* Acceso a carpetas privadas

![img](./img/captura21.PNG)

  * Autenticación mediante .htaccess: Ver enlace

![img](./img/captura27.PNG)

![img](./img/captura28.PNG)

---

No hemos podido continuar con la práctica debido a que la página no se muestra tal cual debería ser y no coge las configuraciones determinadas.

---
