### SHOW CODE DEMONSTRATING HOW FETCH() IS USED. USE PRINT_R(). WITH pre TAG IN BETWEEN.
### index.php
```php
<?php require_once 'core/dbConfig.php'; ?>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    

    <?php
    $stmt = $pdo->prepare("SELECT * FROM owners");

    if ($stmt->execute()) {
        echo "<pre>";
        print_r($stmt->fetch());
        echo "<pre>";
    }
    ?>
</body>
</html>
```
