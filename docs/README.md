# Bookstore API Documention
---
this is the documentation for the api end points provided by the server
# Base URL 

<!-- ## Introduction -->

<!-- Introduction to the Bookstore API
The Bookstore API is a RESTful API that allows you to manage your bookstore. It provides the following endpoints:

1. Bookstores: This endpoint allows you to create, read, update, and delete bookstores.
2. Authors: This endpoint allows you to create, read, update, and delete authors.
3. Books: This endpoint allows you to create, read, update, and delete books.
4. Owner registration: This endpoint allows bookstore owners to register for an account.
5. User authentication with JWT: This endpoint allows users to authenticate and obtain a JWT token, which can be used to authenticate subsequent requests to the API. -->

## Authentication


All requests to this API must be authenticated with a JWT token. You can obtain a JWT token by authenticating to the /login endpoint. The request body must contain the following fields:
<ul>
<li>
email
</li>
<li>
password
</li>
</ul>

# Endpoints
---
The Bookstore API is a  API that allows you to manage your bookstore. It provides the following endpoints:
## Owner registration

<ul>
<li>
Url:api/owners/signup
</li>
<li>
method:Post
</li>
<li>
Description:registers a new user
</li>
<li>
Request Body:
</li>
</ul>




|**Field**   |**Type**   | Description   |   
|---|---|---|
|  name | String  |  The name of the owner. |  
| email  | String  |   The email of the owner. |   
| password |string   |	The password of the owner.   |   

## Response
```json

   {
    "status": 201,
    "message": "Owner created successfully",
    "newOwner": {
        "id": 3,
        "name": " Cali xuseen",
        "email": "cali@gmail.com",
        "password": "$2b$10$cDgoUnlr69fxWhqYM1uCqeAnY.xOSveB4ZLpBONai9sn8Wo6Iws5G",
        "created": "2023-10-07T05:35:40.828Z",
        "updated": "2023-10-07T05:35:40.828Z"
    }
}

```

<!-- owner login-->
## Owner Login

<ul>
<li>
Url:api/owners/login
</li>
<li>
method:Post
</li>
<li>
Description:Authenticates a user
</li>
<li>
Request Body:
</li>
</ul>




|**Field**   |**Type**   | Description   |   
|---|---|---|
|  email | String  |  The email address of the owner. |  
| password  | String  |   The password of the owner. |   
   

## Response
```json

 {
    "status": 200,
    "message": "Owner logged in successfully",
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MywiZW1haWwiOiJjYWxpQGdtYWlsLmNvbSIsImlhdCI6MTY5NjY1NzM4NywiZXhwIjoxNjk2NjYwOTg3fQ.pjPApdmcw_qz0xgIDiVVXKElshEsRupEtuoyCBuEph8"
}

```



<!-- Bookstore Endpoints-->
# Bookstore Endpoints
## create bookstore
<ul>
<li>
Url:api/bookstore/
</li>
<li>
method:Post
</li>
<li>
Description:creates a bookstore
</li>
<li>
Request Body:
</li>
</ul>




|**Field**   |**Type**   | Description   |   
|---|---|---|
| ownerId | int  |  The ID of the owner. |  
| name  | String  |   The name of the bookstore. |  
| location  | String  |   The location of the bookstore. | 
 
   

## Response
```json

{
    "status": 200,
    "message": "BookStore created"
}

```
## update bookstore
<ul>
<li>
Url:api/bookstore/:id
</li>
<li>
method:put
</li>
<li>
Description:update a bookstore
</li>
<li>
Request Body:
</li>
</ul>




|**Field**   |**Type**   | Description   |   
|---|---|---|
| ownerId | int  |  The ID of the owner. |  
| name  | String  |   The name of the bookstore. |  
| location  | String  |   The location of the bookstore. | 
 
   

## Response
```json

{
    "status": 200,
    "message": "BookStore updated"
}

```
<!--  -->
## delete bookstore
<ul>
<li>
URL:api/bookstore/:id
</li>
<li>
method:delete
</li>
<li>
Description:delete a bookstore
</li>
<li>
Request Body:
</li>
</ul>


|**Field**   |**Type**   | Description   |   
|---|---|---|
| id | number  |  The ID of the bookstore. |  

 
   

## Response
```json

{
    "status": 200,
    "message": "BookStore successfully deleted"
}

```

## create books
<ul>
<li>
URL:api/books/
</li>
<li>
method:post
</li>
<li>
Description:create a book
</li>
<li>
Request Body:
</li>
</ul>


|**Field**   |**Type**   | Description   |   
|---|---|---|
| authorId | number  |  The ID of the author. |  
| bookstoreId | number  |  The ID of the bookstore. |  
| title | string  |  The title of the book. |  
| price | int  |  The price of the book. |
| image | string  |  The image of the book. |

 
   

## Response
```json

{
    "status": 200,
    "message": "Book was created successfully"
}

```

## update books
<ul>
<li>
URL:api/books/:id
</li>
<li>
method:put
</li>
<li>
Description:update a book
</li>
<li>
Request Body:
</li>
</ul>


|**Field**   |**Type**   | Description   |   
|---|---|---|
| authorId | number  |  The ID of the author. |  
| bookstoreId | number  |  The ID of the bookstore. |  
| title | string  |  The title of the book. |  
| price | int  |  The price of the book. |
| image | string  |  The image of the book. |

 
   

## Response
```json

{
    "status": 200,
    "message": "Book was updated successfully"
}

```

## delete books
<ul>
<li>
URL:api/books/:id
</li>
<li>
method:delete
</li>
<li>
Description:delete a book
</li>
<li>
Request Body:
</li>
</ul>


|**Field**   |**Type**   | Description   |   
|---|---|---|
| id | number  |  The ID of the book. |  


 
   

## Response
```json

{
    "status": 200,
    "message": "Book successfully deleted"
}

```

## create author
<ul>
<li>
URL:api/authors/
</li>
<li>
method:post
</li>
<li>
Description:create Author
</li>
<li>
Request Body:
</li>
</ul>


|**Field**   |**Type**   | Description   |   
|---|---|---|
| name | string  |  The name of the author. |  


 
   

## Response
```json

{
    "status": 200,
    "message": "Author created"
}

```

## update author
<ul>
<li>
URL:api/authors/:id
</li>
<li>
method:put
</li>
<li>
Description:update Author
</li>
<li>
Request Body:
</li>
</ul>


|**Field**   |**Type**   | Description   |   
|---|---|---|
| name | string  |  The name of the author. |  


 
   

## Response
```json

{
    "status": 200,
    "message": "Author updated successfully"
}

```

## delete author
<ul>
<li>
URL:api/authors/:id
</li>
<li>
method:delete
</li>
<li>
Description:delete Author
</li>
<li>
Request Body:
</li>
</ul>


|**Field**   |**Type**   | Description   |   
|---|---|---|
| id | int  |  The id of the author. |  


 
   

## Response
```json

{
    "status": 200,
    "message": "Author deleted successfully"
}

```