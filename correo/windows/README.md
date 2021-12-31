# Informe Correo Windows - Zebensui Lorenzo Esquivel

# SMTP (IIS 6.6)

Vamos a instalar y configurar el servicio de correo electrónico en nuestro servidor de Windows.

Para ello lo primero que tenemos que hacer es instalar la característica SMTP desde los roles del servidor.



![](img/1.png)



Una vez instalado vamos a Herramientas y seleccionamosAdministrador de aplicaciones (IIS) 6.0.

Cuando estemos dentro vamos a configurar el servidor de correo a través de las propiedades.



![](img/2.png)



En la primera ventana que nos sale nada más darle a propiedades vamos a establecer como IP todas las asignadas (aunque ponga que no son todas realmente si lo son porque esta mal) limitamos el número de conexiones a 50 y habilitamos el registro en formato W3c, diario y en una carpeta en concreto.



![](img/3.png)



![](img/4.png)


Nos vamos a la pestaña de acceso y le establecemos una inventada, pero dentro de la red, en la parte de conexiones y restricciones de retransmisión



![](img/5.png)



![](img/6.png)



![](img/7.png)



![](img/8.png)



![](img/9.png)



También activamos la autenticación anónima.



![](img/10.png)



Le damos a aceptar y comprobamos que se ha creado el dominio correctamente.



![](img/11.png)



Ahora creamos un alias que apunte a ese dominio que sera el nombre del servicio de correo. Osea lo que va detrás del @.



![](img/12.png)



![](img/13.png)



![](img/14.png)



Comprobamos la carpeta C:\Inetpub\mailroot.



![](img/15.png)



Ahora nos vamos al DNS, creamos el registro de tipo Correo y comprobamos que funciona.



![](img/16.png)



![](img/17.png)



![](img/18.png)



Para seguir con las comprobaciones nos tenemos que ir al cliente descargar e instalar Pegasus Mail.



![](img/19.png)



![](img/20.png)



![](img/21.png)



Para configurarlo tenemos que poner el nombre de nuestra cuenta de correo, en nuestro caso es el nombre de un usuario que tengamos creado en el dominio del servidor.



![](img/22.png)



Esta parte nos la saltamos porque no tenemos nada de POP3 instalado.



![](img/23.png)



Ponemos la IP del servidor.



![](img/24.png)



Lo dejamos como esta.



![](img/25.png)



Ahora nos queda hacer todas las comprobaciones de envió de correos.



- La primera es hacia un usuario que existe en el AD


![](img/26.png)



![](img/27.png)



- La segunda a un usuario que está en el sistema pero no en el AD



![](img/32.png)



![](img/33.png)



- La tercera a un usuario que no existe.



![](img/28.png)



![](img/29.png)



- La última a mi cuenta de correo personal.



![](img/30.png)



![](img/31.png)

Ahora vamos a establecer la autenticación básica de Windows desde el IIS 6.6


![](img/34.png)



![](img/35.png)



Lo que tenemos que hacer en el Pegasus desde el cliente es lo que se ve a continuación, activar el logearte con SMTP, poner el usuario y la contraseña y activar el STARTTLS.



![](img/37.png)



Con esto se supone que debería funcionar pero en mi caso me salio este error y no supe como solucionarlo la verdad porque le pregunte a mis compañeros que le funcionaba y lo tenían como yo.



![](img/36.png)



# hMailServer



Ahora vamos a empezar a configurar el hMailServer para esto tenemos que desinstalar primero el SMTP.



![](img/38.png)



![](img/39.png)



Una vez descargado empezamos con la instalación.



![](img/40.png)



Le especificamos la ruta



![](img/41.png)



Le decimos que queremos la instalacióncompleta



![](img/42.png)



Queremos que use su base de datos



![](img/43.png)



Ponemos la contraseña



![](img/44.png)



Nos dira que tenemos que instalar una dependencia para que funcione el programa, que es Microsoft.NET Framework. Lo puedes descargar con el programa que lo hace de forma automática o la descargar tu de forma manual antes de instalar el hMailServer.



![](img/45.png)



![](img/46.png)



![](img/47.png)



Ahora lo abrimos, seleccionamos el usuario y entramos con la contraseña que pusimos antes.



![](img/48.png)



![](img/49.png)



Lo primero que tenemos que hacer es crear los dominios, para ello nos vamos a Domains y le damos a Add



![](img/50.png)



![](img/51.png)



![](img/52.png)



Le especificamos la carpeta en la que se guardaran todos los backups y seleccionamos que guarde los mensajes.



![](img/53.png)



Ahora nos vamos al dominio, le damos en Accounts y Add para crear los usuarios.



![](img/54.png)



El primero, que es ficticio1, tendrá un máximo de 2GB en el servidor para almacenar sus correos.



![](img/55.png)



Al segundo, que es ficticio2, le ponemos el nombre y apellidos



![](img/56.png)



Al tercero, que es ficticio3, le configuramos la auto respuesta.



![](img/57.png)



Y al ultimo, que es ficticio4, le decimos que reenvíe todos los correos al primer usuario.



![](img/58.png)



Ahora nos vamos al DNS y creamos las entradas correspondientes.



![](img/59.png)

Vamos a configurar el servidor un poco a nuestro gusto.


Creamos un rango de IPs, es decir solo los ordenadores que se encuentren en este rango podrán usar el servidor.



![](img/63.png)



![](img/64.png)



Le especificamos que mande una copia de todos los correos enviados a mi correo personal.



![](img/65.png)



Le cambiamos el puerto al IMAP



![](img/66.png)



Vamos a poner mensajes de bienvenida en los tres protocolos.



![](img/60.png)



![](img/61.png)



![](img/62.png)



Para comprobarlos necesitamos descargar el telnet.



![](img/69.png)



Ahora nos vamos a la consola de comandos y escribimos telnet localhost y el puerto al que nos queremos conectar.



![](img/71.png)



![](img/72.png)



![](img/74.png)



![](img/75.png)



Por último vamos a desactivar el Auto-Ban por si nos equivocamos a la hora de entrar con el usuario que no nos bloquee la cuenta.



![](img/73.png)



Nos descargamos el cliente Thunderbird y le especificamos lo siguiente:



![](img/76.png)



Nos dara un aviso, le damos que lo si



![](img/77.png)



Y ya lo tenemos, solo tenemos que hacer esto con todos los usuarios.



![](img/80.png)



Ahora vamos a empezar a comprobar el envió y recepción de correos.



- De ficitico1 a ficticio2



![](img/81.png)



![](img/82.png)



Vemos que si se manda la copia a mi correo tal y como le dijimos.



![](img/83.png)



- De ficitico1 a ficticio3



![](img/84.png)



Vamos que si se envía la auto respuesta de ficticio3 tal y como la configuramos.



![](img/85.png)



![](img/86.png)



- De ficitico1 a ficticio4



Vemos que automáticamente el correo que enviamos a ficticio4 se nos envía a ficticio1 tal y como le especificamos.



![](img/88.png)



![](img/89.png)

Lo último que nos queda es crear una lista de distribución, para ello nos tenemos que ir al dominio creado.

![](img/90.png)

Le ponemos nombre, la habilitamos y le decimos que sea publica para que acceda cualquiera.

![](img/91.png)

Le añadimos los mienbros de miempresa.com

![](img/92.png)

El problema viene que te deja entrar con la cuenta de empleados pero te pide contraseña cuando no la tiene

![](img/94.png)

Aunque te deja enviar correos pero no llegan a ninguna parte.

![](img/93.png)

![](img/95.png)
