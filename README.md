<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Smart Stationery - Your Complete Stationery & Sports Store</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: #f8f9fa;
            color: #333;
        }

        /* Navigation */
        nav {
            background: linear-gradient(135deg, #FF6B6B 0%, #4ECDC4 100%);
            color: white;
            padding: 15px 0;
            box-shadow: 0 4px 20px rgba(0,0,0,0.15);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .nav-content {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 15px;
        }

        .logo {
            font-size: 2em;
            font-weight: bold;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .nav-menu {
            display: flex;
            gap: 30px;
            align-items: center;
        }

        .nav-menu a {
            color: white;
            text-decoration: none;
            font-size: 1.1em;
            transition: all 0.3s;
            padding: 8px 16px;
            border-radius: 20px;
        }

        .nav-menu a:hover {
            background: rgba(255,255,255,0.2);
            transform: translateY(-2px);
        }

        .search-container {
            position: relative;
            flex: 1;
            max-width: 400px;
        }

        .search-bar {
            width: 100%;
            padding: 12px 20px;
            border-radius: 25px;
            border: none;
            font-size: 1em;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        .cart-btn {
            background: rgba(255,255,255,0.25);
            padding: 12px 25px;
            border-radius: 30px;
            cursor: pointer;
            transition: all 0.3s;
            position: relative;
            border: 2px solid white;
            font-size: 1.1em;
            font-weight: bold;
        }

        .cart-btn:hover {
            background: rgba(255,255,255,0.4);
            transform: scale(1.05);
        }

        .cart-badge {
            background: #FF4757;
            color: white;
            border-radius: 50%;
            padding: 4px 10px;
            font-size: 0.75em;
            position: absolute;
            top: -10px;
            right: -10px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.3);
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 80px 20px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '✏️📚⚽📓🏏📖';
            position: absolute;
            font-size: 8em;
            opacity: 0.1;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            white-space: nowrap;
        }

        .hero-content {
            position: relative;
            z-index: 1;
        }

        .hero h1 {
            font-size: 3.5em;
            margin-bottom: 20px;
            text-shadow: 2px 2px 8px rgba(0,0,0,0.3);
            animation: fadeInDown 1s;
        }

        .hero p {
            font-size: 1.5em;
            margin-bottom: 30px;
            opacity: 0.95;
        }

        .hero-buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
        }

        .cta-button {
            background: white;
            color: #667eea;
            padding: 18px 40px;
            border: none;
            border-radius: 30px;
            font-size: 1.2em;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
        }

        .cta-button:hover {
            transform: translateY(-5px);
            box-shadow: 0 6px 25px rgba(0,0,0,0.3);
        }

        .cta-button.secondary {
            background: transparent;
            color: white;
            border: 2px solid white;
        }

        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Delivery Info Banner */
        .delivery-banner {
            background: linear-gradient(135deg, #4ECDC4 0%, #44A08D 100%);
            color: white;
            padding: 25px 20px;
            text-align: center;
        }

        .delivery-content {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
            gap: 20px;
        }

        .delivery-item {
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 1.1em;
        }

        .delivery-item span {
            font-size: 1.5em;
        }

        /* Categories */
        .categories {
            max-width: 1400px;
            margin: 50px auto;
            padding: 0 20px;
        }

        .section-title {
            font-size: 2.5em;
            margin-bottom: 30px;
            color: #2c3e50;
            text-align: center;
            position: relative;
            padding-bottom: 15px;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: linear-gradient(135deg, #FF6B6B 0%, #4ECDC4 100%);
            border-radius: 2px;
        }

        .category-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
            margin-bottom: 50px;
        }

        .category-card {
            background: white;
            padding: 40px 30px;
            border-radius: 20px;
            text-align: center;
            cursor: pointer;
            transition: all 0.4s;
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
            position: relative;
            overflow: hidden;
        }

        .category-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #FF6B6B 0%, #4ECDC4 100%);
            opacity: 0;
            transition: opacity 0.4s;
        }

        .category-card:hover::before {
            opacity: 0.1;
        }

        .category-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 35px rgba(0,0,0,0.2);
        }

        .category-icon {
            font-size: 4em;
            margin-bottom: 15px;
            position: relative;
            z-index: 1;
        }

        .category-name {
            font-size: 1.4em;
            font-weight: bold;
            color: #2c3e50;
            position: relative;
            z-index: 1;
        }

        .category-count {
            font-size: 0.9em;
            color: #7f8c8d;
            margin-top: 8px;
            position: relative;
            z-index: 1;
        }

        /* Products Section */
        .products {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 20px;
            margin-bottom: 60px;
        }

        .filter-container {
            background: white;
            padding: 25px;
            border-radius: 15px;
            margin-bottom: 30px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.08);
        }

        .filter-buttons {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
            justify-content: center;
        }

        .filter-btn {
            padding: 12px 30px;
            background: white;
            border: 2px solid #4ECDC4;
            color: #4ECDC4;
            border-radius: 25px;
            cursor: pointer;
            transition: all 0.3s;
            font-size: 1.05em;
            font-weight: 600;
        }

        .filter-btn.active {
            background: linear-gradient(135deg, #FF6B6B 0%, #4ECDC4 100%);
            color: white;
            border-color: transparent;
            transform: scale(1.05);
        }

        .filter-btn:hover {
            background: linear-gradient(135deg, #FF6B6B 0%, #4ECDC4 100%);
            color: white;
            border-color: transparent;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
            margin-bottom: 50px;
        }

        .product-card {
            background: white;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
            transition: all 0.4s;
            position: relative;
        }

        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 40px rgba(0,0,0,0.15);
        }

        .product-badge {
            position: absolute;
            top: 15px;
            right: 15px;
            background: #FF4757;
            color: white;
            padding: 6px 15px;
            border-radius: 20px;
            font-size: 0.85em;
            font-weight: bold;
            z-index: 10;
        }

        .product-image {
            width: 100%;
            height: 280px;
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 6em;
            position: relative;
            overflow: hidden;
        }

        .product-image::before {
            content: '';
            position: absolute;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.3) 0%, transparent 70%);
            animation: shimmer 3s infinite;
        }

        @keyframes shimmer {
            0%, 100% { transform: translate(-50%, -50%) scale(1); opacity: 0; }
            50% { transform: translate(-50%, -50%) scale(1.5); opacity: 1; }
        }

        .product-info {
            padding: 25px;
        }

        .product-category {
            color: #4ECDC4;
            font-size: 0.9em;
            font-weight: 600;
            margin-bottom: 8px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .product-name {
            font-size: 1.4em;
            font-weight: bold;
            margin-bottom: 12px;
            color: #2c3e50;
        }

        .product-description {
            color: #7f8c8d;
            margin-bottom: 18px;
            line-height: 1.6;
        }

        .product-rating {
            color: #f39c12;
            margin-bottom: 15px;
        }

        .product-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 20px;
            padding-top: 20px;
            border-top: 2px solid #f8f9fa;
        }

        .price-container {
            display: flex;
            flex-direction: column;
        }

        .product-price {
            font-size: 2em;
            color: #27ae60;
            font-weight: bold;
        }

        .old-price {
            text-decoration: line-through;
            color: #95a5a6;
            font-size: 0.5em;
        }

        .discount-badge {
            background: #27ae60;
            color: white;
            padding: 4px 10px;
            border-radius: 12px;
            font-size: 0.4em;
            margin-left: 8px;
        }

        .add-btn {
            background: linear-gradient(135deg, #FF6B6B 0%, #4ECDC4 100%);
            color: white;
            border: none;
            padding: 14px 28px;
            border-radius: 25px;
            cursor: pointer;
            font-size: 1.05em;
            font-weight: bold;
            transition: all 0.3s;
            box-shadow: 0 4px 15px rgba(78, 205, 196, 0.3);
        }

        .add-btn:hover {
            transform: scale(1.1);
            box-shadow: 0 6px 25px rgba(78, 205, 196, 0.5);
        }

        .add-btn:active {
            transform: scale(0.95);
        }

        /* Cart Modal */
        .cart-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.7);
            z-index: 1000;
            animation: fadeIn 0.3s;
        }

        .cart-modal.active {
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .cart-content {
            background: white;
            border-radius: 25px;
            padding: 35px;
            max-width: 750px;
            width: 90%;
            max-height: 90vh;
            overflow-y: auto;
            box-shadow: 0 15px 60px rgba(0,0,0,0.4);
            animation: slideUp 0.3s;
        }

        @keyframes slideUp {
            from {
                transform: translateY(100px);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        .cart-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
            padding-bottom: 20px;
            border-bottom: 3px solid #f8f9fa;
        }

        .cart-header h2 {
            font-size: 2.2em;
            color: #2c3e50;
        }

        .close-cart {
            background: #FF4757;
            color: white;
            border: none;
            padding: 12px 24px;
            border-radius: 25px;
            cursor: pointer;
            font-size: 1.05em;
            font-weight: bold;
            transition: all 0.3s;
        }

        .close-cart:hover {
            background: #ff3838;
            transform: scale(1.05);
        }

        .cart-items {
            margin-bottom: 30px;
        }

        .cart-item {
            display: flex;
            gap: 20px;
            padding: 20px;
            background: #f8f9fa;
            border-radius: 15px;
            margin-bottom: 20px;
            transition: all 0.3s;
        }

        .cart-item:hover {
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
        }

        .cart-item-image {
            font-size: 4em;
            width: 100px;
            height: 100px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            border-radius: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-shrink: 0;
        }

        .cart-item-details {
            flex: 1;
        }

        .cart-item-name {
            font-size: 1.3em;
            font-weight: bold;
            margin-bottom: 8px;
            color: #2c3e50;
        }

        .cart-item-category {
            color: #4ECDC4;
            font-size: 0.9em;
            margin-bottom: 10px;
        }

        .cart-item-price {
            color: #27ae60;
            font-size: 1.2em;
            font-weight: bold;
        }

        .cart-item-controls {
            display: flex;
            align-items: center;
            gap: 12px;
            margin-top: 15px;
        }

        .qty-btn {
            background: linear-gradient(135deg, #FF6B6B 0%, #4ECDC4 100%);
            color: white;
            border: none;
            width: 40px;
            height: 40px;
            border-radius: 10px;
            cursor: pointer;
            font-size: 1.3em;
            font-weight: bold;
            transition: all 0.3s;
        }

        .qty-btn:hover {
            transform: scale(1.1);
        }

        .qty-display {
            padding: 8px 20px;
            background: white;
            border-radius: 10px;
            font-weight: bold;
            font-size: 1.1em;
            min-width: 50px;
            text-align: center;
        }

        .remove-btn {
            background: #FF4757;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 10px;
            cursor: pointer;
            margin-left: auto;
            transition: all 0.3s;
        }

        .remove-btn:hover {
            background: #ff3838;
            transform: scale(1.05);
        }

        .cart-summary {
            background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
            padding: 25px;
            border-radius: 15px;
            margin-bottom: 25px;
        }

        .summary-row {
            display: flex;
            justify-content: space-between;
            margin-bottom: 15px;
            font-size: 1.15em;
        }

        .summary-total {
            font-size: 1.8em;
            font-weight: bold;
            color: #27ae60;
            border-top: 3px solid #dee2e6;
            padding-top: 20px;
            margin-top: 20px;
        }

        .delivery-options {
            background: white;
            padding: 20px;
            border-radius: 15px;
            margin-bottom: 25px;
            border: 2px solid #4ECDC4;
        }

        .delivery-options h3 {
            color: #2c3e50;
            margin-bottom: 15px;
        }

        .delivery-option {
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 12px;
            margin-bottom: 10px;
            background: #f8f9fa;
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s;
        }

        .delivery-option:hover {
            background: #e9ecef;
        }

        .delivery-option input[type="radio"] {
            width: 20px;
            height: 20px;
            cursor: pointer;
        }

        .checkout-btn {
            width: 100%;
            padding: 20px;
            background: linear-gradient(135deg, #27ae60 0%, #229954 100%);
            color: white;
            border: none;
            border-radius: 15px;
            font-size: 1.4em;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 0 6px 25px rgba(39, 174, 96, 0.4);
        }

        .checkout-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 35px rgba(39, 174, 96, 0.6);
        }

        .empty-cart {
            text-align: center;
            padding: 80px 20px;
            color: #95a5a6;
        }

        .empty-cart-icon {
            font-size: 6em;
            margin-bottom: 25px;
        }

        .empty-cart h3 {
            font-size: 1.8em;
            margin-bottom: 15px;
        }

        /* Features Section */
        .features {
            background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
            padding: 70px 20px;
            margin-top: 60px;
        }

        .features-grid {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 35px;
        }

        .feature-card {
            background: white;
            text-align: center;
            padding: 40px 30px;
            border-radius: 20px;
            transition: all 0.4s;
            box-shadow: 0 5px 20px rgba(0,0,0,0.08);
        }

        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 35px rgba(0,0,0,0.15);
        }

        .feature-icon {
            font-size: 4em;
            margin-bottom: 20px;
        }

        .feature-title {
            font-size: 1.5em;
            font-weight: bold;
            margin-bottom: 15px;
            color: #2c3e50;
        }

        .feature-text {
            color: #7f8c8d;
            line-height: 1.7;
        }

        /* Footer */
        footer {
            background: #2c3e50;
            color: white;
            padding: 50px 20px 30px;
        }

        .footer-content {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-section h3 {
            margin-bottom: 20px;
            font-size: 1.5em;
            color: #4ECDC4;
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-section li {
            margin-bottom: 12px;
        }

        .footer-section a {
            color: #bdc3c7;
            text-decoration: none;
            transition: all 0.3s;
        }

        .footer-section a:hover {
            color: #4ECDC4;
            padding-left: 5px;
        }

        .footer-section p {
            color: #bdc3c7;
            line-height: 1.8;
        }

        .social-icons {
            display: flex;
            gap: 15px;
            margin-top: 15px;
        }

        .social-icon {
            width: 45px;
            height: 45px;
            background: rgba(78, 205, 196, 0.2);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.3s;
            font-size: 1.5em;
        }

        .social-icon:hover {
            background: #4ECDC4;
            transform: translateY(-5px);
        }

        .footer-bottom {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(255,255,255,0.1);
            color: #95a5a6;
        }

        /* Notification */
        .notification {
            position: fixed;
            top: 100px;
            right: 30px;
            background: linear-gradient(135deg, #27ae60 0%, #229954 100%);
            color: white;
            padding: 20px 30px;
            border-radius: 15px;
            box-shadow: 0 6px 30px rgba(0,0,0,0.3);
            z-index: 2000;
            animation: slideInRight 0.4s;
            font-size: 1.1em;
            font-weight: 600;
        }

        @keyframes slideInRight {
            from {
                transform: translateX(500px);
                opacity: 0;
            }
            to {
                transform: translateX(0);
                opacity: 1;
            }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.2em;
            }

            .nav-content {
                flex-direction: column;
            }

            .search-container {
                max-width: 100%;
            }

            .products-grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }

            .filter-buttons {
                justify-content: flex-start;
            }

            .notification {
                right: 20px;
                left: 20px;
                top: 80px;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav>
        <div class="nav-content">
            <div class="logo">
                <span>✏️</span> Smart Stationery
            </div>
            <div class="search-container">
                <input type="text" class="search-bar" placeholder="Search products..." id="searchInput" onkeyup="searchProducts()">
            </div>
            <div class="nav-menu">
                <a href="#home">Home</a>
                <a href="#products">Products</a>
                <a href="#features">Features</a>
                <div class="cart-btn" onclick="toggleCart()">
                    🛒 Cart
                    <span class="cart-badge" id="cartBadge">0</span>
                </div>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <div class="hero" id="home">
        <div class="hero-content">
            <h1>📚 Welcome to Smart Stationery 🏏</h1>
            <p>Your One-Stop Shop for Stationery, Notebooks, Books & Sports Equipment!</p>
            <div class="hero-buttons">
                <button class="cta-button" onclick="document.getElementById('products').scrollIntoView({behavior: 'smooth'})">
                    Shop Now
                </button>
                <button class="cta-button secondary" onclick="toggleCart()">
                    View Cart
                </button>
            </div>
        </div>
    </div>

    <!-- Delivery Banner -->
    <div class="delivery-banner">
        <div class="delivery-content">
            <div class="delivery-item">
                <span>🚚</span>
                <strong>Online Delivery Available</strong>
            </div>
            <div class="delivery-item">
                <span>🏪</span>
                <strong>Offline Store Pickup</strong>
            </div>
            <div class="delivery-item">
                <span>💯</span>
                <strong>100% Genuine Products</strong>
            </div>
            <div class="delivery-item">
                <span>⚡</span>
                <strong>Fast Delivery</strong>
            </div>
        </div>
    </div>

    <!-- Categories -->
    <div class="categories">
        <h2 class="section-title">Browse by Category</h2>
        <div class="category-grid">
            <div class="category-card" onclick="filterProducts('stationery')">
                <div class="category-icon">✏️</div>
                <div class="category-name">Stationery</div>
                <div class="category-count">Pens, Pencils, Colors & More</div>
            </div>
            <div class="category-card" onclick="filterProducts('notebooks')">
                <div class="category-icon">📓</div>
                <div class="category-name">Notebooks</div>
                <div class="category-count">All Types of Notebooks</div>
            </div>
            <div class="category-card" onclick="filterProducts('books')">
                <div class="category-icon">📚</div>
                <div class="category-name">Books</div>
                <div class="category-count">Educational & Story Books</div>
            </div>
            <div class="category-card" onclick="filterProducts('sports')">
                <div class="category-icon">⚽</div>
                <div class="category-name">Sports Equipment</div>
                <div class="category-count">Cricket, Football & More</div>
            </div>
        </div>
    </div>

    <!-- Products Section -->
    <div class="products" id="products">
        <h2 class="section-title">Our Products</h2>
        
        <div class="filter-container">
            <div class="filter-buttons">
                <button class="filter-btn active" onclick="filterProducts('all')">All Products</button>
                <button class="filter-btn" onclick="filterProducts('stationery')">Stationery</button>
                <button class="filter-btn" onclick="filterProducts('notebooks')">Notebooks</button>
                <button class="filter-btn" onclick="filterProducts('books')">Books</button>
                <button class="filter-btn" onclick="filterProducts('sports')">Sports Equipment</button>
            </div>
        </div>

        <div class="products-grid" id="productsGrid"></div>
    </div>

    <!-- Features -->
    <div class="features" id="features">
        <h2 class="section-title">Why Choose Us?</h2>
        <div class="features-grid">
            <div class="feature-card">
                <div class="feature-icon">🚚</div>
                <div class="feature-title">Online & Offline Delivery</div>
                <div class="feature-text">Get your products delivered at home or pick up from our store - your choice!</div>
            </div>
            <div class="feature-card">
                <div class="feature-icon">💰</div>
                <div class="feature-title">Best Prices</div>
                <div class="feature-text">Competitive prices with regular discounts and special offers</div>
            </div>
            <div class="feature-card">
                <div class="feature-icon">✅</div>
                <div class="feature-title">Quality Guaranteed</div>
                <div class="feature-text">100% genuine products from trusted brands</div>
            </div>
            <div class="feature-card">
                <div class="feature-icon">⚡</div>
                <div class="feature-title">Fast Service</div>
                <div class="feature-text">Quick delivery and instant store pickup options</div>
            </div>
        </div>
    </div>

    <!-- Cart Modal -->
    <div class="cart-modal" id="cartModal">
        <div class="cart-content">
            <div class="cart-header">
                <h2>🛒 Your Cart</h2>
                <button class="close-cart" onclick="toggleCart()">Close</button>
            </div>
            <div class="cart-items" id="cartItemsContainer"></div>
            <div class="cart-summary" id="cartSummary" style="display: none;">
                <div class="summary-row">
                    <span>Subtotal:</span>
                    <span>₹<span id="subtotal">0</span></span>
                </div>
                <div class="summary-row">
                    <span>Delivery:</span>
                    <span id="deliveryCharge">₹0</span>
                </div>
                <div class="summary-row summary-total">
                    <span>Total:</span>
                    <span>₹<span id="total">0</span></span>
                </div>
            </div>
            <div class="delivery-options" id="deliveryOptions" style="display: none;">
                <h3>Select Delivery Method:</h3>
                <label class="delivery-option">
                    <input type="radio" name="delivery" value="online" checked>
                    <div>
                        <strong>🚚 Online Delivery (₹40)</strong>
                        <div style="font-size: 0.9em; color: #7f8c8d;">Delivered to your doorstep in 2-3 days</div>
                    </div>
                </label>
                <label class="delivery-option">
                    <input type="radio" name="delivery" value="offline">
                    <div>
                        <strong>🏪 Store Pickup (FREE)</strong>
                        <div style="font-size: 0.9em; color: #7f8c8d;">Collect from our store - Ready in 1 hour</div>
                    </div>
                </label>
            </div>
            <button class="checkout-btn" onclick="checkout()" id="checkoutBtn" style="display: none;">
                Proceed to Checkout
            </button>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-section">
                <h3>Smart Stationery</h3>
                <p>Your trusted partner for all stationery, notebook, book, and sports equipment needs. Quality products at the best prices!</p>
                <div class="social-icons">
                    <div class="social-icon">📘</div>
                    <div class="social-icon">📷</div>
                    <div class="social-icon">💬</div>
                </div>
            </div>
            <div class="footer-section">
                <h3>Quick Links</h3>
                <ul>
                    <li><a href="#home">Home</a></li>
                    <li><a href="#products">Products</a></li>
                    <li><a href="#features">Features</a></li>
                    <li><a href="#">About Us</a></li>
                </ul>
            </div>
            <div class="footer-section">
                <h3>Categories</h3>
                <ul>
                    <li><a href="#" onclick="filterProducts('stationery')">Stationery Items</a></li>
                    <li><a href="#" onclick="filterProducts('notebooks')">Notebooks</a></li>
                    <li><a href="#" onclick="filterProducts('books')">Books</a></li>
                    <li><a href="#" onclick="filterProducts('sports')">Sports Equipment</a></li>
                </ul>
            </div>
            <div class="footer-section">
                <h3>Contact Us</h3>
                <ul>
                    <li>📧 info@smartstationery.com</li>
                    <li>📱 +91 98765 43210</li>
                    <li>📍 123 Main Street, Delhi, India</li>
                    <li>🕒 Mon-Sat: 9 AM - 8 PM</li>
                </ul>
            </div>
        </div>
        <div class="footer-bottom">
            <p>&copy; 2026 Smart Stationery. All Rights Reserved. Made with ❤️ in India</p>
        </div>
    </footer>

    <script>
        // Products Database
        const products = [
            // Stationery Items
            { 
                id: 1, 
                name: 'Premium Pen Set', 
                category: 'stationery', 
                price: 149, 
                oldPrice: 249, 
                description: 'Set of 5 smooth writing pens - Blue, Black, Red', 
                emoji: '✒️',
                rating: '⭐⭐⭐⭐⭐',
                badge: '40% OFF'
            },
            { 
                id: 2, 
                name: 'Pencil Box Complete', 
                category: 'stationery', 
                price: 199, 
                oldPrice: 349, 
                description: 'Pencils, eraser, sharpener, ruler - All in one box', 
                emoji: '✏️',
                rating: '⭐⭐⭐⭐⭐',
                badge: '43% OFF'
            },
            { 
                id: 3, 
                name: 'Color Pencil Set 24', 
                category: 'stationery', 
                price: 299, 
                oldPrice: 499, 
                description: '24 vibrant colors for drawing and coloring', 
                emoji: '🎨',
                rating: '⭐⭐⭐⭐',
                badge: '40% OFF'
            },
            { 
                id: 4, 
                name: 'Marker Set Permanent', 
                category: 'stationery', 
                price: 179, 
                oldPrice: 299, 
                description: 'Waterproof permanent markers - 6 colors', 
                emoji: '🖊️',
                rating: '⭐⭐⭐⭐⭐',
                badge: '40% OFF'
            },
            { 
                id: 5, 
                name: 'Geometry Box Premium', 
                category: 'stationery', 
                price: 249, 
                oldPrice: 399, 
                description: 'Complete math instrument set with compass', 
                emoji: '📐',
                rating: '⭐⭐⭐⭐⭐',
                badge: '38% OFF'
            },
            { 
                id: 6, 
                name: 'Highlighter Set 6 Colors', 
                category: 'stationery', 
                price: 129, 
                oldPrice: 199, 
                description: 'Fluorescent highlighters for study notes', 
                emoji: '🖍️',
                rating: '⭐⭐⭐⭐',
                badge: '35% OFF'
            },

            // Notebooks
            { 
                id: 7, 
                name: 'Single Line Notebook', 
                category: 'notebooks', 
                price: 45, 
                oldPrice: 70, 
                description: '172 pages single ruled notebook for school', 
                emoji: '📓',
                rating: '⭐⭐⭐⭐⭐',
                badge: '36% OFF'
            },
            { 
                id: 8, 
                name: 'Four Line Notebook', 
                category: 'notebooks', 
                price: 40, 
                oldPrice: 65, 
                description: '172 pages four lined for handwriting practice', 
                emoji: '📔',
                rating: '⭐⭐⭐⭐⭐',
                badge: '38% OFF'
            },
            { 
                id: 9, 
                name: 'Long Notebook 300 Pages', 
                category: 'notebooks', 
                price: 89, 
                oldPrice: 149, 
                description: 'Premium quality long notebook for college', 
                emoji: '📒',
                rating: '⭐⭐⭐⭐⭐',
                badge: '40% OFF'
            },
            { 
                id: 10, 
                name: 'Drawing Book A4 Size', 
                category: 'notebooks', 
                price: 79, 
                oldPrice: 129, 
                description: 'Blank pages for sketching and drawing', 
                emoji: '🎨',
                rating: '⭐⭐⭐⭐',
                badge: '39% OFF'
            },
            { 
                id: 11, 
                name: 'Graph Book', 
                category: 'notebooks', 
                price: 55, 
                oldPrice: 90, 
                description: 'Graph paper notebook for mathematics', 
                emoji: '📊',
                rating: '⭐⭐⭐⭐⭐',
                badge: '39% OFF'
            },
            { 
                id: 12, 
                name: 'Practical File Set', 
                category: 'notebooks', 
                price: 149, 
                oldPrice: 249, 
                description: 'Set of 5 practical files for school projects', 
                emoji: '📁',
                rating: '⭐⭐⭐⭐',
                badge: '40% OFF'
            },

            // Books
            { 
                id: 13, 
                name: 'English Grammar Book', 
                category: 'books', 
                price: 299, 
                oldPrice: 499, 
                description: 'Complete English grammar guide with exercises', 
                emoji: '📕',
                rating: '⭐⭐⭐⭐⭐',
                badge: '40% OFF'
            },
            { 
                id: 14, 
                name: 'Math Practice Book', 
                category: 'books', 
                price: 349, 
                oldPrice: 549, 
                description: 'Mathematics problem solving book Class 6-10', 
                emoji: '📗',
                rating: '⭐⭐⭐⭐⭐',
                badge: '36% OFF'
            },
            { 
                id: 15, 
                name: 'Science Textbook', 
                category: 'books', 
                price: 399, 
                oldPrice: 599, 
                description: 'Physics, Chemistry, Biology - Complete guide', 
                emoji: '📘',
                rating: '⭐⭐⭐⭐⭐',
                badge: '33% OFF'
            },
            { 
                id: 16, 
                name: 'Story Books Collection', 
                category: 'books', 
                price: 249, 
                oldPrice: 399, 
                description: 'Inspiring moral stories for children', 
                emoji: '📚',
                rating: '⭐⭐⭐⭐⭐',
                badge: '38% OFF'
            },
            { 
                id: 17, 
                name: 'General Knowledge Book', 
                category: 'books', 
                price: 199, 
                oldPrice: 329, 
                description: 'GK book for competitive exams preparation', 
                emoji: '📙',
                rating: '⭐⭐⭐⭐',
                badge: '40% OFF'
            },
            { 
                id: 18, 
                name: 'Hindi Vyakaran Book', 
                category: 'books', 
                price: 279, 
                oldPrice: 449, 
                description: 'Complete Hindi grammar with practice questions', 
                emoji: '📖',
                rating: '⭐⭐⭐⭐⭐',
                badge: '38% OFF'
            },

            // Sports Equipment
            { 
                id: 19, 
                name: 'Cricket Bat Full Size', 
                category: 'sports', 
                price: 1499, 
                oldPrice: 2499, 
                description: 'Kashmir willow cricket bat with cover', 
                emoji: '🏏',
                rating: '⭐⭐⭐⭐⭐',
                badge: '40% OFF'
            },
            { 
                id: 20, 
                name: 'Cricket Ball Leather', 
                category: 'sports', 
                price: 399, 
                oldPrice: 649, 
                description: 'Premium quality leather cricket ball', 
                emoji: '🔴',
                rating: '⭐⭐⭐⭐⭐',
                badge: '39% OFF'
            },
            { 
                id: 21, 
                name: 'Football Official Size', 
                category: 'sports', 
                price: 699, 
                oldPrice: 1199, 
                description: 'FIFA approved size 5 football', 
                emoji: '⚽',
                rating: '⭐⭐⭐⭐⭐',
                badge: '42% OFF'
            },
            { 
                id: 22, 
                name: 'Badminton Racket Set', 
                category: 'sports', 
                price: 899, 
                oldPrice: 1499, 
                description: 'Set of 2 rackets with shuttlecocks', 
                emoji: '🏸',
                rating: '⭐⭐⭐⭐',
                badge: '40% OFF'
            },
            { 
                id: 23, 
                name: 'Tennis Ball Cricket Set', 
                category: 'sports', 
                price: 599, 
                oldPrice: 999, 
                description: '6 tennis balls with bat for practice', 
                emoji: '🎾',
                rating: '⭐⭐⭐⭐⭐',
                badge: '40% OFF'
            },
            { 
                id: 24, 
                name: 'Sports Bag Large', 
                category: 'sports', 
                price: 799, 
                oldPrice: 1299, 
                description: 'Waterproof sports duffle bag with pockets', 
                emoji: '🎒',
                rating: '⭐⭐⭐⭐',
                badge: '38% OFF'
            },
        ];

        let cart = [];
        let currentFilter = 'all';

        // Display Products
        function displayProducts(productsToShow = products) {
            const grid = document.getElementById('productsGrid');
            grid.innerHTML = productsToShow.map(product => `
                <div class="product-card" data-category="${product.category}">
                    ${product.badge ? `<div class="product-badge">${product.badge}</div>` : ''}
                    <div class="product-image">${product.emoji}</div>
                    <div class="product-info">
                        <div class="product-category">${product.category}</div>
                        <div class="product-name">${product.name}</div>
                        <div class="product-description">${product.description}</div>
                        <div class="product-rating">${product.rating}</div>
                        <div class="product-footer">
                            <div class="price-container">
                                <div class="product-price">
                                    ₹${product.price}
                                    <span class="old-price">₹${product.oldPrice}</span>
                                </div>
                            </div>
                            <button class="add-btn" onclick="addToCart(${product.id})">
                                Add to Cart
                            </button>
                        </div>
                    </div>
                </div>
            `).join('');
        }

        // Filter Products
        function filterProducts(category) {
            currentFilter = category;
            
            // Update active button
            document.querySelectorAll('.filter-btn').forEach(btn => {
                btn.classList.remove('active');
                if (btn.textContent.toLowerCase().includes(category) || 
                    (category === 'all' && btn.textContent.includes('All'))) {
                    btn.classList.add('active');
                }
            });

            // Filter and display
            if (category === 'all') {
                displayProducts(products);
            } else {
                const filtered = products.filter(p => p.category === category);
                displayProducts(filtered);
            }

            // Smooth scroll to products
            document.getElementById('products').scrollIntoView({ behavior: 'smooth' });
        }

        // Search Products
        function searchProducts() {
            const searchTerm = document.getElementById('searchInput').value.toLowerCase();
            const filtered = products.filter(p => 
                p.name.toLowerCase().includes(searchTerm) || 
                p.description.toLowerCase().includes(searchTerm) ||
                p.category.toLowerCase().includes(searchTerm)
            );
            displayProducts(filtered);
        }

        // Add to Cart
        function addToCart(productId) {
            const product = products.find(p => p.id === productId);
            const existingItem = cart.find(item => item.id === productId);

            if (existingItem) {
                existingItem.quantity++;
            } else {
                cart.push({ ...product, quantity: 1 });
            }

            updateCart();
            showNotification('✅ ' + product.name + ' added to cart!');
        }

        // Update Cart
        function updateCart() {
            const badge = document.getElementById('cartBadge');
            const container = document.getElementById('cartItemsContainer');
            const summary = document.getElementById('cartSummary');
            const deliveryOptions = document.getElementById('deliveryOptions');
            const checkoutBtn = document.getElementById('checkoutBtn');

            // Update badge
            const totalItems = cart.reduce((sum, item) => sum + item.quantity, 0);
            badge.textContent = totalItems;

            // Update cart display
            if (cart.length === 0) {
                container.innerHTML = `
                    <div class="empty-cart">
                        <div class="empty-cart-icon">🛒</div>
                        <h3>Your cart is empty</h3>
                        <p>Start shopping to add your favorite items!</p>
                    </div>
                `;
                summary.style.display = 'none';
                deliveryOptions.style.display = 'none';
                checkoutBtn.style.display = 'none';
            } else {
                container.innerHTML = cart.map(item => `
                    <div class="cart-item">
                        <div class="cart-item-image">${item.emoji}</div>
                        <div class="cart-item-details">
                            <div class="cart-item-name">${item.name}</div>
                            <div class="cart-item-category">${item.category.toUpperCase()}</div>
                            <div class="cart-item-price">₹${item.price} × ${item.quantity} = ₹${item.price * item.quantity}</div>
                            <div class="cart-item-controls">
                                <button class="qty-btn" onclick="changeQuantity(${item.id}, -1)">-</button>
                                <span class="qty-display">${item.quantity}</span>
                                <button class="qty-btn" onclick="changeQuantity(${item.id}, 1)">+</button>
                                <button class="remove-btn" onclick="removeFromCart(${item.id})">Remove</button>
                            </div>
                        </div>
                    </div>
                `).join('');

                // Calculate totals
                const subtotal = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
                const deliveryMethod = document.querySelector('input[name="delivery"]:checked')?.value || 'online';
                const deliveryCharge = deliveryMethod === 'offline' ? 0 : 40;
                const total = subtotal + deliveryCharge;

                document.getElementById('subtotal').textContent = subtotal;
                document.getElementById('deliveryCharge').textContent = deliveryCharge === 0 ? 'FREE' : '₹' + deliveryCharge;
                document.getElementById('total').textContent = total;

                summary.style.display = 'block';
                deliveryOptions.style.display = 'block';
                checkoutBtn.style.display = 'block';
            }
        }

        // Update delivery charge when option changes
        document.addEventListener('change', function(e) {
            if (e.target.name === 'delivery') {
                updateCart();
            }
        });

        // Change Quantity
        function changeQuantity(productId, change) {
            const item = cart.find(i => i.id === productId);
            if (item) {
                item.quantity += change;
                if (item.quantity <= 0) {
                    removeFromCart(productId);
                } else {
                    updateCart();
                }
            }
        }

        // Remove from Cart
        function removeFromCart(productId) {
            cart = cart.filter(item => item.id !== productId);
            updateCart();
            showNotification('🗑️ Item removed from cart');
        }

        // Toggle Cart
        function toggleCart() {
            const modal = document.getElementById('cartModal');
            modal.classList.toggle('active');
        }

        // Close cart when clicking outside
        document.getElementById('cartModal').addEventListener('click', function(e) {
            if (e.target === this) {
                toggleCart();
            }
        });

        // Checkout
        function checkout() {
            if (cart.length === 0) {
                alert('आपकी cart खाली है! पहले products add करें।');
                return;
            }

            const total = document.getElementById('total').textContent;
            const itemCount = cart.reduce((sum, item) => sum + item.quantity, 0);
            const deliveryMethod = document.querySelector('input[name="delivery"]:checked')?.value || 'online';
            const deliveryText = deliveryMethod === 'offline' ? 'Store Pickup (FREE)' : 'Online Delivery (₹40)';
            
            alert(`🎉 धन्यवाद आपके order के लिए!\n\n📦 Total Items: ${itemCount}\n💰 Total Amount: ₹${total}\n🚚 Delivery: ${deliveryText}\n\n${deliveryMethod === 'offline' ? '🏪 आप 1 घंटे में हमारी shop से सामान ले सकते हैं!' : '📦 हम 2-3 दिनों में आपके घर पर delivery कर देंगे!'}\n\nPayment Options:\n• Cash on Delivery\n• UPI/PhonePe/GooglePay/Paytm\n• Card Payment\n\nहमारा Address:\n123 Main Street, Delhi, India\nPhone: +91 98765 43210`);
            
            cart = [];
            updateCart();
            toggleCart();
        }

        // Show Notification
        function showNotification(message) {
            const notification = document.createElement('div');
            notification.className = 'notification';
            notification.textContent = message;
            document.body.appendChild(notification);

            setTimeout(() => {
                notification.remove();
            }, 3000);
        }

        // Initialize
        displayProducts();
    </script>
</body>
</html>
