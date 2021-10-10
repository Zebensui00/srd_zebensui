<center>

 # Informe DNS Windows - Zebensui Lorenzo Esquivel

En este caso vamos a instalar y configurar el servidor de nombres (DNS) en una máquina Windows Server 2016

Para ello lo primero es instalarlo mediante le asistente. Como siempre nos vamos a la parte de Agregar Roles y Características y seleccionamos el servicio DNS aunque lo más probable es que ya lo tengamos instalados como es mi caso, puesto que se instala cuando promovemos el AC a controlador de dominio.

 ![](./img/1.png)


Nos vamos a la parte de herramientas y lo abrimos.

![](img/2.png)

# Zona de búsqueda Directa

Lo que vamos a hacer ahora es crear una zona de búsqueda directa en nuestro servidor, para ello clicamos en zona de búsqueda directa y le damos a Zona nueva...

![](img/3.png)

Se nos abrirá el asistente que nos va a ser de gran ayuda a la hora de configurarlo todo.

![](img/4.png)

Ahora vamos a ir poco a poco seleccionando las opciones que queramos. En el primer caso nosotros vamos a crear una zona principal.

![](img/5.png)

Esta opción nos da igual ahora mismo porque no tenemos otro servidor DNS en este dominio pero igualmente es bueno marcarla por si en algún futuro se planea crear otro.

![](img/6.png)

Sencillamente elegimos el nombre que queramos, a poder ser uno sencillo porque luego nos vamos a cansar de escribirlo.

![](img/7.png)

Escogemos como queremos gestionar las actualizaciones, en mi caso escogí la opción que esta a medio camino entre comodidad y seguridad.

![](img/8.png)

Con esto hemos finalizado la creación de la zona directa.

![](img/9.png)

Comprobamos que se creo correctamente.

![](img/10.png)

# Zona de búsqueda Inversa

Ahora vamos a por la zona de búsqueda inversa que realmente se crea de la misma forma.

![](img/11.png)

Las primeras opciones que nos muestra son las mimas que antes por lo que las dejamos iguales.

![](img/12.png)

![](img/13.png)

![](img/14.png)

Ahora elegimos para que clase de IP va a ser la zona. En nuestro caso IPv4.

![](img/15.png)

Escogemos le rango de IP de la zona y el nombre se pondrá solo.

![](img/16.png)

Lo mismo que antes.

![](img/17.png)

Y con esto hemos terminado la Zona Inversa.

![](img/18.png)

# Reenviadores

Para los reenviadores nos vamos a nuestro máquina dentro del DNS, le damos click derecho Propiedades, Reenviadores

![](img/20.png)

Aquí añadimos las IP de los servidores DNS a los que queremos que nuestro servidor haga peticiones cuando le pregunten por una IP que el no conozca. Nota: No puse la puerta de enlace porque no estoy en la red de clase y por ello no podía validarla.

![](img/21.png)

# Server Cache

Ahora vamos a configurar el server como Cache. Para ello tenemos que tener la configuración de red estática de la siguiente forma:

![](img/19.png)

Y el cliente así:

![](img/22.png)

Ahora comprobamos (con el comando nslookup /displaydns) desde el servidor buscando una web y luego desde el cliente buscando esa misma web para ver que nos da lo mismo que en el servidor pero saliendo por él.

Server:

![](img/24.png)

![](img/25.png)

Cliente:

![](img/23.png)

# Server Master

Vamos a empezar a añadir nuevos host al servicio DNS. El funcionamiento para todos es el mismo, le damos click derecho en la zona que hemos creado y seleccionamos le tipo de registro que queremos, para el primero sera un Alias CNAME del servidor en el que estamos

![](img/27.png)

Tendremos que ponerle el nombre que queramos y seleccionar hacía que máquina apunta.

![](img/28.png)

![](img/29.png)

![](img/30.png)

Para todos los siguientes lo hacemos de la misma forma solo que en este caso es un host nuevo, osea un registro A

![](img/31.png)

Importante marcar en todos "Crear registro PTR asociado" para que se cree en la zona inversa de forma automática

![](img/32.png)

Para el de correos primero creamos el registro host (A) y creamos un MX que apunte a él.

![](img/33.png)

![](img/44.png)

![](img/45.png)

Así nos queda:

![](img/34.png)

Para el de correos primero creamos el registro host (A) y creamos un MX que apunte a él.

![](img/35.png)

![](img/36.png)

Seguimos el procedimiento como antes

![](img/37.png)

![](img/38.png)

![](img/39.png)

Así nos queda:

![](img/40.png)

Y la zona inversa:

![](img/41.png)

Antes de seguir a hacer las comprobaciones vamos a asegurarnos de que el servidor DNS registra a nuestro cliente

![](img/26.png)

![](img/42.png)

# Comprobaciones

Lo que nos falta es comprobar que se resuelven todos los registros que hemos creado desde el servidor y desde el cliente.

Servidor:

![](img/46.png)

![](img/47.png)

Cliente:

![](img/48.png)

![](img/49.png)

Nslookp desde el cliente hacia el exterior:

![](img/50.png)

</center>
