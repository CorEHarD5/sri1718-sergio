# Informe ISS- Servidor Web básico

En esta práctica utilizaremos una máquina Windows 2012 Server y otra máquina W10 cliente para comprobaciones.

## Instalación y configuración de ISS en Servidor

 * Para instalar ISS en nuestro servidor nos vamos a `Administrar -> Agregar roles y características`.

 ![imagen](./images/captura1.PNG)

 * Seguidamente seleccionamos el rol de servidor con el nombre `Servidor web(IIS)`.

 ![imagen](./images/captura2.1.PNG)

 * Agregamos las características necesarias para el Servidor web ISS.

 ![imagen](./images/captura2.PNG)

 ![imagen](./images/captura3.PNG)

 * A continuación seleccionamos la opción `Autenticación de Windows` en *Servicios de rol*.

 ![imagen](./images/captura4.PNG)

 * Ya solo queda instalar.

 ![imagen](./images/captura5.PNG)

 ![imagen](./images/captura6.PNG)

 * Para comprobar que se nos ha instalado bien vamos a un navegador y ponemos nuestra ip de servidor.
> En el propio servidor

  ![imagen](./images/captura7.PNG)

> En el cliente, ya que le pusimos como proovedor dns nuestro servidor. ![imagen](./images/captura52.PNG)

 ![imagen](./images/captura8.PNG)

* Ahora aprovechamos una zona de busqueda directa que ya teníamos creada llamada *zona servidor* que apunta a nuestro servidor.

 ![imagen](./images/captura53.PNG)

 * Para poder entrar a la zona servidor mediante `www.zonaservidor` tenemos que crear un alias dentro de la *zonaservidor*.

  ![imagen](./images/captura9.1.PNG)

  * Comprobamos en el cliente que podemos acceder usando `www.`

   ![imagen](./images/captura9.2.PNG)

* Después vamos a crear una página web HMTL sencilla para utilizarla como página principal de nuestro dominio.Para ello debemos poner el archivo `index.htm` en la ruta `C:\Inetpub\wwwroot`.

 ![imagen](./images/captura9.PNG)

 > contenido del index

  ![imagen](./images/captura10.PNG)

* Comprobamos que se nos muestra la página web  en nuestro dominio.

> servidor

 ![imagen](./images/captura11.PNG)


> cliente

 ![imagen](./images/captura12.PNG)

 * Ahora vamos a crear una carpeta dentro del la ruta fisica por defecto de ISS (`\Inetpub\wwroot`)

 ![imagen](./images/captura15.PNG)


 * De esta manera nos mostraría el index que hay dentro de ella.

 ![imagen](./images/captura16.PNG)

* Ahora comprobamos que nos muestre el index.

 ![imagen](./images/captura17.PNG)

## Creación de sitios web independientes

* Para crear un sitio web independiente asociado a un dominio principal debemos crear una zona de búsqueda directa nueva.

> Click derecho sobre zona de búbusqueda directa y seleccionamos `Zona nueva`.
 ![imagen](./images/captura18.PNG)

  ![imagen](./images/captura19.PNG)

* Seleccionamos el tipo de zona, en nuestro caso principal.

 ![imagen](./images/captura20.PNG)

 * Escogemos la opción siguiente de que se repliquen los datos DNS:

  ![imagen](./images/captura21.PNG)

* Le ponemos como nombre `principalxd.com`.

 ![imagen](./images/captura22.PNG)

* Ya solo nos queda darle a finalizar.

 ![imagen](./images/captura24.PNG)

* Ahora creamos un Host dentro de la nueva zona con la dirección ip de nuestro servidor.

 ![imagen](./images/captura25.PNG)

 * Además le ponemos un alias *www* para que se pueda acceder como `www.principalxd.com`.
 > obviamente el alias es sobre nuestra nueva zona
   ![imagen](./images/captura25.PNG)

![imagen](./images/captura26.PNG)

* Después de hacer esto nos vamos a `Herramientas -> Administrador de Internet Information Services `

![imagen](./images/captura54.PNG)

* A continuación seleccionamos nuestro servidor u clickamos con botón derecho sobre `Sitios` y seleccionamos `Agregrar sitio web...`

![imagen](./images/captura29.PNG)

* Y para que se cree correctamente debemos rellenarlo de la siguiente manera.
> Ponemos la ruta de una carpeta que creamos anteriormente.

![imagen](./images/captura28.PNG)


* Dentro de la carpeta que creeamos en el escritorio ponemos un index.

![imagen](./images/captura30.PNG)

* El contenido del `index.htm` es el siguiente.

![imagen](./images/captura31.PNG)

* Además hay que darle permisos sobre la carpeta al usuario IUSR para que no de problemas.

![imagen](./images/captura32.PNG)

* Comprobamos la página web en un navegador.
>server

![imagen](./images/captura33.PNG)

>cliente

![imagen](./images/captura33.1.PNG)

>además probamos el alias

![imagen](./images/captura34.1.PNG)

* Ahora vamos a crear el subdominio. Para ello debemos crear un dominio dns nuevo llamado *subd* dentro de la zona directa nueva.

![imagen](./images/captura35.1.PNG)

![imagen](./images/captura55.PNG)

* Dentro de esta "subzona" añadimos un host que indica a la ip del propio servidor.

![imagen](./images/captura35.2.PNG)

* Después de hacer esto tenemos que ir al `Administrador de Internet Information Services` y agregar un sitio web nuevo.

![imagen](./images/captura37.PNG)

* Este tiene como ruta física una carpeta dentro de *principalxd* llamada *subd*.

![imagen](./images/captura36.PNG)

* Dentro de subd tenemos que poner un `index.htm`.

![imagen](./images/captura38.PNG)

* En este caso el `index.htm` es de la siguiente forma.

![imagen](./images/captura39.PNG)

* Ahora comprobamos en el navegador.

> en el servidor

![imagen](./images/captura40.PNG)

> en el cliente

![imagen](./images/captura41.PNG)

## Creación de Directorios Virtuales

* Para crear un directorio virtual nos vamos al `Administrador de Internet Information Services` y clickamos con botón derecho sobre nuestro sitio web llamado *principal*.

![imagen](./images/captura42.PNG)

* Este directorio virtual va a ser la carpeta que hemos creado llamada entornos.

![imagen](./images/captura43.PNG)

* Dentro de la carpeta entorno ponemos las carpeta entorno1, entorno 2 y entorno 3, las cuales contienen un `index.htm` como el siguiente.

![imagen](./images/captura58.PNG)

* Además de esto nos vamos a la seccion de  `Administrador de Internet Information Services` llamada `Examen de directorios`.

![imagen](./images/captura57.PNG)

* Una vez ahí habilitamos esa opción.

![imagen](./images/captura56.PNG)

* Comprobamos que se hizo correctamente.

>en el servidor

![imagen](./images/captura50.PNG)

> en el cliente

![imagen](./images/captura51.PNG)

* Después clickamos en cada enlace de los directorios para comprobar que funcionan.

![imagen](./images/captura59.PNG)

![imagen](./images/captura60.PNG)

![imagen](./images/captura61.PNG)
