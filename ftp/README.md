# Informe FTP - Zebensui Lorenzo Esquivel

## Windows

### Primer Sitio

1. Lo primero es instalar la función de crear sitios FTP desde el ISS.

![](windows/img/1.png)

2. Nos vamos al ISS y le damos a añadir sitio FTP para empezar a configurarlo.

![](windows/img/2.png)

3. Empezamos con la configuración poniendo el nombre del sitio y la carpeta a la que se accederá desde él.

![](windows/img/3.png)

4. Ponemos la IP y el puerto por la que se accederá al sitio y le decimos que permitimos la conexión sin certificado.

![](windows/img/4.png)

5. Le indicamos la clase de autenticación, lo usuarios que van a poder acceder y los permisos de estos.  

![](windows/img/5.png)

6. Ahora vamos a comprobar si funciona el sitio FTP.

![](windows/img/6.png)

![](windows/img/7.png)

![](windows/img/8.png)

![](windows/img/9.png)

![](windows/img/10.png)

![](windows/img/11.png)

7. Vamos a instalarnos el WinSCP que es un cliente de FTP, para comprobar que funciona desde ahí.

![](windows/img/12.png)

![](windows/img/13.png)

![](windows/img/14.png)

![](windows/img/15.png)

![](windows/img/16.png)

![](windows/img/17.png)

![](windows/img/18.png)

![](windows/img/19.png)

- Las opciones de configuración que tenemos de nuestro sitio FTP, aunque parezcan muchas no son tantas en realidad, son más o menos las mismas que podemos configurar cuando estamos creando el sitio, los usuarios que pueden acceder al sitio, el certificado SSL, el enlace con el DNS,... También tenemos cosas que no podemos cambiar desde otro sitio como la primera en la que podemos decidir que usuarios pueden o no acceder al sitio o la opción de configurar el firewall.

![](windows/img/43.png)

### Segundo Sitio

8. Vamos a por el segundo sitio que se hace igual que el primero solo que le vamos a añadir un certificado SSL.

![](windows/img/20.png)

![](windows/img/21.png)

9. Nos vamos a los usuarios del sistema para ver el grupo al que pertenecen todos los del dominio y lo agregamos.

![](windows/img/22.png)

![](windows/img/23.png)

10. Y volvemos a comprobar.

![](windows/img/24.png)

![](windows/img/25.png)

![](windows/img/28.png)

![](windows/img/29.png)

![](windows/img/30.png)

![](windows/img/31.png)

### Tercer Sitio

11. Vamos con el último que es se hace igual que los demás pero en este caso vamos a dejar que se conecten los usuarios anónimos.

![](windows/img/32.png)

![](windows/img/4.png)

**IMPORTANTE** Aunque en la captura ponga todos los Usuarios (y debería funcionar así) lo suyo es darle a Usuarios Anónimos, para que no de problemas

![](windows/img/35.png)

12. Tenemos que irnos a la carpeta que hemos puesto como directorio raíz del sitio y añadir al grupo IUSR con permisos de lectura.

![](windows/img/37.png)

13. Añadimos la IP al registro DNS con el nombre por el que queramos acceder a ella.

![](windows/img/33.png)

14. Solo nos queda comprobar

![](windows/img/40.png)

![](windows/img/38.png)

![](windows/img/39.png)

15. Para conectarte a dos sitios FTP a la vez lo único que tenemos que hacer es poner cada sitio en un puerto diferente.

![](windows/img/41.png)

![](windows/img/42.png)
