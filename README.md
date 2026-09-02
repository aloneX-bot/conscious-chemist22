# conscious-chemist22
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Conscious Chemist | Intelligent & Clean Skincare</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700&family=Playfair+Display:wght@600;700&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg: #FAFAF7;
      --surface: #FFFFFF;
      --text: #1C2826;
      --muted: #62726B;
      --primary: #2C4A3E;
      --accent: #E29578;
      --accent-light: #FFDDD2;
      --border: #E5E7E4;
      --radius: 12px;
      --shadow: 0 4px 20px rgba(0, 0, 0, 0.06);
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: 'Plus Jakarta Sans', sans-serif;
      background-color: var(--bg);
      color: var(--text);
      line-height: 1.5;
    }

    /* Header */
    nav {
      position: sticky;
      top: 0;
      background: rgba(250, 250, 247, 0.9);
      backdrop-filter: blur(10px);
      border-bottom: 1px solid var(--border);
      z-index: 100;
      padding: 1rem 1.5rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .brand {
      font-family: 'Playfair Display', serif;
      font-size: 1.4rem;
      font-weight: 700;
      letter-spacing: -0.5px;
      color: var(--primary);
      text-transform: uppercase;
    }

    .cart-btn {
      position: relative;
      background: var(--primary);
      color: white;
      border: none;
      padding: 0.6rem 1.2rem;
      border-radius: 30px;
      cursor: pointer;
      font-weight: 600;
      font-size: 0.9rem;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .cart-count {
      background: var(--accent);
      color: white;
      border-radius: 50%;
      padding: 2px 7px;
      font-size: 0.75rem;
    }

    /* Hero Section */
    .hero {
      position: relative;
      border-radius: var(--radius);
      margin: 1rem 1.5rem;
      overflow: hidden;
      min-height: 380px;
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center;
      color: white;
    }

    .hero-img {
      position: absolute;
      width: 100%;
      height: 100%;
      object-fit: cover;
      top: 0;
      left: 0;
      filter: brightness(0.65);
    }

    .hero-content {
      position: relative;
      z-index: 1;
      padding: 2rem;
      max-width: 600px;
    }

    .hero-title {
      font-family: 'Playfair Display', serif;
      font-size: 2.5rem;
      margin-bottom: 0.5rem;
    }

    .hero-sub {
      font-size: 1rem;
      margin-bottom: 1.5rem;
      opacity: 0.9;
    }

    .hero-cta {
      display: inline-block;
      background: var(--surface);
      color: var(--primary);
      padding: 0.8rem 1.8rem;
      border-radius: 30px;
      text-decoration: none;
      font-weight: 700;
      transition: transform 0.2s;
    }

    .hero-cta:hover {
      transform: translateY(-2px);
    }

    /* Products Carousel / Grid */
    .section-title {
      font-family: 'Playfair Display', serif;
      font-size: 1.8rem;
      margin: 2rem 1.5rem 1rem;
      color: var(--primary);
    }

    .products-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
      gap: 1.5rem;
      padding: 0 1.5rem 2rem;
    }

    .product-card {
      background: var(--surface);
      border-radius: var(--radius);
      padding: 1rem;
      border: 1px solid var(--border);
      box-shadow: var(--shadow);
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }

    .product-card img {
      width: 100%;
      height: 220px;
      object-fit: cover;
      border-radius: 8px;
      margin-bottom: 1rem;
    }

    .product-title {
      font-size: 1.1rem;
      font-weight: 700;
      margin-bottom: 0.25rem;
    }

    .product-desc {
      font-size: 0.85rem;
      color: var(--muted);
      margin-bottom: 0.8rem;
    }

    .product-bottom {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-top: auto;
    }

    .price {
      font-size: 1.1rem;
      font-weight: 700;
      color: var(--primary);
    }

    .add-btn {
      background: var(--accent-light);
      color: var(--primary);
      border: none;
      padding: 0.5rem 1rem;
      border-radius: 20px;
      font-weight: 600;
      cursor: pointer;
      transition: all 0.2s;
    }

    .add-btn:hover {
      background: var(--accent);
      color: white;
    }

    /* Cart Drawer */
    .cart-drawer {
      position: fixed;
      top: 0;
      right: -100%;
      width: 100%;
      max-width: 400px;
      height: 100%;
      background: var(--surface);
      box-shadow: -5px 0 25px rgba(0,0,0,0.15);
      z-index: 1000;
      transition: right 0.3s ease;
      display: flex;
      flex-direction: column;
      padding: 1.5rem;;
    }

    .cart-drawer.active {
      right: 0;
    }

    .cart-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      border-bottom: 1px solid var(--border);
      padding-bottom: 1rem;
      margin-bottom: 1rem;
    }

    .close-cart {
      background: none;
      border: none;
      font-size: 1.5rem;
      cursor: pointer;
    }

    .cart-items {
      flex: 1;
      overflow-y: auto;
      margin-bottom: 1rem;
    }

    .cart-item {
      display: flex;
      justify-content: space-between;
      margin-bottom: 1rem;
      border-bottom: 1px solid var(--border);
      padding-bottom: 0.5rem;
    }

    .cart-total {
      font-size: 1.2rem;
      font-weight: 700;
      display: flex;
      justify-content: space-between;
      margin-bottom: 1rem;
    }

    /* Form Styles */
    form {
      display: flex;
      flex-direction: column;
      gap: 0.8rem;
    }

    input, textarea {
      width: 100%;
      padding: 0.75rem;
      border: 1px solid var(--border);
      border-radius: 8px;
      font-family: inherit;
    }

    .submit-btn {
      background: var(--primary);
      color: white;
      border: none;
      padding: 0.8rem;
      border-radius: 8px;
      font-weight: 700;
      cursor: pointer;
    }

    /* WhatsApp Float */
    .whatsapp-btn {
      position: fixed;
      bottom: 20px;
      left: 20px;
      background: #25D366;
      color: white;
      width: 50px;
      height: 50px;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      text-decoration: none;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
      z-index: 90;
      font-weight: bold;
      font-size: 1.2rem;
    }
  </style>
</head>
<body>

  <!-- Navigation -->
  <nav>
    <div class="brand">Conscious Chemist</div>
    <button class="cart-btn" onclick="toggleCart()">
      Cart <span class="cart-count" id="cart-count">0</span>
    </button>
  </nav>

  <!-- Hero Section -->
  <section class="hero">
    <img src="https://i.ibb.co/vCSnPwXC/Screenshot-20260901-191214-Whats-App.jpg" class="hero-img" alt="Conscious Chemist Hero">
    <div class="hero-content">
      <h1 class="hero-title">Clean, Intelligent Skincare</h1>
      <p class="hero-sub">Science-backed formulations for biocompatible, healthy, glowing skin.</p>
      <a href="#products" class="hero-cta">Explore Best Sellers</a>
    </div>
  </section>

  <!-- Products Section -->
  <h2 class="section-title" id="products">Our Bestsellers</h2>
  <div class="products-grid" id="products-container"></div>

  <!-- Cart Drawer -->
  <div class="cart-drawer" id="cart-drawer">
    <div class="cart-header">
      <h3>Your Shopping Cart</h3>
      <button class="close-cart" onclick="toggleCart()">&times;</button>
    </div>
    
    <div class="cart-items" id="cart-items">
      <p style="color: var(--muted);">Your cart is currently empty.</p>
    </div>

    <div class="cart-total">
      <span>Total:</span>
      <span id="cart-total-price">₹0</span>
    </div>

    <!-- Order Submission Form via Formspree -->
    <form action="https://formspree.io/f/optimuscore01@gmail.com" method="POST" id="checkout-form" onsubmit="prepareOrderDetails()">
      <input type="text" name="Customer Name" placeholder="Full Name" required />
      <input type="tel" name="Phone Number" placeholder="Phone Number" required />
      <textarea name="Shipping Address" rows="2" placeholder="Shipping Address" required></textarea>
      
      <!-- Hidden field to pass cart details -->
      <input type="hidden" name="Order Summary" id="order-summary-input" />
      <input type="hidden" name="Total Amount" id="order-total-input" />
      
      <button type="submit" class="submit-btn">Place Order</button>
    </form>
  </div>

  <!-- WhatsApp Floating Button -->
  <a href="https://wa.me/910000000000" class="whatsapp-btn" target="_blank" title="Chat on WhatsApp">WA</a>

  <script>
    // Product Data
    const products = [
      {
        id: 1,
        name: "Berry Bright Sunscreen",
        desc: "SPF 50 PA++++ | Niacinamide & Berry Extracts",
        price: 499,
        image: "https://i.ibb.co/fwDpr9S/Screenshot-20260901-191230-Whats-App.jpg"
      },
      {
        id: 2,
        name: "Hyaluronic Acid Hydra Gel",
        desc: "72-Hr Hydration | Ultra Lightweight Formula",
        price: 599,
        image: "https://i.ibb.co/fwDpr9S/Screenshot-20260901-191230-Whats-App.jpg"
      },
      {
        id: 3,
        name: "Snail Magic Repair Cream",
        desc: "Barrier Repair & Deep Nourishment",
        price: 649,
        image: "https://i.ibb.co/fwDpr9S/Screenshot-20260901-191230-Whats-App.jpg"
      }
    ];

    let cart = [];

    // Render Products
    function renderProducts() {
      const container = document.getElementById('products-container');
      container.innerHTML = products.map(product => `
        <div class="product-card">
          <img src="${product.image}" alt="${product.name}">
          <div>
            <div class="product-title">${product.name}</div>
            <div class="product-desc">${product.desc}</div>
          </div>
          <div class="product-bottom">
            <span class="price">₹${product.price}</span>
            <button class="add-btn" onclick="addToCart(${product.id})">+ Add</button>
          </div>
        </div>
      `).join('');
    }

    // Toggle Cart Drawer
    function toggleCart() {
      document.getElementById('cart-drawer').classList.toggle('active');
    }

    // Add to Cart
    function addToCart(productId) {
      const product = products.find(p => p.id === productId);
      const existing = cart.find(item => item.id === productId);

      if (existing) {
        existing.qty += 1;
      } else {
        cart.push({ ...product, qty: 1 });
      }

      updateCart();
      toggleCart();
    }

    // Update Cart UI
    function updateCart() {
      const cartItemsContainer = document.getElementById('cart-items');
      const cartCount = document.getElementById('cart-count');
      const cartTotalPrice = document.getElementById('cart-total-price');

      const totalItems = cart.reduce((sum, item) => sum + item.qty, 0);
      const totalPrice = cart.reduce((sum, item) => sum + (item.price * item.qty), 0);

      cartCount.innerText = totalItems;
      cartTotalPrice.innerText = `₹${totalPrice}`;

      if (cart.length === 0) {
        cartItemsContainer.innerHTML = `<p style="color: var(--muted);">Your cart is currently empty.</p>`;
        return;
      }

      cartItemsContainer.innerHTML = cart.map(item => `
        <div class="cart-item">
          <div>
            <strong>${item.name}</strong><br>
            <small>₹${item.price} x ${item.qty}</small>
          </div>
          <div><strong>₹${item.price * item.qty}</strong></div>
        </div>
      `).join('');
    }

    // Prepare order payload before Formspree submission
    function prepareOrderDetails() {
      if (cart.length === 0) {
        alert("Your cart is empty! Add products before checking out.");
        event.preventDefault();
        return;
      }

      const summary = cart.map(item => `${item.name} (x${item.qty}) - ₹${item.price * item.qty}`).join(', ');
      const total = cart.reduce((sum, item) => sum + (item.price * item.qty), 0);

      document.getElementById('order-summary-input').value = summary;
      document.getElementById('order-total-input').value = `₹${total}`;
    }

    // Initialize
    renderProducts();
  </script>
</body>
</html>
