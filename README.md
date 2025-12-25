# ✈️ Aviation Services Management System

A comprehensive Full-Stack MERN (MongoDB, Express, React, Node) application designed to streamline airport operations, enhance passenger experiences, and provide robust administrative controls.

[![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://reactjs.org/)
[![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)](https://nodejs.org/)
[![MongoDB](https://img.shields.io/badge/MongoDB-4ea94b?style=for-the-badge&logo=mongodb&logoColor=white)](https://www.mongodb.com/)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Express.js](https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white)](https://expressjs.com/)
[![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)
[![Asgardeo](https://img.shields.io/badge/Asgardeo-FF7300?style=for-the-badge&logo=auth0&logoColor=white)](https://asgardeo.io/)

---

## �️ Project Architecture & Features

This project is split into two main components: a **Vite-powered React Frontend** and a **Node/Express Backend**.

### 🎨 Frontend (The "View")
The frontend handles the user interface and client-side logic.
- **Flight & Air Taxi Booking**: Interactive workflows for searching flights and booking private air taxis.
- **Seat Selection**: Dynamic seat mapping where users can select specific seats for their journey.
- **Real-Time Dashboards**: Separate views for Passengers (trips, boarding passes) and Admins (system oversight).
- **Flight Tracking**: A live status board to monitor flight arrivals and departures.
- **Authentication**: Integrated with **Asgardeo IAM** for secure login/signup and Role-Based Access Control (RBAC).

### ⚙️ Backend (The "Logic")
The backend manages data persistence and business rules.
- **RESTful API**: Clean endpoints for all CRUD (Create, Read, Update, Delete) operations.
- **Data Modeling**: Structured MongoDB schemas for Bookings, Users, and Requests.
- **Automated Emails**: Integrated **Nodemailer** to send HTML-formatted booking confirmations to passengers.
- **Validation Engine**: Server-side logic to ensure data integrity (e.g., verifying seat counts, validating passport details).
- **Regex Searching**: Efficient data retrieval using regular expressions for user-specific queries.

---

## 🔗 How the Parts Combine

The frontend and backend communicate via a **Client-Server Architecture**:
1.  **Request**: The Frontend (running on port 5173) sends an HTTP request (via Axios) to the Backend API.
2.  **Processing**: The Backend (running on port 3001) receives the request, validates the JWT token (if applicable), interacts with MongoDB, and processes business logic.
3.  **Persistence**: Data is saved to or retrieved from the **MongoDB Atlas** cloud database.
4.  **Response**: The Backend sends a JSON response back to the Frontend.
5.  **Update**: The Frontend receives the data and uses **TanStack Query** to update the UI without refreshing the page.

---

## 🛠️ Getting Started

### 1. Clone & Install
```bash
git clone https://github.com/RUSIRUDEVINDA/Aviation-Services-Management-System.git
```

### 2. Backend Setup
1.  Navigate to `backend/`.
2.  Install: `npm install`.
3.  Create `.env`:
    ```env
    MONGODB_USER=your_username
    MONGODB_PASS=your_password
    MONGODB_DB=airport_management
    ```
4.  Launch: `npm start`.

### 3. Frontend Setup
1.  Navigate to `frontend/`.
2.  Install: `npm install`.
3.  Launch: `npm run dev`.

---

## 🎓 Learning Concepts & CS Fundamentals

This project serves as a practical implementation of several core Computer Science and Software Engineering concepts:

### 1. Data Structures
- **Objects & JSON**: Used as the primary data exchange format between the frontend and backend.
- **Arrays**: Extensively used to store lists of passengers, seat selections, and flight schedules.
- **BSON (Binary JSON)**: The underlying data structure for MongoDB documents, optimized for high-speed read/write.

### 2. Algorithms
- **Filtering & Searching**: Implementation of search algorithms using MongoDB `$regex` to allow case-insensitive and partial matching for user bookings.
- **Validation Logic**: Conditional algorithms in the controller layer that verify business rules (e.g., ensuring `returnDate` exists only for `Round Trip` bookings).
- **Mapping & Transformation**: Using `.map()` and `.filter()` algorithms in React to dynamically render UI components from raw API data.

### 3. Software Engineering Concepts
- **Standardized REST API**: Implementation of the architectural style for networked applications.
- **Middleware**: Use of the **Chain of Responsibility** pattern for handling CORS and centralized error logging.
- **Asynchronous Programming**: Orchestrating non-blocking I/O operations using `async/await` and Promises for database and email services.
- **State Management**: Using client-side caching algorithms via TanStack Query to minimize redundant network requests.
- **Authentication (IAM)**: Implementing Identity and Access Management principles to secure user data.

---

