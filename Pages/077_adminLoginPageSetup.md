<?php
include '../includes/db.php';
session_start();

if (isset($_POST['login'])) {
    $email = $_POST['email'];
    $password = $_POST['password'];

    // Check if the email belongs to an admin
    $stmt = $conn->prepare("SELECT * FROM users WHERE email = ? AND role = 'admin'");
    $stmt->execute([$email]);
    $user = $stmt->fetch(PDO::FETCH_ASSOC);

    if ($user && password_verify($password, $user['password'])) {
        // Start admin session and redirect to dashboard
        $_SESSION['admin_id'] = $user['id'];
        header("Location: dashboard.php");
        exit();
    } else {
        echo "<p style='color:red; text-align:center;'>Invalid credentials or not an admin.</p>";
    }
}
?>
