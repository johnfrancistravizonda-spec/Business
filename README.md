<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Graham Bites - Inventory Management</title>

    <link rel="stylesheet" href="style.css">
</head>
<body>

    <header>
        <h1>John's Inventory Management System</h1>
        <h2>Graham Bites</h2>
        <p>Manage your products and stocks easily</p>
    </header>

    <main class="container">

        <!-- DASHBOARD -->
        <section class="dashboard">

            <div class="card">
                <h3>Total Products</h3>
                <h2 id="totalProducts">0</h2>
            </div>

            <div class="card">
                <h3>Total Stock</h3>
                <h2 id="totalStock">0</h2>
            </div>

            <div class="card">
                <h3>Inventory Value</h3>
                <h2 id="totalValue">₱0.00</h2>
            </div>

        </section>

        <!-- PRODUCT FORM -->
        <section class="form-container">

            <h2 id="formTitle">Add New Product</h2>

            <form id="productForm">

                <div class="form-grid">

                    <input
                        type="text"
                        id="productName"
                        placeholder="Product Name"
                        maxlength="80"
                        required
                    >

                    <input
                        type="text"
                        id="category"
                        placeholder="Category"
                        maxlength="50"
                        required
                    >

                    <input
                        type="number"
                        id="quantity"
                        placeholder="Quantity"
                        min="0"
                        step="1"
                        required
                    >

                    <input
                        type="number"
                        id="price"
                        placeholder="Price (₱)"
                        min="0"
                        step="0.01"
                        required
                    >

                </div>

                <div class="form-buttons">

                    <button type="submit" class="add-btn" id="submitBtn">
                        Add Product
                    </button>

                    <button
                        type="button"
                        class="clear-btn"
                        id="clearBtn"
                    >
                        Clear
                    </button>

                </div>

            </form>

        </section>

        <!-- INVENTORY TABLE -->
        <section class="table-container">

            <h2>Product Inventory</h2>

            <input
                type="text"
                class="search"
                id="search"
                placeholder="Search products..."
            >

            <div class="table-scroll">

                <table>

                    <thead>
                        <tr>
                            <th>Product Name</th>
                            <th>Category</th>
                            <th>Quantity</th>
                            <th>Price</th>
                            <th>Total</th>
                            <th>Status</th>
                            <th>Actions</th>
                        </tr>
                    </thead>

                    <tbody id="productList"></tbody>

                </table>

            </div>

            <p id="emptyMessage">
                No products found.
            </p>

        </section>

    </main>

    <footer>
        <p>Graham Bites Inventory Management System</p>
    </footer>

    <script src="script.js"></script>

</body>
</html>
/* GENERAL SETTINGS */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: Arial, sans-serif;
}

body {
    background: #f3f5f9;
    color: #333;
}

/* HEADER */
header {
    background: #243b55;
    color: white;
    padding: 25px 15px;
    text-align: center;
}

header h1 {
    font-size: 27px;
    margin-bottom: 8px;
}

header h2 {
    font-size: 21px;
    margin-bottom: 8px;
}

header p {
    font-size: 14px;
}

/* MAIN CONTAINER */
.container {
    max-width: 1200px;
    margin: 30px auto;
    padding: 20px;
}

/* DASHBOARD */
.dashboard {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
    margin-bottom: 25px;
}

.card {
    background: white;
    padding: 25px;
    border-radius: 10px;
    box-shadow: 0 3px 10px #00000010;
    border-left: 5px solid #243b55;
}

.card h3 {
    color: #777;
    font-size: 15px;
    margin-bottom: 12px;
}

.card h2 {
    color: #243b55;
    font-size: 28px;
}

/* FORM AND TABLE */
.form-container,
.table-container {
    background: white;
    padding: 25px;
    border-radius: 10px;
    margin-bottom: 25px;
    box-shadow: 0 3px 10px #00000010;
}

.form-container h2,
.table-container h2 {
    margin-bottom: 20px;
    color: #243b55;
}

/* INPUT FIELDS */
.form-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 15px;
}

input {
    width: 100%;
    padding: 12px;
    border: 1px solid #ddd;
    border-radius: 6px;
    font-size: 14px;
    outline: none;
}

input:focus {
    border-color: #243b55;
    box-shadow: 0 0 4px #243b5533;
}

/* BUTTONS */
button {
    padding: 11px 16px;
    border: none;
    border-radius: 6px;
    cursor: pointer;
    color: white;
    font-weight: bold;
    transition: 0.2s;
}

button:hover {
    opacity: 0.85;
}

.form-buttons {
    margin-top: 15px;
    display: flex;
    gap: 10px;
}

.add-btn {
    background: #243b55;
}

.clear-btn {
    background: #777;
}

.edit-btn {
    background: #e69b25;
    margin: 3px;
}

.delete-btn {
    background: #dc3545;
    margin: 3px;
}

/* SEARCH */
.search {
    margin-bottom: 20px;
    max-width: 350px;
}

/* TABLE */
.table-scroll {
    width: 100%;
    overflow-x: auto;
}

table {
    width: 100%;
    border-collapse: collapse;
    min-width: 750px;
}

th,
td {
    padding: 14px;
    border-bottom: 1px solid #eee;
    text-align: left;
}

th {
    background: #243b55;
    color: white;
}

tr:hover {
    background: #f8f9fc;
}

/* PRODUCT STATUS */
.low-stock {
    color: #dc3545;
    font-weight: bold;
}

.available {
    color: #198754;
    font-weight: bold;
}

.out-stock {
    color: #dc3545;
    font-weight: bold;
}

/* EMPTY MESSAGE */
#emptyMessage {
    text-align: center;
    padding: 20px;
    color: #777;
}

/* FOOTER */
footer {
    background: #243b55;
    color: white;
    padding: 18px;
    text-align: center;
    font-size: 13px;
}

/* MOBILE RESPONSIVE */
@media (max-width: 700px) {

    .dashboard {
        grid-template-columns: 1fr;
    }

    .form-grid {
        grid-template-columns: 1fr;
    }

    .container {
        padding: 12px;
        margin: 15px auto;
    }

    .form-container,
    .table-container {
        padding: 18px;
    }

    header h1 {
        font-size: 21px;
    }

    .card h2 {
        font-size: 25px;
    }
} 
// ======================================
// GRAHAM BITES INVENTORY MANAGEMENT
// ======================================


// LOAD SAVED PRODUCTS
function loadProducts() {
    try {
        const saved = localStorage.getItem("inventory");
        const data = saved ? JSON.parse(saved) : [];

        if (!Array.isArray(data)) {
            return [];
        }

        return data.filter(product =>
            product &&
            typeof product.id === "number" &&
            typeof product.name === "string" &&
            typeof product.category === "string" &&
            Number.isInteger(product.quantity) &&
            product.quantity >= 0 &&
            Number.isFinite(product.price) &&
            product.price >= 0
        );

    } catch (error) {
        console.error("Error loading products:", error);
        return [];
    }
}


let products = loadProducts();
let editId = null;


// GET HTML ELEMENTS
const productForm = document.getElementById("productForm");
const productName = document.getElementById("productName");
const category = document.getElementById("category");
const quantity = document.getElementById("quantity");
const price = document.getElementById("price");

const productList = document.getElementById("productList");
const search = document.getElementById("search");

const totalProducts = document.getElementById("totalProducts");
const totalStock = document.getElementById("totalStock");
const totalValue = document.getElementById("totalValue");

const emptyMessage = document.getElementById("emptyMessage");
const formTitle = document.getElementById("formTitle");
const submitBtn = document.getElementById("submitBtn");
const clearBtn = document.getElementById("clearBtn");


// SAVE PRODUCTS
function saveProducts() {
    try {
        localStorage.setItem(
            "inventory",
            JSON.stringify(products)
        );
    } catch (error) {
        alert("Unable to save products. Your browser storage may be full.");
        console.error(error);
    }
}


// FORMAT CURRENCY
function formatCurrency(amount) {
    return "₱" + amount.toLocaleString("en-PH", {
        minimumFractionDigits: 2,
        maximumFractionDigits: 2
    });
}


// ESCAPE TEXT FOR SAFE HTML DISPLAY
function escapeHTML(value) {
    return String(value).replace(/[&<>"']/g, character => {
        const entities = {
            "&": "&amp;",
            "<": "&lt;",
            ">": "&gt;",
            '"': "&quot;",
            "'": "&#039;"
        };

        return entities[character];
    });
}


// ADD OR UPDATE PRODUCT
productForm.addEventListener("submit", function(event) {

    event.preventDefault();

    const name = productName.value.trim();
    const productCategory = category.value.trim();

    const productQuantity = Number(quantity.value);
    const productPrice = Number(price.value);

    // VALIDATION
    if (!name || !productCategory) {
        alert("Please complete all product information.");
        return;
    }

    if (
        quantity.value.trim() === "" ||
        !Number.isInteger(productQuantity) ||
        productQuantity < 0
    ) {
        alert("Please enter a valid whole-number quantity.");
        return;
    }

    if (
        price.value.trim() === "" ||
        !Number.isFinite(productPrice) ||
        productPrice < 0
    ) {
        alert("Please enter a valid price.");
        return;
    }

    if (!Number.isSafeInteger(Date.now())) {
        alert("Unable to generate product ID.");
        return;
    }

    if (editId !== null) {

        // UPDATE EXISTING PRODUCT
        const index = products.findIndex(
            product => product.id === editId
        );

        if (index !== -1) {
            products[index] = {
                ...products[index],
                name: name,
                category: productCategory,
                quantity: productQuantity,
                price: productPrice
            };

            alert("Product updated successfully!");
        }

    } else {

        // ADD NEW PRODUCT
        const newProduct = {
            id: Date.now(),
            name: name,
            category: productCategory,
            quantity: productQuantity,
            price: productPrice
        };

        products.push(newProduct);

        alert("Product added successfully!");
    }

    saveProducts();
    resetForm();
    displayProducts();

});


// DISPLAY PRODUCTS
function displayProducts() {

    productList.innerHTML = "";

    const searchText = search.value.toLowerCase().trim();

    const filteredProducts = products.filter(product => {

        return (
            product.name.toLowerCase().includes(searchText) ||
            product.category.toLowerCase().includes(searchText)
        );

    });

    filteredProducts.forEach(product => {

        const total = product.quantity * product.price;

        let status = "";
        let statusClass = "";

        if (product.quantity === 0) {
            status = "Out of Stock";
     
