#Laravel ToDo App
This is a simple ToDo app with multiple user support.

This is built on Laravel Framework 9.3. 

###Installation
Clone the repository-https://github.com/benjirojaya/ToDo_api

git clone https://github.com/milon521/laravel-todo.git
Then cd into the folder with this command-

cd laravel-todo
Then do a composer install

composer install
Then create a environment file using this command-

cp .env.example .env
Then edit .env file with appropriate credential for your database server. Just edit these two parameter(DB_USERNAME, DB_PASSWORD).

Then create a database named task and then do a database migration using this command-

php artisan migrate


###Run server
Run server using this command-

php artisan serve
