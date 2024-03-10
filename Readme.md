# ModuloOdoo

## Que es OpenAcademy?
Open Academy es un módulo de Odoo que nos permite gestionar cursos, sesiones, asistentes, etc, este es utilizado en direntes empresas para gestionar diferentes cursos y sesiones.


## Docker compose:

### Odoo:

![CapturaDocker1.png](Imagenes/CapturaDocker1.png)

### Postgres:

![CapturaDocker2.png](Imagenes/CapturaDocker2.png)

En el apartado de postrges tenemos que tener cuidado con los puertos que utilizamos ya que si tenemos otro servicio que este utilizando el puerto 5432 no podremos utilizarlo.

### Para ejecutar el docker-compose.yml utilizamos el siguiente comando:


```bash
docker-compose up -d
```
## Funcionamiento de la base de datos desde nuestro IDE:

Para comprobar que la base de datos esta en correcto funcionamiento podemos desde nuestro IDE en mi caso Pycharm comprobar que la base de datos esta en funcionamiento:
+ Lo primero que tendremos que hacer es entrar en nuestra pestaña de bases de datos de nuestro IDE y crear una base de datos en Postgresql.
![BaseDeDatos.png](Imagenes/BaseDeDatos.png)


+ Una vez creada la base de datos nos aparecera una nueva pestaña emergente en la cual tendremos que rellenar diferentes campos como pueden ser el Usuario, la contraseña, el host, el puerto... en esta ventana una vez introduciomos todos los campos necesarios podemos hacer una comporbacion de la conexion para comprobar que todo esta en correcto funcionamiento.
![BaseDeDatos2.png](Imagenes/BaseDeDato2.png)


+ Una vez creada la base de datos y comprobado que esta en correcto funcionamiento aparecera en la pestaña de bases de datos de nuestro IDE.
![BaseDeDatos3.png](Imagenes/BaseDeDato3.png)

## Comprobacion de que odoo esta en correcto funcionamiento:
Para comprobar que odoo esta en correcto funcionamiento tendremos que introducir en la url de nuestro navegador <localhost:8069> y nos aparecera la ventana de inicio de sesion de odoo.
![InicioSesionOdoo.png](Imagenes/InicioSesionOdoo.png)

### Comprobacion de que la nueva base de datos creada con odoo esta en funcionamiento:
Para comprobar que la base de datos esta en correcto funcionamiento debemos entrar denuevo en la pestaña de bases de datos y devemos refrescar, una vez refrescamos nos daremos cuenta de que a la derecha de la base de datos hay una nueva etiqueta de 1 of 2 lo cual nos indica que la base de datos fue creada con exito y esta en correcto funcionamiento.

![BaseDeDatos4.png](Imagenes/BaseDeDato4.png)

### Instalar Modulo OpenAcademy

Para instalar el modulo de OpenAcademy en Odoo tendremos que seguir los siguientes pasos:
+ Lo primero que tendremos que hacer es crear un nuevo directorio dentro de nuestro proyecto el cual se llame `extra-addons`.
+ Una vez creado el directorio debemos vincular el docker-compose con el volumen `extra-addons:/mnt/extra-addons` para que odoo pueda leer el modulo.
![CapturaDocker3.png](Imagenes/CapturaDocker3.png)
+ Una vez tenemos estos pasos completados debemos utilizar una serie de comandos para poder instalar el modulo en odoo:
```bash
docker exec -u root -it nombre_contenedor_odoo-web-1 /bin/bash
```
+ Una vez dentro del contenedor de odoo debemos entrar en la carpeta de addons con el siguiente comando:
```bash
cd /mnt/extra-addons
```
+ En el siguiente paso crearemos un modulo utilizando el siguiente comando:
```bash
odoo scaffold openacademy
```
+ En el momento que creemos el modulo utilizando el comando aneterior utilizaremos el siguiente comando para cambiar los permisos de la carpeta del modulo:
```bash
chown -R 777 openacademy
```
+ Una vez cambiados los permidos de la carpeta utilizaremos el comando `exit` para salir del contenedor de odoo y lo reiniciaremos con el comando:
```bash
docker restart moduloodoo-web-1 
```
+ Cuando acabemos de utilizar todos los comandos la estructura de nuestro proyecto deberia quedar de la siguiente manera:

![EstructuraProyecto.png](Imagenes/EstructuraProyecto.png)

## Configuracion del modulo OpenAcademy
Una vez creamos el modulo de openacademy nos dirigiremos a la carpeta models y debemos modificar el archivo `models.py` dentro del archivo debemos modificar la clase TestModel

![Models.png](Imagenes/Models.png)

