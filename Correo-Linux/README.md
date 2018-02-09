# Instalación y Configuración  de un Servidor de Correo en Linux


Instalar servicio SMTP en Linux, utilizando el servidor Postfix:
* Descargar e instalar postfix: `apt-get install postfix`.

![imagen](./img/000133.png)
* Configuración de postfix:
* Escoger instalación como Sitio de Internet

![imagen](./img/000131.png)
* Crear dominio miempresa.com o similar

![imagen](./img/000132.png)
* Comprobar servicio (y puerto) SMTP activo y a la escucha con `netstat –utap`

![imagen](./img/000134.png)
* Realizar una prueba de envío de mensaje entre dos usuarios del sistema mediante
telnet, tal y como se indica en el ejemplo del apartado Prueba de Funcionamiento del
documento pdf.

![imagen](./img/000135.png)

![imagen](./img/000136.png)
* Instalar un cliente de correo electrónico en un cliente (por ejemplo Evolution, para
Ubuntu).

![imagen](./img/000137.png)

![imagen](./img/000138.png)

![imagen](./img/000139.png)

![imagen](./img/000140.png)

![imagen](./img/000141.png)

![imagen](./img/000142.png)

![imagen](./img/000143.png)

![imagen](./img/000144.png)
* Crear dos nuevas entradas en `/etc/hosts`: `smtp.miempresa.com` y `pop.miempresa.com`
asociadas a la IP del servidor.

![imagen](./img/000145.png)
* Crear al menos dos cuentas asociadas a usuarios existentes en el servidor y asociadas al
dominio creado en Postfix. Configurar datos de las cuentas (dirección correo, servidores
entrante y saliente).

![imagen](./img/000147.png)
* Realizar envío de dos correos, uno con cada una de las cuentas creadas. Comprobar la
recepción de estos correos en el servidor examinando la carpeta `/var/mail`.

![imagen](./img/000146.png)

![imagen](./img/000148.png)

![imagen](./img/000149.png)
* Instalar servicio IMAP y servidor Correo Web SquirrelMail:
* Instalar servicio IMAP con `apt-get install dovecot-imapd`

![imagen](./img/000150.png)
* Comprobar servicio (y puerto) IMAP activo y a la escucha con `netstat –utap`

![imagen](./img/000151.png)
* Instalar aplicación correo web SquirrelMail con `apt-get install squirrelmail`

![imagen](./img/000152.png)
* Carpeta de configuración en `/etc/squirrelmail`
* Carpeta de aplicación en `/usr/share/squirrelmail`
* Copiar lineas no comentadas `/etc/squirrelmail/apache.conf` en un nuevo fichero `.conf` de
`/etc/apache2/sites-available`, habilitar sitio y reiniciar apache

![imagen](./img/000153.png)

![imagen](./img/000154.png)
* Acceder vía HTTP en `/localhost/squirrelmail`

![imagen](./img/000165.png)

![imagen](./img/000166.png)
*  Acceder desde una máquina cliente, vía HTTP, al gestor de correo SquirrelMail instalado

![imagen](./img/000163.png)

![imagen](./img/000164.png)
*  Enviar y recibir correos entre las dos cuentas creadas desde el cliente y utilizando el
gestor de correo web SquirrelMail

![imagen](./img/000167.png)

![imagen](./img/000168.png)
* Comprobar que los mensajes enviados desde ambas cuentas se siguen encontrando en
los respectivos buzones de los usuarios en `/var/mail`

![imagen](./img/000169.png)

![imagen](./img/000170.png)
* Instalar servicio POP3:
* Instalar servicio POP3 con `apt-get install dovecot-pop3d`

![imagen](./img/000171.png)
* Comprobar servicio (y puerto) POP3 activo y a la escucha con `netstat –utap`

![imagen](./img/000172.png)
* Configurar MUA (gestor de correo cliente Evolution o similar) en máquina cliente para
que acceda a la recepción de correo a través del protocolo POP3 instalado en el
servidor.

![imagen](./img/000173.png)

![imagen](./img/000174.png)

![imagen](./img/000175.png)

![imagen](./img/000176.png)

* Enviar y recibir correos entre las dos cuentas creadas desde el cliente y utilizando el
gestor de correo del cliente

![imagen](./img/000177.png)
* Comprobar que los correos enviados y recibidos han desaparecido (han sido extraídos
por POP3) de los buzones respectivos de los usuarios en `/var/mail`

![imagen](./img/000178.png)

![imagen](./img/000179.png)
