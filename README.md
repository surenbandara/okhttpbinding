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
   ```shell
   git clone https://github.com/surenbandara/okhttpbinding.git
   cd flutter-jni-okhttp
   ```

2. **Install dependencies**:
```shell
flutter pub get
```

3. **Configure JNI Bindings**:
   Ensure the jni_bindings.dart file is properly set up to bind with the OkHttp library.

### Running the Application
To run the app on an emulator or a connected device:

```shell
flutter run
```

#### If you encounter issues:

Ensure that your Android emulator is running or your physical device is connected.
Run the following command if there are Android SDK issues:
```shell
flutter doctor --android-licenses
```

## Usage
1. **Enter a URL**:
Type a valid HTTP URL (e.g., `https://jsonplaceholder.typicode.com/todos/1`) into the text field.

2. **Send Request**:
Press the Send Request button (the floating action button) to send the HTTP request.

3. **View Response**:
The server’s response will be displayed below the text field. If the URL is invalid, `"Invalid url"` will be shown.

### Key Functionalities
Below are the core JNI-based functionalities used:

1. `OkHttpClient`: Creates a new HTTP client for managing requests.
2. `Request_Builder`: Constructs an HTTP request using the provided URL.
  - `url1(JString.fromString(url))`: Sets the request URL using a JString wrapper.
  - `build()`: Builds the HTTP request.
3. **Sending the Request**:
  - `okHttpClient.newCall(request).execute()`: Sends the request and returns the response.
4.  **Error Handling**:
If an invalid URL is provided, the app catches the exception and displays `"Invalid url"`.

### Code Overview
Below is the key Dart code used to build the HTTP request with JNI bindings and display the response:

```shell
void _sendRequest(String url) {
  setState(() {
    try {
      // Build the request using the Request_Builder
      request = request_builder.url1(JString.fromString(url)).build();

      // Execute the request using OkHttpClient
      Response response = okHttpClient.newCall(request).execute();

      // Display the response
      resp = response.toString();
    } catch (e) {
      // Handle invalid URL errors
      resp = "Invalid url";
    }
  });
}
```

## Acknowledgments

- **OkHttp**: A popular Java HTTP client that simplifies making HTTP requests.
- **Flutter**: A framework for building cross-platform mobile applications efficiently.
- **JNI Documentation**: Provides guidelines for interfacing with native Java code through the Java Native Interface (JNI).

