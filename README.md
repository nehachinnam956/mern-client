# Book Management System — Backend API

A REST API built with **Node.js**, **Express**, and **MongoDB (Mongoose)** that powers a full-stack book management application. Supports user authentication, JWT-based authorization, and full CRUD operations on books with pagination and search.

**Live API:** https://mern-server-3tiw.onrender.com
**Frontend Repo:** [mern-client](https://github.com/nehachinnam956/mern-client)

---

## Features

- User registration and login with hashed passwords (bcrypt)
- JWT-based authentication and route protection
- Role-based structure (user / admin)
- Full CRUD for books (Create, Read, Update, Delete)
- Server-side pagination and search (by title or author)
- MongoDB Atlas cloud database integration
- Deployed on Render with environment-based configuration

---

## Tech Stack

`Node.js` · `Express.js` · `MongoDB` · `Mongoose` · `JWT` · `bcryptjs` · `dotenv` · `cors`

---

## Project Structure

```
├── controllers/
│   ├── authController.js     # Register & login logic
│   └── bookController.js     # Book CRUD, pagination, search
├── middleware/
│   └── authMiddleware.js     # JWT verification
├── models/
│   ├── User.js                # User schema
│   └── Book.js                 # Book schema
├── routes/
│   ├── authRoutes.js
│   └── bookRoutes.js
├── seed.js                    # One-time sample data insert
├── server.js                  # App entry point
└── package.json
```

---

## API Reference

### Auth

| Method | Endpoint | Description | Protected |
|---|---|---|---|
| POST | `/api/auth/register` | Register a new user | No |
| POST | `/api/auth/login` | Login, returns JWT | No |

**Register body**
```json
{ "username": "neha", "email": "neha@test.com", "password": "yourpassword" }
```

**Login response**
```json
{ "token": "JWT_TOKEN", "user": { "id": "...", "username": "neha", "email": "neha@test.com", "role": "user" } }
```

### Books

| Method | Endpoint | Description | Protected |
|---|---|---|---|
| GET | `/api/books?page=1&limit=5&search=gatsby` | List books, paginated & searchable | No |
| POST | `/api/books` | Create a book | Yes (Bearer token) |
| PUT | `/api/books/:id` | Update a book | Yes (Bearer token) |
| DELETE | `/api/books/:id` | Delete a book | Yes (Bearer token) |

---

## Running Locally

```bash
npm install
```

Create a `.env` file:
```
MONGO_URL=mongodb+srv://<username>:<password>@cluster0.xxxxx.mongodb.net/bookdb
JWT_SECRET=your_secret_key
PORT=8800
```

Seed sample data (run once only):
```bash
node seed.js
```

Start the server:
```bash
npm start
```

---

## Deployment

Deployed on [Render](https://render.com) as a free web service, connected to a [MongoDB Atlas](https://www.mongodb.com/atlas) cluster with network access open to all IPs (required since Render doesn't use a static IP on the free tier).

---

## Author

**Neha Chinnam**
[GitHub](https://github.com/nehachinnam956)
