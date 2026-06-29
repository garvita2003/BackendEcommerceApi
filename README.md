# BackendEcommerceApi 🛒

## 📌 Introduction

**BackendEcommerceApi** is a full-featured Node.js and Express-based REST API for an e-commerce application. This project demonstrates the implementation of complete CRUD operations for an e-commerce platform with user authentication, product management, shopping cart functionality, and order processing. The API provides secure access through JWT authentication and role-based authorization for users and admins.

**Key Features:**
- ✅ User authentication with JWT tokens
- ✅ Password encryption using Crypto-JS
- ✅ Complete CRUD operations for users, products, carts, and orders
- ✅ Role-based access control (Admin & User)
- ✅ MongoDB cloud database integration
- ✅ Query-based product filtering (new, category)
- ✅ Order and user statistics tracking
- ✅ RESTful API design
- ✅ Error handling and validation

---

## 🔄 Process / Flow

**Authentication Flow:**
1. User registers with username, email, and password
2. Password encrypted using Crypto-JS AES algorithm
3. User data saved to MongoDB
4. On login, password decrypted and verified
5. JWT token generated upon successful login
6. Token valid for 11 days
7. Token required for all authorized operations

**CRUD Operations Flow:**
1. User/Admin makes API request with JWT token
2. Token verified by middleware (verifyToken)
3. Authorization checked (verifyTokenAndAuthorization, verifyTokenAndAdmin)
4. Operation performed if authorized
5. Database updated through Mongoose
6. Response returned to client

**Product Query Flow:**
1. Products can be queried by: all products, new products, or by category
2. Results filtered based on query parameters
3. Products returned as JSON array

---

## 🛠️ Technology Used

| Component | Technology |
|-----------|-----------|
| **Runtime** | Node.js |
| **Framework** | Express.js |
| **Database** | MongoDB (Cloud Atlas) |
| **Authentication** | JWT (JsonWebToken) |
| **Password Encryption** | Crypto-JS (AES) |
| **Environment Variables** | dotenv |
| **Development** | Nodemon |
| **Payment** | Stripe |

---

## 🎓 Skills Gained

**Backend Development:**
- ✅ Express.js server setup and routing
- ✅ REST API design and implementation
- ✅ HTTP methods (GET, POST, PUT, DELETE)
- ✅ Request/response handling
- ✅ Middleware usage and custom middleware

**Authentication & Security:**
- ✅ User authentication and registration
- ✅ JWT token generation and verification
- ✅ Password encryption and decryption
- ✅ Role-based access control
- ✅ Authorization middleware implementation
- ✅ Security best practices

**Database:**
- ✅ MongoDB connection and configuration
- ✅ Mongoose schema design and modeling
- ✅ CRUD operations implementation
- ✅ Data validation and error handling
- ✅ Database aggregation pipelines
- ✅ Query optimization

**API Development:**
- ✅ RESTful API principles
- ✅ Status codes and error handling
- ✅ Query parameter handling
- ✅ JSON data serialization
- ✅ API testing with Postman
- ✅ Token-based authorization

---

## 📂 Project Structure

```
BackendEcommerceApi/
├── models/                      # Database schemas
│   ├── User.js                  # User model with authentication
│   ├── Product.js               # Product model
│   ├── Cart.js                  # Shopping cart model
│   └── Order.js                 # Order model
│
├── routes/                      # API routes
│   ├── auth.js                  # Authentication routes (register, login)
│   ├── user.js                  # User management routes
│   ├── product.js               # Product management routes
│   ├── cart.js                  # Cart management routes
│   ├── order.js                 # Order management routes
│   └── verifyToken.js           # JWT verification middleware
│
├── index.js                     # Main server entry point
├── package.json                 # Project dependencies
├── package-lock.json            # Locked dependency versions
├── .env                         # Environment variables (not in repo)
└── README.md                    # Documentation
```

---

## 📸 Demonstration

**API Testing Screenshots:**
Multiple Postman testing screenshots demonstrating CRUD operations across all endpoints.

![image](https://github.com/garvita2003/Backend---EcommerceApi/assets/102051676/32d03cb1-6ff0-4c32-8a07-4c8512836cf8)
![image](https://github.com/garvita2003/Backend---EcommerceApi/assets/102051676/3b65e013-e414-4511-9b7c-8ffa4be1024c)
![image](https://github.com/garvita2003/Backend---EcommerceApi/assets/102051676/c400da81-6295-485d-84ab-aaad9237cc29)
![image](https://github.com/garvita2003/Backend---EcommerceApi/assets/102051676/a2bcc4f0-ff58-448a-8a3d-11209f83fa69)
![image](https://github.com/garvita2003/Backend---EcommerceApi/assets/102051676/747f400a-23c5-4191-a3ac-432df97c1ea6)
![image](https://github.com/garvita2003/Backend---EcommerceApi/assets/102051676/29a9c03c-1990-4518-a60f-05da9d12539b)
![image](https://github.com/garvita2003/Backend---EcommerceApi/assets/102051676/c4842902-c691-4f6d-8342-74733806b20f)
![image](https://github.com/garvita2003/Backend---EcommerceApi/assets/102051676/f10410f5-f280-4ce6-ab9d-92c43a9d2aac)
![image](https://github.com/garvita2003/Backend---EcommerceApi/assets/102051676/3a05668a-4574-4266-8a48-44dfa546059d)
![image](https://github.com/garvita2003/Backend---EcommerceApi/assets/102051676/fd340dd4-e0d1-4928-bb43-093d1fbdc6de)
![image](https://github.com/garvita2003/Backend---EcommerceApi/assets/102051676/2125269d-dde7-4527-ac49-f4e66f1d6b57)
![image](https://github.com/garvita2003/Backend---EcommerceApi/assets/102051676/39943f5b-5e63-4c61-b0ae-155fdff501ea)
![image](https://github.com/garvita2003/Backend---EcommerceApi/assets/102051676/1974d671-88a1-4173-a193-0cbc902035c0)
![image](https://github.com/garvita2003/Backend---EcommerceApi/assets/102051676/1d602419-5b5c-496d-8061-e2b2f8f3f6f8)
![image](https://github.com/garvita2003/Backend---EcommerceApi/assets/102051676/b55903cd-c570-4af9-a20d-6fdb55d16079)
![image](https://github.com/garvita2003/Backend---EcommerceApi/assets/102051676/7b214525-8fc3-4478-80ce-6ad2a8a5b8a3)
![image](https://github.com/garvita2003/Backend---EcommerceApi/assets/102051676/05b521c9-184e-40aa-b46a-43b57bc386da)
![image](https://github.com/garvita2003/Backend---EcommerceApi/assets/102051676/d359c4cb-6fff-4f54-8411-e69c08453c83)
![image](https://github.com/garvita2003/Backend---EcommerceApi/assets/102051676/21ba261d-9f73-46f3-a0e4-20264095203e)

---

## ⚙️ Setup Instructions

### Prerequisites:
- Node.js and npm installed on your system
- MongoDB Atlas account (cloud.mongodb.com) with cluster created
- Postman (for API testing)
- Git and command-line terminal

### Installation Steps:

```bash
# 1. Clone the repository
git clone https://github.com/garvita2003/BackendEcommerceApi.git
cd BackendEcommerceApi

# 2. Install dependencies
npm install

# 3. Create .env file in root directory
# Add the following variables:
# MONGO_URL=your_mongodb_connection_string
# PORT=5000
# PASS_SEC=your_encryption_secret_key
# JWT_SEC=your_jwt_secret_key

# 4. Start the development server
npm start
# Server will run on http://localhost:5000
```
---

## 📋 API Endpoints

### Authentication Routes (`/api/auth`)

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| POST | `/register` | Register new user | No |
| POST | `/login` | Login existing user | No |

### User Routes (`/api/users`)

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| PUT | `/:id` | Update user profile | Yes (User or Admin) |
| GET | `/find/:id` | Get specific user | Yes (Admin) |
| GET | `/` | Get all users | Yes (Admin) |
| GET | `/stats` | Get user statistics | Yes (Admin) |
| DELETE | `/:id` | Delete user | Yes (User or Admin) |

### Product Routes (`/api/products`)

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| POST | `/` | Create product | Yes (Admin) |
| PUT | `/:id` | Update product | Yes (Admin) |
| GET | `/find/:id` | Get specific product | No |
| GET | `/` | Get all products | No |
| GET | `/?new=true` | Get newest products | No |
| GET | `/?category=category_name` | Get products by category | No |
| DELETE | `/:id` | Delete product | Yes (Admin) |

### Cart Routes (`/api/carts`)

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| POST | `/` | Create cart | Yes (User) |
| PUT | `/:id` | Update cart | Yes (User or Admin) |
| GET | `/find/:userId` | Get user's cart | Yes (User or Admin) |
| GET | `/` | Get all carts | Yes (Admin) |
| DELETE | `/:id` | Delete cart | Yes (User or Admin) |

### Order Routes (`/api/orders`)

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| POST | `/` | Create order | Yes (User) |
| PUT | `/:id` | Update order | Yes (Admin) |
| GET | `/find/:userId` | Get user's orders | Yes (User or Admin) |
| GET | `/` | Get all orders | Yes (Admin) |
| GET | `/income` | Get order statistics | Yes (Admin) |
| DELETE | `/:id` | Delete order | Yes (Admin) |
