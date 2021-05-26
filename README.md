# 3APIS-POSTGRE


-----------Laravel-----------------

1.Debes tener npm por lo cual usa el siguinete comando:

-npm install

2.Depués debes configurar el archivo .env con tus datos en este caso estamos usando postgre asi que debes tener abierto para que se pueda conectar a la api.

DB_CONNECTION=pgsql
DB_HOST=127.0.0.1
DB_PORT=5433
DB_DATABASE=flask
DB_USERNAME=postgres
DB_PASSWORD=1234

una vez teniendo esto lo guardamos.


-----------Adonis-----------------

1.Debes tener npm por lo cual usa el siguinete comando:

-npm install

2. Hay que istalar el driver de postgresql con el siguiente comando:

-npm i pg

verifica que tienes a postgresql corriendo en tu maquina.

3.Ahora te vas al archivo database.js

  connection: Env.get('DB_CONNECTION', 'sqlite')
   
  te aseguras que este por "sqlite" la conexión principal.
  
 4. Abres tu archivo .env y cambias por tus datos:
 
HOST=127.0.0.1
PORT=3333
NODE_ENV=development
APP_URL=http://${HOST}:${PORT}
CACHE_VIEWS=false
APP_KEY=79RQJhv0bhB7DysNJMbzFM53NvX6Tqrx
DB_CONNECTION=pg
DB_HOST=127.0.0.1
DB_PORT=5433
DB_USER=postgres
DB_PASSWORD=1234
DB_DATABASE=flask
SESSION_DRIVER=cookie
HASH_DRIVER=bcrypt

una vez teniendo esto lo guardamos.


-----------Flask-----------------

1.Tenemos que tener instalado lo siguiente para ello usa los siguinetes comandos:
-pip install psycopg2
-pip install pygresql

2. En el archivo bd.py tenemos que cambair por tus datos:

credenciales = {
        "dbname": "flask",
        "user": "postgres",
        "password": "1234",
        "host": "localhost",
        "port": 5433
    }
    
verifica que tienes a postgresql corriendo en tu maquina.

Guardamos cambios.

-----------Correr las Migraciones-----------------

Recuerda que las 3 APIS deben estar apuntando a una misma bd asi que en las configuraciones pasadas de bd debiste apuntar a la misma base de datos.

Ahora puedes correr las migaciones ya sea con laravel o adonis para crear las tablas necesarias 
en este caso la tabla se llama mascotas la cual ingresas el nombre y la edad de la mascota.

Recuerda que con que solo corras la migracion ya sea adonis o laravel es suficiente.

Para correr la migracion con laravel:

-php artisan migrate 

Para correr la migracion con Adonis:

-adonis migration:run

-----------Correr las APIS-----------------

Una vez que ya esten las migaciones es hora de correr las apis con los siguientes comandos:

--Laravel

-php artisan serve

--Adonis

-adonis serve --dev


--Flask

-export FLASK_APP=app.py

-export FLASK_ENV=development

-flask run


-----------Consumir APIS-----------------

Recuerda que pide 2 valores 

"nombre":"Hola desde Python",
	"edad":"20"
  
Puedes consumir las apis con insomia,postman etc.

---Laravel

Ruta para consumir:

http://127.0.0.1:8000/reg (Por post)

{
	"nombre":"Hola desde Laravel",
	"edad":"45"
}

---Adonis

Ruta para consumir:

http://127.0.0.1:3333/registro (Por post)

{
	"nombre":"Hola desde Adonis",
	"edad":"123"
}

---Flask

Ruta para consumir:

http://127.0.0.1:5000/insertarmascotas (Por post)

{
	"nombre":"Hola desde Python",
	"edad":"20"
	
}


Y eso seria todo. 👍🏻👍🏻👍🏻👍🏻



