<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Future Management</title: 0;
      padding: 0: border-box;
      font-family: 'Segoe UI', Tahoma, Verdana, sans-serif;
    }

    body {
      background: #f4f;
      color333;
     0    }

    header {
      background: #243b55;
      color: white padding: 20px;
      text-align: center;
      font-size: 24px;
      font;
    }

    .container {
      max-width: 800px;
      margin:0px auto;
      background: white;
      padding: 25px;
      border-radius: 10px;
-shadow: 4px 10(0, 0, 0, 0.1);
    }

2 {
      margin-bottom: 20px;
      color: #25;
    }

    . {
      display: flex;
      gap: 10px;
      margin-bottom: 15px;
    }

    input[type="text"],
    input[type="number"] {
      padding: 10px border: 1px solid #ccc;
      border-radius: 5px;
: 1;
    }

    button {
      padding: 1      background-color: #243b;
      color;
      border: none 5px;
      cursor:    }

    button:hover {
      background-color: #1a40;
    }

    table {
      width: 100%;
      border-collapse: collapse;
      margin-top: 20px;
    }

    td {
      padding: 12px;
      text-align: left;
      border: 1px solid #ccc;
    }

    th {
      background-color: #3b55;
      color:    }

    .search-bar {
     ;
    }

        1      width: 100%;
      border-radius:px;
    .no-products {
      text-align: center;
      color: #888;
      font-style: italic;
    }
  </style>
</head>
<body>

  <header>
    <h1>Future Business Product Management</h1>
  </header>

  <div class="container">
    <h2>Manage Products</h2>

    <div class="search      <input type="text" id="searchInput" placeholder="Search products..." />
    </div>

    <div class="form-group">
      <input type="text" id="productName" placeholder="Product Name" />
      <input type="number" id="productPrice" placeholder="addProduct Product</button>
    </div>

    <table id="productTable <thead>
        <tr>
          <th>Product Name</th>
th>Price</th>
          <th>Action</th>
        </tr>
      </      <tbody>
        <!-- Products will be added here -->
      </tbody>
    </table>
div < products = function      const name = document.getElementById("productName").value.trim();
      const price = parseFloat(document.getElementById("productPrice").value);

      if (!name || isNaN(price)) {
        alert("Please enter valid product name
