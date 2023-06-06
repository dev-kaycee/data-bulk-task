# Task API Documentation
The Task API allows you to manage tasks. You can perform operations such as retrieving all tasks, creating a new task, updating an existing task, and deleting a task.

# Getting Started

## To use the Task API, follow the steps below:
Clone the repository or download the source code.

##### Install the required dependencies using the following command:

```
dotnet restore
```
##### Apply the database migrations by running the following command:

```
dotnet ef database update
```

##### Start the API server:

```
dotnet run
```


## API Documentation
The API is documented using Swagger. After starting the API server, you can access the Swagger UI by navigating to http://localhost:{port}/swagger.

## Authentication
The Task API uses JWT (JSON Web Token) for authentication. To access the protected endpoints, you need to include a valid JWT token in the Authorization header of your requests.

#### Base URL
The base URL for accessing the Task API is: https://localhost:{port}/api/tasks

#### Endpoints
##### GET /api/tasks
Retrieves all tasks.

###### Request
Method: GET
Endpoint: /api/tasks
###### Response
Status Code: 200 (OK)
Content: Array of tasks in JSON format
```json
[
  {
    "id": 1,
    "title": "Task 1",
    "description": "Description of Task 1"
  },
  {
    "id": 2,
    "title": "Task 2",
    "description": "Description of Task 2"
  },
  
]
```
##### GET /api/tasks/{id}
Retrieves a specific task by its ID.

###### Request
Method: GET
Endpoint: /api/tasks/{id} (Replace {id} with the ID of the task)
###### Response
Status Code: 200 (OK)
Content: Task details in JSON format

```
{
  "id": 1,
  "title": "Task 1",
  "description": "Description of Task 1"
}
```
Status Code: 404 (Not Found) if the task with the specified ID does not exist
POST /api/tasks
Creates a new task.

###### Request
Method: POST
Endpoint: /api/tasks
Body: Task details in JSON format

```json
{
  "title": "New Task",
  "description": "Description of the new task"
}
```

###### Response
Status Code: 201 (Created)
Content: Task details of the created task in JSON format

```json
{
  "id": 3,
  "title": "New Task",
  "description": "Description of the new task"
}
```
PUT /api/tasks/{id}
Updates an existing task by its ID.

###### Request
Method: PUT
Endpoint: /api/tasks/{id} (Replace {id} with the ID of the task)
Body: Updated task details in JSON format
```json
{
  "id": 3,
  "title": "Updated Task",
  "description": "Updated description of the task"
}
```
###### Response
Status Code: 204 (No Content)
Status Code: 400 (Bad Request) if the provided ID in the URL and the task ID in the body do not match
Status Code: 404 (Not Found) if the task with the specified ID does not exist

##### DELETE /api/tasks/{id}
Deletes a task by its ID.

###### Request
Method: DELETE
Endpoint: /api/tasks/{id} (Replace {id} with the ID of the task)
###### Response
Status Code: 204 (No Content)
Status Code: 404 (Not Found) if the task with the specified ID does not exist
