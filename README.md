# Flask-SQLAlchemy-Basics
Completar el curso de Flask SQLAlquemy
![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/4008511104f6ace2111ea563ea6635ab798ab644/flask/captura%201.jpg)

## Paso 1:
Debemos crear una carpeta especifica y una vez creada,abriremos un terminal en Visual Studio Code.

1.Primero crearemos un entorno vrtual adecuado con el siguiente comando:
  - python3 -m venv env
  
![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/4008511104f6ace2111ea563ea6635ab798ab644/flask/captura4.jpg)

2.Una vez creado el entorno procedemos a su activación para poder instalar las herramientas necesarias para realización del mismo. Para ello ejecutamos el comando 
- env\Scripts\activate.ps1.(Este comando es para ejecutarlo en Windows)

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/73d7bcdb6685c0dd75c44460b6e3a2696569da90/flask/captura5.jpg)

Debemos instalar Flask SQLAlquemy con el siguiente comando:
  - pip install flask flask-sqlalquemy

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/fb64f6a53df01e02fa06b7dc4f3ca504a482004a/flask/captura6.jpg)

## Paso 2:
Creamos un archivo Python y procedemos a configurar nuestra base de datos:
  - Primero importamos lo que vamos a necesitar
  - Creamos una instancia que por defecto se llama app
  - Por último, establecemos una relación entre nuestra app de Flask y nuestra base de datos
  
![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/40e95dd26aac03f8ed750ed64d506fa8517972b5/flask/capt.jpg)

## Paso 3:
Creamos nuestras tablas (Models).

 1.Tabla Customer.
 
![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/58087ebd2e939c4224d92a7fd8e11bc7a96a107b/flask/capt%201.jpg)

2.Tabla Order.

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/58087ebd2e939c4224d92a7fd8e11bc7a96a107b/flask/capt%202.jpg)

3.Tabla Product.

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/58087ebd2e939c4224d92a7fd8e11bc7a96a107b/flask/capt%203.jpg)


Como podemos observar:

Creamos las columnas de nuestras tablas y establecemos el tipo de datos de cada una de ellas.
Establecemos como primary_key la columna id en las 3 tablas.
En caso de la tabla Order, la columna order_date recibirá por defecto la hora en ese momento.
Las columnas que no pueden recibir un valor nulo, contienen dentro de su declaración la palabra reservada nullable con valor False.
Las columnas, que son únicas, contienen dentro de su declaración la palabra reservada unique con valor True

## Paso 4

Establecemos la relación entre nuestras tablas.

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/58087ebd2e939c4224d92a7fd8e11bc7a96a107b/flask/capt%204.jpg)
![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/58087ebd2e939c4224d92a7fd8e11bc7a96a107b/flask/capt%205.jpg)

Quedando nuestro código de la siguiente manera.

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/af5205a0834dea20fa4252b6ce4a5d7c31a0bb8b/flask/fianl.jpg)

## Paso 5
Creación del archivo que contiene nuestra base de datos. Comprobamos su correcto funcionamiento.

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/c9271aa59ad91466ec84e05b2479c9b65c397e8d/flask/captura%209.1.jpg)
 Los pasos que hemos realiazado:

1. Accedemos a la consola Flask haciendo uso del comando flask shell.
2. Importamos de nuestra aplicación flask "app" db para poder generar nuestra base de datos.
3. Generamos nuestra base de datos haciendo uso del comando db.create_all().

 Ahora nos situamos en la carpeta que contiene la base de datos.
 
![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/c09bc0f9e42452ffe12f65739b302501ccfb6db9/flask/captura9.4.jpg)

Una vez dentro podemos comprobar su funcionamiento con el comando:

- sqlite3 db.sqlite4

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/c09bc0f9e42452ffe12f65739b302501ccfb6db9/flask/captura9.5.jpg)


Debemos comprobar que se cumplen los siguiente pasos para que todo este correcto

- Debemos verificar que tenemos instalada la herramienta sqlite3.
- Ejecutamos el comando sqlite3 nombre_del_archivo_db.
- Verificamos las tablas creadas con el comando .tables.
- Verificamos el esquema de cada una de nuestras tablas con el comando .schema.
- De esa forma comprobamos que todo está en orden y podemos continuar.


## Paso 6
Agregar información a nuestra base de datos.

Pasos a seguir:

1. Accedemos a nuestra consola Flask con el comando - flask shell.
2. Importamos de nuestra app flask "app": db, Product, Order, Customer.
3. Para crear un registro primero creamos una variable y una instancia de la clase (model), en este caso queremos agregar un producto llamado computer .
4. Añadimos a nuestra base de datos el c¡producto haciendo uso del comando db.session.add(nombre_de_la_variable).
5. Por último, guardamos los cambios con el comando db.session.commit().

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/a7663ac8f32438ae8eaccd46402248eebb99fce3/flask/captura9.7.jpg)

Haremos lo mismo con la tabla order:

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/1a77fcf2f08048c567a3c1b207aed5a0e2bef9a2/flask/captura9.8.jpg)

Procedemos a comprobar que hemos agregado correctamente nuestro producto.

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/43c9e1c04d6d946570faab0c8046fe53bbd222ea/flask/captura9.9.jpg)

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/47738c99df3a9ff2962a0e0eb15227537f3b217d/flask/captura9.10.jpg)

## Paso 7
Actualizar nuestra base de datos.

Pasos:

- Accedemos a nuestra consola Flask.
- Importamos de nuestra app flask "app": db, Customer.
- Realizamos una query utilizando un filtro filter_by() y decimos por convenio que queremos solo el primer registro utilizando first().
- Comprobamos que es el registro que deseamos actualizar.
- En este caso deseo actualizar la dirección karla.address = "...".
- Una vez actualizado el valor, guardamos los cambios db.session.commit().

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/ece4b2ed05c8a1667ce98465c8717a724fbac961/flask/karla.jpg)

## Paso 8
Borrar datos.

Primero.
Hacemos una query para poder encontrar el registro que deseamos y lo asignamos una variable, en nuestro caso es 'Ashley'.

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/ece4b2ed05c8a1667ce98465c8717a724fbac961/flask/captura9.15jpg.jpg)


Eliminamos el registro haciendo uso del comando:

- db.session.delete(ashley).

Guardamos el proceso.

-  db.session.commit

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/ece4b2ed05c8a1667ce98465c8717a724fbac961/flask/captura9.16.jpg)

## Paso 9


Generar información para nuestra base de datos.
Para ello utilizamos la librería Faker para generar datos falsos. Ya la hemos instalado desde el inicio del tutorial cuando creamos el entorno de trabajo.

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/eb2894056cb37c9c2dfdfa259c4d5c4a96bf7d6a/flask/faker/cap1.jpg)
![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/d1b0b42fc4b43a1e16044747c4587b0d9cd5f13b/flask/faker/fake.jpg)


Creamos un método para generar 100 clientes falsos.

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/5e8a4abf3c186346590ad4249507681854abb054/flask/jack/jack1.jpg)

Creamos un método para generar 1000 pedidos.

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/5e8a4abf3c186346590ad4249507681854abb054/flask/jack/jack2.jpg)

Creamos un método para agregar 10 productos.

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/5e8a4abf3c186346590ad4249507681854abb054/flask/jack/jack3.jpg)

Establecemos la relación entre Order y Product.

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/5e8a4abf3c186346590ad4249507681854abb054/flask/jack/jack4.jpg)

Creamos un método para llamar a las funciones anteriormente creadas y generar la información para nuestra base de datos.

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/5e8a4abf3c186346590ad4249507681854abb054/flask/jack/jack5.jpg)

Borramos la base de datos que creamos al inicio, con el comando:
- rm db.sqlite4

Abrimos nuestra consola Flask e importamos el método para generar información.

Realizamos el comando - Flask shell e importamos la nueva base de datos.

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/5e8a4abf3c186346590ad4249507681854abb054/flask/faker/cap3.jpg)

### Verificamos que la información ha sido correctamente generada.

Para ello accedemos a nuestra base de datos con el comando sqlite3 nombre_de_la_base_de_datos.

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/5e8a4abf3c186346590ad4249507681854abb054/flask/faker/cap4.jpg)

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/eb2894056cb37c9c2dfdfa259c4d5c4a96bf7d6a/flask/faker/cap5.jpg)
![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/eb2894056cb37c9c2dfdfa259c4d5c4a96bf7d6a/flask/faker/cap6.jpg)
![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/eb2894056cb37c9c2dfdfa259c4d5c4a96bf7d6a/flask/faker/cap7.jpg)
![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/eb2894056cb37c9c2dfdfa259c4d5c4a96bf7d6a/flask/faker/cap8.jpg)


Como podemos observar, nuestra base de datos tiene la información deseada.

## Paso 10
Realizando queries a nuestra base de datos.

Pedidos realizados por un cliente.

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/d1b0b42fc4b43a1e16044747c4587b0d9cd5f13b/flask/cape/cap9.1.1.jpg)
![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/d1b0b42fc4b43a1e16044747c4587b0d9cd5f13b/flask/cape/cap9.1.jpg)


Como podemos observar, nuestro método funciona correctamente.

Queremos saber cuantos pedidos hay pendientes.

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/f105e52995475015de9220582a7da08006b9b93a/flask/query/query5.jpg)

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/f105e52995475015de9220582a7da08006b9b93a/flask/1.jpg)

Número de clientes.

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/f105e52995475015de9220582a7da08006b9b93a/flask/query/query6.jpg)

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/f105e52995475015de9220582a7da08006b9b93a/flask/2.jpg)
Vemos que funciona correctamente.


Órdenes con cupón de compra.
Que no sea nulo y no sea el cupón "FREESHIPPING".

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/f105e52995475015de9220582a7da08006b9b93a/flask/query/query7.jpg)
![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/f105e52995475015de9220582a7da08006b9b93a/flask/3.jpg)


Queremos los ingresos en los x días anteriores, por defecto definimos 30.

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/f105e52995475015de9220582a7da08006b9b93a/flask/query/query8.jpg)
![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/f105e52995475015de9220582a7da08006b9b93a/flask/cape/cape1.jpg)
![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/f105e52995475015de9220582a7da08006b9b93a/flask/cape/cape2.jpg)


Vemos que todo funciona correctamente.

Tiempo promedio que se demora un cliente en completar su compra.

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/f105e52995475015de9220582a7da08006b9b93a/flask/query/query9.jpg)
![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/f105e52995475015de9220582a7da08006b9b93a/flask/cape/cape3.jpg)

Vemos que todo funciona correctamente.

Por último queremos saber cuantos clientes han gastado una cantidad superior a x cantidad de dollars.

![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/f105e52995475015de9220582a7da08006b9b93a/flask/query/query10.jpg)
![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/f105e52995475015de9220582a7da08006b9b93a/flask/cape/cape4.jpg)


![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/f105e52995475015de9220582a7da08006b9b93a/flask/cape/cape5.jpg)
![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/f105e52995475015de9220582a7da08006b9b93a/flask/cape/cape6.jpg)

Vemos que todo funciona correctamente e hicimos varias pruebas con diversas cantidades.


# Final del curso 
![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/4f33b799398537d3af915d24b727f7066e231784/flask/fin+.jpg)
![](https://github.com/zazi479/Flask-SQLAlchemy-Basics/blob/f105e52995475015de9220582a7da08006b9b93a/flask/cape/cape7.jpg)

