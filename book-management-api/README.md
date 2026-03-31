# Book Management API                                                                                         │
│  2                                                                                                               │
│  3 A simple Express REST API for managing a list of books.                                                       │
│  4                                                                                                               │
│  5 ## Getting Started                                                                                            │
│  6                                                                                                               │
│  7 ### 1. Install Dependencies                                                                                   │
│  8 Ensure you have Node.js installed, then run:                                                                  │
│  9 ```bash                                                                                                       │
│ 10 npm install                                                                                                   │
│ 11 ```                                                                                                           │
│ 12                                                                                                               │
│ 13 ### 2. Start the Server                                                                                       │
│ 14 Run the following command to start the API:                                                                   │
│ 15 ```bash                                                                                                       │
│ 16 node index.js                                                                                                 │
│ 17 ```                                                                                                           │
│ 18 The server will be running at `http://localhost:3000`.                                                        │
│ 19                                                                                                               │
│ 20 ## API Endpoints                                                                                              │
│ 21                                                                                                               │
│ 22 ### 1. Get All Books                                                                                          │
│ 23 Retrieves a list of all books in the collection.                                                              │
│ 24 - **URL**: `/books`                                                                                           │
│ 25 - **Method**: `GET`                                                                                           │
│ 26 - **Usage**:                                                                                                  │
│ 27   ```bash                                                                                                     │
│ 28   curl http://localhost:3000/books                                                                            │
│ 29   ```                                                                                                         │
│ 30                                                                                                               │
│ 31 ### 2. Get a Specific Book                                                                                    │
│ 32 Retrieves a single book by its ID.                                                                            │
│ 33 - **URL**: `/books/:id`                                                                                       │
│ 34 - **Method**: `GET`                                                                                           │
│ 35 - **Usage**:                                                                                                  │
│ 36   ```bash                                                                                                     │
│ 37   curl http://localhost:3000/books/1                                                                          │
│ 38   ```                                                                                                         │
│ 39                                                                                                               │
│ 40 ### 3. Add a New Book                                                                                         │
│ 41 Adds a new book to the collection.                                                                            │
│ 42 - **URL**: `/books`                                                                                           │
│ 43 - **Method**: `POST`                                                                                          │
│ 44 - **Data Params**: `{ "title": "String", "author": "String" }`                                                │
│ 45 - **Usage**:                                                                                                  │
│ ```bash                                                                                                     │
│ 47   curl -X POST -H "Content-Type: application/json" -d '{"title":"The Hobbit","author":"J.R.R. Tolkien"}'      │
│    http://localhost:3000/books                                                                                   │
│ 48   ```                                                                                                         │
│ 49                                                                                                               │
│ 50 ## Verification                                                                                               │
│ 51 You can confirm the API is working by running the server and executing the `curl` commands above. A           │
│    successful `POST` request will return the newly created book with an assigned ID.  
