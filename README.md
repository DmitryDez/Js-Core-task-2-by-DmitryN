# Js-Core-task-2-by-DmitryN
task 4.2.7
there is nothing useful here

postman web version

vars
myURL   - https://blog.kata.academy/api
myToken - ******

1. Registration

Method - POST

https://blog.kata.academy/api/users
{{myURL}}/users

Headers
Content-Type - application/json

Body
{
 "user": {
   "username": "dmitry",
   "email":    "xy@gmail.com",
   "password": "12345"
 }
}

2. Log in

Method - POST

https://blog.kata.academy/api/users/login
{{myURL}}/users/login

Headers
Content-Type - application/json

Body
{
 "user": {
   "email":    "xy@gmail.com",
   "password": "12345"
 }
}

tests
let myData  = pm.response.json();
let myToken = myData.user.token;
pm.collectionVariables.set("myToken", myToken);

3. Get user's data

Method - GET

https://blog.kata.academy/api/user
{{myURL}}/user

authorization
Bearer token - myToken
