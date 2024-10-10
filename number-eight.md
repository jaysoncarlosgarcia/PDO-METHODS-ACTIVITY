### SHOW CODE DEMONSTRATING AN SQL QUERY’S RESULT SET IS RENDERED ON AN HTML TABLE
### index.php
```php
<?php require_once 'core/dbConfig.php'; ?>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Owners Table</title>
</head>
<body>
    
    <h1>Owners Table</h1>

    <?php
    // Rendering a SQL query result set on an HTML table

    $stmt = $pdo->prepare("SELECT * FROM owners");

    if ($stmt->execute()) {
        $owners = $stmt->fetchAll(PDO::FETCH_ASSOC);

        if ($owners) {
            // Start the HTML table
            echo "<table border='1' cellpadding='10' cellspacing='0'>";
            echo "<thead>";
            echo "<tr>";

            // Dynamically generate the table headers based on column names
            foreach ($owners[0] as $column => $value) {
                echo "<th>{$column}</th>";
            }

            echo "</tr>";
            echo "</thead>";
            echo "<tbody>";

            // Loop through each row and display it in the table
            foreach ($owners as $owner) {
                echo "<tr>";
                foreach ($owner as $value) {
                    echo "<td>{$value}</td>";
                }
                echo "</tr>";
            }

            echo "</tbody>";
            echo "</table>";
        } else {
            echo "<p>No data found in the 'owners' table.</p>";
        }
    } else {
        echo "<p>Query Failed.</p>";
    }

    ?>
</body>
</html>
```
