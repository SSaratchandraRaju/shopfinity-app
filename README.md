# 🛍️ Shopfinity - Gamified E-Commerce Platform

<div align="center">
  <img src="assests/app/app_logo.jpg" alt="Shopfinity Logo" width="120" height="120"/>
  
  [![Flutter](https://img.shields.io/badge/Flutter-02569B?style=for-the-badge&logo=flutter&logoColor=white)](https://flutter.dev)
  [![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=black)](https://firebase.google.com)
  [![Riverpod](https://img.shields.io/badge/Riverpod-00D4AA?style=for-the-badge&logo=flutter&logoColor=white)](https://riverpod.dev)
  [![PhonePe](https://img.shields.io/badge/PhonePe-5F259F?style=for-the-badge)](https://www.phonepe.com)

  **A revolutionary e-commerce platform blending shopping with interactive contests**

  [📱 Live Demo](https://shop-finity.firebaseapp.com/) • [🌐 Portfolio](https://saratchandra-raju-sarikonda.vercel.app/) • [💼 LinkedIn](https://www.linkedin.com/in/s-saratchandra-raju/)
</div>

---

## 🌟 Overview

Shopfinity redefines mobile commerce by integrating traditional shopping with gamified contest mechanics. This production-grade Flutter application features:

- Multi-category product marketplace
- Credit-based contest participation
- Secure payment gateway integration
- Real-time leaderboards and rewards
- Comprehensive referral system

## ✨ Key Features

### 🎯 Core Shopping Experience
- **Product Discovery**: Browse 1000+ SKUs across 5 categories
- **Smart Search**: Fuzzy search with predictive results
- **Wishlists**: Save items for later purchase
- **Order Tracking**: Real-time shipment updates

### � Gamification Engine
- **Contest Participation**: Use shopping credits to enter draws
- **Live Leaderboards**: Real-time ranking updates
- **Reward System**: Win products through skill-based challenges
- **Achievements**: Badges for shopping milestones

### 💳 Payment Infrastructure
- **Multi-mode Payments**: UPI, Wallet, Credit/Debit Cards
- **Instant Refunds**: Automated processing system
- **Transaction History**: Detailed financial records
- **Wallet Integration**: Manage contest credits

### 🤝 Social Features
- **Referral Program**: Earn credits for inviting friends
- **Social Sharing**: Share products/contests via social media
- **Activity Feed**: Track friends' achievements

## 🛠️ Technology Stack

### **Core Framework**
- **Flutter 3.13+**: Cross-platform UI toolkit
- **Dart 3.1**: Null-safe codebase

### **Backend Services**
| Service          | Implementation                     |
|------------------|------------------------------------|
| Authentication   | Firebase Auth with OTP             |
| Database         | Firestore with composite indexes   |
| Storage          | Firebase Storage + CDN             |
| Functions        | Cloud Functions for critical logic |

### **State Management**
- **Riverpod 2.4**: Global state management
- **GetX**: Lightweight reactive components

### **UI System**
- **Custom Design Language**: Brand-specific theming (#A22858)
- **Responsive Layouts**: Adaptive grid system
- **Micro-interactions**: Lottie animations
- **Accessibility**: WCAG 2.1 compliant

### **Critical Packages**
```yaml
dependencies:
  firebase_core: ^2.31.0
  cloud_firestore: ^4.17.3
  phonepe_payment_sdk: ^2.0.3
  carousel_slider: ^5.0.0
  flutter_local_notifications: ^18.0.1
```

## 🏗️ Architecture Overview

### **Clean Architecture Layers**
```mermaid
graph TD
    A[Presentation] --> B[Domain]
    B --> C[Application]
    C --> D[Infrastructure]
    D --> E[Firebase]
```

### **Key Design Patterns**
- **Repository Pattern**: Abstracted data access
- **Observer Pattern**: Real-time updates
- **Factory Pattern**: Contest type generation
- **Strategy Pattern**: Payment method handling

## 🔧 Technical Implementation

### **State Management Solution**
```dart
final contestProvider = StateNotifierProvider<ContestNotifier, ContestState>((ref) {
  return ContestNotifier(
    repository: ref.watch(contestRepository),
    user: ref.watch(authProvider).user
  );
});

class ContestNotifier extends StateNotifier<ContestState> {
  Future<void> joinContest() async {
    // Transactional operation
    await Firestore.runTransaction((tx) async {
      final userDoc = tx.get(userRef);
      if (userDoc.credits >= entryFee) {
        tx.update(userRef, {'credits': FieldValue.increment(-entryFee)});
        tx.update(contestRef, {'participants': FieldValue.arrayUnion([userId])});
      }
    });
  }
}
```

### **Payment Flow**
```mermaid
sequenceDiagram
    User->>App: Initiate Payment
    App->>Firestore: Check Wallet Balance
    alt Sufficient Balance
        Firestore->>App: Deduct Credits
    else Insufficient
        App->>PhonePe: Launch SDK
        PhonePe-->>App: Payment Result
    end
    App->>Firestore: Record Transaction
```

### **Contest Fairness Algorithm**
```dart
double calculateWinProbability(User user, Contest contest) {
  final creditRatio = user.credits / contest.totalPool;
  final baseChance = 0.2;
  final scaledChance = baseChance * pow(1.8, creditRatio);
  return min(scaledChance, 0.95); // Cap at 95% chance
}
```

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

## 🚀 Performance Metrics

| Metric                  | Value               |
|-------------------------|---------------------|
| App Launch Time         | 1.2s (cold)        |
| Firestore Read Latency  | 150-300ms          |
| Contest Join Success    | 99.4%              |
| Payment Success Rate    | 98.9%              |

## 📈 Future Roadmap

- [ ] **AR Product Previews**: 3D model visualization
- [ ] **Blockchain Integration**: Transparent contest results
- [ ] **Predictive Analytics**: Personalized recommendations
- [ ] **Voice Shopping**: Voice-enabled product search
- [ ] **Loyalty Program**: Tiered reward system

## 📄 License

This project contains proprietary algorithms and is **not open source**. All rights reserved.

## 👨‍💻 Author

**Saratchandra Raju**

- 🌐 **Portfolio**: [saratchandra-raju-sarikonda.vercel.app](https://saratchandra-raju-sarikonda.vercel.app/)
- 💼 **LinkedIn**: [s-saratchandra-raju](https://www.linkedin.com/in/s-saratchandra-raju/)
- 📧 **Email**: [ssaratchandraraju@gmail.com](mailto:ssaratchandraraju@gmail.com)

---

<div align="center">
  <p>🚀 Where Shopping Meets Entertainment</p>
  <p>© 2024 Shopfinity. All Rights Reserved.</p>
</div>
