# Informe ISS- Servidor Web avanzado

* Crea una nueva zona de búsqueda directa en los servicios DNS asociado al dominio miEmpresa. Crea también una carpeta miEmpresa en C:\ y una subcarpeta ‘principal’.

![imagen](./images/captura1.PNG)

![imagen](./images/captura2.PNG)

![imagen](./images/captura3.PNG)

![imagen](./images/captura4.PNG)

![imagen](./images/captura5.PNG)

![imagen](./images/captura6.PNG)

* Crea un nuevo sitio web denominado miEmpresa en IIS asociado a la subcarpeta anterior y con acceso a través de la dirección www.miEmpresa.com. Actualiza DNS adecuadamente.

![imagen](./images/captura7.PNG)

![imagen](./images/captura8.PNG)

![imagen](./images/captura9.PNG)

![imagen](./images/captura10.PNG)

![imagen](./images/captura11.PNG)

![imagen](./images/captura12.PNG)

* Siguiendo los pasos detallados en el documento PDF de Carpetas Seguras y Privadas, crea un nuevo sitio web (denominado ‘pagos’) como subdominio de miEmpresa (pagos.miEmpresa.com) y configura este último para ser accedido de forma segura, vía ‘https’.
* Crea el sitio web, asociado a una carpeta (miEmpresa\pagos) y con la configuración adecuada en IIS y en los servicios DNS. Comprueba el acceso (aún vía ‘http’) con un navegador desde el propio servidor y desde un cliente W7.

![imagen](./images/captura13.PNG)

![imagen](./images/captura14.PNG)



* Configuración A: Siguiendo los pasos del tutorial correspondiente, configura el nuevo sitio para que se pueda acceder (sólo) como sitio web seguro (https) con un Certificado Autofirmado.

![imagen](./images/captura15.PNG)

![imagen](./images/captura16.PNG)

![imagen](./images/captura17.PNG)

![imagen](./images/captura18.PNG)

![imagen](./images/captura19.PNG)

![imagen](./images/captura20.PNG)

![imagen](./images/captura21.PNG)

* Configuración B: Crearemos un nuevo sitio seguro (tienda.miempresa.com) con la generación de un Certificado Digital a través de la aplicación OpenSSL. Para empezar, realizaremos la solicitud de un nuevo certificado de servidor para nuestro sitio seguro (crear fichero certreq.txt).

![imagen](./images/captura22.PNG)

![imagen](./images/captura23.PNG)

![imagen](./images/captura24.PNG)

* Descargar e instalar OpenSSL para Windows.

![imagen](./images/captura25.PNG)

![imagen](./images/captura26.PNG)

* A través de OpenSSl genera un nuevo certificado de servidor, siguiendo los pasos que se detallan en tutorial web (y comprobando los ficheros generados en cada paso): generar una clave privada de la entidad certificadora, crear un certificado digital de la entidad certificadora y, finalmente, crear un certificado digital de nuestra web.

![imagen](./images/captura27.PNG)

![imagen](./images/captura28.PNG)

![imagen](./images/captura29.PNG)

![imagen](./images/captura30.PNG)

![imagen](./images/captura31.PNG)

![imagen](./images/captura32.PNG)


* Importar el nuevo certificado de servidor creado para completar la petición pendiente en nuestro sitio seguro ‘pagos’.

![imagen](./images/captura33.PNG)


* Requerir que nuestros sitio seguros sólo se pueda acceder mediante una conexión segura y reiniciar los sitios web.

![imagen](./images/captura34.PNG)

* Finalmente, acceder mediante http y mediante https a los sitios seguros desde el propio servidor y desde un cliente W7, aceptando los posibles problemas con la entidad certificadora.

![imagen](./images/captura35.PNG)

* Guiándote por los pasos detallados en el apartado de carpetas privadas del documento PDF de Carpetas Seguras y Privadas, vamos a crear un nuevo sitio web (empleados.miEmpresa.com) destinado a almacenar información privada de los empleados, con las siguientes características:

* Necesitamos crear una carpeta empleados (dentro de miEmpresa) y, dentro de esta, tres o cuatro subcarpetas personales con nombres de empleados y una, denominada común, a la que tendrán acceso todos los empleados, pero no otros usuarios sin identificar.

![imagen](./images/captura36.PNG)

* Crearemos el nuevo sitio web, como subdominio de nuestro dominio principal, asociado a la carpeta genérica empleados.

![imagen](./images/captura38.PNG)

![imagen](./images/captura37.PNG)

* Colocar un fichero index.html diferente en cada una de las carpetas creadas, con el objetivo de poder comprobar el acceso desde un navegador.

![imagen](./images/captura43.PNG)

![imagen](./images/captura39.PNG)

![imagen](./images/captura41.PNG)

![imagen](./images/captura42.PNG)

* Para el sitio web creado y para cada una de sus carpetas, deshabilitamos el acceso anónimo.

![imagen](./images/captura45.PNG)

![imagen](./images/captura46.PNG)

* Agregar función de Autenticación Básica a nuestro Servicio de IIS a través de la Administración del Servidor.

![imagen](./images/captura58.PNG)

* En Active Directory, crearemos un usuario para cada empleado (tantos como carpetas personales) y un grupo Empleados que los incluya a todos.

![imagen](./images/captura47.PNG)

![imagen](./images/captura48.PNG)

![imagen](./images/captura49.PNG)

![imagen](./images/captura50.PNG)

![imagen](./images/captura51.PNG)

![imagen](./images/captura52.0.PNG)
* Desactivamos, para la carpeta empleados, los permisos heredables a través de las opciones avanzadas en la ficha de seguridad. Añadimos grupo de Administradores con Control Total y grupo Empleados con Lectura y Ejecución+ Mostrar Carpeta+Leer.

![imagen](./images/captura52.1.PNG)

![imagen](./images/captura52.2.PNG)


* Realizamos el mismo procedimiento para cada una de las carpetas personales de los empleados, colocando como usuarios autorizados el Grupo de Administradores (Control Total) y el empleado propietario de cada carpeta (con los permisos que creas convenientes).

![imagen](./images/captura53.PNG)

![imagen](./images/captura54.PNG)

![imagen](./images/captura55.PNG)

* Realizamos el mismo procedimiento para la carpeta ‘comun’, colocando como usuarios autorizados el Grupo de Administradores (Control Total) y el grupo Empleados (con los permisos que creas convenientes).


![imagen](./images/captura56.PNG)

* Activamos Examen de directorios

![imagen](./images/captura59.PNG)

* Comprobamos el acceso, tanto desde el servidor como desde el cliente W7, a las diferentes carpetas con distintos usuarios.

>en el servidor

![imagen](./images/captura61.1.PNG)

![imagen](./images/captura61.PNG)

![imagen](./images/captura62.PNG)

>en el cliente

![imagen](./images/captura63.PNG)

![imagen](./images/captura64.PNG)

![imagen](./images/captura65.PNG)

![imagen](./images/captura66.PNG)

![imagen](./images/captura67.PNG)

![imagen](./images/captura68.PNG)

![imagen](./images/captura69.PNG)

![imagen](./images/captura70.PNG)
