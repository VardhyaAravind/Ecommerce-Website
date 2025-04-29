```php
<?php
session_start(); // Start the session

// Destroy the session
session_unset(); // Unset all session variables
session_destroy(); // Destroy the session

// Redirect to the login page
header('Location: login.php');
exit();
?>
```

**Explanation**:
- `session_start()`: Initializes the session.
- `session_unset()`: Frees all session variables.
- `session_destroy()`: Completely terminates the session.
- `header('Location: login.php')`: Redirects the user to the login page after the session ends.

---

#### Step 3: Add a Logout Link to Other Pages
To ensure users can log out from anywhere, add a logout link to the navigation bar on user-facing pages like `index.php`:

```html
<li><a href="pages/logout.php">Logout</a></li>
```

---

