# Book Management API

A simple Express REST API for managing a list of books.

## Getting Started

### 1. Install Dependencies
Ensure you have Node.js installed, then run:

```bash
npm install
```

### 2. Start the Server
Run the following command to start the API:

```bash
node index.js
```

The server will be running at `http://localhost:3000`.

## API Endpoints

### 1. Get All Books
Retrieves a list of all books in the collection.

- **URL**: `/books`
- **Method**: `GET`

**Usage:**
```bash
curl http://localhost:3000/books
```

### 2. Get a Specific Book
Retrieves a single book by its ID.

- **URL**: `/books/:id`
- **Method**: `GET`

**Usage:**
```bash
curl http://localhost:3000/books/1
```

### 3. Add a New Book
Adds a new book to the collection.

- **URL**: `/books`
- **Method**: `POST`
- **Data Params**:
```json
{ "title": "String", "author": "String" }
```

**Usage:**
```bash
curl -X POST -H "Content-Type: application/json" \
-d '{"title":"The Hobbit","author":"J.R.R. Tolkien"}' \
http://localhost:3000/books
```

## Verification

You can confirm the API is working by running the server and executing the `curl` commands above.

A successful `POST` request will return the newly created book with an assigned ID.
