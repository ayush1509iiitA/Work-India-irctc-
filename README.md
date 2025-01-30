SDE API Round - IRCTC
This is a railway management system built with Node.js, Express.js, and MySQL. It provides APIs for users to check train availability, book seats, and manage bookings. It also includes an admin interface for creating and managing trains.

By using transactions and row-level locking, I ensure that only one user can book the available seats at a given time.

Features
User registration and authentication
Train creation and management (admin only)
Check train availability between source and destination
Book seats on available trains (handled race conditions)
View booking details
Technologies Used
Node.js
Express.js
MySQL
JSON Web Tokens (JWT)
bcrypt.js
Installation
Clone the repository: git clone [ https://github.com/ayush1509iiitA/Work-India-irctc-.git ]
Navigate to the project directory: cd WorkInda-IRCTC
Install dependencies: npm install
Create a .env file and set the following environment variables:
HOST: MySQL database host
USER: MySQL database user
PASSWORD: MySQL database password
NAME: MySQL database name
JWT_SECRET: Secret key for JWT token generation
ADMIN_KEY: Admin key for protected routes
Create the MySQL database and tables by running the SQL scripts in the database directory.
Start the server: npm start
API Documentation
Authentication
POST /auth/register: Register a new user
POST /auth/login: Authenticate and obtain a JWT token
Trains (Admin Only)
POST /trains/create: Create a new train
Bookings
GET /trains/availability?source=<source>&destination=<destination>: Get available trains between source and destination
POST /bookings/book: Book seats on a train
GET /bookings/details?trainId=<trainId>: Get booking details for a specific train
Handled RACE CONDITIONS while booking using transactions and row-level locking.

Users
GET /users/me: Get user details (requires authentication)
