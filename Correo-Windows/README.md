# Práctica Servicio SMTP Windows 2012 Server

* Instalar Servicio SMTP en Windows 2012 Server

![imagen](./img/Windows1/captura1.PNG)

![imagen](./img/Windows1/captura2.PNG)

![imagen](./img/Windows1/captura3.PNG)

![imagen](./img/Windows1/captura4.PNG)

![imagen](./img/Windows1/captura5.PNG)

![imagen](./img/Windows1/captura6.PNG)

![imagen](./img/Windows1/captura7.PNG)

![imagen](./img/Windows1/captura8.PNG)

* Configuración de servicio SMTP a través del administrador de aplicaciones (IIS) 6.0. Realizar las siguientes acciones de configuración:

![imagen](./img/Windows1/captura9.PNG)
* Establecer como IP nuestro servidor

![imagen](./img/Windows1/captura10.PNG)

![imagen](./img/Windows1/captura11.PNG)

* Limitar el número de conexiones a 50

![imagen](./img/Windows1/captura13.PNG)
* Habilitar el registro en formato W3C, diario y en una carpeta determinada

![imagen](./img/Windows1/captura14.PNG)
* Configurar envío de mensajes dentro de nuestra red local: Aceptar la conexión al servidor y la retransmisión de mensajes a todos los equipos menos los que aparecen en la lista (incluir una IP cualquiera en la lista para impedir su acceso y retransmisión)

![imagen](./img/Windows1/captura16.PNG)
* Establecer autenticación anónima

![imagen](./img/Windows1/captura15.PNG)
* Echar un vistazo al resto de opciones de configuración del servidor. Aplicar cambios y reiniciar servicio.

![imagen](./img/Windows1/captura17.PNG)
* Comprobar la existencia del dominio AD predeterminado. Crea un dominio de tipo alias para disponer de cuentas en otro dominio.

![imagen](./img/Windows1/captura18.PNG)

![imagen](./img/Windows1/captura19.PNG)

![imagen](./img/Windows1/captura20.PNG)
* Comprueba carpetas de correo creados en `C:\Inetpub\mailroot`.

![imagen](./img/Windows1/captura21.PNG)

En el cliente Windows:
* Comprobar acceso al nuevo nombre DNS creado en el servidor.(No se pudo acceder tras varios intentos, por lo que opté por poner la IP directamente (**Comprobastes que estaba todo bien configurado, simplemente no funcionaba** )

![imagen](./img/Windows1/captura22.PNG)

![imagen](./img/Windows1/captura23.PNG)

![imagen](./img/Windows1/captura25.PNG)

* Configurar el cliente de correo Live mail agregando dos cuentas de correo cualesquiera (usuarios AD -dominio- y no AD). Se deberá especificar: usuario / buzón, contraseña,  servidor SMTP.

![imagen](./img/Windows1/captura26.PNG)

![imagen](./img/Windows1/captura27.PNG)


* Enviar varios correos desde / hacia las diferentes cuentas y comprobar envío (real o ficticio) y carpetas mailroot. Las carpetas existentes en mailroot alojan mensajes en cola (Queue), mensajes para destinatarios desconocidos (Badmail) y mensajes entregados (Drop)

![imagen](./img/Windows1/captura28.PNG)

> Comprobación en carpeta Badmail de correo inexistente.

![imagen](./img/Windows1/captura47.PNG)

* Nueva configuración de servicio SMTP a través del administrador de aplicaciones (IIS) 6.0. Establecer autenticación básica de Windows. Probar diferentes configuraciones de dominio predeterminado, cifrado TLS, etc.

![imagen](./img/Windows1/captura29.PNG)

![imagen](./img/Windows1/captura30.PNG)

> Creamos un usuario de Active Directory destinado a comprobar la autenticación

![imagen](./img/Windows1/captura31.PNG)

![imagen](./img/Windows1/captura32.PNG)
En el cliente Windows:
* Configurar las cuentas según los parámetros especificados en el servidor. Enviar varios correos desde / hacia las diferentes cuentas y comprobar envío y carpetas mailroot. En este caso sólo tendrán acceso al servidor SMTP cuentas del dominio y correspondientes a usuarios de AD.

![imagen](./img/Windows1/captura33.PNG)

![imagen](./img/Windows1/captura34.PNG)

![imagen](./img/Windows1/captura35.PNG)

![imagen](./img/Windows1/captura36.PNG)

> Prueba para enviar un correo desde la cuenta creada hasta mi cuenta de correo personal.

![imagen](./img/Windows1/captura37.PNG)


![imagen](./img/Windows1/captura38.PNG)

> Ahora activamos la opción de certificado TLS.

![imagen](./img/Windows1/captura39.PNG)

![imagen](./img/Windows1/captura40.PNG)

> Configuramos la cuenta de correo ya creada con la opción para TLS.

![imagen](./img/Windows1/captura41.PNG)

![imagen](./img/Windows1/captura42.PNG)

![imagen](./img/Windows1/captura43.PNG)

> Prueba para enviar un correo desde la cuenta creada hasta mi cuenta de correo personal.

![imagen](./img/Windows1/captura44.PNG)

![imagen](./img/Windows1/captura45.PNG)

![imagen](./img/Windows1/captura46.1.PNG)

![imagen](./img/Windows1/captura46.2.PNG)

# Práctica hMailServer

* En primer lugar, hay que desinstalar el servicio SMTP de Windows 2012 Server.

![imagen](./img/Windows2/captura1.PNG)

![imagen](./img/Windows2/captura2.PNG)

![imagen](./img/Windows2/captura3.PNG)

![imagen](./img/Windows2/captura4.PNG)

![imagen](./img/Windows2/captura5.PNG)

![imagen](./img/Windows2/captura6.PNG)

![imagen](./img/Windows2/captura7.PNG)

![imagen](./img/Windows2/captura8.PNG)

> Reiniciamos el servidor

![imagen](./img/Windows2/captura9.PNG)
* Debes descargar e instalar en el servidor Windows 2012 server el servidor de correo hMailServer.

![imagen](./img/Windows2/captura10.PNG)

![imagen](./img/Windows2/captura11.PNG)

![imagen](./img/Windows2/captura12.PNG)

![imagen](./img/Windows2/captura13.PNG)

![imagen](./img/Windows2/captura14.PNG)

![imagen](./img/Windows2/captura15.PNG)

![imagen](./img/Windows2/captura16.PNG)

![imagen](./img/Windows2/captura17.PNG)

> Es necesario instalar en .NET Framework 3.5

![imagen](./img/Windows2/captura18.PNG)

* Crea dos dominios denominados srd.edu y asir.edu.

> Nos conectamos en localhost introduciendo la password que dimos al instalarlo.

![imagen](./img/Windows2/captura19.PNG)

![imagen](./img/Windows2/captura20.PNG)

![imagen](./img/Windows2/captura21.1.PNG)

![imagen](./img/Windows2/captura21.PNG)

![imagen](./img/Windows2/captura22.PNG)

![imagen](./img/Windows2/captura23.PNG)
* Ejecuta los diagnósticos para ambos dominios y soluciona el error de backup asignando una carpeta para tal fin. Establece copia de seguridad de los mensajes.

![imagen](./img/Windows2/captura24.PNG)

![imagen](./img/Windows2/captura25.PNG)

![imagen](./img/Windows2/captura26.PNG)

![imagen](./img/Windows2/captura27.PNG)

![imagen](./img/Windows2/captura28.PNG)

![imagen](./img/Windows2/captura29.PNG)

![imagen](./img/Windows2/captura30.PNG)

![imagen](./img/Windows2/captura31.PNG)

![imagen](./img/Windows2/captura32.PNG)

* Crea dos cuentas para dos usuarios ficticios en cada uno de los dos dominios. Investiga y configura las cuentas con diferentes opciones (cuota de disco, auto-reply, forwarding, signature, etc.)

![imagen](./img/Windows2/captura33.PNG)

![imagen](./img/Windows2/captura34.PNG)

![imagen](./img/Windows2/captura35.PNG)

![imagen](./img/Windows2/captura36.PNG)

![imagen](./img/Windows2/captura37.PNG
  )
![imagen](./img/Windows2/captura38.PNG)

* Configura el servicio DNS para crear las entradas mail.srd.edu y mail.asir.edu que apunten a la dirección ip del servidor windows 2012.

![imagen](./img/Windows2/captura39.PNG)

![imagen](./img/Windows2/captura40.PNG)
* Realiza todas las opciones de configuración que consideres necesarias y/o convenientes.Consulta para ello los tutoriales cuyos enlaces se proporcionan (opciones de protocolos SMTP, POP e IMAP, rangos de IP, bloqueo de correo entrante, nombre de host, reenvío dominios remotos, blacklists, opciones de logging, etc.)

![imagen](./img/Windows2/captura41.PNG)

![imagen](./img/Windows2/captura42.PNG)

![imagen](./img/Windows2/captura43.PNG)

![imagen](./img/Windows2/captura44.PNG)

![imagen](./img/Windows2/captura45.PNG)
* Configura en el cliente W7 un cliente de correo como thunderbird o Live Mail (en los ordenadores clientes) para acceder al servidor de correo instalado en Windows 2012.

![imagen](./img/Windows2/captura46.PNG)

![imagen](./img/Windows2/captura47.PNG)

![imagen](./img/Windows2/captura48.PNG)

* Realiza prueba de envío y recepción de correos entre los diferentes usuarios, comprobando, además de envío y recepción correctas, el efecto de las opciones configuradas en las cuentas.

![imagen](./img/Windows2/captura49.PNG)

![imagen](./img/Windows2/captura50.PNG)

> No me dejaba enviar un correo a mi cuenta personal de gmail (**mirastes las configuraciones y estaban bien**)

![imagen](./img/Windows2/captura51.PNG)

![imagen](./img/Windows2/captura52.1.PNG)

![imagen](./img/Windows2/captura52.2.PNG)
* Crea una lista de distribución empleados asociada al dominio y añade a los dos usuarios de miempresa.com a ella.

![imagen](./img/Windows2/captura52.PNG)

![imagen](./img/Windows2/captura53.PNG)

![imagen](./img/Windows2/captura54.PNG)
* Realiza prueba de envío y recepción de correos por medio de la lista de distribución.

![imagen](./img/Windows2/captura55.PNG)

![imagen](./img/Windows2/captura56.PNG)

![imagen](./img/Windows2/captura57.PNG)
