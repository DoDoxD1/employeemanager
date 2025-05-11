```markdown
# Employee Management API Documentation

RESTful API for managing employees. The API provides endpoints to create, read, update, and delete employee records.

## Base URL
```
http://localhost:8080/employee
``

### Endpoints

### Get All Employees
- **URL:** `/all`
- **Method:** `GET`
- **Success Response:**
  - **Code:** 200 OK
  - **Content:** Array of employee objects
```json
[
    {
        "id": "Long",
        "name": "String",
        "email": "String",
        "jobTitle": "String",
        "phone": "String",
        "imageUrl": "String",
        "employeeCode": "String"
    }
]
```

### Get Employee by ID
- **URL:** `/find/{id}`
- **Method:** `GET`
- **URL Params:** `id=[Long]`
- **Success Response:**
    - **Code:** 200 OK
    - **Content:** Employee object
- **Error Response:**
    - **Code:** 404 NOT FOUND
    - **Content:** `{"message": "User by id {id} was not found"}`

### Add Employee
- **URL:** `/add`
- **Method:** `POST`
- **Request Body:**
```json
{
    "name": "String",
    "email": "String",
    "jobTitle": "String",
    "phone": "String",
    "imageUrl": "String"
}
```
- **Success Response:**
    - **Code:** 201 CREATED
    - **Content:** Created employee object

### Update Employee
- **URL:** `/update`
- **Method:** `PUT`
- **Request Body:**
```json
{
    "id": "Long",
    "name": "String",
    "email": "String",
    "jobTitle": "String",
    "phone": "String",
    "imageUrl": "String"
}
```
- **Success Response:**
    - **Code:** 200 OK
    - **Content:** Updated employee object

### Delete Employee
- **URL:** `/delete/{id}`
- **Method:** `DELETE`
- **URL Params:** `id=[Long]`
- **Success Response:**
    - **Code:** 200 OK

## CORS
The API allows cross-origin requests from `http://localhost:4200`
```