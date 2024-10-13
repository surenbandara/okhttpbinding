# Flutter JNI Bindings for OkHttp

This project demonstrates how to use **JNI (Java Native Interface) bindings** to integrate Java’s **OkHttp** library into a Flutter application. The app allows users to enter a URL, send an HTTP request, and view the server's response.

---

## Table of Contents
- [Features](#features)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Running the Application](#running-the-application)
- [Usage](#usage)
  - [Key Functionalities](#key-functionalities)
  - [Code Overview](#code-overview)
- [Screenshots](#screenshots)
- [License](#license)
- [Acknowledgments](#acknowledgments)

---

## Features

- **JNI Integration**: Dart interacts with Java code using JNI bindings.
- **OkHttp Integration**: Utilize the Java OkHttp library directly within Flutter.
- **Simple UI**: Input a URL and fetch the HTTP response.
- **Error Handling**: Invalid URLs are detected, and an error message is displayed.

---

## Getting Started

### Prerequisites

Ensure you have the following installed:
- **Flutter SDK**: [Install Flutter](https://flutter.dev/docs/get-started/install)
- **Java Development Kit (JDK)**: Ensure the JDK is installed and properly configured.
- **Android Studio or VS Code**: For testing and running the Flutter app.

### Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/flutter-jni-okhttp.git
   cd flutter-jni-okhttp
