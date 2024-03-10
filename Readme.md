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