
# E-Commerce Website Setup Guide

## Prerequisites

Make sure you have the following installed:
- [XAMPP](https://www.apachefriends.org/index.html) (PHP, MySQL, and phpMyAdmin)

## Project Setup

### Step 1: Clone the Project

1. Open your terminal or command prompt and clone the project from GitHub:
   ```
   git clone https://github.com/Poonamdharamkar/ECommerce
   ```
2. Once cloned, move the project folder to the `htdocs` directory of your XAMPP installation:
   - Default location for `htdocs` on Windows:
     ```
     C:\xampp\htdocs\
     ```
   - Default location for `htdocs` on macOS:
     ```
     /Applications/XAMPP/htdocs/
     ```

   After moving, your project path should look like:
   ```
   C:\xampp\htdocs\ECommerce
   ```

### Step 2: Start XAMPP

1. Open the XAMPP Control Panel.
2. Start the `Apache` and `MySQL` services by clicking the "Start" button next to each.

### Step 3: Import the Database

1. Open your browser and go to [phpMyAdmin](http://localhost/phpmyadmin).
2. Create a new database:
   - Click on **Databases**.
   - Enter a name for your database (e.g., `ecommerce_db`).
   - Click **Create**.

3. Import the database from the `sql` folder:
   - Click on the database you just created in the left sidebar.
   - Click the **Import** tab.
   - Select the `amazon.sql` file located in the `sql` folder of your project.
   - Click **Go** to import the database tables and data.

### Step 4: Update the Database Configuration

1. Open the `php/db.php` file in your code editor.
2. Update the following details to match your local environment:

   ```php
   <?php
   $host = 'localhost'; // Keep it as localhost
   $user = 'root';      // Default MySQL user for XAMPP is 'root'
   $password = '';      // Leave empty if no password is set
   $dbname = 'ecommerce_db';  // The name of the database you created

   $conn = new mysqli($host, $user, $password, $dbname);

   if ($conn->connect_error) {
       die("Connection failed: " . $conn->connect_error);
   }
   ?>
   ```

   Ensure:
   - The database name matches the one you created in phpMyAdmin (`ecommerce_db`).
   - Username is `root` by default in XAMPP.
   - Password is left empty for `root` user unless you've set one.

### Step 5: Access the Website

1. Open your browser and go to:
   ```
   http://localhost/ECommerce/
   ```

2. You should now see the e-commerce website running locally.

---

## Troubleshooting

- Ensure `Apache` and `MySQL` are running in the XAMPP Control Panel if the website doesn't load.
- Check the details in `php/db.php` if you encounter database connection errors.
- Make sure the `amazon.sql` file is correctly imported into phpMyAdmin.

---

## Additional Information

For more details on the project structure, please refer to the documentation or visit the [GitHub Repository](https://github.com/Poonamdharamkar/ECommerce).
