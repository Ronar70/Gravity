# Gravity
Proyecto SQL JAVA
## sección bbdd
![diagrama de base datos](imagen.png)



## Script Base de datos
La base de datos contiene una lista de 1127 titulos de libros y mas de 920 autores de diferentes paises, escritos en diferentes idiomas  y años. Puedes ver el script en este documento [Script Gravity Books](Script Gravity Books.txt)

Tenemos algunos ejemplos de consultas.


##### 1 Listado de Libros con su autor
```
SELECT
	book.book_id,
	book.title,
	author.author_name,
	publisher.publisher_name,
	book.publication_date,
	book.isbn13
FROM book
	JOIN book_author ON book.book_id = book_author.book_id
	JOIN author ON author.author_id = book_author.author_id
	JOIN publisher ON publisher.publisher_id = book.publisher_id
where author.author_name = 'Larry Burkett';
```
 
##### 2 Cantidad de libros por autor

```
SELECT 
count(*)
from book b, book_author ba, author a
where b.book_id = ba.book_id and
      ba.author_id = a.author_id;
```
##### 3 Busqueda de libros por ISBN

```
SELECT 
book.book_id,
book.title, 
author.author_name, 
publisher.publisher_name,
book.publication_date, 
book.isbn13 
FROM book 
JOIN book_author ON book.book_id = book_author.book_id 
JOIN author ON author.author_id = book_author.author_id 
JOIN publisher ON publisher.publisher_id = book.publisher_id 
where book.isbn13 = '8987059752';      
```
           
##### 4  Estado del proyecto
El proyecto aun esta en proceso **actualmente** únicamente están implementadas las siguientes acciones:

Se crean opciones de crear, editar, borrar o listar autores.
* Crear, editar, borrar o listar libros.
* Crear, editar, borrar o listar autores.
* Crear ediciones a partir de un curso existente, pudiendo agregar hasta cinco aulas previamente creadas.
* Editar, borrar o listar libros, autores, idiomas y casas editoriales.

      