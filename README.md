# BookReaderApp
Android Application to reader books from external server.

Android application to show a list of books brought from a server, the web service is consumed and a list is created in a recylerview, if the processing of the answer is correct the list is shown.

The response of the service is as follows:

```
{  
   "estado":1,
   "libros":[  
      {  
         "id_libro":"3",
         "categoria_id_categoria":"0",
         "nombre":"Osmar Test",
         "descripcion":"Osmar Test",
         "tamanio":"497419",
         "tipo":"application\/pdf",
         "nombre_archivo":"boardingpass.pdf",
         "categoria":"Arte"
      },
      {  
         "id_libro":"5",
         "categoria_id_categoria":"0",
         "nombre":"test",
         "descripcion":"test",
         "tamanio":"197801",
         "tipo":"application\/pdf",
         "nombre_archivo":"osmar test.pdf",
         "categoria":"Computacion"
      }
   ]
}
```
If the value of "state" is 1, the answer is correct, otherwise an error has occurred.
It has been tested on a local server, but it works with any external server.

In the project, it will be enough to replace the URL in the following fragment in YOU_SERVER_URL value:

```java
final RequestQueue requestQueue = Volley.newRequestQueue(this);
final String url ="http://YOU_SERVER_URL/movil/web/get_books.php";
JsonObjectRequest req = new JsonObjectRequest(url, null,
```
In the project are attached the configuration files made in PHP, located in the mobile.zip file, in one a singleton model is attached to connect to the database and the Book class (data) and in the other folder (web) the files are found to send the answer by GET.

You will only modify the values corresponding to your database in mysql_login.php file:

```
phpdefine("HOSTNAME", "localhost");// Nombre del host
define("PORT", "3306");// Número del puerto [ Opcional ]
define("DATABASE", "biblioteca"); // Nombre de la base de datos
define("USERNAME", "root"); // Nombre del usuario
define("PASSWORD", ""); // Constraseña

```
