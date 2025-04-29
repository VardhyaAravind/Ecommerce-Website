### Step-by-Step Documentation for Database Setup


#### Step 1: Creating the Database
1. Open **phpMyAdmin** or any database management tool.
2. Create a new database named `ecommerce`.
3. Run the following SQL commands to create the necessary tables:

**Cart Table**
```sql
CREATE TABLE cart (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT NOT NULL,
    product_id INT NOT NULL,
    quantity INT NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
);
```

**Products Table**
```sql
CREATE TABLE products (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    price DECIMAL(10, 2) NOT NULL,
    description TEXT,
    image VARCHAR(255),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

**Users Table**
```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL,
    email VARCHAR(100) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    role ENUM('user', 'admin') DEFAULT 'user'
);
```

---

#### Step 2: Setting Up `db.php`
1. Create a folder named `includes` in your project directory.
2. Inside this folder, create a file named `db.php`.
3. Add the following code:

**`db.php`**
```php
<?php
$host = 'localhost';
$dbname = 'ecommerce';
$user = 'root';
$password = '';

try {
    $conn = new PDO("mysql:host=$host;dbname=$dbname", $user, $password);
    $conn->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
} catch (PDOException $e) {
    echo "Connection failed: " . $e->getMessage();
}
?>
```

