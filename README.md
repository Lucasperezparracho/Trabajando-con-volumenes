# Tarea trabajando con volumenes

1. **Descargar la imagen**

2. **Creamos el contenedor**

En este caso montamos un contendor con en nombre 'dam_httpd'.
```
docker run -dit --name dam_httpd
```
3. **Mapea el puerto**

```
-p 8000:80
```
De esta forma podemos podremos conctarnos a el contenedor con la ip de nuestro equipo

4. **Utiliza bind mount**

El siguiente comando se utiliza para montar un cirectorio de tu equipo en un contenedor de httpd.
```
-v "$PWD"/htdocs:/usr/local/apache2/htdocs/
```
5. **Realiza un html**

Para puder visualizar el Hola Mundo en el navegador con lanzar correctamente los comandos anteriores:
```
docker run -dit --name dam_httpd -p 8000:80 -v "$PWD":/usr/local/apache2/htdocs/ httpd:2.4
```
Deberia de valer siempre y cuando tengas un html que se encuente en la carpeta a la que estas accediendo.

6. **Crea otro contenedor con el mismo volumen**

```
docker run -dit --name dam_web2 -p 9080:80 -v "$PWD":/usr/local/apache2/htdocs/ httpd:2.4
```
## Por ultimo
Lo ultimo que realize despues de lanzar mis comandos fue comprobar que el ambos rapositores funcionaban.

Para ello abrí los siguentes enlaces en el navegador:

- [dam_httpd](http://10.0.9.5:8000/)

- [dam_web2](http://10.0.9.5:9080/)
    
Y compruebo que funciona.

Y finalmente cambie el html y recarge las paginas para ver si se actualizaba.
