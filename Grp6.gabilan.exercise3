<?php
$filePath = 'feedback.txt';

if ($_SERVER['REQUEST_METHOD'] == 'POST' && isset($_POST['newContent'])) {
    $newContent = htmlspecialchars($_POST['newContent']) . "\n\n";

    file_put_contents($filePath, $newContent, FILE_APPEND);

    $message = "Your message has been added to the guest comment!";
}

if (file_exists($filePath)) {
    $fileContent = file_get_contents($filePath);
    $fileLines = file($filePath);
} else {
    $initialContent = "Share your thoughts about our Website!";
    file_put_contents($filePath, $initialContent);
    $fileContent = $initialContent;
    $fileLines = file($filePath);
}
?>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Website </title>
    <link rel="stylesheet" href="feedback.css">
</head>
<body>

  <header>
      <h1>Give Us Your Feedback</h1>
      <p>Share your thoughts on our website and provide feedback!</p>
  </header>

<div class="container">

    <?php if (isset($message)): ?>
        <p class="success"><?php echo $message; ?></p>
    <?php endif; ?>

    <div class="message">
        <h2>Thoughts From Our Visitors</h2>
        <pre><?php echo htmlspecialchars($fileContent); ?></pre>
    </div>

    <div class="add-entry">
        <h2>Add Your Message</h2>
        <form action="" method="POST">
            <textarea class="message-text" name="newContent" placeholder="Share your thoughts about our website..." required></textarea>
            <button type="submit" class="send">Submit</button>
        </form>
    </div>
</div>
<footer>
        <p>&copy; 2024 Group 6. All rights reserved.</p>
        <p><a href="privacy-policy.html" class="footer-link">Privacy Policy</a> | <a href="terms-of-service.html" class="footer-link">Terms of Service</a></p>
    </footer>

</body>
</html>
