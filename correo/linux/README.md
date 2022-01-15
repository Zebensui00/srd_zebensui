# Servicio de Correo en Linux - Zebensui Lorenzo Esquivel

Vamos a configurar un servicio de correo en nuestra máquina Ubuntu 20.

## SMTP

Lo primero que hacemos es instalar el servidor Postfix que nos distribuirá el servicio SMTP.
Cuando lo estemos instalando seleccionamos "Internet Site" y le ponemos el nombre de dominio que queramos.

![](img/1.png)

![](img/2.png)

![](img/3.png)

Comprobamos que esta en funcionamiento y con sus respectivos puertos funcionando.

![](img/4.png)

![](img/5.png)

Vamos a realizar una prueba de envío entre dos usuarios del sistema mediante telnet. Luego vamos a la carpeta /var/spool/mail/zebensui y comprobamos que se a enviado y recibido correctamente.

![](img/11.png)

Ahora nos vamos al cliente e instalamos el Evolution

![](img/15.png)

Lo configuramos de la siguiente manera

1. Ponemos el nombre de nuestro usuario, que es el nombre normal del usuario con el dominio que configuramos a la hora de instalarnos el Postfix 

![](img/16.png)

2. Lo dejamos sin nada.

![](img/17.png)

3. Le especificamos la IP del servidor, el puerto y no le ponemos método de cifrado.

![](img/21.png)

4. Nos queda tal que así:

![](img/25.png)

5. Tenemos que hacer lo mismo con todas las cuentas con la que queramos hacer envíos.

![](img/24.png)

Vamos a hacer la prueba de envío.

![](img/20.png)

![](img/23.png)

## IMAP

Nos instalamos el IMAP con el comando:

```
sudo apt install dovecot-imapd
```
Y comprobamos los puertos

![](img/14.png)

Para usar el IMAP nos vamos a descargar el SquirrelMail que en la última versión de Ubuntu lo tenemos que hacer que pillar de una página web, descomprimirlo y darle permisos porque ya no esta en los repositorios. Lo hacemos con estos comandos:

```
wget https://sourceforge.net/projects/squirrelmail/files/stable/1.4.22/squirrelmail-webmail-1.4.22.zip

unzip squirrelmail-webmail-1.4.22.zip

sudo mv squirrelmail-webmail-1.4.22 /var/www/html/

sudo chown -R www-data:www-data /var/www/html/squirrelmail-webmail-1.4.22/

sudo chmod 755 -R /var/www/html/squirrelmail-webmail-1.4.22/

sudo mv /var/www/html/squirrelmail-webmail-1.4.22/ /var/www/html/squirrelmail
```

Para configurarlo ponemos el siguiente comando que nos abrirá los ajustes

```
sudo perl /var/www/html/squirrelmail/config/conf.pl
```

![](img/27.png)


Una vez dentro lo primero que hacemos es cambiar el nombre del dominio. Pulsamos el 2, luego el 1 y añadimos el dominio que pusimos al principio en Postfix

![](img/28.png)

Ahora nos volvemos al menú de antes, pulsamos el 4 y tenemos que cambiar las dos primeras rutas que nos pone y la opción 11 de false a true.

![](img/33.png)

Con esto es suficiente. Nos vamos al navegador ponemos localhost/squirrelmail y deberíamos entrar a la pantalla para poner nuestros credenciales.

![](img/31.png)

Nos vamos al cliente, añadimos la dirección del servidor al archivo /etc/hosts con el nombre con el que queramos entrar y nos debería de volver a salir la pantalla para meter los credenciales.

![](img/35.png)

Ahora vamos a hacer la prueba de envío.

![](img/37.png)

![](img/38.png)

![](img/39.png)

![](img/40.png)

![](img/41.png)

## POP3

Nos instalamos el POP3 con el comando:

```
sudo apt install dovecot-pop3d
```
Y comprobamos los puertos y el servicio

![](img/42.png)

![](img/43.png)

Ahora nos tenemos que ir otra vez al Evolution y configurarlo igual que antes pero añadiendo el POP3 de la siguiente forma:

![](img/44.png)

![](img/45.png)

![](img/46.png)

![](img/47.png)

Por último hacemos una prueba de envío, y debería borrarse el mensaje el problema es que en las últimas versiones del POP3 eso ha cambiado y el mensaje no desaparece por lo que se nos queda igual que antes pero por lo menos sabemos que si envía todo correctamente.

![](img/48.png)

![](img/49.png)