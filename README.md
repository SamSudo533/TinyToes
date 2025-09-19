TinyToes 🍼👣

An e-commerce mobile application built with Flutter & Dart

TinyToes is a cloud-ready e-commerce platform prototype specializing in curated baby products. It demonstrates modern app development practices, including cross-platform mobile development, CI/CD integration, and cloud deployment.

📱 Features

User authentication (signup/login)

Product catalog browsing

Shopping cart functionality

Wishlist management

Order summary & checkout flow

Responsive UI for Android & iOS

Scalable backend integration (cloud-ready)

🛠️ Tech Stack

Frontend: Flutter (Dart)

Backend (future-ready): Firebase / Azure App Service (choose based on scope)

Database: Firebase Firestore / Azure CosmosDB

CI/CD: GitHub Actions (or Azure DevOps pipelines)

Cloud Provider: Microsoft Azure (primary), Firebase (optional integration)

📋 Requirements
Prerequisites

Flutter SDK (>=3.0.0)

Dart (>=2.18)

Android Studio / VS Code with Flutter extension

Git & GitHub account

(Optional) Firebase CLI

(Optional) Azure CLI

Dependencies

Add these (example list — update according to your actual pubspec.yaml):

dependencies:
  flutter:
    sdk: flutter
  cupertino_icons: ^1.0.6
  provider: ^6.0.5
  http: ^0.13.6
  firebase_core: ^2.4.1
  cloud_firestore: ^4.3.2
  firebase_auth: ^4.2.5

🏗️ Architecture

TinyToes follows a clean MVVM architecture with separation of concerns:

lib/
├── models/        # Data models (Product, User, Order, etc.)
├── views/         # UI screens (Catalog, Cart, Checkout, etc.)
├── viewmodels/    # Business logic & state management (Provider/ChangeNotifier)
├── services/      # API calls, Firebase/Azure services
├── utils/         # Helpers, constants
└── main.dart      # Entry point

☁️ Cloud Deployment
Option 1: Firebase Hosting / Firebase Functions

Install Firebase CLI:

npm install -g firebase-tools
firebase login
firebase init


Configure Firestore & Authentication.

Deploy backend functions:

firebase deploy

Option 2: Azure App Service + CosmosDB

Install Azure CLI & login:

az login


Create Resource Group & App Service:

az group create --name TinyToesRG --location eastus
az appservice plan create --name TinyToesPlan --resource-group TinyToesRG --sku FREE
az webapp create --resource-group TinyToesRG --plan TinyToesPlan --name TinyToesApp --runtime "DOTNET:6"


Connect with backend API (Node.js/Dart/Firebase Functions).

Use CosmosDB for data storage.

🔄 CI/CD Setup
GitHub Actions (recommended)

Add .github/workflows/flutter-ci.yml:

name: Flutter CI

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repo
        uses: actions/checkout@v3
      - name: Setup Flutter
        uses: subosito/flutter-action@v2
        with:
          flutter-version: '3.10.0'
      - name: Install dependencies
        run: flutter pub get
      - name: Run tests
        run: flutter test
      - name: Build APK
        run: flutter build apk --release

Azure DevOps (alternative)

Create pipeline with Flutter tasks.

Configure automated build, test, and release to App Service.

🚀 How to Run Locally
# Clone repository
git clone https://github.com/<your-username>/TinyToes.git
cd TinyToes

# Get dependencies
flutter pub get

# Run app
flutter run

📦 Future Enhancements

Payment gateway integration (Stripe/PayPal)

Push notifications for promotions/orders

Multi-language support

Admin dashboard for product management

Analytics & tracking

🤝 Contributing

Fork the repo

Create a new branch (feature/your-feature)

Commit changes

Push to branch

Open a Pull Request

📜 License

MIT License. 
