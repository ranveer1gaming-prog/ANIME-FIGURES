```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Otaku Haven - Premium Anime Merch</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-purple: #8B5CF6;
            --secondary-blue: #06B6D4;
            --dark-bg: #0F0F23;
            --card-bg: #1A1A2E;
            --accent-purple: #A78BFA;
            --accent-blue: #22D3EE;
            --text-light: #F8FAFC;
            --text-muted: #94A3B8;
            --success: #10B981;
            --warning: #F59E0B;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background: var(--dark-bg);
            color: var(--text-light);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Header */
        .header {
            background: rgba(26, 26, 46, 0.95);
            backdrop-filter: blur(10px);
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            z-index: 1000;
            padding: 1rem 0;
            border-bottom: 1px solid rgba(139, 92, 246, 0.2);
        }

        .nav-container {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            background: linear-gradient(135deg, var(--primary-purple), var(--secondary-blue));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-decoration: none;
        }

        .nav-menu {
            display: flex;
            list-style: none;
            gap: 2rem;
            align-items: center;
        }

        .nav-link {
            color: var(--text-light);
            text-decoration: none;
            font-weight: 500;
            transition: color 0.2s ease;
            position: relative;
        }

        .nav-link:hover {
            color: var(--primary-purple);
        }

        .nav-link::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary-purple);
            transition: width 0.3s ease;
        }

        .nav-link:hover::after {
            width: 100%;
        }

        .search-box {
            position: relative;
            display: flex;
            align-items: center;
            background: var(--card-bg);
            border: 1px solid rgba(139, 92, 246, 0.3);
            border-radius: 25px;
            padding: 0.5rem 1rem;
            width: 300px;
        }

        .search-input {
            background: none;
            border: none;
            color: var(--text-light);
            width: 100%;
            outline: none;
            font-size: 0.9rem;
        }

        .search-btn {
            background: none;
            border: none;
            color: var(--primary-purple);
            cursor: pointer;
        }

        .icons {
            display: flex;
            gap: 1.5rem;
            align-items: center;
        }

        .icon-btn {
            position: relative;
            color: var(--text-light);
            font-size: 1.2rem;
            cursor: pointer;
            transition: color 0.2s ease;
        }

        .icon-btn:hover {
            color: var(--primary-purple);
        }

        .badge {
            position: absolute;
            top: -8px;
            right: -8px;
            background: var(--success);
            color: white;
            border-radius: 50%;
            width: 20px;
            height: 20px;
            font-size: 0.7rem;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .mobile-menu-toggle {
            display: none;
            flex-direction: column;
            cursor: pointer;
            gap: 4px;
        }

        .mobile-menu-toggle span {
            width: 25px;
            height: 3px;
            background: var(--text-light);
            transition: 0.3s;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, rgba(139, 92, 246, 0.1), rgba(6, 182, 212, 0.1)), 
                        url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 600"><rect fill="%230f0f23" width="1200" height="600"/><path fill="%238B5CF6" opacity="0.1" d="M0 300Q300 0 600 300T1200 300V600H0z"/><path fill="%2306B6D4" opacity="0.1" d="M0 300Q400 600 800 300T1200 300V0H0z"/></svg>');
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero-content {
            max-width: 800px;
            padding: 0 2rem;
            z-index: 2;
        }

        .hero h1 {
            font-size: clamp(2.5rem, 5vw, 4rem);
            font-weight: 700;
            margin-bottom: 1.5rem;
            background: linear-gradient(135deg, var(--primary-purple), var(--secondary-blue));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            color: var(--text-muted);
        }

        .cta-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .cta-btn {
            padding: 1rem 2rem;
            border: none;
            border-radius: 50px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--primary-purple), var(--accent-purple));
            color: white;
        }

        .btn-secondary {
            background: transparent;
            color: var(--text-light);
            border: 2px solid var(--primary-purple);
        }

        .cta-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(139, 92, 246, 0.4);
        }

        /* Sections */
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        .section {
            padding: 5rem 0;
        }

        .section-title {
            font-size: 2.5rem;
            font-weight: 700;
            text-align: center;
            margin-bottom: 3rem;
            background: linear-gradient(135deg, var(--primary-purple), var(--secondary-blue));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        /* Categories */
        .categories-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }

        .category-card {
            position: relative;
            height: 250px;
            border-radius: 20px;
            overflow: hidden;
            cursor: pointer;
            transition: all 0.3s ease;
            border: 1px solid rgba(139, 92, 246, 0.2);
        }

        .category-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(139, 92, 246, 0.3);
        }

        .category-overlay {
            position: absolute;
            inset: 0;
            background: linear-gradient(135deg, rgba(15, 15, 35, 0.9), rgba(26, 26, 46, 0.9));
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 2rem;
        }

        .category-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            background: linear-gradient(135deg, var(--primary-purple), var(--secondary-blue));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        /* Products Grid */
        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 2rem;
        }

        .product-card {
            background: var(--card-bg);
            border-radius: 20px;
            overflow: hidden;
            transition: all 0.3s ease;
            border: 1px solid rgba(139, 92, 246, 0.1);
            position: relative;
        }

        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(139, 92, 246, 0.2);
        }

        .product-image {
            height: 250px;
            position: relative;
            overflow: hidden;
        }

        .product-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.3s ease;
        }

        .product-card:hover .product-image img {
            transform: scale(1.05);
        }

        .product-badge {
            position: absolute;
            top: 1rem;
            right: 1rem;
            background: var(--success);
            color: white;
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 600;
        }

        .product-info {
            padding: 1.5rem;
        }

        .product-title {
            font-size: 1.1rem;
            font-weight: 600;
            margin-bottom: 0.5rem;
            color: var(--text-light);
        }

        .product-price {
            font-size: 1.3rem;
            font-weight: 700;
            color: var(--primary-purple);
            margin-bottom: 1rem;
        }

        .old-price {
            text-decoration: line-through;
            color: var(--text-muted);
            font-size: 1rem;
            margin-left: 0.5rem;
        }

        .product-rating {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            margin-bottom: 1rem;
        }

        .stars {
            color: var(--warning);
        }

        .product-actions {
            display: flex;
            gap: 0.5rem;
        }

        .btn-small {
            flex: 1;
            padding: 0.7rem;
            border: none;
            border-radius: 10px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.2s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.3rem;
            font-size: 0.9rem;
        }

        .btn-wishlist {
            background: rgba(139, 92, 246, 0.1);
            color: var(--primary-purple);
            border: 1px solid rgba(139, 92, 246, 0.3);
        }

        .btn-cart {
            background: linear-gradient(135deg, var(--primary-purple), var(--accent-purple));
            color: white;
        }

        .btn-small:hover {
            transform: translateY(-2px);
        }

        /* Shop Page Filters */
        .shop-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 3rem;
            flex-wrap: wrap;
            gap: 1rem;
        }

        .filters {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
        }

        .filter-select {
            background: var(--card-bg);
            border: 1px solid rgba(139, 92, 246, 0.3);
            color: var(--text-light);
            padding: 0.8rem 1rem;
            border-radius: 10px;
            font-size: 0.9rem;
        }

        /* Product Page */
        .product-detail {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            margin-bottom: 4rem;
        }

        .product-gallery {
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }

        .gallery-main {
            height: 450px;
            border-radius: 20px;
            overflow: hidden;
            background: var(--card-bg);
        }

        .gallery-main img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .gallery-thumbs {
            display: flex;
            gap: 0.5rem;
        }

        .thumb {
            width: 80px;
            height: 80px;
            border-radius: 10px;
            overflow: hidden;
            cursor: pointer;
            border: 2px solid transparent;
            transition: all 0.2s ease;
        }

        .thumb.active {
            border-color: var(--primary-purple);
        }

        .product-details-content {
            padding: 2rem 0;
        }

        .product-details-title {
            font-size: 2rem;
            font-weight: 700;
            margin-bottom: 1rem;
        }

        .product-details-price {
            font-size: 2.2rem;
            font-weight: 700;
            color: var(--primary-purple);
            margin-bottom: 1rem;
        }

        .size-selector {
            display: flex;
            gap: 0.5rem;
            margin: 2rem 0;
            flex-wrap: wrap;
        }

        .size-btn {
            padding: 0.8rem 1.2rem;
            border: 2px solid rgba(139, 92, 246, 0.3);
            background: var(--card-bg);
            color: var(--text-light);
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.2s ease;
        }

        .size-btn.active {
            background: var(--primary-purple);
            border-color: var(--primary-purple);
            color: white;
        }

        .quantity-selector {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin: 2rem 0;
        }

        .quantity-btn {
            width: 40px;
            height: 40px;
            border: 1px solid rgba(139, 92, 246, 0.3);
            background: var(--card-bg);
            color: var(--text-light);
            border-radius: 8px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .quantity-input {
            width: 60px;
            text-align: center;
            background: var(--card-bg);
            border: 1px solid rgba(139, 92, 246, 0.3);
            color: var(--text-light);
            border-radius: 8px;
            padding: 0.5rem;
        }

        .add-to-cart-large {
            width: 100%;
            padding: 1.2rem;
            font-size: 1.2rem;
            margin-bottom: 1rem;
        }

        /* Cart Page */
        .cart-item {
            display: grid;
            grid-template-columns: 120px 1fr auto auto;
            gap: 1.5rem;
            align-items: center;
            padding: 1.5rem;
            background: var(--card-bg);
            border-radius: 15px;
            margin-bottom: 1rem;
        }

        .cart-item-image {
            width: 120px;
            height: 120px;
            border-radius: 10px;
            object-fit: cover;
        }

        .cart-item-info h4 {
            margin-bottom: 0.5rem;
        }

        .cart-item-price {
            font-size: 1.2rem;
            font-weight: 600;
            color: var(--primary-purple);
        }

        .cart-total {
            background: var(--card-bg);
            padding: 2rem;
            border-radius: 20px;
            margin-top: 2rem;
        }

        .total-row {
            display: flex;
            justify-content: space-between;
            margin-bottom: 1rem;
            font-size: 1.1rem;
        }

        .grand-total {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary-purple);
            border-top: 2px solid rgba(139, 92, 246, 0.3);
            padding-top: 1rem;
            margin-top: 1rem;
        }

        /* Checkout Page */
        .checkout-form {
            background: var(--card-bg);
            padding: 2rem;
            border-radius: 20px;
            margin-bottom: 2rem;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-label {
            display: block;
            margin-bottom: 0
