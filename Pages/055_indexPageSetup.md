### Step-by-Step Documentation for the Home Page (`index.php`)

---

#### 1. Create the `index.php` File
- Place this file in the root directory.
- Add the following HTML structure with navigation links and a container for products:

```php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Online Store</title>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>
    <header>
        <div class="header-container">
            <h1>Welcome to Our Store</h1>
            <nav>
                <a href="pages/login.php">Login</a>
                <a href="pages/register.php">Register</a>
                <a href="pages/cart.php" class="cart-link">
                    <img src="images/cart-icon.png" alt="Cart" class="cart-icon">
                    Cart
                </a>
                <form method="POST" style="display: inline;">
                    <button type="submit" name="logout" class="logout-button">Logout</button>
                </form>
            </nav>
        </div>
    </header>
    <div class="main-container">
        <main>
            <h2>Products</h2>
            <div class="product-list">
                <!-- PHP to display products will go here -->
            </div>
        </main>
    </div>
    <footer>
        <p>&copy; <?= date('Y'); ?> Online Store. All rights reserved.</p>
    </footer>
</body>
</html>
```

---

