
# Vishwakarma Agriculture (formerly Arogya Rahita)

This is an e-commerce project for an agricultural products business. It features a client-facing website and a comprehensive admin panel for managing products and orders.

## Features

*   **User Authentication:** SMS-based OTP authentication using Twilio.
*   **Product Management:** Full CRUD functionality for products, including image uploads to Cloudinary.
*   **Order Management:** Admin panel for viewing and managing customer orders.
*   **Search:** Search functionality for products.
*   **User Profiles:** Users can view and edit their profiles.

## Tech Stack

*   **Frontend:** React.js
*   **Backend:** Node.js, Express.js
*   **Database:** MongoDB
*   **Image Storage:** Cloudinary
*   **SMS OTP:** Twilio

## Setup Instructions

### Prerequisites

*   Node.js (v18 or higher)
*   MongoDB
*   Twilio account
*   Cloudinary account

### 1. Server Setup

```bash
cd server
npm install
```

Create a `.env` file in the `server` directory with the following content:

```env
# Server Configuration
PORT=5000
NODE_ENV=development

# MongoDB Connection
MONGODB_URI=mongodb://localhost:27017/arogyamrahita

# JWT Secrets
JWT_SECRET=your_jwt_secret_key_here
JWT_REFRESH_SECRET=your_jwt_refresh_secret_key_here

# Twilio Configuration for SMS OTP
TWILIO_ACCOUNT_SID=your_twilio_account_sid_here
TWILIO_AUTH_TOKEN=your_twilio_auth_token_here
TWILIO_PHONE_NUMBER=your_twilio_phone_number_here

# Cloudinary Configuration for Image Storage
CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name_here
CLOUDINARY_API_KEY=your_cloudinary_api_key_here
CLOUDINARY_API_SECRET=your_cloudinary_api_secret_here

# Base URL for the application
BASE_URL=http://localhost:5000
```

Start the server:

```bash
npm run dev
```

### 2. Client Setup

```bash
cd client
npm install
npm start
```

## Admin Panel

The admin panel is located at the `/admin` route of the application.

### Admin Credentials

There are no default admin credentials. To create an admin user, you need to manually edit a user's role in the database.

1.  Register a new user through the application's registration form.
2.  Connect to your MongoDB database.
3.  In the `users` collection, find the user you just created.
4.  Change the value of the `role` field for that user from `"user"` to `"admin"`.

Once you have an admin user, you can log in with that user's credentials and access the admin panel.
