# Documents

## List All Documents
> Sample JSON structured response:

```javascript
{
  "documents": [
      {
          "id": 15,
          "userId": 1,
          "title": "Biodun's Dilemma",
          "access": 0,
          "content": "So, what will I eat for breakfast now that there's an election going on????",
          "createdAt": "2017-07-22T06:53:06.520Z",
          "updatedAt": "2017-07-22T06:53:06.520Z",
          "user": {
              "id": 1,
              "username": "admin",
              "roleId": 1,
              "fullname": "admin",
              "email": "admin@gmail.com"
          }
      },
      {
          "id": 14,
          "userId": 1,
          "title": "Sunday",
          "access": 1,
          "content": "First document edited",
          "createdAt": "2017-07-22T06:50:11.150Z",
          "updatedAt": "2017-07-23T15:03:56.047Z",
          "user": {
              "id": 1,
              "username": "admin",
              "roleId": 1,
              "fullname": "admin",
              "email": "admin@gmail.com"
          }
      },
      {
          "id": 12,
          "userId": 4,
          "title": "Nath's role document",
          "access": 2,
          "content": "Role document by nathan!!",
          "createdAt": "2017-07-21T12:58:33.691Z",
          "updatedAt": "2017-07-21T12:58:33.691Z",
          "user": {
              "id": 4,
              "username": "nathan",
              "roleId": 2,
              "fullname": "nathan",
              "email": "nathan@gmail.com"
          }
      },
  ],
  "pagination": {
      "totalCount": 7,
      "pages": 2,
      "currentPage": 1,
      "pageSize": 6
  }
}
```

### Request
- Endpoint: GET: `/api/v1/documents`

### Query Parameters
Parameter | Default | Description
--------- | ------- | -----------
limit | 6 | Sets the limit.
offset | 0 | Sets the offset.

### Response
- Status: `200: OK`
- Body: `(application/json)`


## Create Document

> Request:

```javascript
{
  "title": "Chester",
  "content": "I'm so high, I can hear heaven. Oh, but Heaven can't hear me",
  "access": 2
}
```

> Sample JSON structured response:

```javascript
{
  "id": 3,
  "title": "Hello",
  "content": "Hello, It's me",
  "access": 0,
  "userId": 1,
  "createdAt": "2017-05-28T22:43:37.097Z",
  "updatedAt": "2017-05-28T22:43:37.097Z",
  "user": {
    "id": 2,
    "username": "admin",
    "fullname": "admin",
    "email": "admin",
    "roleId": 1
  },
}
```

### Request
- Endpoint: POST: `/api/v1/documents`
- Requires: Authentication
- Body: `(application/json)`


### Response
- Status: `201: Created`
- Body: `(application/json)`


## Get Document

> Sample JSON structured response:

```javascript
{
  "id": 6,
  "title": "Hello",
  "content": `Hello, It's me`,
  "access": 2,
  "userId": 3,
  "createdAt": "2017-05-28T22:19:08.870Z",
  "updatedAt": "2017-05-28T22:19:08.871Z",
  "user": {
    "id": 2,
    "username": "funms",
    "fullname": "funmi",
    "email": "funms@gmail.com",
    "roleId": 3
  }
}
```

### Request
- Endpoint: GET: `/api/v1/documents/:id`

### Response
- Status: `200: OK`
- Body: `(application/json)`


## Edit Document

> Request:

```javascript
{
  "content": "What's new?"
}
```

> Sample JSON structured response:

```javascript
{
  "id": 3,
  "title": "Hello",
  "content": "What's new?",
  "access": 0,
  "userId": 1,
  "createdAt": "2017-05-28T22:43:37.097Z",
  "updatedAt": "2017-05-28T22:43:37.097Z",
  "user": {
    "id": 2,
    "username": "admin",
    "fullname": "admin",
    "email": "admin@gmail.com",
    "roleId": 1
  },
}
```

### Request
- Endpoint: PUT: `/api/v1/documents/:id`
- Requires: Authentication
- Body: `(application/json)`

### Response
- Status: `200: OK`
- Body: `(application/json)`


## Delete Document

> Sample JSON structured response:

```javascript
{
  "message": "Document deleted successfully"
}
```

### Request
- Endpoint: DELETE: `/api/v1/documents/:id`
- Requires: Authentication

### Response
- Status: `200: OK`
- Body: `(application/json)`


## Search Documents

> Sample JSON structured response:

```javascript
{
  "documents": [
      {
      "id": 2,
      "title": "Saruman's Words",
      "content": `The hour is late and Gandalf the Grey comes to
      Isengard seeking my counsel...`,
      "access": -1,
      "userId": 2,
      "createdAt": "2017-05-28T22:19:08.871Z",
      "updatedAt": "2017-05-28T22:19:08.871Z",
      "user": {
        "id": 2,
        "username": "elf",
        "fullname": "arwen",
        "email": "arwen@aragon.com",
        "roleId": 2
      }
    },
    {
      "id": 1,
      "title": "Glory",
      "content": `When the glory comes, it will be ours, oh it will be ours,
      One day, when the war is won, we will be sure...`,
      "access": 0,
      "userId": 1,
      "createdAt": "2017-05-28T22:19:08.870Z",
      "updatedAt": "2017-05-28T22:19:08.871Z",
      "user": {
        "id": 3,
        "username": "sara",
        "fullname": "sara",
        "email": "sara@gmail.com",
        "roleId": 1
      }
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
- Endpoint: GET: `/api/v1/search/documents/`
- Requires: Authentication

### Query Parameters
Parameter | Default | Description
--------- | ------- | -----------
searchKey | "" | Search query.

### Response
- Status: `200: OK`
- Body: `(application/json)`
