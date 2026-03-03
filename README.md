# AgriSwap — Smart Barter System

<p align="center">
  <em>A trust-enabled agricultural exchange platform for small farmers to transparently barter surplus produce, equipment, labor, and resources.</em>
</p>

## 📖 Overview

AgriSwap is built to empower farmers through a fair, transparent exchange network. The platform connects farmers directly with other farmers and customers, allowing them to list crops, farming equipment, and services for barter or trade without relying solely on traditional currency transfers. 

The application utilizes a **Vanilla Web Stack** for a robust and extremely fast frontend, coupled with a solid **Node.js/Express Backend**.

## ✨ Key Features
- **Secure Authentication:** Firebase-powered login (Google Sign-In integration) ensuring that user profiles, barter listings, and histories are safe.
- **Multilingual Support:** A built-in Google Translate integration providing seamless browsing in **English (Default), Hindi, Marathi, Kannada, and Telugu**.
- **Role-Based Workflows:** Distinct dashboard capabilities and actions catered to either a **Farmer** or a **Customer**.
- **The Barter Market:** Browse through various categories of agricultural commodities.
- **Export Connect:** Global visibility for surplus stock for export markets.
- **Interactive UI Design:** Lucide Icons, Modern Fonts (Inter & Outfit), responsive design for all screen sizes (mobile and desktop), and rich visual animations.

## 🏗️ Architecture Design

AgriSwap follows a modern, decoupled client-server architecture designed for high performance, security, and scalability without the overhead of heavy frameworks.

### 1. Presentation Layer (Frontend)
Built with **HTML5, Vanilla CSS, and modular Vanilla JS**. It operates as a fast Single Page Application (SPA).
- **UI Components:** Reusable vanilla JS modules (e.g., `navbar.js`, `listingCard.js`) render the views dynamically.
- **State Management:** A centralized `state.js` maintains session data, UI state, and active localization preferences.
- **Client Routing:** Intercepts navigation to provide seamless, instant transitions (`app.js`) without full page reloads.

### 2. Application API Layer (Backend)
A lightweight **Node.js & Express.js** server acts as the secure intermediary between the client and the data layer.
- **RESTful Endpoints:** Serves as the gateway for complex queries, securely handling business logic.
- **Security Middleware:** Integrates `cors` and `express-rate-limit` to prevent abuse and manage cross-origin traffic safely.
- **Auth Verification:** Uses `firebase-admin` to validate JWT bearer tokens sent from the frontend before processing sensitive requests.

### 3. Data & Identity Layer (Firebase)
- **Authentication:** **Firebase Auth** handles the Google Sign-In flow securely on the client side.
- **Database:** Serves as the primary serverless NoSQL datastore for user profiles, product listings, and barter histories. The backend securely interacts with this layer using the Admin SDK.

### 🔄 System Data Flow
1. **User Action:** The user logs in via Firebase Auth on the Frontend.
2. **Token Generation:** The client receives a secure JWT.
3. **API Request:** The client makes a REST request to the Node.js Backend, attaching the JWT in the Authorization header.
4. **Validation:** The Backend verifies the JWT using the Firebase Admin SDK.
5. **Data Interaction:** Upon successful validation, the Backend queries or mutates the Firebase datastore and returns the response to the client.

## 🤝 Contributors

This project was built during the Hackathon by **The Core Coders** team.

- **Frontend Development:** Mahammadzeeshan Madras, Pranav Angadi
- **Backend Development:** Mayur Habib, Vikyat Haveri

---
<p align="center">
  <i>Empowering India's farmers through fair exchange. 🇮🇳</i>
</p>
