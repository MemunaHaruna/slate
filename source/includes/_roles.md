# Roles

## List All Roles
> Sample JSON structured response:

```javascript
[
  {
    "id": 1,
    "title": "admin"
  },
  {
    "id": 2,
    "title": "user"
  }
]
```

### Request
- Endpoint: GET: `/api/roles`
- Requires: Authentication

### Response
- Status: `200: OK`
- Body: `(application/json)`

## Create Role

> Request:

```javascript
{
  "title": "guest",
}
```

> Sample JSON structured response:

```javascript
{
  "id": 3,
  "title": "guest",
}
```

### Request
- Endpoint: POST: `/api/roles`
- Requires: Authentication
- Body: `(application/json)`


### Response
- Status: `201: Created`
- Body: `(application/json)`

## Delete Role

> Sample JSON structured response:

```javascript
{
  "message": "Role deleted successfully"
}
```

### Request
- Endpoint: DELETE: `/api/roles/:id`
- Requires: Authentication

### Response
- Status: `200: OK`
- Body: `(application/json)`
