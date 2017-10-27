# Instalación y Configuración DNS W2012

## 1. Máquinas necesarias

Para esta práctica necesitaremos una máquina Windows 2012 Server y otra máquina Cliente con Windows 10.

Ponemos la tarjeta de red del server y el cliente en modo puente. Además al server le ponemos la siguiente configuración de red:

![imagen](./images/captura1.1.PNG)

En el cliente solo le ponemos como servidor dns la ip del servidor:

![imagen](./images/captura1.2.PNG)

## 2. Configurar el servicio DNS

Para ello vamos al servidor y clickamos sobre `Herramientas -> DNS`.

![imagen](./images/captura1.PNG)

Una vez hecho esto, se nos abre una ventana para administrar el DNS.

![imagen](./images/captura2.PNG)

>En él se puede ver que ya hay una zona de búsqueda directa que esta asociado al dominio

## 3.1 Creación de zona de búsqueda directa

Ahora vamos a crear una nueva zona de búsqueda directa.Para ello clickamos con el botón derecho dentro de la zona de búsqueda directa y le damos a `crear nueva zona`.

A continuación se nos despliega el `asistente para nueva zona`.

![imagen](./images/captura3.PNG)

Le damos a `siguiente` y seleccionamos el tipo de zona en nuestro caso `zona principal`.

![imagen](./images/captura4.PNG)

Seguidamente le ponemos un nombre a la zona que queremos crear.

![imagen](./images/captura5.PNG)

Ya solo queda especificar el tipo de actualizaciones que aceptará la zona DNS.

![imagen](./images/captura6.PNG)

Después de haber hecho esto ya podemos comprobar que hemos creado una nueva zona.

![imagen](./images/captura7.PNG)

## 3.2 Creación de zona de búsqueda inversa

Ahora vamos a crear una nueva zona de búsqueda inversa.Para ello clickamos con el botón derecho dentro de la zona de búsqueda inversa y le damos a `crear nueva zona`.

A continuación, al igual que en la directa, nos sale el `asistente para nueva zona`, en este caso inversa.Seleccionamos la opción para redes con *IPv4*.

![imagen](./images/captura8.PNG)

Le damos a siguiente y escribimos una ip para identificar a la zona de búsqueda inversa.

![imagen](./images/captura9.PNG)

Ya solo queda darle a finalizar y tenemos creado nuesta zona.

![imagen](./images/captura10.PNG)

Podemos comprobarlo en la parte de zonas de búsqueda inversa.

![imagen](./images/captura11.PNG)

## 4. Configurar los reenviadores

Clickamos con el botón derecho sobre el nombre de nuestro servidor y seleccionaos `Propiedades`.

![imagen](./images/captura12.PNG)

 Una vez hecho esto vamos a la pestaña que pone `Reenviadores` dentro de las `Propiedades` de nuestro servidor.

 ![imagen](./images/captura13.PNG)

 Y Clickamos en Editar, dentro de ahí ponemos las siguientes direcciones ip.

 ![imagen](./images/captura14.PNG)

Depués de haber hecho esto nos vamos a la máquina Windows 10
cliente y comprobamos que los reenviadores estan bien configurados.

Para esto abrimos una `cmd` y hacemos un `nslookup` a cualquier dirección web conocida.

![imagen](./images/captura14.1.PNG)

## 5. Añadiendo registros a zona de busqueda directa
> Para hacer esto clickamos con el botón derecho dentro de la zona y seleccionando el registro que queremos crear
![imagen](./images/captura15.PNG)

Vamos a la zona de búsqueda y añadimos los siguientes registros:

 * Un alias para tu servidor denominado server.

    * Primero elegimos el nombre de alias que queremos poner .

    * Después debemos seleccionar de quien va a ser alias(nuestro servidor) y aceptamos.

![imagen](./images/captura16.PNG)

![imagen](./images/captura16.2.PNG)

 * Una impresora con IP fija denominada printer (no hace falta alias).
    * Simplemente hay que crear un host nuevo llamado *impresora*, le asignamos una ip cualquiera fija y le damos a `agregar host`.

  ![imagen](./images/captura17.PNG)


 * Un servidor de correo (ficticio) denominado correo, asociado a una dirección en tu servidor.

    * Primero tenemos que crear un host nuevo llamado correo.
    * Después agregamos un registro llamado `Agente de intercambio de correo(MX)`. En él hay que especificar el host que creamos anteriormente y un nombre de dominio.

![imagen](./images/captura18.PNG)

![imagen](./images/captura20.PNG)

![imagen](./images/captura19.PNG)

### 5.1 Comprobaciones tanto en el propio servidor como en el cliente.

>registros de servidor

![imagen](./images/captura22.1.PNG)

![imagen](./images/captura22.PNG)

![imagen](./images/captura23.1.PNG)

![imagen](./images/captura23.PNG)

>registro de impresora

![imagen](./images/captura21.1.PNG)

![imagen](./images/captura21.PNG)

>registros de correo

![imagen](./images/captura24.1.PNG)

![imagen](./images/captura24.PNG)

![imagen](./images/captura25.1.PNG)

![imagen](./images/captura25.PNG)

## 6. Creación de una subzona  

Vamos a la zonaservidor que creamos anteriormete y clickamos con el botón derecho sobre él y seleccionamos `dominio nuevo`.

![imagen](./images/captura27.PNG)

 Le ponemos de nombre servicios

 ![imagen](./images/captura28.PNG)

 Ahora dentro de la subzona añadimos los siguientes:

 * Un servidor ftp (asociado a la misma IP del servidor)
    * Simplemente creamos un host nuevo con la ip de servidor.

![imagen](./images/captura29.PNG)

 * Una impresora nueva (con una IP fija)  
    * Creamos otro host con una ip fija.

![imagen](./images/captura30.PNG)

 * Un equipo del administrador del sistema (también con IP fija)

    * Igual que antes creamos un host con una ip fija.

![imagen](./images/captura31.PNG)  
### 6.2 Comprobaciones

> registro de servidor

![imagen](./images/captura32.1.PNG)

> registro de impresora2

![imagen](./images/captura32.2.PNG)

> registro del equipo administrador

![imagen](./images/captura32.3.PNG)

## 7. Unión al dominio y comprobacion de registro

### 7.1 Validamos un cliente en el dominio

Para ello hay que entrar en la máquina cliente y unirlo al dominio. Nos pide iniciar sesión.

![imagen](./images/captura33.1.PNG)

 Después nos sale un mensaje de que se ha unido al dominio.

 ![imagen](./images/captura33.2.PNG)

### 7.2 Comprobación del registro

Vamos al servidor y miramos la zona de búsqueda directa que ya teníamos creada (preteneciente al domino) y comprobamos que hay un registro de tipo *A* con el nombre del equipo.

![imagen](./images/captura34.PNG)

## 8. Comprobación final en el cliente

Hacemos una última comprobación mediante lookup después de todos los cambios.

![imagen](./images/captura35.PNG)
