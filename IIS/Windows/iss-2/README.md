# Informe Servidor Web avanzado Windows - Zebensui Lorenzo Esquivel

Informe Esta práctica tiene dos partes. En la primera vamos a crear certificados para una página web, el primero sera autofirmado y el otro lo generaremos nosotros, y en la segunda vamos a crear carpetas y darles permisos a ciertos usuarios para poder entrar en ellas validandonos.

## Ceritifcado autofirmado.

Creamos el sitio web y configuramos el DNS para poder acceder a él desde el navegador con el nombre que escojamos.

![](img/1.png)

![](img/2.png)

![](img/3.png)

![](img/4.png)

Ahora vamos a crear un subdominio dentro de la página anterior y vamos a añadirle el certificado autofirmado.
Para ello lo tenemos que crear primero, y esto lo hacemos desde el panel de control del servicio IIS tal y como se muestra a continuación:

![](img/5.png)

![](img/6.png)

![](img/7.png)

![](img/8.png)

Creamos la página y comprobamos (desde el servidor y el cliente) que se accede a ella con el protocolo https y que sin él nos muestra la página por defecto.

![](img/9.png)

![](img/10.png)

![](img/11.png)

![](img/12.png)

![](img/13.png)

![](img/14.png)

## Ceritifcado generado.

Ahora nos vamos a la parte donde creamos el certificado autofirmado anteriormente pero en este caso lo vamos a generar nosotros por lo que tenemos que configurarlo con los siguientes datos:

**Nos instalamos antes el OpenSSL para poder generarlo**

![](img/19.png)

Los datos que queramos:

![](img/15.png)

El servicio criptográfico y la longitud de la clave:

![](img/16.png)

Y el lugar donde la vamos a guardar:

![](img/20.png)

![](img/18.png)

Nos vamos a la carpeta donde nos genero la clave y vamos a introducir los siguientes comandos en el orden que su muestra, esto nos generara tres archivos más.

![](img/21.png)

![](img/22.png)

![](img/23.png)

![](img/24.png)

![](img/25.png)

![](img/26.png)

Ahora solo tenemos que ir a completar la generación del certificado con el último documento que hemos generado.

![](img/27.png)

Creamos el sitio con el certificado que acabamos de crear y comprobamos (desde el servidor y el cliente) que funciona.

![](img/28.png)

![](img/29.png)

![](img/30.png)

![](img/31.png)

![](img/32.png)

![](img/33.png)

## Carpetas y permisos.

Creamos el sitio web y dentro ponemos una carpeta para cada usuario que queramos que se conecte, y una para todos a la que llamaremos común.

![](img/34.png)

![](img/35.png)

![](img/36.png)

Vamos al servidor IIS y deshabilitamos la autenticación anónima y habilitamos la básica.

![](img/37.png)

Creamos los usuarios correspondientes y los metemos en el grupo empleados,

![](img/38.png)

Solo nos queda dejar las carpetas con los permisos que se nos indica.

![](img/39.png)

![](img/43.png)

![](img/40.png)

![](img/41.png)

![](img/42.png)

Vamos a comprobar desde el cliente que las páginas con accesibles y que nos piden nuestros credenciales.

![](img/44.png)

![](img/45.png)

![](img/46.png)

![](img/47.png)

![](img/48.png)

![](img/49.png)

![](img/50.png)

![](img/51.png)
