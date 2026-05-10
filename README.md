
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
  <title>Élégance Accessoires | Boutique Premium</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: system-ui, 'Segoe UI', 'Inter', 'Helvetica Neue', sans-serif;
    }

    body {
      background: linear-gradient(145deg, #f8fafc 0%, #f1f5f9 100%);
      color: #0f172a;
      padding-bottom: 2rem;
      overflow-x: hidden;
    }

    /* Animation de chargement */
    @keyframes fadeInUp {
      from {
        opacity: 0;
        transform: translateY(30px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    @keyframes slideInLeft {
      from {
        opacity: 0;
        transform: translateX(-50px);
      }
      to {
        opacity: 1;
        transform: translateX(0);
      }
    }

    @keyframes slideInRight {
      from {
        opacity: 0;
        transform: translateX(50px);
      }
      to {
        opacity: 1;
        transform: translateX(0);
      }
    }

    @keyframes pulse {
      0% {
        transform: scale(1);
      }
      50% {
        transform: scale(1.05);
      }
      100% {
        transform: scale(1);
      }
    }

    @keyframes shimmer {
      0% {
        background-position: -200% 0;
      }
      100% {
        background-position: 200% 0;
      }
    }

    @keyframes bounce {
      0%, 100% {
        transform: translateY(0);
      }
      50% {
        transform: translateY(-10px);
      }
    }

    @keyframes rotate {
      from {
        transform: rotate(0deg);
      }
      to {
        transform: rotate(360deg);
      }
    }

    /* Header moderne avec animation */
    .header {
      background: rgba(255, 255, 255, 0.95);
      backdrop-filter: blur(16px);
      box-shadow: 0 8px 24px rgba(0, 0, 0, 0.05);
      position: sticky;
      top: 0;
      z-index: 100;
      padding: 0.9rem 2rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 1rem;
      border-bottom: 1px solid rgba(226, 232, 240, 0.8);
      animation: slideInLeft 0.6s ease;
    }

    .logo {
      font-size: 1.7rem;
      font-weight: 800;
      background: linear-gradient(135deg, #1e293b, #3b82f6, #8b5cf6);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      letter-spacing: -0.3px;
      display: flex;
      align-items: center;
      gap: 8px;
      transition: transform 0.3s ease;
    }

    .logo:hover {
      transform: scale(1.05);
    }

    .logo span {
      font-size: 1.8rem;
      animation: bounce 2s ease infinite;
      display: inline-block;
    }

    /* Boutons contact dans le header */
    .contact-buttons {
      display: flex;
      gap: 12px;
      align-items: center;
      flex-wrap: wrap;
      animation: slideInRight 0.6s ease;
    }

    .contact-header-btn {
      display: flex;
      align-items: center;
      gap: 8px;
      padding: 8px 16px;
      border-radius: 60px;
      font-weight: 600;
      font-size: 0.85rem;
      cursor: pointer;
      transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
      border: 1px solid #e2e8f0;
      background: white;
      text-decoration: none;
      position: relative;
      overflow: hidden;
    }

    .contact-header-btn::before {
      content: '';
      position: absolute;
      top: 50%;
      left: 50%;
      width: 0;
      height: 0;
      border-radius: 50%;
      background: rgba(255, 255, 255, 0.3);
      transform: translate(-50%, -50%);
      transition: width 0.6s, height 0.6s;
    }

    .contact-header-btn:hover::before {
      width: 300px;
      height: 300px;
    }

    .contact-header-btn.whatsapp {
      background: #25D366;
      color: white;
      border-color: #25D366;
    }

    .contact-header-btn.whatsapp:hover {
      background: #128C7E;
      transform: scale(1.05) translateY(-2px);
      box-shadow: 0 8px 20px rgba(37, 211, 102, 0.3);
    }

    .contact-header-btn.facebook {
      background: #1877F2;
      color: white;
      border-color: #1877F2;
    }

    .contact-header-btn.facebook:hover {
      background: #0d5cb6;
      transform: scale(1.05) translateY(-2px);
      box-shadow: 0 8px 20px rgba(24, 119, 242, 0.3);
    }

    .contact-header-btn.phone {
      background: #ef4444;
      color: white;
      border-color: #ef4444;
    }

    .contact-header-btn.phone:hover {
      background: #dc2626;
      transform: scale(1.05) translateY(-2px);
      box-shadow: 0 8px 20px rgba(239, 68, 68, 0.3);
    }

    .cart-icon {
      position: relative;
      cursor: pointer;
      background: #ffffff;
      padding: 0.6rem 1.3rem;
      border-radius: 60px;
      display: flex;
      align-items: center;
      gap: 10px;
      font-weight: 600;
      transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
      box-shadow: 0 2px 8px rgba(0,0,0,0.03);
      border: 1px solid #e2e8f0;
      animation: slideInRight 0.6s ease;
    }

    .cart-icon:hover {
      background: #f8fafc;
      transform: scale(1.05);
      border-color: #cbd5e1;
      box-shadow: 0 8px 18px rgba(0,0,0,0.08);
    }

    .cart-count {
      background: #ef4444;
      color: white;
      border-radius: 40px;
      padding: 0px 9px;
      font-size: 0.75rem;
      font-weight: bold;
      margin-left: 4px;
      transition: all 0.3s ease;
    }

    .cart-count.pulse {
      animation: pulse 0.5s ease;
    }

    /* Grille raffinée avec animations */
    .products-container {
      max-width: 1350px;
      margin: 2.5rem auto;
      padding: 0 1.8rem;
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
      gap: 2rem;
    }

    .product-card {
      background: #ffffff;
      border-radius: 28px;
      overflow: hidden;
      box-shadow: 0 12px 28px rgba(0, 0, 0, 0.05);
      transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
      cursor: pointer;
      border: 1px solid rgba(203, 213, 225, 0.3);
      display: flex;
      flex-direction: column;
      opacity: 0;
      animation: fadeInUp 0.6s ease forwards;
      position: relative;
    }

    .product-card:nth-child(1) { animation-delay: 0.05s; }
    .product-card:nth-child(2) { animation-delay: 0.1s; }
    .product-card:nth-child(3) { animation-delay: 0.15s; }
    .product-card:nth-child(4) { animation-delay: 0.2s; }
    .product-card:nth-child(5) { animation-delay: 0.25s; }
    .product-card:nth-child(6) { animation-delay: 0.3s; }
    .product-card:nth-child(7) { animation-delay: 0.35s; }
    .product-card:nth-child(8) { animation-delay: 0.4s; }
    .product-card:nth-child(9) { animation-delay: 0.45s; }
    .product-card:nth-child(10) { animation-delay: 0.5s; }
    .product-card:nth-child(11) { animation-delay: 0.55s; }
    .product-card:nth-child(12) { animation-delay: 0.6s; }
    .product-card:nth-child(13) { animation-delay: 0.65s; }
    .product-card:nth-child(14) { animation-delay: 0.7s; }

    .product-card::before {
      content: '';
      position: absolute;
      top: 0;
      left: -100%;
      width: 100%;
      height: 100%;
      background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
      transition: left 0.5s ease;
      pointer-events: none;
    }

    .product-card:hover::before {
      left: 100%;
    }

    .product-card:hover {
      transform: translateY(-12px) scale(1.02);
      box-shadow: 0 28px 40px -16px rgba(0, 0, 0, 0.25);
      border-color: #cbd5e1;
    }

    .product-img {
      width: 100%;
      height: 240px;
      object-fit: cover;
      background: linear-gradient(145deg, #eef2ff, #e2e8f0);
      display: block;
      transition: transform 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
    }

    .product-card:hover .product-img {
      transform: scale(1.08);
    }

    .product-info {
      padding: 1.4rem 1.2rem 1.5rem;
      flex: 1;
      display: flex;
      flex-direction: column;
    }

    .product-title {
      font-size: 1.25rem;
      font-weight: 700;
      margin-bottom: 0.4rem;
      color: #0f172a;
      transition: color 0.3s ease;
    }

    .product-card:hover .product-title {
      color: #3b82f6;
    }

    .product-price {
      font-size: 1.5rem;
      font-weight: 800;
      color: #2563eb;
      margin: 0.5rem 0 0.8rem;
      letter-spacing: -0.3px;
      transition: transform 0.3s ease;
    }

    .product-card:hover .product-price {
      transform: scale(1.05);
    }

    .product-price::after {
      content: " AR";
      font-size: 0.9rem;
      font-weight: 500;
      color: #475569;
      margin-left: 3px;
    }

    .add-to-cart {
      background: #0f172a;
      color: white;
      border: none;
      width: 100%;
      padding: 12px 0;
      border-radius: 44px;
      font-weight: 600;
      font-size: 0.95rem;
      cursor: pointer;
      transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
      margin-top: 0.75rem;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      position: relative;
      overflow: hidden;
    }

    .add-to-cart::before {
      content: '';
      position: absolute;
      top: 50%;
      left: 50%;
      width: 0;
      height: 0;
      border-radius: 50%;
      background: rgba(59, 130, 246, 0.5);
      transform: translate(-50%, -50%);
      transition: width 0.6s, height 0.6s;
    }

    .add-to-cart:hover::before {
      width: 300px;
      height: 300px;
    }

    .add-to-cart:hover {
      background: #1e293b;
      transform: scale(1.02);
      gap: 12px;
    }

    .add-to-cart:active {
      transform: scale(0.98);
    }

    /* Panier latéral premium */
    .cart-overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.5);
      backdrop-filter: blur(6px);
      visibility: hidden;
      opacity: 0;
      transition: 0.3s ease;
      z-index: 200;
    }

    .cart-overlay.open {
      visibility: visible;
      opacity: 1;
    }

    .cart-sidebar {
      position: fixed;
      right: 0;
      top: 0;
      width: 100%;
      max-width: 500px;
      height: 100%;
      background: #ffffff;
      box-shadow: -12px 0 35px rgba(0, 0, 0, 0.2);
      display: flex;
      flex-direction: column;
      transform: translateX(100%);
      transition: transform 0.4s cubic-bezier(0.2, 0.9, 0.4, 1.1);
      z-index: 201;
      border-radius: 28px 0 0 28px;
      overflow: hidden;
    }

    .cart-overlay.open .cart-sidebar {
      transform: translateX(0);
    }

    .cart-header {
      padding: 1.4rem 1.8rem;
      border-bottom: 2px solid #f1f5f9;
      display: flex;
      justify-content: space-between;
      align-items: center;
      background: #fff;
    }

    .cart-header h2 {
      font-size: 1.6rem;
      font-weight: 700;
      background: linear-gradient(145deg, #1e293b, #334155);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    .close-cart {
      background: #f1f5f9;
      border: none;
      font-size: 1.6rem;
      cursor: pointer;
      width: 36px;
      height: 36px;
      display: flex;
      align-items: center;
      justify-content: center;
      border-radius: 50%;
      transition: all 0.3s ease;
    }

    .close-cart:hover {
      background: #e2e8f0;
      transform: rotate(90deg);
    }

    .cart-items {
      flex: 1;
      overflow-y: auto;
      padding: 1.2rem 1.5rem;
    }

    .cart-item {
      display: flex;
      gap: 1rem;
      margin-bottom: 1.6rem;
      border-bottom: 1px solid #eef2ff;
      padding-bottom: 1.2rem;
      animation: slideInLeft 0.3s ease;
    }

    .cart-item-img {
      width: 80px;
      height: 80px;
      object-fit: cover;
      border-radius: 20px;
      background: #eef2ff;
      box-shadow: 0 4px 8px rgba(0,0,0,0.05);
      transition: transform 0.3s ease;
    }

    .cart-item-img:hover {
      transform: scale(1.05);
    }

    .cart-item-details {
      flex: 1;
    }

    .cart-item-title {
      font-weight: 700;
      font-size: 1rem;
    }

    .cart-item-price {
      color: #3b82f6;
      font-weight: 700;
      margin-top: 4px;
    }

    .item-quantity {
      display: flex;
      align-items: center;
      gap: 12px;
      margin-top: 10px;
      flex-wrap: wrap;
    }

    .item-quantity button {
      background: #f1f5f9;
      border: none;
      width: 32px;
      height: 32px;
      border-radius: 40px;
      font-weight: bold;
      font-size: 1.1rem;
      cursor: pointer;
      transition: all 0.2s ease;
    }

    .item-quantity button:hover {
      background: #e2e8f0;
      transform: scale(1.1);
    }

    .item-quantity button:active {
      transform: scale(0.95);
    }

    .remove-item {
      background: #fff0f0;
      color: #dc2626;
      border: none;
      padding: 6px 14px;
      border-radius: 40px;
      font-size: 0.7rem;
      font-weight: 600;
      cursor: pointer;
      margin-left: 4px;
      transition: all 0.2s ease;
    }

    .remove-item:hover {
      background: #fee2e2;
      transform: scale(1.05);
    }

    .cart-total {
      padding: 1.3rem 1.8rem 1.8rem;
      border-top: 2px solid #eef2ff;
      background: #ffffff;
    }

    .total-row {
      display: flex;
      justify-content: space-between;
      font-size: 1.3rem;
      font-weight: 800;
      margin-bottom: 1.2rem;
    }

    .checkout-btn {
      background: linear-gradient(105deg, #10b981, #059669);
      color: white;
      border: none;
      width: 100%;
      padding: 15px;
      border-radius: 60px;
      font-weight: 700;
      font-size: 1rem;
      cursor: pointer;
      transition: all 0.3s ease;
      position: relative;
      overflow: hidden;
    }

    .checkout-btn::before {
      content: '';
      position: absolute;
      top: 0;
      left: -100%;
      width: 100%;
      height: 100%;
      background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
      transition: left 0.5s ease;
    }

    .checkout-btn:hover::before {
      left: 100%;
    }

    .checkout-btn:hover {
      filter: brightness(1.04);
      transform: scale(1.02);
    }

    .empty-cart {
      text-align: center;
      color: #64748b;
      margin-top: 3.5rem;
      font-weight: 500;
    }

    /* Modal Contact */
    .contact-modal {
      position: fixed;
      bottom: 30px;
      right: 30px;
      z-index: 250;
    }

    .contact-fab {
      background: linear-gradient(135deg, #3b82f6, #8b5cf6);
      width: 60px;
      height: 60px;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
      box-shadow: 0 8px 20px rgba(0,0,0,0.2);
      transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
      border: none;
      font-size: 28px;
    }

    .contact-fab:hover {
      transform: scale(1.15) rotate(10deg);
      box-shadow: 0 12px 28px rgba(0,0,0,0.3);
    }

    .contact-popup {
      position: absolute;
      bottom: 80px;
      right: 0;
      background: white;
      border-radius: 24px;
      box-shadow: 0 20px 40px rgba(0,0,0,0.2);
      width: 280px;
      padding: 20px;
      display: none;
      animation: fadeInUp 0.3s ease;
    }

    .contact-popup.show {
      display: block;
    }

    .contact-popup h3 {
      font-size: 1.2rem;
      margin-bottom: 15px;
      color: #1e293b;
      text-align: center;
    }

    .contact-popup a {
      display: flex;
      align-items: center;
      gap: 12px;
      padding: 12px 16px;
      margin: 8px 0;
      border-radius: 60px;
      text-decoration: none;
      font-weight: 600;
      transition: all 0.3s ease;
      color: white;
    }

    .contact-popup .whatsapp-link {
      background: #25D366;
    }

    .contact-popup .whatsapp-link:hover {
      background: #128C7E;
      transform: translateX(8px);
    }

    .contact-popup .facebook-link {
      background: #1877F2;
    }

    .contact-popup .facebook-link:hover {
      background: #0d5cb6;
      transform: translateX(8px);
    }

    .contact-popup .phone-link {
      background: #ef4444;
    }

    .contact-popup .phone-link:hover {
      background: #dc2626;
      transform: translateX(8px);
    }

    /* Toast animation */
    .toast-msg {
      position: fixed;
      bottom: 25px;
      left: 50%;
      transform: translateX(-50%) scale(0.9);
      background: #0f172a;
      color: white;
      padding: 12px 24px;
      border-radius: 60px;
      font-size: 0.9rem;
      font-weight: 500;
      z-index: 300;
      opacity: 0;
      transition: 0.3s ease;
      pointer-events: none;
      box-shadow: 0 10px 20px rgba(0,0,0,0.2);
    }

    /* Particules d'animation */
    .particle {
      position: fixed;
      width: 4px;
      height: 4px;
      background: linear-gradient(135deg, #3b82f6, #8b5cf6);
      border-radius: 50%;
      pointer-events: none;
      z-index: 9999;
      animation: particleFloat 1s ease-out forwards;
    }

    @keyframes particleFloat {
      0% {
        opacity: 1;
        transform: translateY(0) scale(1);
      }
      100% {
        opacity: 0;
        transform: translateY(-50px) scale(0);
      }
    }

    /* Scroll reveal animation */
    .scroll-reveal {
      opacity: 0;
      transform: translateY(30px);
      transition: all 0.6s ease;
    }

    .scroll-reveal.revealed {
      opacity: 1;
      transform: translateY(0);
    }

    @media (max-width: 860px) {
      .contact-buttons {
        order: 3;
        width: 100%;
        justify-content: center;
      }
      .products-container {
        gap: 1rem;
        padding: 0 1rem;
      }
      .header {
        padding: 0.7rem 1.2rem;
      }
      .cart-sidebar {
        max-width: 100%;
        border-radius: 0;
      }
    }
  </style>
</head>
<body>

<div class="header">
  <div class="logo">
    <span>✨</span> ÉLÉGANCE ACCESSOIRES
  </div>
  <div class="contact-buttons">
    <a href="https://wa.me/261373436938?text=Bonjour%20je%20suis%20intéressé%20par%20vos%20produits" target="_blank" class="contact-header-btn whatsapp">
      📱 WhatsApp
    </a>
    <a href="https://www.facebook.com/profile.php?id=Juvence Rjn" target="_blank" class="contact-header-btn facebook">
      📘 Facebook
    </a>
    <a href="tel:+261383146589" class="contact-header-btn phone">
      📞 Appeler
    </a>
  </div>
  <div class="cart-icon" id="cartIcon">
    🛒 Mon panier
    <span class="cart-count" id="cartCount">0</span>
  </div>
</div>

<div class="products-container" id="productsContainer"></div>

<!-- Panneau latéral panier -->
<div class="cart-overlay" id="cartOverlay">
  <div class="cart-sidebar">
    <div class="cart-header">
      <h2>🛍️ Votre panier</h2>
      <button class="close-cart" id="closeCartBtn">✕</button>
    </div>
    <div class="cart-items" id="cartItemsList">
      <div class="empty-cart">🛒 Panier vide, ajoutez des articles</div>
    </div>
    <div class="cart-total" id="cartTotalSection">
      <div class="total-row">
        <span>Total TTC</span>
        <span id="cartTotalPrice">0 AR</span>
      </div>
      <button class="checkout-btn" id="checkoutBtn">✅ Valider la commande</button>
    </div>
  </div>
</div>

<!-- Modal Contact Flottant -->
<div class="contact-modal">
  <button class="contact-fab" id="contactFabBtn">
    💬
  </button>
  <div class="contact-popup" id="contactPopup">
    <h3>📞 Contactez-nous</h3>
    <a href="https://wa.me/261373436938?text=Bonjour%20je%20suis%20intéressé%20par%20vos%20produits" target="_blank" class="whatsapp-link">
      💬 WhatsApp
    </a>
    <a href="https://www.facebook.com/profile.php?id=Juvence Rjn" target="_blank" class="facebook-link">
      📘 Facebook
    </a>
    <a href="tel:+261383146589" class="phone-link">
      📞 Téléphone
    </a>
  </div>
</div>

<div id="toastMsg" class="toast-msg"></div>

<script>
  // ---------- CATALOGUE PRODUITS ----------
  const products = [
    { id: 1, name: "Montre Connectée", price: 70000, image: "https://images.unsplash.com/photo-1523275335684-37898b6baf30?w=400&h=300&fit=crop&q=80&fm=jpg" },
    { id: 2, name: "Air Jordan High", price: 120000, image: "https://images.unsplash.com/photo-1600185365483-26d7a4cc7519?w=400&h=300&fit=crop&q=80&fm=jpg" },
    { id: 3, name: "Casque Bluetooth Pro", price: 30000, image: "https://images.unsplash.com/photo-1505740420928-5e560c06d30e?w=400&h=300&fit=crop&q=80&fm=jpg" },
    { id: 4, name: "Sac à Dos Urbain", price: 65000, image: "https://images.unsplash.com/photo-1553062407-98eeb64c6a62?w=400&h=300&fit=crop&q=80&fm=jpg" },
    { id: 5, name: "Lunettes Style Icon", price: 160000, image: "https://images.unsplash.com/photo-1572635196237-14b3f281503f?w=400&h=300&fit=crop&q=80&fm=jpg" },
    { id: 6, name: "Écouteurs Bluetooth", price: 25000, image: "https://images.unsplash.com/photo-1606220588913-b3aacb4d2f46?w=400&h=300&fit=crop&q=80&fm=jpg" },
    { id: 7, name: "Robe Élégante", price: 40000, image: "https://images.unsplash.com/photo-1612336307429-8a898d10e223?w=400&h=300&fit=crop&q=80&fm=jpg" },
    { id: 8, name: "Escarpins Luxe", price: 60000, image: "https://images.unsplash.com/photo-1543163521-1bf539c55dd2?w=400&h=300&fit=crop&q=80&fm=jpg" },
    { id: 9, name: "Maillot Football", price: 40000, image: "https://images.unsplash.com/photo-1517466787929-bc90951d0974?w=400&h=300&fit=crop&q=80&fm=jpg" },
    { id: 10, name: "Tenis", price: 40000, image: "https://images.unsplash.com/photo-1542291026-7eec264c27ff?w=400&h=300&fit=crop&q=80&fm=jpg" },
    { id: 11, name: "Jogging Confort", price: 45000, image: "https://images.unsplash.com/photo-1556905055-8f358a7a47b2?w=400&h=300&fit=crop&q=80&fm=jpg" },
    { id: 12, name: "Collier Argent", price: 65000, image: "https://images.unsplash.com/photo-1599643478518-a784e5dc4c8f?w=400&h=300&fit=crop&q=80&fm=jpg" },
    { id: 13, name: "Sac à main", price: 25000, image: "https://images.unsplash.com/photo-1594633313593-bab3825d0caf?w=400&h=300&fit=crop&q=80&fm=jpg" },
    { id: 14, name: "Combinaison Chic", price: 70000, image: "https://images.unsplash.com/photo-1539109136881-3be0616acf4b?w=400&h=300&fit=crop&q=80&fm=jpg" }
  ];

  let cart = [];

  // Créer des particules d'animation
  function createParticle(x, y) {
    const particle = document.createElement('div');
    particle.classList.add('particle');
    particle.style.left = x + 'px';
    particle.style.top = y + 'px';
    document.body.appendChild(particle);
    setTimeout(() => {
      particle.remove();
    }, 1000);
  }

  function showToast(message, duration = 1800) {
    const toast = document.getElementById("toastMsg");
    toast.textContent = message;
    toast.style.opacity = "1";
    toast.style.transform = "translateX(-50%) scale(1)";
    setTimeout(() => {
      toast.style.opacity = "0";
      toast.style.transform = "translateX(-50%) scale(0.9)";
    }, duration);
  }

  function saveCart() {
    localStorage.setItem("eleganceCart", JSON.stringify(cart));
  }

  function loadCart() {
    const saved = localStorage.getItem("eleganceCart");
    if (saved) {
      try {
        cart = JSON.parse(saved);
        if (!Array.isArray(cart)) cart = [];
      } catch(e) { cart = []; }
    } else {
      cart = [];
    }
    updateCartUI();
  }

  function addToCart(productId, event) {
    const product = products.find(p => p.id === productId);
    if (!product) return;

    // Créer particule au clic
    if (event) {
      createParticle(event.clientX, event.clientY);
    }

    const existing = cart.find(item => item.id === productId);
    if (existing) {
      existing.quantity += 1;
      showToast(`📦 ${product.name} ×${existing.quantity}`, 1000);
    } else {
      cart.push({ id: product.id, quantity: 1, product: { ...product } });
      showToast(`✨ ${product.name} ajouté au panier`, 1000);
    }
    saveCart();
    updateCartUI();

    const cartIconDiv = document.getElementById("cartIcon");
    cartIconDiv.style.transform = "scale(1.07)";
    setTimeout(() => { if(cartIconDiv) cartIconDiv.style.transform = ""; }, 180);
    
    // Animation du compteur
    const cartCount = document.getElementById("cartCount");
    cartCount.classList.add('pulse');
    setTimeout(() => cartCount.classList.remove('pulse'), 500);
  }

  function updateQuantity(productId, delta) {
    const idx = cart.findIndex(item => item.id === productId);
    if (idx === -1) return;
    const newQty = cart[idx].quantity + delta;
    if (newQty <= 0) {
      const removedName = cart[idx].product.name;
      cart.splice(idx, 1);
      showToast(`🗑️ ${removedName} retiré`, 900);
    } else {
      cart[idx].quantity = newQty;
      showToast(`🔄 Quantité mise à jour : ${cart[idx].product.name} ×${newQty}`, 800);
    }
    saveCart();
    updateCartUI();
  }

  function removeItem(productId) {
    const removedItem = cart.find(item => item.id === productId);
    if (removedItem) {
      cart = cart.filter(item => item.id !== productId);
      showToast(`❌ ${removedItem.product.name} supprimé`, 900);
      saveCart();
      updateCartUI();
    }
  }

  function updateCartUI() {
    const totalItems = cart.reduce((sum, item) => sum + item.quantity, 0);
    const cartCountSpan = document.getElementById("cartCount");
    if (cartCountSpan) cartCountSpan.innerText = totalItems;

    const cartItemsContainer = document.getElementById("cartItemsList");
    const cartTotalSpan = document.getElementById("cartTotalPrice");

    if (!cartItemsContainer) return;

    if (cart.length === 0) {
      cartItemsContainer.innerHTML = `<div class="empty-cart">🛍️ Votre panier est vide<br>✨ Ajoutez des articles tendance ✨</div>`;
      if (cartTotalSpan) cartTotalSpan.innerText = "0 AR";
      return;
    }

    let itemsHTML = "";
    let total = 0;

    for (const item of cart) {
      const prod = item.product;
      const itemTotal = prod.price * item.quantity;
      total += itemTotal;
      itemsHTML += `
        <div class="cart-item">
          <img class="cart-item-img" src="${prod.image}" alt="${prod.name}" loading="lazy">
          <div class="cart-item-details">
            <div class="cart-item-title">${escapeHtml(prod.name)}</div>
            <div class="cart-item-price">${formatPrice(itemTotal)} AR</div>
            <div class="item-quantity">
              <button class="qty-decr" data-id="${prod.id}">−</button>
              <span style="min-width: 28px; text-align:center;">${item.quantity}</span>
              <button class="qty-incr" data-id="${prod.id}">+</button>
              <button class="remove-item" data-id="${prod.id}">🗑 Supprimer</button>
            </div>
          </div>
        </div>
      `;
    }

    cartItemsContainer.innerHTML = itemsHTML;
    if (cartTotalSpan) cartTotalSpan.innerText = `${formatPrice(total)} AR`;

    document.querySelectorAll('.qty-incr').forEach(btn => {
      btn.removeEventListener('click', incHandler);
      btn.addEventListener('click', incHandler);
    });
    document.querySelectorAll('.qty-decr').forEach(btn => {
      btn.removeEventListener('click', decHandler);
      btn.addEventListener('click', decHandler);
    });
    document.querySelectorAll('.remove-item').forEach(btn => {
      btn.removeEventListener('click', removeHandler);
      btn.addEventListener('click', removeHandler);
    });
  }

  function incHandler(e) {
    const id = parseInt(e.currentTarget.dataset.id);
    updateQuantity(id, 1);
  }
  function decHandler(e) {
    const id = parseInt(e.currentTarget.dataset.id);
    updateQuantity(id, -1);
  }
  function removeHandler(e) {
    const id = parseInt(e.currentTarget.dataset.id);
    removeItem(id);
  }

  function formatPrice(price) {
    return price.toString().replace(/\B(?=(\d{3})+(?!\d))/g, " ");
  }

  function escapeHtml(str) {
    return str.replace(/[&<>]/g, function(m) {
      if(m === '&') return '&amp;';
      if(m === '<') return '&lt;';
      if(m === '>') return '&gt;';
      return m;
    });
  }

  function renderProducts() {
    const container = document.getElementById("productsContainer");
    if (!container) return;
    container.innerHTML = "";
    products.forEach(product => {
      const card = document.createElement("div");
      card.className = "product-card scroll-reveal";
      card.innerHTML = `
        <img class="product-img" src="${product.image}" alt="${product.name}" loading="lazy" onerror="this.src='https://placehold.co/400x300/e2e8f0/475569?text=Accessoire+JPG'">
        <div class="product-info">
          <div class="product-title">${escapeHtml(product.name)}</div>
          <div class="product-price">${formatPrice(product.price)}</div>
          <button class="add-to-cart" data-id="${product.id}">🛒 Ajouter au panier</button>
        </div>
      `;
      container.appendChild(card);
    });

    document.querySelectorAll(".add-to-cart").forEach(btn => {
      btn.addEventListener("click", (e) => {
        e.stopPropagation();
        const id = parseInt(btn.dataset.id);
        addToCart(id, e);
        const originalText = btn.innerHTML;
        btn.innerHTML = "✓ Ajouté !";
        setTimeout(() => { if(btn) btn.innerHTML = originalText; }, 800);
      });
    });

    // Scroll reveal
    setTimeout(() => {
      const reveals = document.querySelectorAll('.scroll-reveal');
      reveals.forEach(el => el.classList.add('revealed'));
    }, 100);
  }

  const overlay = document.getElementById("cartOverlay");
  const cartIconBtn = document.getElementById("cartIcon");
  const closeCartBtn = document.getElementById("closeCartBtn");

  function openCart() {
    if (overlay) {
      overlay.classList.add("open");
      updateCartUI();
    }
  }
  function closeCart() {
    if (overlay) overlay.classList.remove("open");
  }

  if (cartIconBtn) cartIconBtn.addEventListener("click", openCart);
  if (closeCartBtn) closeCartBtn.addEventListener("click", closeCart);
  if (overlay) {
    overlay.addEventListener("click", (e) => {
      if (e.target === overlay) closeCart();
    });
  }

  const contactFab = document.getElementById("contactFabBtn");
  const contactPopup = document.getElementById("contactPopup");

  if (contactFab) {
    contactFab.addEventListener("click", (e) => {
      e.stopPropagation();
      contactPopup.classList.toggle("show");
    });
  }

  document.addEventListener("click", (e) => {
    if (contactPopup && contactFab) {
      if (!contactPopup.contains(e.target) && !contactFab.contains(e.target)) {
        contactPopup.classList.remove("show");
      }
    }
  });

  const checkoutBtn = document.getElementById("checkoutBtn");
  if (checkoutBtn) {
    checkoutBtn.addEventListener("click", () => {
      if (cart.length === 0) {
        showToast("🛒 Votre panier est vide, ajoutez des articles !", 1800);
        return;
      }
      const total = cart.reduce((sum, item) => sum + (item.product.price * item.quantity), 0);
      if (confirm(`💎 Valider la commande pour un montant total de ${formatPrice(total)} AR ?\nLivraison incluse (simulation).`)) {
        cart = [];
        saveCart();
        updateCartUI();
        closeCart();
        showToast("🎉 Commande confirmée ! Merci pour votre achat. 🎉", 2500);
        updateCartUI();
      }
    });
  }

  function init() {
    renderProducts();
    loadCart();
    document.addEventListener('error', function(e) {
      if (e.target.tagName === 'IMG') {
        e.target.src = "https://placehold.co/400x300/e2e8f0/475569?text=Mode+Access+JPG";
      }
    }, true);
  }

  init();
</script>
</body>
</html>
