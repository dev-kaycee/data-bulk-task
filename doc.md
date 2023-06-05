
Task API
The Task API is a RESTful API that allows you to manage tasks. It provides endpoints for creating, reading, updating, and deleting tasks.

Table of Contents
Getting Started
API Documentation
Authentication
Endpoints
Create Task
Get All Tasks
Get Task by ID
Update Task
Delete Task
Getting Started
To use the Task API, follow the steps below:

Clone the repository or download the source code.

Install the required dependencies using the following command:

dotnet restore
Configure the database connection string in the appsettings.json file.

Apply the database migrations by running the following command:

sql

dotnet ef database update
Start the API server:

arduino

dotnet run
The API will be accessible at http://localhost:5000.

API Documentation
The API is documented using Swagger. After starting the API server, you can access the Swagger UI by navigating to http://localhost:5000/swagger.

Authentication
The Task API uses JWT (JSON Web Token) for authentication. To access the protected endpoints, you need to include a valid JWT token in the Authorization header of your requests.

To obtain a JWT token, you need to send a POST request to the /auth/login endpoint with valid credentials. On successful authentication, the API will respond with a JWT token, which you can then include in the Authorization header for subsequent requests.

Endpoints
Create Task
Endpoint: POST /tasks

Create a new task.

Request Body:

json

{
  "title": "Task 1",
  "description": "Do something"
}
Response:

Status: 201 Created
Body:
json

{
  "id": 1,
  "title": "Task 1",
  "description": "Do something"
}
Get All Tasks
Endpoint: GET /tasks

Retrieve a list of all tasks.

Response:

Status: 200 OK
Body:
json

[
  {
    "id": 1,
    "title": "Task 1",
    "description": "Do something"
  },
  {
    "id": 2,
    "title": "Task 2",
    "description": "Do something else"
  }
]
Get Task by ID
Endpoint: GET /tasks/{id}

Retrieve a task by its ID.

Response:

Status: 200 OK
Body:
json

{
  "id": 1,
  "title": "Task 1",
  "description": "Do something"
}
Update Task
Endpoint: PUT /tasks/{id}

Update a task by its ID.

Request Body:

json

{
  "title": "Updated Task",
  "description": "Updated description"
}
Response:

Status: 200 OK
Body:
json

{
  "id": 1,
  "title": "Updated Task",
  "description": "Updated description"
}
Delete Task
Endpoint: DELETE /tasks/{id}

Delete a task by its ID.

Response:

Status: 204 No Content