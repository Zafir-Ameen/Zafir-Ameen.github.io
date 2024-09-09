<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="A simple GitHub website with a search bar and styled fonts.">
  <title>My GitHub Website</title>

  <!-- Inline CSS -->
  <style>
    /* Apply Berlin Sans FB font with fallback fonts */
    body {
      font-family: "Berlin Sans FB", Arial, sans-serif;
      text-align: center;
      padding: 20px;
      background-color: #f4f4f4;
    }

    /* Style the search bar */
    form {
      display: flex;
      justify-content: center;
      margin-top: 20px;
    }

    input[type="text"] {
      padding: 10px;
      font-size: 16px;
      border: 1px solid #ccc;
      border-radius: 5px;
      width: 300px;
    }

    button {
      padding: 10px 15px;
      font-size: 16px;
      background-color: #4CAF50;
      color: white;
      border: none;
      border-radius: 5px;
      margin-left: 10px;
      cursor: pointer;
    }

    button:hover {
      background-color: #45a049;
    }

    /* General text styling */
    h1 {
      color: #333;
      font-size: 2.5em;
    }

    p {
      font-size: 1.2em;
      color: #666;
    }
  </style>
</head>
<body>
  <h1>Welcome to My GitHub Page!</h1>
  <p>This is a simple website hosted on GitHub Pages.</p>

  <!-- Search Bar -->
  <form action="/search" method="GET">
    <input type="text" placeholder="Search..." name="query" />
    <button type="submit">Search</button>
  </form>
</body>
</html>



