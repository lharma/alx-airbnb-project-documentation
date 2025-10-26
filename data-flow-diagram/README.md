# Data Flow Diagram — Airbnb Clone Backend

## Overview
This document explains the **Data Flow Diagram (DFD)** for the Airbnb Clone backend system.  
The DFD illustrates how data moves between different entities (like users, hosts, and admins) and the system’s internal processes, such as authentication, booking management, and payments.

The diagram helps visualize the **flow of information**, ensuring a clear understanding of how input data is processed and stored in the database.

---

## 🧩 Main Entities and Processes

### External Entities:
1. **User (Guest)** – Interacts with the system to register, search, book, and make payments.  
2. **Host** – Adds, updates, or removes property listings.  
3. **Admin** – Manages users, bookings, and monitors the platform.  
4. **Payment Gateway** – Handles payments and refunds securely.

### Processes:
1. **User Registration & Authentication** – Validates new users and generates session tokens.  
2. **Property Management** – Allows hosts to create, update, or delete property listings.  
3. **Booking Management** – Handles availability checks, booking creation, and cancellations.  
4. **Payment Processing** – Sends and receives payment data between the system and the gateway.  
5. **Review System** – Collects, stores, and displays user reviews.

### Data Stores:
- **Users Table** – Stores user details and credentials.  
- **Properties Table** – Stores information about property listings.  
- **Bookings Table** – Stores booking details (dates, status, guest info).  
- **Payments Table** – Stores transaction details and statuses.  
- **Reviews Table** – Stores feedback and ratings.

---

## 🔄 Data Flow Summary
1. **User Registration** → User data sent → Auth Process → Data stored in Users Table.  
2. **Host Lists Property** → Property details sent → Property Process → Stored in Properties Table.  
3. **Guest Books Property** → Booking info sent → Booking Process → Stored in Bookings Table → Payment Request sent to Gateway.  
4. **Payment Gateway** → Sends confirmation → Stored in Payments Table.  
5. **User Leaves Review** → Review Process → Stored in Reviews Table.  

---

## 📁 File Details
- **Diagram:** `data-flow.png`
- **Tool Used:** [Draw.io](https://draw.io) or [Lucidchart](https://lucid.app)
- **Purpose:** To visualize data processing paths within the Airbnb Clone backend.

---

### 📄 Directory Structure
