# 🌿 B2B Hyperlocal & National Marketplace

A production-ready, scalable B2B marketplace platform designed to connect wholesalers and buyers. It features intelligent geospatial search, real-time inventory management, and an end-to-end order processing engine.

## 🚀 Core Features

### 🌍 Intelligent Geospatial Search
* **Smart Proximity Routing:** Utilizes MongoDB `$geoNear` to automatically calculate distances and sort products from closest to farthest.
* **National Discovery:** Removes hard radius limits to allow buyers to discover nationwide deals seamlessly.
* **Amazon-Style Discovery:** URL-driven search (`?q=`), case-insensitive matching, and dynamic category filters.

### 🔐 Auth & Smart Onboarding
* **Multi-Step Flow:** OTP verification, Role selection (Buyer/Seller), and Business Info/GST capture.
* **Security:** JWT-based session management and Role-Based Access Control (RBAC).

### 📦 Seller Inventory Console
* **Private Management:** Dedicated Inventory page for sellers to view their own stock.
* **Full CRUD Operations:** Add, Edit, and Delete products with pre-filled forms for quick updates.

### 🛒 End-to-End Order Engine
* **Transaction Flow:** Buyers can place orders with automated Minimum Order Quantity (MOQ) and Total Price calculations.
* **Dual Dashboards:** Order history supports "Buyer View" (My Purchases) and "Seller View" (My Sales) with status tracking (Pending, Shipped, Delivered).

### 🎨 Premium UI/UX & Architecture
* **Design System:** Strict "Soft Green (#4CAF50) & Pure White" premium B2B aesthetic.
* **Scalability:** Built-in pagination (Load More) loading 20 products at a time for optimal performance.
* **Resilience:** Global React `ErrorBoundary` prevents hard crashes.
* **PWA Ready:** Integrated Service Workers and Push Notification architecture.

---

## 💻 Tech Stack

**Frontend (apps/web):**
* React 18 + Vite
* TypeScript
* Tailwind CSS
* React Router DOM
* Google Maps API Integration

**Backend (apps/api):**
* Node.js + Express
* TypeScript
* MongoDB + Mongoose (2dsphere indexes for location data)
* JSON Web Tokens (JWT) & bcrypt

---

## 🗄️ Database Architecture (Key Models)

1. **User Model:** Manages authentication, onboarding progress, and role assignment.
2. **Organization Model:** Stores GeoJSON coordinates (`type: "Point"`), legal business details, and verification status.
3. **Product Model:** Tracks item metadata, price, unit, MOQ, and is heavily indexed for text and location searches.
4. **Order Model:** The transactional bridge linking `buyerId`, `sellerId`, `productId`, `quantity`, and fulfillment `status`.

---

## 🛠️ Quick Start

```bash
# Install dependencies
npm install

# Start Local MongoDB (if using Docker)
docker compose up -d

# Start Development Servers
npm run dev
```
