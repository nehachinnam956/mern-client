# Book Management System — Frontend

A React (Vite) frontend for a full-stack book management application, with JWT-based authentication, protected routes, and full CRUD support for books.

**Live App:** https://mern-client.vercel.app
**Backend Repo:** [mern-server](https://github.com/nehachinnam956/mern-server)

---

## Features

- User registration and login
- JWT stored client-side, attached automatically to requests via an Axios interceptor
- Protected routes — unauthenticated users are redirected to login
- Auto-logout on token expiration
- Book list with add, edit, and delete
- Search and pagination
- Responsive layout with sidebar and navbar

---

## Tech Stack

`React 19` · `Vite` · `React Router DOM` · `Axios` · `Context API` · `CSS`

---

## Project Structure

```
├── src/
│   ├── api/
│   │   └── axios.js           # Axios instance, JWT interceptor
│   ├── components/
│   │   ├── Navbar.jsx
│   │   ├── Sidebar.jsx
│   │   └── ProtectedRoute.jsx
│   ├── context/
│   │   └── AuthContext.jsx     # Auth state management
│   ├── pages/
│   │   ├── Home.jsx
│   │   ├── Login.jsx
│   │   ├── Register.jsx
│   │   └── Books.jsx
│   ├── styles/
│   ├── App.jsx
│   └── main.jsx
├── vercel.json                 # SPA rewrite rules for React Router
└── package.json
```

---

## Authentication Flow

```
User logs in
   → Backend returns JWT
   → Token stored in localStorage
   → Axios interceptor attaches token to every request
   → Protected routes check token before rendering
   → Expired/invalid token triggers auto-logout
```

---

## Running Locally

```bash
npm install
```

Create a `.env` file in the project root:
```
VITE_API_BASE_URL=http://localhost:8800/api
```

Start the dev server:
```bash
npm run dev
```

---

## Deployment

Deployed on [Vercel](https://vercel.com), connected to the [mern-server](https://github.com/nehachinnam956/mern-server) backend on Render. `VITE_API_BASE_URL` is set as an environment variable in the Vercel project pointing to the live backend URL. A `vercel.json` rewrite rule ensures client-side routes (e.g. `/login`, `/books`) resolve correctly on refresh.

---

## Author

**Neha Chinnam**
[GitHub](https://github.com/nehachinnam956)
