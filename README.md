
# Todo API

This is a simple ToDo API



## Installation

Clone the repository-

```bash
 -https://github.com/benjirojaya/ToDo_api

```

Make sure you have composer,xampp and php installed.Move project folder into
```bash
c:\xampp\htdocs

```

Then cd into the folder with this command-
```bash
 cd laravel-Task

```


Then open project and edit .env file as show
```bash
 DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=Task
DB_USERNAME=root
DB_PASSWORD=
```


## Run server
Run server using this command-


```bash
php artisan serve
```
 

Then create a database named task and then do a database migration using this command-
```bash
php artisan migrate
```


Setting up JWT
```bash
php artisan jwt:secret
```

This will update our .env file with something like this:
```bash
JWT_SECRET=xxxxxxxx
```



## Features

- Login/Register User
- Create a todo if logged in
- Update a todo if logged in
- Show all todos if not login


## Test API
### Auth:api
Lets start by installing Postman if we dont have it installed.
Before we move to Postman and start testing the API endpoints, we need to start our Laravel application.

Run the below command to start the Laravel application:

```bash
  php artisan serve
```
###  Register Test
Start the Postman application, add the registration API in the address bar, select the POST HTTP request method from the dropdown, choose the form-data option on the Body tab and select the name, email, and password input fields.

As shown below;

```bash
   Registration API=http://127.0.0.1:8000/api/Register
   HTTP request=POST
   form-data=
   {
    email='enter email user'
    name='enter username'
    password='enter users password'
   }


   Then, click Send to see the server response.
```

### Show All Todos
Enter the link below to show all Todos
```bash
   Registration API=http://127.0.0.1:8000/api/todos
   HTTP request=GET
```
### Login Test
In the previous step, we created an account in the Postman application. To log in to the API, add the email and password to the input field, and click Send to see the response.

```bash
   Registration API=http://127.0.0.1:8000/api/login
   HTTP request=POST
   form-data=
   {
    email='enter registered email of user'
    password='enter registered users password'
   }
   Then, click Send to see the server response.
```
Remember to copy our login token.


### Test Endpoints
The create a todo,edit a todo,delete a todo endpoints are all protected by the auth:api middleware and therefore require that we send a valid token with the authorization header.
#### Create A Todo List
Select Bearer Token from the dropdown on the Authorization tab, paste the copied token into the Token field and update Postman with the below.

```bash
    
   Registration API=http://127.0.0.1:8000/api/todo
   HTTP request=POST
   form-data=
   {
    title='enter title of todo'
    description='enter content  of todo'
   }


   Then, click Send to see the server response.
```
#### Show All Todo List

Update Postman with entries below to show all Todo list w
```bash
    
   Registration API=http://127.0.0.1:8000/api/todos
   HTTP request=GET


   Then, click Send to see the server response.
```
#### Update a Todo
The user must be logged in to be able to update a todo.
Copy the login token
Select Bearer Token from the dropdown on the Authorization tab, paste the copied token into the Token field and update Postman with the below.
```bash
    
   Registration API=http://127.0.0.1:8000/api/todo/1
   we parse parameter 1 to update todo 1
   HTTP request=PUT
   x-www-form-urlencoded
   {
        title='update of title of todo'
        description='update of body of todo'
    }

   Then, click Send to see the server response.
```


