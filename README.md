## API Testing Report

#### [Reqres][https://reqres.in]

## Method

- POST
- GET
- PUT
- DELETE

## Endpoints

### Register Users

POST `https://reqres.in/api/register`

The request body needs to be in JSON format and include the following properties:

{
"email": "your email",
"password": "your pass"
}
Registered total 6 different users.

After each registration new tokens will be generated for each users.

### Users

GET `{{url}}/users`

Returns the User Lists of the API.

### Details of a Single Users

GET `{{url}}/users/id`

Retrieve detailed information about a user.

### Resources

GET `{{url}}/unknown`

Returns the resources of the API.

### Details of a Single Resources

GET `{{url}}/unknown/id`

Retrieve detailed information about a resource.

## API Authentication

To Update and delete those generated tokens in the registration phases required.

PUT `{{url}}/users/{{id}}`

The request body needs to be in JSON format and include the following properties:

Example

```
{
   "first_name": "your first name",
   "last_name": "your last name",
}
```

The response body will contain the access token in the Authorization tab.

### Delete a User

DELETE `{{url}}/users/{{id}}`

Delete an existing user. Requires authentication.

The request body needs to be empty.

Example

```
DELETE /users/3
Authorization: Bearer <YOUR TOKEN>
```

## Command

1. **Newman Install:**

   - npm install -g newman

2. **Reporter Install:**

   - npm install -g newman-reporter-html
   - npm install -g newman-reporter-htmlextra

3. **Report Generate:**
   - newman run "..\CollectionName.json" -e "..\EnvironmentName.json" -r cli,html
   - newman run "..\CollectionName.json" -e "..\EnvironmentName.json" -r cli,htmlextra
