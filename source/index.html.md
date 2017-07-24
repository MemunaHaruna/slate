---
title: DocGenie API Documentation

language_tabs: # must be one of https://git.io/vQNgJ
  - javascript

toc_footers:
  - <span> &copy2017, Developed by Memuna Haruna in Andela </span>

includes:
  - users
  - documents
  - roles

search: true
---

# DocGenie API Documentation

## Introduction
Docgenie API contains several end points that allows users to create, edit, retrieve and delete documents. It also sets access privileges so only authorized users can perform certain operations.
That is, only users in a particular role can view role-access documents, while only the creator of a document has the right to delete or edit it.

## Development
The application was developed with [NodeJs](http://nodejs.org/) and [Express](http://expressjs.com/) is used for routing. The [Postgres](http://postgresql.com/) database was used with sequelize as the ORM.

## Installation
Follow the steps below to setup a local development environment. First ensure you have [Postgresql](https://www.postgresql.org/) installed, and a version of [Node.js](http://nodejs.org/) equal or greater than v6.8.0.

1. Clone the repository to your local machine: `git clone https://github.com/andela-mharuna/DocGenie.git`.
2. Cd into the project directory:  `cd DocGenie`
3. Rename `.env_example` to `.env` and add the required environment variables.
4. Install project dependencies `npm install`
5. Start the express server in development mode: `npm run start:dev`.

## API Summary
### Users
EndPoint                           |   Functionality
-----------------------------------|------------------------
POST /auth/api/users/login         |   Logs in a user.
POST /api/users/logout             |   Logs out a user.
POST /auth/api/users/              |   Creates a new user.
GET /api/users/                    |   Gets all registered users (available only to the Admin).
GET /api/users/:id                 |   Finds a particular user by his/her id.
PUT /api/users/:id                 |   Updates a user's attributes based on the id specified (available to the profile owner or admin)
DELETE /api/users/:id              |   Deletes a user (available only to the profile owner)
GET /api/users/:id/documents       | Gets all documents belonging to a particular user

### Documents
EndPoint                      |   Functionality
------------------------------|------------------------
POST /api/documents/          |   Creates a new document.
GET /api/documents/           |   Gets all documents.
GET /api/documents/:id        |   Find a particular document by it's id.
PUT /api/documents/:id        |   Updates a document attributes. (available only to the owner)
DELETE /api/documents/:id     |   Delete a particular document. (available only to the owner)
GET /api/search/documents/?searchKey=${query} | Get all documents with title or content containing the search query

### Roles (available only to the Admin)
EndPoint                          |   Functionality
----------------------------------|------------------------
GET /api/roles/                   |   Get all created Roles.
POST /api/roles/                  |   Create a new Role.
DELETE /api/roles/:id             |   Delete a Role.
