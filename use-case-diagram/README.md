# Use Case Diagram — Airbnb Clone Backend

## Overview
This document contains the **Use Case Diagram** for the **Airbnb Clone Backend** project.  
The diagram visually represents the key system interactions between different actors (users, hosts, and the admin) and the major functionalities they can perform in the system.

## Actors
1. **User (Guest):** A registered user who can browse and book properties.
2. **Host:** A registered user who can list, update, or remove properties.
3. **Admin:** The system administrator who manages user accounts and monitors platform activities.
4. **Payment Gateway (External System):** Processes payments securely for bookings.

## Main Use Cases
Below are the main use cases shown in the diagram:

### 👤 User (Guest)
- Register and log in to the system  
- Search for properties  
- View property details  
- Book a property  
- Make payments for bookings  
- Leave reviews for properties

### 🏠 Host
- Register and log in to the system  
- List new properties  
- Edit or delete listed properties  
- View bookings for their properties  
- Respond to reviews

### 🛠️ Admin
- Manage user accounts (activate/deactivate)  
- Monitor listings and bookings  
- Handle reports or flagged content

### 💳 Payment Gateway
- Process and confirm payments  
- Handle refunds for canceled bookings

## Relationships
- A **User** can book **many properties**.  
- A **Host** can own **many properties**.  
- A **Booking** generates a **Payment** via the Payment Gateway.  
- Both **User** and **Host** can interact with **Reviews**.

## File Details
- **Diagram:** `use-case-diagram.png`
- **Format:** Exported from [Draw.io](https://draw.io)
- **Purpose:** To serve as a visual reference for understanding the core system interactions before backend implementation.

## How to View
Open the `use-case-diagram.png` file in this directory to view the full diagram representation of system actors and use cases.

---

### 📁 Directory Structure
