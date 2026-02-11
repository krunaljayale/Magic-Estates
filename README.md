<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Inspire Estates - Documentation</title>
    <style>
        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, Arial, sans-serif;
            line-height: 1.6;
            color: #24292e;
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
        }
        h1, h2, h3 {
            border-bottom: 1px solid #eaecef;
            padding-bottom: 0.3em;
            margin-top: 24px;
        }
        h1 { font-size: 2em; display: flex; align-items: center; justify-content: space-between; }
        h2 { font-size: 1.5em; }
        ul { padding-left: 2em; }
        li { margin-bottom: 5px; }
        code {
            background-color: #f6f8fa;
            padding: 0.2em 0.4em;
            border-radius: 3px;
            font-family: SFMono-Regular, Consolas, "Liberation Mono", Menlo, monospace;
            font-size: 85%;
        }
        pre {
            background-color: #f6f8fa;
            padding: 16px;
            border-radius: 6px;
            overflow-x: auto;
            line-height: 1.45;
        }
        pre code {
            background-color: transparent;
            padding: 0;
            font-size: 100%;
        }
        table {
            border-collapse: collapse;
            width: 100%;
            margin: 20px 0;
        }
        th, td {
            border: 1px solid #dfe2e5;
            padding: 6px 13px;
        }
        th {
            background-color: #f6f8fa;
            font-weight: 600;
            text-align: left;
        }
        tr:nth-child(2n) {
            background-color: #f6f8fa;
        }
        .btn-demo {
            background-color: #fe424d;
            color: white;
            padding: 10px 20px;
            text-decoration: none;
            border-radius: 5px;
            font-size: 0.6em;
            font-weight: bold;
            vertical-align: middle;
        }
        .btn-demo:hover {
            background-color: #e02f3a;
        }
    </style>
</head>
<body>

    <h1>
        <span>🏡 Inspire Estates</span>
        <a href="https://inspire-estates-tfjk.onrender.com/" target="_blank" class="btn-demo">View Live Demo 🚀</a>
    </h1>

    <p><strong>Inspire Estates</strong> is a full-stack web application inspired by Airbnb. It allows users to list properties (estates), view details, upload images, post reviews, and make bookings.</p>

    <p>The project is built using the <strong>MVC (Model-View-Controller)</strong> architecture with <strong>Node.js</strong>, <strong>Express</strong>, and <strong>EJS</strong> for server-side rendering.</p>

    <h2>✨ Features</h2>
    <ul>
        <li><strong>User Authentication & Authorization</strong>:
            <ul>
                <li>Secure Login and Signup using <code>Passport.js</code>.</li>
                <li>Role-based access: Only the owner can edit/delete their listing.</li>
                <li>Review authors can only delete their own reviews.</li>
            </ul>
        </li>
        <li><strong>CRUD Operations for Listings</strong>:
            <ul>
                <li>Create, Read, Update, and Delete property listings.</li>
                <li>Upload images directly to cloud storage (Cloudinary) using <code>multer</code>.</li>
            </ul>
        </li>
        <li><strong>Reviews System</strong>:
            <ul>
                <li>Users can leave reviews and ratings for specific listings.</li>
            </ul>
        </li>
        <li><strong>Booking System</strong>:
            <ul>
                <li>Functionality to book a listing directly from the details page.</li>
            </ul>
        </li>
        <li><strong>Error Handling</strong>:
            <ul>
                <li>Custom error handling middleware (<code>ExpressError</code>) and async wrappers (<code>wrapAsync</code>).</li>
            </ul>
        </li>
        <li><strong>MVC Structure</strong>:
            <ul>
                <li>Clean separation of concerns using Controllers, Routes, and Models.</li>
            </ul>
        </li>
    </ul>

    <h2>🛠️ Tech Stack</h2>
    
    <h3>Backend</h3>
    <ul>
        <li><strong>Node.js</strong>: Runtime environment.</li>
        <li><strong>Express.js</strong>: Web framework for routing and middleware.</li>
        <li><strong>Passport.js</strong>: Authentication strategy (Local).</li>
        <li><strong>Joi</strong>: Schema validation for server-side data protection.</li>
        <li><strong>Multer</strong>: Middleware for handling <code>multipart/form-data</code> (image uploads).</li>
    </ul>

    <h3>Frontend</h3>
    <ul>
        <li><strong>EJS (Embedded JavaScript)</strong>: Templating engine for server-side rendering.</li>
        <li><strong>HTML5 / CSS3</strong>: Basic structure and styling.</li>
    </ul>

    <h3>Database & Storage</h3>
    <ul>
        <li><strong>MongoDB</strong>: NoSQL Database (via Mongoose).</li>
        <li><strong>Cloudinary</strong>: Cloud storage service for hosting listing images.</li>
    </ul>

    <h2>⚙️ Installation & Setup</h2>

    <ol>
        <li>
            <strong>Clone the repository</strong>
            <pre><code>git clone https://github.com/krunaljayale/Inspire-Estates.git
cd Inspire-Estates</code></pre>
        </li>
        <li>
            <strong>Install dependencies</strong>
            <pre><code>npm install</code></pre>
        </li>
        <li>
            <strong>Configure Environment Variables</strong>
            <p>Create a <code>.env</code> file in the root directory and add the following keys:</p>
            <pre><code>CLOUD_NAME=your_cloudinary_name
CLOUD_API_KEY=your_cloudinary_api_key
CLOUD_API_SECRET=your_cloudinary_api_secret
MONGO_URL=your_mongodb_connection_string
SECRET=your_session_secret</code></pre>
        </li>
        <li>
            <strong>Run the application</strong>
            <pre><code>node app.js
# OR if using nodemon
nodemon app.js</code></pre>
        </li>
        <li>
            <strong>Access the app</strong>
            <p>Open your browser and go to <code>http://localhost:8080</code> (or your configured port).</p>
        </li>
    </ol>

    <h2>🛣️ API Routes</h2>

    <h3>🏠 Listings (<code>/listings</code>)</h3>
    <table>
        <thead>
            <tr>
                <th>Method</th>
                <th>Endpoint</th>
                <th>Description</th>
                <th>Auth Required</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td><strong>GET</strong></td>
                <td><code>/listings</code></td>
                <td>Show all listings (Index)</td>
                <td>No</td>
            </tr>
            <tr>
                <td><strong>GET</strong></td>
                <td><code>/listings/new</code></td>
                <td>Render form to create a new listing</td>
                <td>Yes (Login)</td>
            </tr>
            <tr>
                <td><strong>POST</strong></td>
                <td><code>/listings</code></td>
                <td>Create a new listing (Uploads image)</td>
                <td>Yes (Login)</td>
            </tr>
            <tr>
                <td><strong>GET</strong></td>
                <td><code>/listings/:id</code></td>
                <td>Show details of a specific listing</td>
                <td>No</td>
            </tr>
            <tr>
                <td><strong>GET</strong></td>
                <td><code>/listings/:id/edit</code></td>
                <td>Render form to edit a listing</td>
                <td>Yes (Owner)</td>
            </tr>
            <tr>
                <td><strong>PUT</strong></td>
                <td><code>/listings/:id</code></td>
                <td>Update a listing</td>
                <td>Yes (Owner)</td>
            </tr>
            <tr>
                <td><strong>GET</strong></td>
                <td><code>/listings/:id/delete</code></td>
                <td>Delete a listing</td>
                <td>Yes (Owner)</td>
            </tr>
            <tr>
                <td><strong>POST</strong></td>
                <td><code>/listings/:id/book</code></td>
                <td>Book a specific listing</td>
                <td>Yes (Login)</td>
            </tr>
        </tbody>
    </table>

    <h3>⭐ Reviews (<code>/listings/:id/reviews</code>)</h3>
    <table>
        <thead>
            <tr>
                <th>Method</th>
                <th>Endpoint</th>
                <th>Description</th>
                <th>Auth Required</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td><strong>POST</strong></td>
                <td><code>/</code></td>
                <td>Post a review for a listing</td>
                <td>Yes (Login)</td>
            </tr>
            <tr>
                <td><strong>DELETE</strong></td>
                <td><code>/:reviewId</code></td>
                <td>Delete a specific review</td>
                <td>Yes (Author)</td>
            </tr>
        </tbody>
    </table>

    <h3>👤 Users (<code>/</code>)</h3>
    <table>
        <thead>
            <tr>
                <th>Method</th>
                <th>Endpoint</th>
                <th>Description</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td><strong>GET</strong></td>
                <td><code>/signup</code></td>
                <td>Render signup form</td>
            </tr>
            <tr>
                <td><strong>POST</strong></td>
                <td><code>/signup</code></td>
                <td>Register a new user</td>
            </tr>
            <tr>
                <td><strong>GET</strong></td>
                <td><code>/login</code></td>
                <td>Render login form</td>
            </tr>
            <tr>
                <td><strong>POST</strong></td>
                <td><code>/login</code></td>
                <td>Authenticate user</td>
            </tr>
            <tr>
                <td><strong>GET</strong></td>
                <td><code>/logout</code></td>
                <td>Logout user</td>
            </tr>
        </tbody>
    </table>
    
    <h2>🤝 Contributing</h2>
    <p>Contributions, issues, and feature requests are welcome! Feel free to check the <a href="https://github.com/krunaljayale/Inspire-Estates/issues">issues page</a>.</p>

</body>
</html>
