# Informe ISS tercera parte - Zebensui Lorenzo Esquivel.

En esta ocasión vamos a montar un servicio de hosting dentro de nuestra página tal y como lo haríamos si contratáramos un servicio de host por internet para dar de alta nuestra página.

Para ello necesitamos PHP, MySQL, phpMyADmin, C++ y tenemos que tener mucho cuidado con las versión ya que dan problemas de compativilidad.

| Programa | Versión     |
| :------------- | :------------- |
| PHP       | 5.3.9       |
| MySQL     | 5.5.60      |
| phpMyAdmin     | 4.4.15       |

1. Vamos a instalar en primer lugar el PHP.

![](img/1.png)

![](img/2.png)

Marcamos la primera opción.

![](img/3.png)

![](img/4.png)

Comprobamos que se instalo correctamente en nuestro sitio web después de haber añadido el index.php a nuestra web.

![](img/5.png)

2. Ahora vamos con instalación del MySQL

**IMPORTANTE: LAS SIGUIENTES CAPTURAS SON DE LA VERSIÓN 5.5.30 Y NO DE LA 5.5.60 QUE NO ES LA VERSIÓN QUE NOS TENEMOS QUE INSTALAR PERO SON LAS PRIMERAS QUE HICE Y REALMENTE PARA TODAS LAS VERSIONES TENEMOS QUE SEGUIR LOS MISMOS PASOS**

![](img/26.png)

![](img/7.png)

![](img/8.png)

![](img/9.png)

3. Instalamos el C++ entre medio de la instalación de MySQL y luego seguimos con ella.

![](img/10.png)

![](img/11.png)

![](img/12.png)

![](img/13.png)

![](img/14.png)

![](img/15.png)

![](img/16.png)

![](img/17.png)

![](img/18.png)

![](img/19.png)

![](img/20.png)

![](img/21.png)

4. Intentamos instalar .NET Framework 4 aunque lo más probable es que nos diga que ya esta instalado.

![](img/22.png)

5. Ahora hacemos lo de siempre y vamos a crear el sitio web que tendrá alojado el phpMyAdmin.

![](img/23.png)

![](img/24.png)

6. Ahora tenemos que descargarnos el phpMyAdmin y descomprimir todo el contenido de su carpeta dentro del sitio que acabamos de crear, y si todo funciona correctamente y las versiones son compatibles nos debería quedar tal que así.

![](img/28.png)

7. En el servidor ya solo nos queda instalar el Filezilla Server.

![](img/29.png)

![](img/30.png)

![](img/31.png)

![](img/32.png)

![](img/33.png)

![](img/34.png)

![](img/35.png)

8. Una vez instalado nos queda crear el usuario para luego conectarnos desde el cliente y crear el alias en el DNS.

![](img/36.png)

![](img/47.png)

![](img/38.png)

9. Ahora nos vamos al cliente y comprobamos que nos conecta con el sitio phpMyAdmin.

![](img/39.png)

10. Nos instalamos el cliente de Filezilla.

![](img/41.png)

![](img/42.png)

![](img/43.png)

![](img/44.png)

![](img/45.png)

![](img/46.png)

11. Comprobamos al conectividad entre cliente servidor con Filezilla.

![](img/48.png)

![](img/49.png)

12. Nos instalamos drupal en el cliente y lo pasamos a la carpeta del sitio www.miempresa.com del servidor.

![](img/40.png)

![](img/50.png)

![](img/51.png)

13. Creamos la base de datos y el usuario de la misma desde el phpMyAdmin.

![](img/53.png)

![](img/54.png)

![](img/55.png)

14. Nos vamos a la carpeta default dentro de sites de nuestro sitio web y clonamos el archivo que esta dentro cambiandole el nombre a settings

![](img/56.png)

![](img/57.png)

15. Vamos a nuestro sitio web y ahora si podemos seguir con la instalación del Drupal.

![](img/52.png)

![](img/58.png)

![](img/59.png)

![](img/60.png)

![](img/61.png)

![](img/62.png)

![](img/63.png)

16. Lo último que tenemos que hacer es personalizar nuestro sitio con Drupal.
Para ellos vamos a hacer varias cosas, la primera es cambiar el idioma a Español.
Para ello tenemos que instalar el modulo Locale, seleccionar el idioma Español por defecto, descargarnos el paquete de Español e importarlo.

![](img/64.png)

![](img/65.png)

![](img/66.png)

![](img/67.png)

![](img/68.png)

17. Nos instalamos el modulo para tener todos los idiomas disponibles.

![](img/69.png)

18. Instalamos varios temas y cambiamos el que tenemos.

![](img/70.png)

19. Ya solo nos queda crear el contenido de las páginas y ponerles un menú.

![](img/71.png)

![](img/72.png)

![](img/73.png)

![](img/74.png)
