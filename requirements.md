# 🧾 Requirements Specifications for Backend Features

This document outlines the **technical and functional requirements** for key backend features of the **Airbnb Clone** project.

---

## 1️⃣ User Authentication

### Description  
Enables users to create accounts, log in securely, and manage their sessions.

### Functional Requirements
- Users can register with name, email, and password.  
- Passwords are encrypted using **bcrypt** before being stored.  
- Login returns a **JWT token** for authenticated access.  
- Auth middleware validates JWT for protected routes.  

### API Endpoints

| Method | Endpoint | Description |
|--------|-----------|-------------|
| POST | `/api/auth/register` | Register new user |
| POST | `/api/auth/login` | Log in existing user |
| GET | `/api/auth/profile` | Fetch logged-in user profile |
| PUT | `/api/auth/update` | Update user info |

### Input Validation
- Email must be in a valid format.  
- Password must be **at least 8 characters** long.  
- No duplicate emails allowed.

### Performance Criteria
- Response time: **< 1s**  
- Token expiration: **24 hours**

---

## 2️⃣ Property Management

### Description  
Allows users (hosts) to list, update, and delete properties.

### Functional Requirements
- Hosts can create property listings with images, price, and location.  
- Only property owners can update or delete their listings.  
- Properties are visible to all users.  

### API Endpoints

| Method | Endpoint | Description |
|--------|-----------|-------------|
| POST | `/api/properties` | Create new property |
| GET | `/api/properties` | Get all properties |
| GET | `/api/properties/:id` | Get single property |
| PUT | `/api/properties/:id` | Update property details |
| DELETE | `/api/properties/:id` | Delete property |

### Input Validation
- `title`, `price`, `location`, and `description` are required.  
- `price` must be a **positive number**.

### Performance Criteria
- Listing fetch time: **< 2s**  
- Pagination enabled for lists with more than 20 items.

---

## 3️⃣ Booking System

### Description  
Allows users to book available properties for specific dates.

### Functional Requirements
- Users can view property availability before booking.  
- Bookings prevent overlapping date ranges.  
- Only logged-in users can book.  

### API Endpoints

| Method | Endpoint | Description |
|--------|-----------|-------------|
| POST | `/api/bookings` | Create new booking |
| GET | `/api/bookings` | Get user’s bookings |
| GET | `/api/bookings/:id` | Get single booking |
| DELETE | `/api/bookings/:id` | Cancel booking |

### Input Validation
- `propertyId`, `checkIn`, and `checkOut` are required.  
- `checkOut` date must be after `checkIn`.  

### Performance Criteria
- Booking confirmation time: **< 3s**  
- Prevents **double booking** conflicts.

---

## 4️⃣ Payment Processing *(Optional Advanced Feature)*

### Description  
Handles secure payments using third-party APIs like **Stripe** or **PayPal**.

### Functional Requirements
- Secure checkout process for confirmed bookings.  
- Payment status updates for success or failure.  

### API Endpoints

| Method | Endpoint | Description |
|--------|-----------|-------------|
| POST | `/api/payments/create` | Initialize payment |
| POST | `/api/payments/webhook` | Handle Stripe webhook callbacks |

### Input Validation
- A valid `bookingId` must be provided.  
- Payment amount must match the booking total.

### Performance Criteria
- Payment success/failure logged in the database.  
- Stripe/PayPal API response time: **< 3s**.

---

### ✅ Summary

This backend system ensures:
- Secure authentication using JWT.  
- Efficient property and booking management.  
- Scalable performance and data integrity.  
- Integration-ready architecture for payments and extensions.

