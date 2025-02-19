# Ask for folder name
$folder = Read-Host "Enter the project folder name"

# Create the folder if it doesn't exist
New-Item -ItemType Directory -Path $folder -Force | Out-Null

# Create index.html with boilerplate code
@"
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Project</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Welcome to My Project</h1>
    <script src="script.js"></script>
</body>
</html>
"@ | Set-Content "$folder\index.html"

# Create style.css with new boilerplate code
@"
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

html,
body {
    height: 100%;
    width: 100%;
}
"@ | Set-Content "$folder\style.css"

# Create an empty script.js file
New-Item -ItemType File -Path "$folder\script.js" -Force | Out-Null

Write-Host "Project '$folder' created with index.html, style.css, and an empty script.js!"
