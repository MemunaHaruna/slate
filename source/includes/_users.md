# Users

## List All Users
> Sample JSON structured response:

```javascript
{
  "users": [
      {
          "id": 12,
          "username": "Tolu",
          "fullname": "Tolu Afobs",
          "roleId": 2,
          "email": "tolu@gmail.com"
      },
      {
          "id": 11,
          "username": "biodun",
          "fullname": "biodun",
          "roleId": 2,
          "email": "biodun@gmail.com"
      },
      {
          "id": 8,
          "username": "Rob",
          "fullname": "Robert Ludlum",
          "roleId": 2,
          "email": "robert@robert.com"
      },
      {
          "id": 7,
          "username": "Johnie",
          "fullname": "John Grisham",
          "roleId": 2,
          "email": "john@grisham.com"
      },
      {
          "id": 6,
          "username": "Dorian",
          "fullname": "Dorian Gray",
          "roleId": 2,
          "email": "dorian@gray.com"
      },
      {
          "id": 5,
          "username": "Max",
          "fullname": "Gruocho",
          "roleId": 2,
          "email": "max@max.com"
      }
  ],
  "pagination": {
      "totalCount": 9,
      "pages": 2,
      "currentPage": 1,
      "pageSize": 6
  }
}
```

### Request
- Endpoint: GET: `/api/v1/users`
- Requires: Authentication

### Query Parameters
Parameter | Default | Description
--------- | ------- | -----------
limit | 6 | Sets the limit.
offset | 0 | Sets the offset.

### Response
- Status: `200: OK`
- Body: `(application/json)`


## Create User

> Request:

```javascript
{
  "username": "doro",
  "fullname": "doro bucci",
  "email": "doro@bucci.com",
  "password": "dorobucci",
  "confirmPassword": "dorobucci",
}
```

> Sample JSON structured response:

```javascript
{
    "message": "Signed up successfully",
    "user": {
        "id": 5,
        "username": "doro",
        "fullname": "doro bucci",
        "roleId": 2,
        "email": "doro@bucci.com"
    },
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOjEsInJvbGVJZCI6MSwiaWF0IjoxNTAyMTAwMzA5LCJleHAiOjE1MDIxODY3MDl9.vzMK6Mr7cLr7rk5mXF5KeRXlJn913XBJXQjaOGJEiXo"
}
```

### Request
- Endpoint: POST: `/auth/api/v1/users`
- Body: `(application/json)`


### Response
- Status: `201: Created`
- Body: `(application/json)`

## Get User

> Sample JSON structured response:

```javascript
{
  "id": 4,
  "username": "Mikail",
  "fullname": "Mikail Stanislaski",
  "roleId": 2,
  "email": "mikahil.stanislaski@gmail.com",
}
```

### Request
- Endpoint: GET: `/api/v1/users/:id`

### Response
- Status: `200: OK`
- Body: `(application/json)`


## Edit User

> Request:

```javascript
{
  "username": "mikhy",
}
```

> Sample JSON structured response:

```javascript
{
  "id": 4,
  "username": "mikhy",
  "fullname": "Mikail Stanislaski",
  "email": "mikahil.stanislaski@gmail.com",
  "roleId": 2,
}
```

### Request
- Endpoint: PUT: `/api/v1/users/:id`
- Body: `(application/json)`

### Response
- Status: `200: OK`
- Body: `(application/json)`


## Delete User

> Sample JSON structured response:

```javascript
{
  "message": "User deleted successfully"
}
```

### Request
- Endpoint: DELETE: `/api/v1/users/:id`
- Requires: Authentication

### Response
- Status: `200: OK`
- Body: `(application/json)`


## Login User

> Request:

```javascript
{
  "email": "tolu@gmail.com",
  "password": "afolabi"
}
```

> Sample JSON structured response:

```javascript
{
    "message": "Signed in successfully",
    "user": {
        "id": 1,
        "username": "tolu",
        "fullname": "tolu afobs",
        "roleId": 1,
        "email": "tolu@gmail.com"
    },
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOjEsInJvbGVJZCI6MSwiaWF0IjoxNTAyMTAwMzA5LCJleHAiOjE1MDIxODY3MDl9.vzMK6Mr7cLr7rk5mXF5KeRXlJn913XBJXQjaOGJEiXo"
}
```

### Request
- Endpoint: POST: `/auth/api/v1/users/login`

### Response
- Status: `200: OK`
- Body: `(application/json)`


## Logout User

> Sample JSON structured response:

```javascript
{
  "message": "Successfully logged out"
}
```

### Request
- Endpoint: POST: `/api/v1/users/logout`

### Response
- Status: `200: OK`
- Body: `(application/json)`



## List User Documents

> Sample JSON structured response:

```javascript
[
  {
    "id": 1,
    "title": "Hello",
    "content": "It's me!",
    "access": 0,
    "userId": 1,
    "createdAt": "2017-05-28T22:19:08.870Z",
    "updatedAt": "2017-05-28T22:58:17.249Z",
    "user": {
      "username": "admin",
      "roleId": 1,
      "email": "admin@gmail.com",
      "fullname": "admin"
    }
  }
]
```

### Request
- Endpoint: GET: `/api/v1/users/:id/documents`
- Requires: Authentication

### Response
- Status: `200: OK`
- Body: `(application/json)`


## Search Users

> Sample JSON structured response:

```javascript
{
  "users": [
      {
          "id": 12,
          "username": "Tolu",
          "fullname": "Tolu Afobs",
          "roleId": 2,
          "email": "tolu@gmail.com"
      },
      {
          "id": 11,
          "username": "biodun",
          "fullname": "biodun",
          "roleId": 2,
          "email": "biodun@gmail.com"
      },
      {
          "id": 8,
          "username": "Rob",
          "fullname": "Robert Ludlum",
          "roleId": 2,
          "email": "robert@robert.com"
      },
  ],
  "pagination": {
      "totalCount": 9,
      "pages": 2,
      "currentPage": 1,
      "pageSize": 6
  }
}
```

### Request
- Endpoint: GET: `/api/v1/search/users/`
- Requires: Authentication

### Query Parameters
Parameter | Default | Description
--------- | ------- | -----------
searchKey | "" | Search query.

### Response
- Status: `200: OK`
- Body: `(application/json)`
