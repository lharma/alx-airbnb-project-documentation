from pathlib import Path

# Content for the README.md file
content = """# Airbnb Clone — Use Case Diagram

## Overview
The **Use Case Diagram** illustrates the main interactions between users (actors) and the Airbnb backend system.  
It shows how **Guests**, **Hosts**, and **Admins** perform key actions such as registering, managing listings, booking stays, and processing payments.

This diagram helps visualize how each type of user interacts with the system’s major functionalities.

---

## Actors

| Actor | Description |
|--------|--------------|
| **Guest** | A registered user who can search, book, and review properties. |
| **Host** | A user who can list properties and manage bookings. |
| **Admin** | Manages users, properties, and oversees the entire system. |
| **System** | The backend API that handles authentication, data storage, and processing. |

---

## Main Use Cases

### 1. User Authentication
- **Register Account** – Users create a new account (Guest or Host).
- **Login** – Users sign in using credentials.
- **Logout** – Ends an active session.

### 2. Property Management (Host)
- **Add Property** – Host lists a new property.
- **Edit Property** – Host updates property details.
- **Delete Property** – Host removes a listing.
- **View Property** – Guests and Hosts can view available properties.

### 3. Booking System (Guest & Host)
- **Search Property** – Guest filters properties by location, price, and availability.
- **Book Property** – Guest makes a reservation.
- **Cancel Booking** – Guest or Host cancels a booking.
- **View Bookings** – Both can see active and past bookings.

### 4. Payment Management
- **Make Payment** – Guest pays for booking via Stripe or similar service.
- **View Payment Status** – Guest and Host can view transaction details.
- **Refund Payment** – Admin or Host can process refunds if necessary.

### 5. Review System
- **Add Review** – Guest leaves a review and rating after stay.
- **View Reviews** – Users can view property ratings and reviews.

### 6. Admin Functions
- **Manage Users** – Admin can disable or remove users.
- **Manage Listings** – Admin oversees properties.
- **View Reports** – Admin checks booking and payment statistics.

---

## Diagram Relationships

| Relationship | Description |
|---------------|--------------|
| Guest → Booking | A Guest can make multiple bookings. |
| Host → Property | A Host can list multiple properties. |
| Property → Booking | Each property can be booked multiple times. |
| Booking → Payment | Each booking leads to one payment. |
| Guest → Review | Guests can leave multiple reviews. |
| Property → Review | Properties can receive multiple reviews. |
| Admin → All Entities | Admin has access to manage users, listings, and payments. |

---

## How to Create the Diagram (Draw.io Instructions)

1. Visit [https://app.diagrams.net/](https://app.diagrams.net/).  
2. Choose **Blank Diagram** → name it **use-case-diagram**.  
3. Add **Actors** (Guest, Host, Admin) as stick figures on the left.  
4. Add **System boundary** labeled *“Airbnb Backend System”*.  
5. Inside it, draw **ellipses** for each use case:
   - Register Account  
   - Login  
   - Add Property  
   - Book Property  
   - Make Payment  
   - Add Review  
   - Manage Users (Admin)
6. Use **arrows** (→) or lines to connect actors to their respective use cases.
7. When done, export as PNG and save it in:
