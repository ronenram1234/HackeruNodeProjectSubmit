# Node.js Final Project – Business Cards Management API

This project is a backend RESTful API developed with Node.js and Express.js. It is designed to manage business card information and user accounts, including registration, login, editing, and admin features. It connects to a MongoDB database and includes middleware, validation, and logging mechanisms.

## 🔧 Technologies Used

- **Node.js**
- **Express.js**
- **MongoDB + Mongoose**
- **JWT (jsonwebtoken)**
- **bcryptjs**
- **dotenv**
- **cors**
- **joi**
- **morgan**

## 📁 Project Structure

```
.
├── index.js               # Entry point
├── .env                   # Environment variables
├── /models                # Mongoose models (User, Card, Login)
├── /routes                # API routes (users, cards)
├── /middlewares           # Middleware (auth, logger)
├── /utils                 # Utility functions
├── /logs                  # Log files for 400+ errors 
├── package.json
└── dataInit.json          # Initial data for seeding users and cards
```

## 🚀 Getting Started

1. **Clone the repository** and run:

```bash
npm install
```

2. **Set up `.env` file** with the following keys:

```
PORT=YOUR_PORT
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
```

3. **Run the server**:

```bash
npm start
```

## 🧪 API Endpoints

### Users

| Method | URL              | Description              | Access         |
|--------|------------------|--------------------------|----------------|
| POST   | `/users`         | Register user            | Public         |
| POST   | `/users/login`   | Login user               | Public         |
| GET    | `/users`         | Get all users            | Admin only     |
| GET    | `/users/:id`     | Get user by ID           | Self/Admin     |
| PUT    | `/users/:id`     | Edit user                | Self only      |
| PATCH  | `/users/:id`     | Toggle isBusiness        | Self only      |
| DELETE | `/users/:id`     | Delete user              | Self/Admin     |

### Cards

| Method | URL                   | Description             | Access              |
|--------|-----------------------|-------------------------|---------------------|
| GET    | `/cards`              | Get all cards           | Public              |
| GET    | `/cards/my-cards`     | Get user's own cards    | Registered user     |
| GET    | `/cards/:id`          | Get card by ID          | Public              |
| POST   | `/cards`              | Create card             | Business user only  |
| PUT    | `/cards/:id`          | Edit card               | Card owner only     |
| PATCH  | `/cards/:id`          | Like/Dislike card       | Registered user     |
| PATCH  | `\cards\bizNumber\:id`| Edir bizNumber          | Admin               |
| DELETE | `/cards/:id`          | Delete card             | Owner/Admin         |

## 🔐 Features

- **JWT-based Authentication**
- **Role-based Authorization**
- **Encrypted passwords with bcryptjs**
- **Joi validation on all request bodies**
- **Detailed request logging via morgan**
- **Support for multiple environments (local/cloud)**

## 📦 Initial Data

Includes 3 users (regular, business, admin) and 3 sample cards. Use `dataInit.json` or `insertRecords` script for seeding.

## 📝 Bonus Features (Optional)

- **Admin-editable bizNumber** with uniqueness check.
- **File-based logger** for 400+ errors.
- **Temporary lockout** after 3 failed login attempts for 24 hours.

## 📄 License

This project is part of a Node.js course at HackerU.

---

*Developed as a final bode project to demonstrate full-stack backend capabilities.*
