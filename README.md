# 🛍️ Shopfinity

**Shopfinity** is a **contest-driven e-commerce application** built with a robust Flutter-Firebase architecture. It blends the traditional shopping experience with gamification, offering users the chance to win exclusive rewards while shopping for their favorite products.

---

## 🎯 Project Overview

Shopfinity provides a multi-category shopping platform that integrates:

* Shopping across diverse product lines
* Gamified contests with prize-winning opportunities
* A referral-based credit system
* Secure, seamless payments

This project leverages modern state management and scalable backend services to deliver a dynamic and engaging mobile experience.

---

## 🚀 Highlights & Functionality

### 🛒 Multi-category Shopping

Users can browse and purchase products across:

* Electronics
* Furniture
* Toys
* Sports & Fitness
* Fashion

### 🏆 Contest Participation

Users earn credits through purchases and referrals. These credits can be used to participate in live contests, creating an interactive, gamified shopping environment.

### 👥 Referral Program

Invite friends and earn credits. Referrals directly impact the user's ability to enter contests and redeem benefits.

### 🎉 Gamified User Experience

The platform includes features like leaderboards, live voting, and interactive product-based contests.

### 📱 Mobile-first Responsive UI

Crafted using Flutter, the UI provides:

* Smooth navigation
* Custom theming (`ARGB(255, 162, 40, 88)` primary color)
* Responsiveness across Android and iOS

---

## 🔧 Technology Stack

| Layer         | Tools & Frameworks                             |
| ------------- | ---------------------------------------------- |
| Frontend      | Flutter (Dart), Cupertino, Material Design     |
| Backend       | Firebase (Auth, Firestore, Storage, Messaging) |
| State Mgmt    | Riverpod, GetX                                 |
| Notifications | Firebase Cloud Messaging, Local Notifications  |
| Payments      | PhonePe SDK, UPI support, Custom Crypto APIs   |
| UI Utilities  | Shimmer, Carousel Slider, Dotted Borders       |
| Media         | Image Picker, Photo Viewer, PDF Generator      |
| Sharing       | Share Plus, QR Generator                       |

---

## 💡 Key Implementation Details

### Firebase Integration

* Auth with OTP-based login and registration flows
* Firestore for real-time product, contest, and user data
* Firebase Storage for image and asset management
* Firebase Messaging for push notifications

### Payments & Offers

* PhonePe SDK integration for secure in-app payments
* Wallet system for managing contest credits and membership
* Referral rewards linked to purchases and wallet

### Contest Mechanics

* Leaderboards and product voting systems
* Dynamic contest screen generation based on Firestore entries
* Winner declaration and credit redemption workflows

### Localization

* Multi-language support via `.arb` files (English, Hindi, Malayalam, Tamil, Telugu)

### Modular Architecture

The project follows a scalable, layered architecture with modular separation:

* `screens/` for UI views
* `controller/` for logic & state
* `services/` for Firebase and business logic
* `models/` for typed DTOs
* `widgets/` for reusable components

---

## 📸 Screenshots

<table>
  <tr>
    <td><img src="assests/screens/home.jpg" alt="Home Page" width="200" /></td>
    <td><img src="assests/screens/product_info.jpg" alt="Product Info" width="200" /></td>
    <td><img src="assests/screens/checkout.jpg" alt="Checkout Page" width="200" /></td>
    <td><img src="assests/screens/order-conf.jpg" alt="Order Confirmation" width="200" /></td>
  </tr>
  <tr>
    <td><img src="assests/screens/invoice.jpg" alt="Invoice" width="200" /></td>
    <td><img src="assests/screens/future-c.jpg" alt="Upcoming Contests" width="200" /></td>
    <td><img src="assests/screens/contest.jpg" alt="Active Contest" width="200" /></td>
    <td><img src="assests/screens/leaderboard.jpg" alt="Leaderboard" width="200" /></td>
  </tr>
  <tr>
    <td><img src="assests/screens/leaderboards.jpg" alt="Leaderboard (Expanded)" width="200" /></td>
    <td><img src="assests/screens/wallet.jpg" alt="Wallet" width="200" /></td>
    <td><img src="assests/screens/referrals.jpg" alt="Referrals" width="200" /></td>
    <td><img src="assests/screens/addresses.jpg" alt="Address Book" width="200" /></td>
  </tr>
  <tr>
    <td><img src="assests/screens/cart.jpg" alt="Cart" width="200" /></td>
    <td><img src="assests/screens/coupons.jpg" alt="Coupons" width="200" /></td>
    <td><img src="assests/screens/order.jpg" alt="Order Details" width="200" /></td>
    <td><img src="assests/screens/orders.jpg" alt="My Orders" width="200" /></td>
  </tr>
</table>

---

## 📂 Project Status

This is a **fully functional, production-ready application**. The core modules including shopping, payments, contests, and referrals are thoroughly tested. The app is in active development with future features planned for A/B testing and micro-analytics.

---

## 🚪 License

This project is **proprietary and confidential**. All rights are reserved by the author. Unauthorized copying, distribution, or modification of any part of this codebase is strictly prohibited.

---

## 📩 Contact

* **Email**: [ssaratchandraraju@gmail.com](mailto:ssaratchandraraju@gmail.com)
* **Website**: [shopfinity](https://shop-finity.firebaseapp.com/)

---

> **Shop smart. Win big. Welcome to Shopfinity.**
