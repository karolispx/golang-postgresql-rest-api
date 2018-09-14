# GoLang, PostgreSQL and Rest API (gorilla/mux package). Very simple examples for inserting, selecting and deleting from PostgreSQL DB using REST APIs.

## Installing PostgreSQL on your machine/server should be straight forward. You should be able to find tutorials on google/youtube. 

### Install PostgreSQL Client on your machine to make your life easier, I'm using Postico on a macOS.
### Installing Postman on your machine will allow you to make GET/POST/DELETE and many more requests to your applications.

You will need to get the following packages to make it work:
* `go get -u github.com/lib/pq`
* `go get -u github.com/gorilla/mux`

## Usage:
1. Get the 2 packages from above
2. Run `go run main.go`
3. Use Postman to test the requests

## Requests:
1. Get all books - [GET] http://localhost:8000/books/
2. Create a book - [POST] http://localhost:8000/books/ - (body: 'x-www-form-urlencoded', pass in bookid and bookname)
3. Delete a book by bookid - [DELETE] http://localhost:8000/books/{bookid} - make sure to use a valid bookid from books dable (bookid not id)
4. Delete all books - [DELETE] http://localhost:8000/books/

## Books table:
```
CREATE TABLE books (
    id SERIAL PRIMARY KEY,
    bookid character varying(50) NOT NULL,
    bookname character varying(255) NOT NULL
);
```

More information about building Rest APIs using gorilla/mux package (https://github.com/gorilla/mux):
* https://www.codementor.io/codehakase/building-a-restful-api-with-golang-a6yivzqdo
* https://semaphoreci.com/community/tutorials/building-and-testing-a-rest-api-in-go-with-gorilla-mux-and-postgresql