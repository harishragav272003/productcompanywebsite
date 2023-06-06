# Web Design for a Software Product Company

## AIM:

To design a static website for a software product company company.

## DESIGN STEPS:

### Step 1:

Requirement collection.

### Step 2:

Creating the layout using HTML and CSS.

### Step 3:

Updating the sample content.

### Step 4:

Choose the appropriate style and color scheme.

### Step 5:

Validate the layout in various browsers.

### Step 6:

Validate the HTML code.

### Step 6:

Publish the website in the given URL.

## PROGRAM :
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Adidas - Indian Cricket Jerseys</title>
  <style>
    /* Reset default styles */
    body, h1, h2, h3, p, ul, li {
      margin: 0;
      padding: 0;
    }

    body {
      font-family: Arial, sans-serif;
    }

    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 20px;
    }

    header {
      background: #000;
      color: #fff;
    }

    header h1 {
      font-size: 24px;
      font-weight: bold;
      padding: 10px;
    }

    nav ul {
      list-style: none;
      display: flex;
      justify-content: flex-end;
      align-items: center;
    }

    nav ul li {
      margin-left: 20px;
    }

    nav ul li a {
      color: #fff;
      text-decoration: none;
    }

    section {
      padding: 40px 0;
    }

    section h2 {
      font-size: 32px;
      margin-bottom: 20px;
    }

    .product-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 20px;
    }

    .product {
      border: 1px solid #ddd;
      padding: 20px;
      text-align: center;
    }

    .product img {
      max-width: 100%;
      height: auto;
      margin-bottom: 10px;
    }

    .product h3 {
      font-size: 20px;
      margin-bottom: 10px;
    }

    .product p {
      margin-bottom: 10px;
    }

    .btn {
      display: inline-block;
      padding: 10px 20px;
      background: #000;
      color: #fff;
      text-decoration: none;
      transition: background 0.3s ease;
    }

    .btn:hover {
      background: #333;
    }

    #cart {
      padding: 40px 0;
      background-color: #f5f5f5;
    }

    #cart .container {
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
    }

    #cart h2 {
      font-size: 24px;
      margin-bottom: 20px;
    }

    #cartItems {
      list-style: none;
      padding: 0;
    }

    #cartItems li {
      margin-bottom: 10px;
      font-size: 18px;
    }

    #totalCost {
      font-size: 20px;
      font-weight: bold;
    }

    #placeOrderBtn {
      padding: 10px 20px;
      background-color: #000;
      color: #fff;
      border: none;
      text-decoration: none;
      font-size: 18px;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }

    #placeOrderBtn:hover {
      background-color: #333;
    }

    footer {
      background: #000;
      color: #fff;
      padding: 20px 0;
      text-align: center;
    }
  </style>
</head>
<body>
  <header>
    <nav>
      <div class="container">
        <h1>Adidas</h1>
        <ul>
          <li><a href="#home">Home</a></li>
          <li><a href="#products">Products</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </div>
    </nav>
  </header>

  <section id="home">
    <div class="container">
      <h2>Welcome to Adidas</h2>
      <p>Shop the latest Indian cricket jerseys for Test, ODI, and T20I matches.</p>
    </div>
  </section>

  <section id="products">
    <div class="container">
      <h2>Indian Cricket Jerseys</h2>
      <div class="product-grid">
        <div class="product">
          <img src="/static/images/test1.jpg" alt="Indian Test Jersey">
          <h3>Indian Test Jersey</h3>
          <p>Price: Rs.4999</p>
          <a href="#" class="btn" onclick="addToCart('Indian Test Jersey')">Add to Cart</a>
        </div>
        <div class="product">
          <img src="/static/images/odi1.jpg" alt="Indian ODI Jersey">
          <h3>Indian ODI Jersey</h3>
          <p>Price: Rs.4999</p>
          <a href="#" class="btn" onclick="addToCart('Indian ODI Jersey')">Add to Cart</a>
        </div>
        <div class="product">
          <img src="/static/images/t201.jpg" alt="Indian T20I Jersey">
          <h3>Indian T20I Jersey</h3>
          <p>Price: Rs.4999</p>
          <a href="#" class="btn" onclick="addToCart('Indian T20I Jersey')">Add to Cart</a>
        </div>
      </div>
    </div>
  </section>

  <section id="cart">
    <div class="container">
      <h2>Cart</h2>
      <ul id="cartItems"></ul>
      <p>Total Cost: Rs. <span id="totalCost">0</span></p>
      <button id="placeOrderBtn" onclick="placeOrder()">Place Order</button>
    </div>
  </section>

  <section id="contact">
    <div class="container">
      <h2>Contact Us</h2>
      <p>For any inquiries or support, please reach out to us:</p>
      <ul>
        <li>Email: info@adidas.com</li>
        <li>Phone: +1 123-456-7890</li>
      </ul>
    </div>
  </section>

  <footer>
    <div class="container">
      <p>&copy; 2023 Adidas. Developed by Harish Ragav. All rights reserved.</p>
    </div>
  </footer>

  <script>
    let cart = [];
    let totalCost = 0;

    function addToCart(product) {
      cart.push(product);
      totalCost += 4999;
      updateCart();
    }

    function updateCart() {
      const cartItems = document.getElementById('cartItems');
      const totalCostElement = document.getElementById('totalCost');

      cartItems.innerHTML = '';
      cart.forEach((product) => {
        const listItem = document.createElement('li');
        listItem.textContent = product;
        cartItems.appendChild(listItem);
      });

      totalCostElement.innerText = totalCost;
    }

    function placeOrder() {
      if (cart.length === 0) {
        alert('Your cart is empty. Please add items to your cart.');
        return;
      }

      // Here you can implement the logic to place the order
      // You can use the 'cart' array and 'totalCost' variable to process the order

      alert('Order placed successfully! Thank you for shopping with Adidas.');
      cart = [];
      totalCost = 0;
      updateCart();
    }
  </script>
</body>
</html>
```


## OUTPUT:

### Home Page:
![image](https://github.com/harishragav272003/productcompanywebsite/assets/119345345/77b24c14-2174-4d2c-8806-dcbf35dc7d28)

### Add Products to Cart:
![image](https://github.com/harishragav272003/productcompanywebsite/assets/119345345/4548ac0b-d384-49c2-b0dd-4c4043e1d4f4)

### Placing Order :
![image](https://github.com/harishragav272003/productcompanywebsite/assets/119345345/ab5635dc-274c-4ac6-80eb-7682b7cb0961)


## Result:

Thus a website is designed for the software product company and the HTML,CSS code are validated.
