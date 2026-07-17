# NazeeyPay - VTU & Data Reselling Application

### 📝 Description
**NazeeyPay** is a fast, secure, and user-friendly mobile application designed for airtime and data reselling in Nigeria. The application allows users to buy cheap internet data (MTN, Airtel, Glo, 9mobile), top-up airtime, pay utility bills, and fund their wallets instantly using personalized virtual bank accounts. 

Built with a modern UI/UX and integrated with reliable VTU APIs, NazeeyPay ensures lightning-fast delivery of telecom services while offering competitive prices for resellers to maximize their profits.

---

### 🚀 Key Features
*   **Instant Wallet Funding:** Automatic wallet funding via personalized virtual bank accounts (powered by Monnify/Paystack).
*   **Cheap Data & Airtime:** Purchase MTN SME data, Airtel CG, Glo, and 9mobile data at highly discounted rates.
*   **User Management:** Secure user registration, login, and password recovery.
*   **Transaction History:** A detailed log of all transactions, receipts, and wallet funding history.
*   **Security:** High-level security including PIN/Biometric authentication for transaction approvals.
*   **Admin Dashboard:** A robust backend dashboard for the owner to manage users, update prices, and view profits.

---

### 🛠️ Tech Stack
*   **Frontend (UI/UX):** FlutterFlow (No-Code App Builder) / Flutter
*   **Database & Authentication:** Google Firebase
*   **Payment Gateway API:** Monnify API & Paystack API
*   **VTU Services API:** Clubkonnect / VTPass / Simhost API

---

### ⚙️ Configuration & Setup Guide

To get **NazeeyPay** up and running, you need to configure three main components: **Firebase** (for database & auth), **Payment Gateway** (for wallet funding), and the **VTU API** (for airtime/data delivery).

#### 1. Firebase Configuration (Backend & Database)
NazeeyPay uses Google Firebase for user authentication, storing wallet balances, and transaction logs.

1. Go to the [Firebase Console](https://console.firebase.google.com/) and create a new project named `NazeeyPay`.
2. Enable **Email/Password Authentication** in the Firebase Auth section.
3. Create a **Cloud Firestore** database in production/test mode.
4. Go to **Project Settings** and copy your **Project ID**.
5. In **FlutterFlow**, navigate to **Settings > Firebase**, paste your Project ID, and click **Connect**.
6. Generate the Firebase Config files and deploy the Firestore Rules and Indexes.

#### 2. Payment Gateway Configuration (Wallet Funding)
To allow users to fund their NazeeyPay wallets automatically via Bank Transfer or Card:

1. Sign up on [Monnify](https://monnify.com) or [Paystack](https://paystack.com) and complete your merchant KYC.
2. Go to your developer dashboard and copy your **API Public Key** and **Secret Key**.
3. In your FlutterFlow project, go to **API Calls** and create a new API Group named `PaymentGateway`.
4. Add the **Initialize Transaction** and **Verify Transaction** endpoints.
5. Pass your API keys in the `Authorization` header:
   ```env
   Authorization: Bearer YOUR_SECRET_KEY

