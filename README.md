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

**Language Composition:**
- JavaScript: 100%

**Core Dependencies:**
- `express` - Web application framework
- `mongoose` - MongoDB object modeling
- `jsonwebtoken` - JWT authentication
- `crypto-js` - Password encryption
- `dotenv` - Environment variable management
- `nodemon` - Development auto-reload
- `stripe` - Payment processing

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

![Postman API Testing](https://github.com/garvita2003/Backend---EcommerceApi/assets/102051676/32d03cb1-6ff0-4c32-8a07-4c8512836cf8)

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

### Environment Variables (.env):

```
MONGO_URL=mongodb+srv://username:password@cluster.mongodb.net/databasename
PORT=5000
PASS_SEC=your_secret_key_for_password_encryption
JWT_SEC=your_secret_key_for_jwt_tokens
STRIPE_API_KEY=your_stripe_api_key
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

---

## 🔐 Authentication & Authorization

**Token Format:**
```
Authorization: Bearer <your_jwt_token>
```

**User Roles:**
- **User**: Can manage their own profile, cart, and orders
- **Admin**: Can manage all users, products, carts, and orders

**Middleware Verification:**
- `verifyToken` - Checks if token is valid
- `verifyTokenAndAuthorization` - User can access only their data (or admin can access all)
- `verifyTokenAndAdmin` - Only admin can access

---

## 💡 Example Requests

### Register User
```bash
POST /api/auth/register
Content-Type: application/json

{
  "username": "john_doe",
  "email": "john@example.com",
  "password": "securePassword123"
}
```

### Login User
```bash
POST /api/auth/login
Content-Type: application/json

{
  "username": "john_doe",
  "password": "securePassword123"
}
# Returns: { ...user_data, accessToken: "jwt_token" }
```

### Create Product (Admin Only)
```bash
POST /api/products
Authorization: Bearer <admin_token>
Content-Type: application/json

{
  "title": "Product Name",
  "description": "Product description",
  "price": 99.99,
  "image": "image_url",
  "categories": ["electronics"]
}
```

### Create Cart (User)
```bash
POST /api/carts
Authorization: Bearer <user_token>
Content-Type: application/json

{
  "userId": "user_id",
  "products": [
    {
      "productId": "product_id",
      "quantity": 2
    }
  ]
}
```

---

## 🧪 Testing with Postman

1. **Import Collection** - Import the API endpoints into Postman
2. **Set Environment Variables** - Add base URL and token to Postman environment
3. **Register & Login** - Test authentication endpoints first
4. **Test CRUD Operations** - Test each endpoint with appropriate authorization
5. **Verify Responses** - Check JSON response structure and status codes

---

## 📊 Database Models

**User Model:**
- username, email, password (encrypted)
- isAdmin (boolean)
- createdAt, updatedAt

**Product Model:**
- title, description, image
- categories, price
- createdAt, updatedAt

**Cart Model:**
- userId, products array
- quantity for each product
- createdAt, updatedAt

**Order Model:**
- userId, products array
- amount, status
- createdAt, updatedAt

---

## ⚠️ Security Notes

- Passwords are encrypted using Crypto-JS AES algorithm
- JWT tokens expire after 11 days
- All sensitive operations require authentication
- Role-based access control prevents unauthorized operations
- Environment variables store sensitive data (not in repository)
- Use HTTPS in production

---

## 🚀 Available Scripts

```bash
# Start development server with auto-reload
npm start

# Install dependencies
npm install

# Add specific package
npm add <package_name>

# Add crypto-js
npm add crypto-js

# Add jsonwebtoken
npm add jsonwebtoken
```

---

## 📝 Notes

- Use Postman or similar tools to test API endpoints
- Ensure MongoDB is running and connection string is correct
- Check `.env` file for all required environment variables
- Token should be sent in Authorization header as "Bearer token"
- Admin operations require isAdmin flag set to true in user model
- All timestamps are automatically managed by Mongoose

---

## 🔗 Useful Resources

- [Express.js Documentation](https://expressjs.com/)
- [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
- [Mongoose Documentation](https://mongoosejs.com/)
- [JWT Documentation](https://jwt.io/)
- [Crypto-JS Documentation](https://cryptojs.gitbook.io/docs/)
- [Postman Download](https://www.postman.com/downloads/)
