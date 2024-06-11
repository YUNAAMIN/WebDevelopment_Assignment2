# E-Clothing Web Store Application
  link to my website: http://web1211524.studentprojects.ritaj.ps/  footer of the page-> selest Assignment --> select Ass2
## Overview

This project is a web application built with PHP and a MySQL database to manage an e-clothing store. The application allows users to add, view, update, and delete products. The main script of the application is `products.php`, which dynamically generates an HTML page to interact with the product catalog.

## Features

### Product Management

- **Add Product**: Users can add new products to the store through a form. Product images must be uploaded as JPEG files.
- **View Product**: Users can view detailed information about a product.
- **Update Product**: Users can update product details such as price, quantity, description, and image.
- **Delete Product**: Users can delete products from the store.

### Search Functionality

- **Filter Search**: Users can search for products by name, category, or price using a filter form.

### User Interface

- **Navigation**: All pages include a header with the store name, logo, and navigation links.
- **Footer**: All pages include a footer with the last update date, store address, customer support information, and a link to the Contact Us page.

## File Structure

- `dbconfig.in.php`: Contains database connection details and creates a PDO object.
- `products.php`: Main script for displaying and managing products.
- `add.php`: Handles adding new products.
- `view.php`: Displays detailed information about a specific product.
- `edit.php`: Handles updating product details.
- `delete.php`: Handles deleting products.
- `Product.php`: Defines the Product class with methods to handle product data.
- `images/`: Directory to store product images.

## Setup Instructions

1. **Database Configuration**:
   - Create a MySQL database.
   - Update the `dbconfig.in.php` file with your database connection details.
     ```php
     <?php
     $dbHost = 'localhost';
     $dbName = 'your_database_name';
     $dbUser = 'your_database_user';
     $dbPass = 'your_database_password';

     try {
         $pdo = new PDO("mysql:host=$dbHost;dbname=$dbName", $dbUser, $dbPass);
         $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
     } catch (PDOException $e) {
         echo "Connection failed: " . $e->getMessage();
     }
     ?>
     ```

2. **Product Class**:
   - Create a `Product` class in `Product.php` with the following methods:
     - `__construct()`: Initializes product attributes.
     - `setters` and `getters`: For each product attribute.
     - `displayInTable()`: Returns product details as an HTML table row.
     - `displayProductPage()`: Generates HTML for displaying detailed product information.

3. **Main Script (products.php)**:
   - Display a table of products with options to add, edit, and delete products.
   - Include a search form for filtering products by name, category, or price.

4. **Add Product (add.php)**:
   - Display a form to add a new product.
   - Handle form submission to store product details in the database and upload the product image.

5. **View Product (view.php)**:
   - Display detailed information about a specific product based on the product ID.

6. **Edit Product (edit.php)**:
   - Display a form to update product details.
   - Handle form submission to update product details in the database and upload a new product image if provided.

7. **Delete Product (delete.php)**:
   - Handle the deletion of a product based on the product ID.

## General Requirements

- **Header**: Include a header with the store name, logo, and navigation links on all pages.
- **Footer**: Include a footer with the last update date, store address, customer support information, and a link to the Contact Us page on all pages.
- **Semantic HTML**: Use semantic HTML tags such as `<article>`, `<nav>`, `<footer>`, `<section>`, and `<figure>`.

## Notes

- Use only prepared statements with named binding parameters for any database SQL.
- Ensure that all images are stored in the `images/` directory and named according to the product ID (e.g., `112.jpeg` for a product with ID `112`).
- Use relative addresses for all links to documents and resources within the site.

## Example Screens

### Products Page (`products.php`)

![Products Page]((http://web1211524.studentprojects.ritaj.ps/ass/assTwo/htdocs/index.php))

### Product Detail Page (`view.php`)

![Product Detail Page]((http://web1211524.studentprojects.ritaj.ps/ass/assTwo/htdocs/show.php?id=53))

### Add Product Page (`add.php`)

![Add Product Page]((http://web1211524.studentprojects.ritaj.ps/ass/assTwo/htdocs/insert.php))

### Edit Product Page (`edit.php`)

![Edit Product Page]((http://web1211524.studentprojects.ritaj.ps/ass/assTwo/htdocs/edit.php?id=53))

---

By following these instructions and using the provided file structure and code examples, you will be able to create a fully functional e-clothing web store application.
