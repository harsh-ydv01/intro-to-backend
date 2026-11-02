# Intro to Backend

A complete, production-ready backend built with **Node.js**, **Express**, and **MongoDB (Mongoose)** following modern ES Modules standards.

[![GitHub Repo](https://img.shields.io/badge/GitHub-Repository-blue?logo=github)](https://github.com/harsh-ydv01/intro-to-backend)
[![License: ISC](https://img.shields.io/badge/License-ISC-blue.svg)](https://opensource.org/licenses/ISC)
[![Node.js](https://img.shields.io/badge/Node.js-v18%2B-green.svg)](https://nodejs.org/)

---

## 📁 Project Structure

```
backend/
├── src/
│   ├── config/
│   │   ├── constants.js          # App constants (DB_NAME, etc.)
│   │   └── database.js           # Mongoose DB connection logic
│   ├── controllers/
│   │   ├── post.controller.js    # Character post CRUD operations
│   │   └── user.controller.js    # Authentication & user operations
│   ├── models/
│   │   ├── post.model.js         # Post Mongoose schema & model
│   │   └── user.model.js         # User schema, bcrypt hashing & password comparison
│   ├── routes/
│   │   ├── post.route.js         # Express router for /api/v1/posts
│   │   └── user.route.js         # Express router for /api/v1/users
│   ├── app.js                    # Express app initialization & route mounting
│   └── index.js                  # App entry point & server listener
├── .env.sample                   # Sample environment variable template
├── .gitignore                    # Ignored files (node_modules, .env)
├── package.json                  # Project dependencies & scripts
└── README.md
```

---

## 🛠 Tech Stack

- **Runtime:** [Node.js](https://nodejs.org/) (ES Modules `"type": "module"`)
- **Framework:** [Express.js](https://expressjs.com/)
- **Database:** [MongoDB](https://www.mongodb.com/) via [Mongoose](https://mongoosejs.com/)
- **Security:** [bcrypt](https://www.npmjs.com/package/bcrypt) for password hashing
- **Environment Management:** [dotenv](https://www.npmjs.com/package/dotenv)
- **Dev Tooling:** [nodemon](https://nodemon.io/) for live reload

---

## 🚀 Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/harsh-ydv01/intro-to-backend.git
cd intro-to-backend
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Configure Environment Variables
Copy `.env.sample` to `.env`:
```bash
cp .env.sample .env
```

Set your values inside `.env`:
```env
PORT=4000
MONGODB_URI=mongodb+srv://<username>:<password>@cluster0.xxxxxx.mongodb.net/
```

> **Note:** Make sure your IP address is whitelisted in **MongoDB Atlas** under **Network Access** (`0.0.0.0/0` or your current IP).

### 4. Run the Server

**Development Mode (with live reload):**
```bash
npm run dev
```

**Production Mode:**
```bash
npm start
```

---

## 📡 API Endpoints

All endpoints are prefixed with `/api/v1`.

### 👤 User Routes (`/api/v1/users`)

| Method | Endpoint | Description | Request Body |
| :--- | :--- | :--- | :--- |
| `POST` | `/register` | Register a new user | `{ "username": "...", "email": "...", "password": "..." }` |
| `POST` | `/login` | Log in user | `{ "email": "...", "password": "..." }` |
| `POST` | `/logout` | Log out user | `{ "email": "..." }` |

### 📝 Post Routes (`/api/v1/posts`)

| Method | Endpoint | Description | Request Body / Params |
| :--- | :--- | :--- | :--- |
| `POST` | `/create` | Create a character post | `{ "name": "...", "description": "...", "age": 25 }` |
| `GET` | `/get-posts` | Retrieve all posts | None |
| `PATCH` | `/update/:id` | Update post by ID | Fields to update in JSON body |
| `DELETE` | `/delete/:id` | Delete post by ID | None (ID in URL parameter) |

---

## 📄 License

This project is licensed under the [ISC License](LICENSE).
