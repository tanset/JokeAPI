# Jokes API

A RESTful API built with Express.js that allows users to manage a collection of jokes. This project supports full CRUD (Create, Read, Update, Delete) operations and includes a simple authentication mechanism for sensitive actions.

## Table of Contents
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [API Endpoints](#api-endpoints)
- [Usage Examples](#usage-examples)

## Features
- Retrieve random jokes or specific jokes by ID.
- Filter jokes by category/type.
- Add new jokes to the collection.
- Fully update (PUT) or partially update (PATCH) existing jokes.
- Delete specific jokes or clear the entire database (requires Master Key).

## Prerequisites
- [Node.js](https://nodejs.org/) (v14 or higher recommended)
- [npm](https://www.npmjs.com/) (comes with Node.js)

## Installation
1. Clone the repository or download the source code.
2. Navigate to the project directory.
3. Install the dependencies:
   ```bash
   npm install
   ```
4. Start the server:
   ```bash
   node index.js
   ```
   The server will start on `http://localhost:3000`.

---

## API Endpoints

### 1. Get a Random Joke
- **URL:** `/random`
- **Method:** `GET`
- **Description:** Returns a random joke from the collection.

### 2. Get a Specific Joke
- **URL:** `/jokes/:id`
- **Method:** `GET`
- **Parameters:** `id` (integer)
- **Description:** Returns the joke with the specified ID.

### 3. Filter Jokes by Type
- **URL:** `/filter`
- **Method:** `GET`
- **Query Parameter:** `type` (e.g., `Science`, `Puns`)
- **Description:** Returns a list of jokes that match the specified `jokeType`.

### 4. Create a New Joke
- **URL:** `/jokes`
- **Method:** `POST`
- **Body (URL-encoded):**
    - `text`: The content of the joke.
    - `type`: The category of the joke.
- **Description:** Adds a new joke to the collection.

### 5. Replace a Joke (Full Update)
- **URL:** `/jokes/:id`
- **Method:** `PUT`
- **Parameters:** `id` (integer)
- **Body (URL-encoded):** `text`, `type`
- **Description:** Replaces an existing joke entirely with new data.

### 6. Update a Joke (Partial Update)
- **URL:** `/jokes/:id`
- **Method:** `PATCH`
- **Parameters:** `id` (integer)
- **Body (URL-encoded):** `text` (optional), `type` (optional)
- **Description:** Updates specific fields of an existing joke.

### 7. Delete a Specific Joke
- **URL:** `/jokes/:id`
- **Method:** `DELETE`
- **Parameters:** `id` (integer)
- **Description:** Deletes the joke with the specified ID.

### 8. Delete All Jokes
- **URL:** `/all`
- **Method:** `DELETE`
- **Query Parameter:** `key` (Your Master Key)
- **Description:** Clears the entire joke collection. Requires the correct `masterKey` for authorization.
- **Master Key:** `4VGP2DN-6EWM4SJ-N6FGRHV-Z3PR3TT`

---

## Usage Examples

### Using Postman
Detailed API documentation and test suite:
[Postman Workspace - Jokes API](https://documenter.getpostman.com/view/6048123/2s9XxsTv8Y)

### Example Request (Add a Joke)
- **Endpoint:** `POST http://localhost:3000/jokes`
- **Body:**
  ```text
  text: "Why did the computer show up late to work? It had a hard drive."
  type: "Programming"
  ```

### Example Request (Delete All Jokes)
- **Endpoint:** `DELETE http://localhost:3000/all?key=4VGP2DN-6EWM4SJ-N6FGRHV-Z3PR3TT`
