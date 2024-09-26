# Simple Button with CleverTap Web SDK Integration and Firebase Push Notifications

This project is a minimal web application that integrates CleverTap's web SDK to track button click events and Firebase for web push notifications. When the button is clicked, a "Product Viewed" event is sent to CleverTap, and the number of clicks is displayed on the page. The app also prompts the user to enable push notifications using Firebase.

## Features

- Tracks button click events using CleverTap's web SDK.
- Sends user login information and a "Product Viewed" event to CleverTap upon clicking the button.
- Prompts users to subscribe to push notifications using Firebase.
- Keeps count of the number of times the button is clicked.

## Project Structure

```
simple_button/
├── index.html        # Main HTML file with button and event script
└── clevertap_sw.js   # Service worker for CleverTap push notifications
```

## Getting Started

### Prerequisites

Before running this project, ensure you have the following:

- A web server environment (e.g., [XAMPP](https://www.apachefriends.org/index.html)) for serving the `index.html` file.

### Setup Instructions

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/Ryeon-MH/CT-Onboarding-Test.git
   cd simple_button
   ```

2. **Place Files in Web Server**:
   - Copy the `simple_button` folder to the `htdocs` directory (if using XAMPP) or the appropriate directory in your local web server setup.

3. **Start the Web Server**:
   - Run your local web server (e.g., XAMPP) and navigate to `http://localhost/simple_button/index.html` in your browser.

## Usage

1. Open the web page in your browser.
2. You will be prompted to enable push notifications.
3. Click the "Click Me" button.
4. Upon clicking, the app will:
   - Send a user login event with the email `jidesh+ryanr@clevertap.com`.
   - Send a "Product Viewed" event to CleverTap.
   - Update the message with the number of times the button has been clicked (e.g., "Button clicked (x1)", "Button clicked (x2)", etc.).

## CleverTap Integration

- **onUserLogin**: Logs the user into CleverTap with their email.
- **event.push**: Sends a "Product Viewed" event to CleverTap when the button is clicked.

## Firebase Push Notifications

The project also uses Firebase to send push notifications. Users are prompted to enable notifications, and CleverTap handles the display of notifications via the service worker (`clevertap_sw.js`).

### How to Modify

To change the event or user data:
- Open `index.html`.
- Modify the `clevertap.onUserLogin.push` and `clevertap.event.push` objects with the desired user or event data.
