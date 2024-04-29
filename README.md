# book-project

for running the project the project
install the dependecies by the following command 
npm i

add .env file and variable {
PORT=4000
SALT_KEY=10
DATABASE_URL=mongodb+srv://steve:steve@cluster0.ut4snfg.mongodb.net/?retryWrites=true&w=majority&appName=Cluster0
SECRET_KEY=book@123
}
run the project using npm run start 

API Endpoints
# login and signup api with their curls
#  sign up  

curl --location 'http://localhost:4000/api/v1/auth/signup' \
--header 'Content-Type: application/json' \
--data '{
    "username": "shivangi",
    "password": "shivangi"
}'

# login http://localhost:4000/api/v1/auth/login 

curl --location 'http://localhost:4000/api/v1/auth/login' \
--header 'Content-Type: application/json' \
--data '{
    "username": "shivangi",
    "password": "shivangi"
}'

Book
# Save Book: POST /api/v1/books
curl --location 'http://localhost:4000/api/v1/books' \
--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiI2NjJmM2RjMTg1NjQ5NjE0Yzc0ZjQzMDIiLCJ1c2VybmFtZSI6InNoaXZhbmdpIiwiaWF0IjoxNzE0MzcyMDYxLCJleHAiOjE3MTQ0NTg0NjF9.CBFCosWi-_ARnSsOBIX4NI1CvLdaNglZDcf6Q_ayMpE' \
--header 'Content-Type: application/json' \
--data '{
    "title": "test",
    "author": "shivangi",
    "publicationYear": 2020
}'

# Update Book: PUT /api/v1/books/:id
curl --location --request PUT 'http://localhost:4000/api/v1/books/662f3eb385649614c74f4305' \
--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiI2NjJmM2RjMTg1NjQ5NjE0Yzc0ZjQzMDIiLCJ1c2VybmFtZSI6InNoaXZhbmdpIiwiaWF0IjoxNzE0MzcyMDYxLCJleHAiOjE3MTQ0NTg0NjF9.CBFCosWi-_ARnSsOBIX4NI1CvLdaNglZDcf6Q_ayMpE' \
--header 'Content-Type: application/json' \
--data '{
    "title": "New book",
    "author": " Book Author",
    "publicationYear": 2023
}'


# Get Book by ID: GET /api/v1/books/:id

curl --location 'http://localhost:4000/api/v1/books/662f3eb385649614c74f4305' \
--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiI2NjJmM2RjMTg1NjQ5NjE0Yzc0ZjQzMDIiLCJ1c2VybmFtZSI6InNoaXZhbmdpIiwiaWF0IjoxNzE0MzcyMDYxLCJleHAiOjE3MTQ0NTg0NjF9.CBFCosWi-_ARnSsOBIX4NI1CvLdaNglZDcf6Q_ayMpE'


# Get All Books: GET /api/v1/books

curl --location 'http://localhost:4000/api/v1/books' \
--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiI2NjJmM2RjMTg1NjQ5NjE0Yzc0ZjQzMDIiLCJ1c2VybmFtZSI6InNoaXZhbmdpIiwiaWF0IjoxNzE0MzcyMDYxLCJleHAiOjE3MTQ0NTg0NjF9.CBFCosWi-_ARnSsOBIX4NI1CvLdaNglZDcf6Q_ayMpE'

# Delete Book: DELETE /api/v1/books/:id

curl --location --request DELETE 'http://localhost:4000/api/v1/books/662ea56ff573e5efe4a9b4c1' \
--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiI2NjJlYTMyYjVlYjM5ZWU5NDJiNjk5MTUiLCJ1c2VybmFtZSI6InN0ZXZlIiwiaWF0IjoxNzE0MzMyOTE3LCJleHAiOjE3MTQ0MTkzMTd9.4qg0p-6mOMeQBdMkL7r92e1GeteBf0OmpPpBjyBunhk'


# Filter Books by Author: GET /api/v1/books/filter/books?author=a
curl --location 'http://localhost:4000/api/v1/books/filter/books?author=a' \
--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiI2NjJlYTMyYjVlYjM5ZWU5NDJiNjk5MTUiLCJ1c2VybmFtZSI6InN0ZXZlIiwiaWF0IjoxNzE0MzMyOTE3LCJleHAiOjE3MTQ0MTkzMTd9.4qg0p-6mOMeQBdMkL7r92e1GeteBf0OmpPpBjyBunhk'

# Filter Books by Publication Year: GET /api/v1/books/filter/books?publicationYear=2023

curl --location 'http://localhost:4000/api/v1/books/filter/books?publicationYear=2023' \
--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiI2NjJlYTMyYjVlYjM5ZWU5NDJiNjk5MTUiLCJ1c2VybmFtZSI6InN0ZXZlIiwiaWF0IjoxNzE0MzMyOTE3LCJleHAiOjE3MTQ0MTkzMTd9.4qg0p-6mOMeQBdMkL7r92e1GeteBf0OmpPpBjyBunhk'


# Filter Books by Both Author and Publication Year: GET /api/v1/books/filter/books?publicationYear=2022&author=a
curl --location 'http://localhost:4000/api/v1/books/filter/books?publicationYear=2022&author=a' \
--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiI2NjJlYTMyYjVlYjM5ZWU5NDJiNjk5MTUiLCJ1c2VybmFtZSI6InN0ZXZlIiwiaWF0IjoxNzE0MzMyOTE3LCJleHAiOjE3MTQ0MTkzMTd9.4qg0p-6mOMeQBdMkL7r92e1GeteBf0OmpPpBjyBunhk'



# book-crud
