# 🏡 Magic Estates

[![Live Demo](https://img.shields.io/badge/Live_Demo-Render-FF424D?style=for-the-badge&logo=render&logoColor=white)](https://inspire-estates-tfjk.onrender.com/)

**Magic Estates** is a full-stack web application inspired by Airbnb. It allows users to list properties (estates), view details, upload images, post reviews, and make bookings.

The project is built using the **MVC (Model-View-Controller)** architecture with **Node.js**, **Express**, and **EJS** for server-side rendering.

## ✨ Features

* **User Authentication & Authorization**:
    * Secure Login and Signup using `Passport.js`.
    * Role-based access: Only the owner can edit/delete their listing.
    * Review authors can only delete their own reviews.
* **CRUD Operations for Listings**:
    * Create, Read, Update, and Delete property listings.
    * Upload images directly to cloud storage (Cloudinary) using `multer`.
* **Reviews System**:
    * Users can leave reviews and ratings for specific listings.
* **Booking System**:
    * Functionality to book a listing directly from the details page.
* **Error Handling**:
    * Custom error handling middleware (`ExpressError`) and async wrappers (`wrapAsync`).
* **MVC Structure**:
    * Clean separation of concerns using Controllers, Routes, and Models.

## 🛠️ Tech Stack

### Backend
* **Node.js**: Runtime environment.
* **Express.js**: Web framework for routing and middleware.
* **Passport.js**: Authentication strategy (Local).
* **Joi**: Schema validation for server-side data protection.
* **Multer**: Middleware for handling `multipart/form-data` (image uploads).

### Frontend
* **EJS (Embedded JavaScript)**: Templating engine for server-side rendering.
* **HTML5 / CSS3**: Basic structure and styling.

### Database & Storage
* **MongoDB**: NoSQL Database (via Mongoose).
* **Cloudinary**: Cloud storage service for hosting listing images.

## ⚙️ Installation & Setup

1.  **Clone the repository**
    ```bash
    git clone [https://github.com/krunaljayale/Inspire-Estates.git](https://github.com/krunaljayale/Inspire-Estates.git)
    cd Inspire-Estates
    ```

2.  **Install dependencies**
    ```bash
    npm install
    ```

3.  **Configure Environment Variables**
    Create a `.env` file in the root directory and add the following keys:
    ```env
    CLOUD_NAME=your_cloudinary_name
    CLOUD_API_KEY=your_cloudinary_api_key
    CLOUD_API_SECRET=your_cloudinary_api_secret
    MONGO_URL=your_mongodb_connection_string
    SECRET=your_session_secret
    ```

4.  **Run the application**
    ```bash
    node app.js
    # OR if using nodemon
    nodemon app.js
    ```

5.  **Access the app**
    Open your browser and go to `http://localhost:8080` (or your configured port).

## 🛣️ API Routes

### 🏠 Listings (`/listings`)
| Method | Endpoint | Description | Auth Required |
| :--- | :--- | :--- | :--- |
| **GET** | `/listings` | Show all listings (Index) | No |
| **GET** | `/listings/new` | Render form to create a new listing | Yes (Login) |
| **POST** | `/listings` | Create a new listing (Uploads image) | Yes (Login) |
| **GET** | `/listings/:id` | Show details of a specific listing | No |
| **GET** | `/listings/:id/edit` | Render form to edit a listing | Yes (Owner) |
| **PUT** | `/listings/:id` | Update a listing | Yes (Owner) |
| **GET** | `/listings/:id/delete`| Delete a listing | Yes (Owner) |
| **POST** | `/listings/:id/book` | Book a specific listing | Yes (Login) |

### ⭐ Reviews (`/listings/:id/reviews`)
| Method | Endpoint | Description | Auth Required |
| :--- | :--- | :--- | :--- |
| **POST** | `/` | Post a review for a listing | Yes (Login) |
| **DELETE** | `/:reviewId` | Delete a specific review | Yes (Author) |

### 👤 Users (`/`)
| Method | Endpoint | Description |
| :--- | :--- | :--- |
| **GET** | `/signup` | Render signup form |
| **POST** | `/signup` | Register a new user |
| **GET** | `/login` | Render login form |
| **POST** | `/login` | Authenticate user |
| **GET** | `/logout` | Logout user |

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!
Feel free to check the [issues page](https://github.com/krunaljayale/Inspire-Estates/issues).
