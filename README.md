# Hapi Bookshelf API

A comprehensive RESTful API for managing a digital bookshelf built with Hapi.js framework. This API allows you to perform full CRUD operations on a book collection with features like adding, retrieving, updating, and deleting books.

## 📖 Description

This project implements a robust bookshelf management system using Hapi.js, a powerful Node.js framework for building scalable applications and services. The API provides endpoints to manage a collection of books with features including:

- ✅ Add new books to the collection
- 📚 Retrieve all books or specific books by ID
- ✏️ Update existing book information
- 🗑️ Delete books from the collection
- 🔍 Search and filter books by various criteria
- 📊 Track reading status and completion

## 🛠️ Tech Stack

- **Node.js** - JavaScript runtime environment
- **Hapi.js** - Rich framework for building applications and services
- **nanoid** - Secure, URL-friendly unique string ID generator
- **ESLint** - Code linting and formatting

## 📋 Prerequisites

Before you begin, ensure you have the following installed on your system:

- [Node.js](https://nodejs.org/) (v14.x or above recommended)
- [npm](https://www.npmjs.com/) (v6.x or above recommended)
- Git (for cloning the repository)

## 🚀 Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/rzkyalbani/hapi-bookshelf-api.git
   ```

2. **Navigate to the project directory:**
   ```bash
   cd hapi-bookshelf-api
   ```

3. **Install dependencies:**
   ```bash
   npm install
   ```

4. **Start the development server:**
   ```bash
   npm start
   ```

5. **Verify installation:**
   The server will start on `http://localhost:9000`. You should see a confirmation message in your terminal.

## 📊 API Endpoints

### Books Management

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/books` | Retrieve all books |
| `GET` | `/books/{id}` | Retrieve a specific book by ID |
| `POST` | `/books` | Add a new book |
| `PUT` | `/books/{id}` | Update an existing book |
| `DELETE` | `/books/{id}` | Delete a book |

### Query Parameters (GET /books)

- `name` - Filter books by title
- `reading` - Filter by reading status (0 or 1)
- `finished` - Filter by completion status (0 or 1)

### Book Object Structure

```json
{
  "id": "string",
  "name": "string",
  "year": "number",
  "author": "string",
  "summary": "string",
  "publisher": "string",
  "pageCount": "number",
  "readPage": "number",
  "reading": "boolean",
  "finished": "boolean",
  "insertedAt": "string (ISO date)",
  "updatedAt": "string (ISO date)"
}
```

## 📝 Usage Examples

### Add a New Book
```bash
curl -X POST http://localhost:9000/books \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Belajar Node.js",
    "year": 2023,
    "author": "John Doe",
    "summary": "Panduan lengkap belajar Node.js",
    "publisher": "Tech Publisher",
    "pageCount": 300,
    "readPage": 50,
    "reading": true
  }'
```

### Get All Books
```bash
curl http://localhost:9000/books
```

### Get Books by Reading Status
```bash
curl http://localhost:9000/books?reading=1
```

### Update a Book
```bash
curl -X PUT http://localhost:9000/books/{bookId} \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Updated Book Title",
    "readPage": 100
  }'
```

### Delete a Book
```bash
curl -X DELETE http://localhost:9000/books/{bookId}
```

## 🔧 Development

### Available Scripts

- **Start the server:**
  ```bash
  npm start
  ```

- **Run ESLint for code quality:**
  ```bash
  npm run lint
  ```

- **Auto-fix ESLint issues:**
  ```bash
  npm run lint -- --fix
  ```

### Code Style

This project follows the Airbnb JavaScript style guide. ESLint is configured to enforce consistent code formatting and catch potential issues.

## 📁 Project Structure

```
hapi-bookshelf-api/
├── src/
│   ├── handler/        # Request handlers
│   ├── routes/         # API route definitions
│   └── server.js       # Server configuration
├── package.json        # Project dependencies and scripts
├── .eslintrc.json      # ESLint configuration
└── README.md          # Project documentation
```

## 🚦 Response Status Codes

- `200` - Success
- `201` - Created successfully
- `400` - Bad request (validation error)
- `404` - Resource not found
- `500` - Internal server error

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the ISC License. See the LICENSE file for details.

## 👨‍💻 Author

**Rizky Albani** - [@rzkyalbani](https://github.com/rzkyalbani)

## 🙏 Acknowledgments

- Hapi.js community for the excellent framework
- Node.js team for the runtime environment
- Contributors and testers

---

⭐ **Star this repository if you found it helpful!**
