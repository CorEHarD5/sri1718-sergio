# DNS Linux.

---

* Instalamos el servicio `bind9`

![img](./img/c1.png)

* Configuramos el archivo `resolv.conf` para que el servidor DNS sea la misma máquina.

![img](./img/c3.png)

* Configuramos el servidor como *caché DNS* con los reenviadores de DNS públicos.

![img](./img/c5.png)

* Configuramos el DNS como maestro, añadiendo una empresa virtual llamada *miempresa.es* y añadimos una zona de búsqueda inversa y directa.

![img](./img/c7.png)

---

* En la máquina cliente, configuramos la IP con su respectiva dirección que nosotros le asignaremos, y a continuación pondremos en su servidor DNS la IP de nuestro servidor.

![img](./img/c6.png)

* Comprobamos que todo va correctamente con un nmap a *www.google.es* y con un ping al mismo host.

![img](./img/c8.png)

* Creamos los archivos de búsqueda directa e inversa de nuestra empresa, para ellos clonamos los que ya teníamos y a continuación los actualizamos.

![img](./img/c9.png)

* En el de búsqueda direta, rellenamos los datos con `miempresa.db` y añadimos el host del propio cliente.

![img](./img/c10.png)

* Y ahora vamos al archivo de búsqueda inversa para configurarlo, en el cual pondremos la IP de la *máquina servidor.*

![img](./img/c16.png)

* Comprobamos que no hay ningún fallo desde el servidor.

![img](./img/c12.png)

![img](./img/c15.png)

* Comprobamos que no hay ningún fallo desde el cliente.

![img](./img/c13.png)

![img](./img/c17.png)

---

* Vamos a clonar la máquina servidor para tener una máquina que haga el funcionamiento como **esclavo**.

![img](./img/c14.png)

* Modificamos los archivos de búsquedas para ponerlos de tipo `esclavo` y añadimos el *master*, que en este caso es la máquina **servidor**.

![img](./img/c18.png)

* Creamos los ficheros de búsqueda pero los dejamos en blanco, ya que esta máquina buscará la información en el servidor.

![img](./img/c19.png)

![img](./img/c20.png)

* Por último comprobamos desde el cliente que funciona la conexión a través de **ping y nslookup**.

> Antes debemos parar el servicio con `/etc/init.d/bind9 stop` en la máquina servidor, y comprobar que en la máquina esclava está activo.

![img](./img/c21.png)

---
