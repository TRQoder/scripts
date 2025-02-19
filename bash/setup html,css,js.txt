#!/bin/bash

# Ask for folder name
read -p "Enter the project folder name: " folder

# Create the folder
mkdir -p "$folder"

# Navigate into the folder
cd "$folder" || exit

# Create index.html with boilerplate code
cat > index.html <<EOF
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
EOF

# Create style.css with the new boilerplate code
cat > style.css <<EOF
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
EOF

# Create an empty script.js file
touch script.js

echo "Project '$folder' created with index.html, style.css, and an empty script.js!"
