### SHOW CODE DEMONSTRATING INSERTION OF RECORD TO YOUR DATABASE
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
    // Inserting new record
    
    $query = "INSERT INTO Owners (OwnerID, FirstName, LastName, PhoneNumber, Email, Address) VALUES (?, ?, ?, ?, ?, ?)";

    $stmt = $pdo->prepare($query);

    $executeQuery = $stmt->execute(
        [11, 'John', 'Doe', '012345678911', 'johndoe@gmail.com', '1234 Beta Street']
    );
    
    if ($executeQuery) {
        echo "Query successful";
    }
    else {
        echo "Query failed";
    }

    ?>
</body>
</html>
```
