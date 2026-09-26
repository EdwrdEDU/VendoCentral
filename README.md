# Vendo Central ng Pilipinas

Vendo Central is a PHP and MySQL web application for managing products, suppliers, customers, and orders. The application supports three user roles:

- **Admin**: manage administrators, suppliers, customers, and products.
- **Supplier**: manage supplier products and contact details.
- **Customer**: browse products, manage a cart, and place orders.

## Requirements

- PHP 7.4 or later with the MySQLi extension
- MySQL or MariaDB
- Apache, such as the server included with XAMPP
- A modern web browser

## Installation

1. Copy or clone this project into the web root of your local server. For XAMPP, use:

	```text
	C:\xampp\htdocs\SVMS
	```

2. Start **Apache** and **MySQL** from the XAMPP control panel.

3. Create the application database. You can use the MySQL command line:

	```bash
	mysql -u root -p < vendocentral_db.sql
	```

	Alternatively, open `vendocentral_db.sql` in phpMyAdmin and select **Import**. The script creates the `vendocentral_db` database and its tables.

4. Check the database settings in `config/constants.php`:

	```php
	define('HOST_NAME', 'localhost');
	define('USER_NAME', 'root');
	define('PASSWORD', '');
	define('DB_NAME', 'vendocentral_db');
	```

	Update the username and password if your MySQL installation uses different credentials.

5. Open the application at:

	```text
	http://localhost/SVMS/
	```

## Demo Accounts

The SQL seed file includes these accounts:

| Role | Email | Password |
| --- | --- | --- |
| Admin | `admin@gmail.com` | `admin123` |
| Supplier | `supplier@gmail.com` | `supplier123` |
| Customer | `customer@gmail.com` | `customer123` |

Change or remove these credentials before deploying the application publicly.

## Main Pages

- `index.php` - login page
- `registration.php` - user registration
- `homepage.php` - customer storefront
- `product_detail.php` - product details
- `cart.php` - shopping cart
- `order.php` - customer orders
- `dashboard_admin.php` - administrator dashboard
- `dashboard_supplier.php` - supplier dashboard

## Project Structure

```text
config/              Database connection and constants
images/              User and application images
includes/             Shared headers and footer
productimages/        Product images
terms/                Supplier terms and related files
*.php                 Application pages and form handlers
vendocentral_db.sql   Database schema and demo data
```

## Development Notes

- Bootstrap 5.3.2 and Bootstrap Icons are loaded from CDNs.
- The application currently expects MySQL to be available on `localhost`.
- Sessions are used to identify the logged-in user and role.
- Do not use the demo credentials in production.
- Before production deployment, passwords should be stored with `password_hash()` and verified with `password_verify()`, and database credentials should be kept outside the public web root.

## License

No license has been specified for this project.
