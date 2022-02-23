# Servicio VoIP en Linux - Robert y Zebensui

Lo primero que tenemos que hacer es descargarnos la ISO de FreePBX e instalarlo.

Seguimos los pasos de la instalación con normalidad.

![](img-2/1.png)

![](img-2/2.png)

![](img-2/3.png)

Establecemos una contraseña para la cuenta de Root

![](img-2/4.png)

Con esto ya lo tenemos instalado.

![](img-2/5.png)

Lo siguiente es poner esta máquina en red interna con el cliente para que se comuniquen entre ellas. Luego nos vamos al navegador del cliente y ponemos la IP del FreePBX.

![](img-2/6.png)

Una vez configuramos los datos necesarios, tenemos que darle a siguiente.

![](img-2/7.png)

Ahora le damos a Administración para poder llegar hasta el panel de control. 

- En este proceso le damos a siguiente siempre, no debería dar problemas.

![](img-2/8.png)

![](img-2/9.png)

![](img-2/10.png)

![](img-2/11.png)

Con todo este llegaremos al panel de control por fin.

![](img-2/12.png)

Para agregar los usuarios nos tenemos que ir a Applications > Add Extension > + Add New SIP [chan_pjsip] Extension

![](img-2/13.png)

Una vez dentro solo tenemos que configurarlo tal y como se ve a continuación:

![](img-2/14.png)

![](img-2/15.png)

![](img-2/20.png)

Una vez hemos creado los usuarios tenemos que descargarnos ZoiPer para ver si funciona todo correctamente.

Una vez instalado entramos con unos de los usuarios que hemos creado.

![](img-2/16.png)

Le ponemos la dirección del servidor.

![](img-2/17.png)

Comprobamos que funciona.

![](img-2/18.png)

Con esto ya estamos dentro con uno de los usuarios listo para llamar y recibir llamadas.

![](img-2/19.png)

Ahora lo que tendríamos que hacer es descargar ZoiPer en el móvil, entrar con el otro usuario y establecer una llamada. 
El problema es que no conseguimos que el móvil este en la misma red que las máquinas virtuales, por mucho que ponemos estas en adaptador puente y le damos una IP de la red a la que esta conectado por WIFI el móvil, por ende es imposible que este se conecte con el cliente mediante una llamada. 

