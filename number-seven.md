### SHOW CODE DEMONSTRATING UPDATING OF RECORD FROM YOUR DATABASE
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
    // Updating a record
    
    $query = "UPDATE Owners SET FirstName = ?, LastName = ?, PhoneNumber = ?, Email = ?, Address = ? WHERE OwnerID = 11";

    $stmt = $pdo->prepare($query);

    $executeQuery = $stmt->execute(
        ["Jane", "Doe", "012345678912", "janedoe@gmail.com", "1234 Alpha Street"]
    );
    
    if ($executeQuery) {
        echo "Update successful";
    }
    else {
        echo "Query failed";
    }

    ?>
</body>
</html>
```
