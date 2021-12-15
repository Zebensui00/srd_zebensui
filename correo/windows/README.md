# Informe Correo Windows - Zebensui Lorenzo Esquivel


1. Vamos a instalar y configurar el servicio de correo electrónico en nuestro servidor de Windows.

Para ello lo primero que tenemos que hacer es instalar la característica SMTP desde los roles del servidor.



![](img/1.png)



2. Una vez instalado vamos a Herramientas y seleccionamosAdministrador de aplicaciones (IIS) 6.0.

Cuando estemos dentro vamos a configurar el servidor de correo a través de las propiedades.



![](img/2.png)



3. En la primera ventana que nos sale nada más darle a propiedades vamos a establecer como IP todas las asignadas (aunque ponga que no son todas realmente si lo son porque esta mal) limitamos el número de conexiones a 50 y habilitamos el registro en formato W3c, diario y en una carpeta en concreto.



![](img/3.png)



![](img/4.png)



4. Nos vamos a la pestaña de acceso y le establecemos una inventada, pero dentro de la red, en la parte de conexiones y restricciones de retransmisión



![](img/5.png)



![](img/6.png)



![](img/7.png)



![](img/8.png)



![](img/9.png)



5. También activamos la autenticación anónima.



![](img/10.png)



6. Le damos a aceptar y comprobamos que se ha creado el dominio correctamente.



![](img/11.png)



7. Ahora creamos un alias que apunte a ese dominio que sera el nombre del servicio de correo. Osea lo que va detrás del @.



![](img/12.png)



![](img/13.png)



![](img/14.png)



8. Comprobamos la carpeta C:\Inetpub\mailroot.



![](img/15.png)



9. Ahora nos vamos al DNS, creamos el registro de tipo Correo y comprobamos que funciona.



![](img/16.png)



![](img/17.png)



![](img/18.png)



10. Para seguir con las comprobaciones nos tenemos que ir al cliente descargar e instalar Pegasus Mail.



![](img/19.png)



![](img/20.png)



![](img/21.png)



11. Para configurarlo tenemos que poner el nombre de nuestra cuenta de correo, en nuestro caso es el nombre de un usuario que tengamos creado en el dominio del servidor.



![](img/22.png)



12. Esta parte nos la saltamos porque no tenemos nada de POP3 instalado.



![](img/23.png)



13. Ponemos la IP del servidor.



![](img/24.png)



14. Lo dejamos como esta.



![](img/25.png)



15. Ahora nos queda hacer todas las comprobaciones de envió de correos.



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
