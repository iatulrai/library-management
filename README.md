# library-management
Technologies Used:

1. Java 11
2. Spring Boot 2.x
3. H2 Database
4. Maven Build Tool
5. Swagger API Documentation
6. Windows machine


Steps to execute the application:

1. Download the library-managment.zip file, extract it and open in your fav IDE.
2. Bulild the application using command: mvn clean install
3. Open your fav web browser and hit the URL: http://localhost:8080/api/v1/swagger-ui.html
	3.1. If PORT 8080 already equpied, change it in the application.properties file accodingly.

4. User managment:

4.1 Create new user: API=> http://localhost:8080/api/v1/user | HTTP Method = POST
Sample JASON object:
{
  "dob": "2021-08-23",
  "name": "Atul",
  "phoneNumber": "9818334819"
}

4.2. Update existing user: API=> http://localhost:8080/api/v1/user | HTTP Method = PUT
Sample JASON object:
{
  "id": 1
  "dob": "2021-08-23",
  "name": "Atul Rai",
  "phoneNumber": "9818334819"
}

4.3 Delete user: API=> http://localhost:8080/api/v1/user/{userId} | HTTP Method = DELETE

Sample: http://localhost:8080/api/v1/user/1


5. Book managment:

5.1 Create new book: API=> http://localhost:8080/api/v1/book | HTTP Method = POST
Sample JASON object:
{
  "cost": 11.3,
  "isbn": "INDIA123",
  "title": "Wings of Fire"
}

5.2. Update existing book: API=> http://localhost:8080/api/v1/book | HTTP Method = PUT
Sample JASON object:
{
  "id": 1,
  "cost": 11.8,
  "isbn": "IND123",
  "title": "Wings of Fire by Dr. Kalam"
}

5.3 Delete book: API=> http://localhost:8080/api/v1/book/{bookId} | HTTP Method = DELETE

Sample: http://localhost:8080/api/v1/book/1

5.4 Search books using fields such as title or ISBN :
API=> http://localhost:8080/api/v1/book/searchBook/title/{bookTitle}/isbn/{isbn}
HTTP Method = GET

Sample: http://localhost:8080/api/v1/book/searchBook/title/Kalam/isbn/IND123

5.5 Advance book search:
API=> http://localhost:8080/api/v1/book/searchBookAdv/title/{bookTitle}
HTTP Method = GET

Sample: http://localhost:8080/api/v1/book/searchBookAdv/title/Kalam


5.6 Search total number of books currently available in the library:
API=> http://localhost:8080/api/v1/book/available-books
HTTP Method = GET



6. Inventory managment:

6.1 Create new inventory: API=> http://localhost:8080/api/v1/inventory | HTTP Method = POST
Sample JASON object:
{
  "bookId": 1,
  "status": "B",
  "userId": 1
}


6.2 Update new inventory: API=> http://localhost:8080/api/v1/inventory/{inventoryId} | HTTP Method = PUT
Sample: http://localhost:8080/api/v1/inventory/3

6.3 Search total number of borrowed books:
API=> http://localhost:8080/api/v1/inventory/borrowed-books
HTTP Method = GET

6.4 Search to find total books borrowed by a specific patron;
API=> http://localhost:8080/api/v1/inventory/borrowed-books/user/{userId}
HTTP Method = GET

Sample: http://localhost:8080/api/v1/inventory/borrowed-books/user/1

6.5 Borrowed books by all users;
API=> http://localhost:8080/api/v1/inventory/borrowed-books/user
HTTP Method = GET
