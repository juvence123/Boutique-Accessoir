
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Boutique Accessoires</title>
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; font-family: system-ui, sans-serif; }
    body { background: linear-gradient(135deg, #f8fafc, #f0f4f8); min-height: 100vh; }
    @keyframes fadeInUp { from { opacity: 0; transform: translateY(30px); } to { opacity: 1; transform: translateY(0); } }
    @keyframes pulse { 0%,100% { transform: scale(1); } 50% { transform: scale(1.08); } }
    .navbar { background: rgba(255,255,255,0.98); backdrop-filter: blur(12px); position: sticky; top: 0; z-index: 100; padding: 0.8rem 2rem; display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 1rem; border-bottom: 1px solid #e2e8f0; }
    .logo { font-size: 1.5rem; font-weight: 800; background: linear-gradient(135deg, #1e293b, #3b82f6, #8b5cf6); -webkit-background-clip: text; background-clip: text; color: transparent; cursor: pointer; }
    .logo span { animation: pulse 2s infinite; display: inline-block; }
    .nav-links { display: flex; gap: 0.5rem; flex-wrap: wrap; }
    .nav-btn { padding: 0.5rem 1.2rem; border-radius: 60px; font-weight: 600; cursor: pointer; background: transparent; border: none; transition: 0.3s; }
    .nav-btn:hover { background: #f1f5f9; }
    .nav-btn.active { background: linear-gradient(135deg, #1e293b, #3b82f6); color: white; }
    .cart-icon { background: white; padding: 0.5rem 1.2rem; border-radius: 60px; display: flex; align-items: center; gap: 8px; font-weight: 600; cursor: pointer; border: 1px solid #e2e8f0; }
    .cart-count { background: #ef4444; color: white; border-radius: 40px; padding: 0 8px; font-size: 0.7rem; }
    .page { display: none; animation: fadeInUp 0.4s ease; }
    .page.active { display: block; }
    .hero { background: linear-gradient(135deg, #0f172a, #1e293b); margin: 1rem; border-radius: 2rem; padding: 2.5rem; text-align: center; color: white; }
    .hero h1 { font-size: 2rem; }
    .features-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 1.5rem; padding: 2rem; max-width: 1200px; margin: 0 auto; }
    .feature-card { background: white; border-radius: 1.5rem; padding: 1.5rem; text-align: center; box-shadow: 0 8px 20px rgba(0,0,0,0.05); transition: 0.3s; }
    .feature-card:hover { transform: translateY(-5px); }
    .feature-icon { font-size: 2.5rem; }
    .products-container { max-width: 1350px; margin: 2rem auto; padding: 0 1.5rem; display: grid; grid-template-columns: repeat(auto-fill, minmax(260px, 1fr)); gap: 1.5rem; }
    .product-card { background: white; border-radius: 1.5rem; overflow: hidden; box-shadow: 0 8px 20px rgba(0,0,0,0.05); transition: 0.3s; }
    .product-card:hover { transform: translateY(-5px); }
    .product-img { width: 100%; height: 200px; object-fit: cover; }
    .product-info { padding: 1rem; }
    .product-title { font-weight: 700; }
    .product-price { font-size: 1.3rem; font-weight: 800; color: #2563eb; margin: 0.5rem 0; }
    .add-to-cart { background: #0f172a; color: white; border: none; width: 100%; padding: 10px; border-radius: 40px; font-weight: 600; cursor: pointer; }
    .add-to-cart:hover { background: #3b82f6; }
    .contact-page, .about-container, .offers-container { max-width: 1000px; margin: 2rem auto; padding: 2rem; background: white; border-radius: 2rem; }
    .contact-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; }
    .contact-method { display: flex; align-items: center; gap: 1rem; padding: 1rem; background: #f8fafc; border-radius: 1rem; text-decoration: none; color: inherit; margin: 1rem 0; }
    .offers-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 1rem; margin-top: 1.5rem; }
    .offer-card { background: linear-gradient(135deg, #fef3c7, #fde68a); border-radius: 1rem; padding: 1.2rem; text-align: center; }
    .cart-overlay { position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.5); backdrop-filter: blur(6px); visibility: hidden; opacity: 0; transition: 0.3s; z-index: 200; }
    .cart-overlay.open { visibility: visible; opacity: 1; }
    .cart-sidebar { position: fixed; right: 0; top: 0; width: 100%; max-width: 450px; height: 100%; background: white; transform: translateX(100%); transition: 0.4s; z-index: 201; border-radius: 28px 0 0 28px; }
    .cart-overlay.open .cart-sidebar { transform: translateX(0); }
    .cart-header { padding: 1rem; border-bottom: 1px solid #eef2ff; display: flex; justify-content: space-between; }
    .cart-items { flex: 1; overflow-y: auto; padding: 1rem; }
    .cart-item { display: flex; gap: 1rem; margin-bottom: 1rem; border-bottom: 1px solid #eef2ff; padding-bottom: 1rem; }
    .cart-item-img { width: 70px; height: 70px; object-fit: cover; border-radius: 1rem; }
    .cart-total { padding: 1rem; border-top: 1px solid #eef2ff; }
    .checkout-btn { background: #10b981; color: white; border: none; width: 100%; padding: 12px; border-radius: 2rem; font-weight: 700; cursor: pointer; }
    .toast-msg { position: fixed; bottom: 25px; left: 50%; transform: translateX(-50%); background: #0f172a; color: white; padding: 10px 24px; border-radius: 60px; z-index: 300; opacity: 0; transition: 0.3s; }
    input, textarea { width: 100%; padding: 10px; border: 1px solid #e2e8f0; border-radius: 1rem; margin-bottom: 1rem; }
    .submit-btn { background: linear-gradient(135deg, #3b82f6, #8b5cf6); color: white; border: none; width: 100%; padding: 12px; border-radius: 2rem; font-weight: 700; cursor: pointer; }
    @media (max-width: 768px) { .navbar { padding: 0.8rem 1rem; } .nav-links { order: 3; width: 100%; justify-content: center; } .contact-grid { grid-template-columns: 1fr; } .hero h1 { font-size: 1.5rem; } }
  </style>
</head>
<body>

<nav class="navbar">
  <div class="logo" data-page="home"><span>✨</span> BOUTIQUE</div>
  <div class="nav-links">
    <button class="nav-btn active" data-page="home">Accueil</button>
    <button class="nav-btn" data-page="products">Produits</button>
    <button class="nav-btn" data-page="offers">Offres</button>
    <button class="nav-btn" data-page="about">À propos</button>
    <button class="nav-btn" data-page="contact">Contact</button>
  </div>
  <div class="cart-icon" id="cartIcon">🛒 Panier <span class="cart-count" id="cartCount">0</span></div>
</nav>

<!-- PAGES -->
<div id="homePage" class="page active">
  <div class="hero"><h1>✨ Élégance & Qualité ✨</h1><p>Boutique Accessoires - Livraison rapide Madagascar</p></div>
  <div class="features-grid">
    <div class="feature-card"><div class="feature-icon">🚚</div><h3>Livraison 48h</h3></div>
    <div class="feature-card"><div class="feature-icon">💎</div><h3>Qualité Premium</h3></div>
    <div class="feature-card"><div class="feature-icon">🔒</div><h3>Paiement sécurisé</h3></div>
    <div class="feature-card"><div class="feature-icon">⭐</div><h3>+1000 Clients</h3></div>
  </div>
</div>

<div id="productsPage" class="page"><div class="products-container" id="productsContainer"></div></div>

<div id="offersPage" class="page"><div class="offers-container"><h1>🎁 Offres Spéciales</h1><div class="offers-grid" id="offersGrid"></div></div></div>

<div id="aboutPage" class="page"><div class="about-container"><h1>📖 Notre Histoire</h1><p>Depuis 2025, Boutique Accessoires propose des produits tendance et authentiques à Madagascar.</p><div style="background:#f1f5f9; padding:1rem; border-radius:1rem; margin-top:1rem;"><h3>⭐ Nos valeurs</h3><ul><li>Qualité irréprochable</li><li>Service réactif</li><li>Prix transparents</li></ul></div></div></div>

<div id="contactPage" class="page"><div class="contact-page"><div class="contact-grid"><div class="about-container"><h2>📬 Contact</h2><a href="https://wa.me/261373436938" class="contact-method">💬 WhatsApp</a><a href="https://www.facebook.com/" class="contact-method">📘 Facebook</a><a href="tel:+261383146589" class="contact-method">📞 Appeler</a></div><div class="about-container"><h2>✉️ Message</h2><form id="contactForm"><input type="text" id="contactName" placeholder="Nom"><textarea id="contactMsg" rows="3" placeholder="Message"></textarea><button type="submit" class="submit-btn">Envoyer</button></form></div></div></div></div>

<!-- PANIER -->
<div class="cart-overlay" id="cartOverlay"><div class="cart-sidebar"><div class="cart-header"><h2>Panier</h2><button id="closeCartBtn" style="background:none; font-size:1.5rem; cursor:pointer;">✕</button></div><div class="cart-items" id="cartItemsList"></div><div class="cart-total"><div style="display:flex; justify-content:space-between;"><span>Total</span><span id="cartTotalPrice">0 AR</span></div><button class="checkout-btn" id="checkoutBtn">Valider</button></div></div></div>
<div id="toastMsg" class="toast-msg"></div>

<script>
  const products = [
    { id: 1, name: "Montre Connectée", price: 180000, image: "https://images.unsplash.com/photo-1523275335684-37898b6baf30?w=400&h=300&fit=crop" },
    { id: 2, name: "Air Jordan", price: 120000, image: "https://images.unsplash.com/photo-1600185365483-26d7a4cc7519?w=400&h=300&fit=crop" },
    { id: 3, name: "Casque Pro", price: 30000, image: "https://images.unsplash.com/photo-1505740420928-5e560c06d30e?w=400&h=300&fit=crop" },
    { id: 4, name: "Sac à Dos", price: 65000, image: "https://images.unsplash.com/photo-1553062407-98eeb64c6a62?w=400&h=300&fit=crop" },
    { id: 5, name: "Lunettes", price: 160000, image: "https://images.unsplash.com/photo-1572635196237-14b3f281503f?w=400&h=300&fit=crop" },
    { id: 6, name: "Écouteurs", price: 25000, image: "https://images.unsplash.com/photo-1606220588913-b3aacb4d2f46?w=400&h=300&fit=crop" }
  ];
  const offers = [{ title: "-20% Montre", code: "MONTRE20" }, { title: "Air Jordan duo", code: "JORDAN15" }, { title: "Casque offert", code: "CASQUE50" }];
  let cart = [];

  function formatPrice(p) { return p.toString().replace(/\B(?=(\d{3})+(?!\d))/g, " "); }
  function showToast(msg) { let t = document.getElementById("toastMsg"); t.textContent = msg; t.style.opacity = "1"; setTimeout(() => t.style.opacity = "0", 1500); }
  function saveCart() { localStorage.setItem("cart", JSON.stringify(cart)); }
  function loadCart() { cart = JSON.parse(localStorage.getItem("cart")) || []; updateCartUI(); }

  function addToCart(id) {
    let prod = products.find(p => p.id === id);
    let existing = cart.find(i => i.id === id);
    if (existing) { existing.quantity++; showToast(`📦 ${prod.name} ×${existing.quantity}`); }
    else { cart.push({ id, quantity: 1, product: { ...prod } }); showToast(`✨ ${prod.name} ajouté`); }
    saveCart(); updateCartUI();
    document.getElementById("cartCount").classList.add("pulse");
    setTimeout(() => document.getElementById("cartCount").classList.remove("pulse"), 300);
  }

  function updateQuantity(id, delta) {
    let idx = cart.findIndex(i => i.id === id);
    if (idx === -1) return;
    cart[idx].quantity += delta;
    if (cart[idx].quantity <= 0) cart.splice(idx, 1);
    saveCart(); updateCartUI();
  }

  function updateCartUI() {
    let count = cart.reduce((s, i) => s + i.quantity, 0);
    document.getElementById("cartCount").innerText = count;
    let container = document.getElementById("cartItemsList");
    if (cart.length === 0) { container.innerHTML = '<div style="text-align:center; padding:2rem;">Panier vide</div>'; document.getElementById("cartTotalPrice").innerText = "0 AR"; return; }
    let html = "", total = 0;
    cart.forEach(item => {
      let p = item.product, sub = p.price * item.quantity;
      total += sub;
      html += `<div class="cart-item"><img class="cart-item-img" src="${p.image}"><div style="flex:1"><strong>${p.name}</strong><div>${formatPrice(sub)} AR</div><div style="display:flex; gap:0.5rem; margin-top:5px;"><button onclick="updateQuantity(${p.id}, -1)">-</button><span>${item.quantity}</span><button onclick="updateQuantity(${p.id}, 1)">+</button><button onclick="removeItem(${p.id})">🗑</button></div></div></div>`;
    });
    container.innerHTML = html;
    document.getElementById("cartTotalPrice").innerHTML = `${formatPrice(total)} AR`;
  }

  function removeItem(id) { cart = cart.filter(i => i.id !== id); saveCart(); updateCartUI(); showToast("Produit retiré"); }
  function renderProducts() {
    let container = document.getElementById("productsContainer");
    if (!container) return;
    products.forEach(p => {
      let card = document.createElement("div"); card.className = "product-card";
      card.innerHTML = `<img class="product-img" src="${p.image}"><div class="product-info"><div class="product-title">${p.name}</div><div class="product-price">${formatPrice(p.price)} AR</div><button class="add-to-cart" data-id="${p.id}">Ajouter</button></div>`;
      container.appendChild(card);
    });
    document.querySelectorAll(".add-to-cart").forEach(btn => btn.addEventListener("click", () => addToCart(parseInt(btn.dataset.id))));
  }
  function renderOffers() { document.getElementById("offersGrid").innerHTML = offers.map(o => `<div class="offer-card"><h3>🎁 ${o.title}</h3><p>Code: ${o.code}</p></div>`).join(''); }
  function switchPage(page) { document.querySelectorAll('.page').forEach(p => p.classList.remove('active')); document.getElementById(`${page}Page`).classList.add('active'); document.querySelectorAll('.nav-btn').forEach(b => b.classList.remove('active')); document.querySelector(`.nav-btn[data-page="${page}"]`).classList.add('active'); }

  document.querySelectorAll('.nav-btn, .logo').forEach(el => el.addEventListener('click', () => switchPage(el.dataset.page || 'home')));
  document.getElementById("cartIcon").onclick = () => { document.getElementById("cartOverlay").classList.add("open"); updateCartUI(); };
  document.getElementById("closeCartBtn").onclick = () => document.getElementById("cartOverlay").classList.remove("open");
  document.getElementById("cartOverlay").onclick = (e) => { if (e.target === document.getElementById("cartOverlay")) document.getElementById("cartOverlay").classList.remove("open"); };
  document.getElementById("checkoutBtn").onclick = () => { if (cart.length === 0) return showToast("Panier vide"); if (confirm("Valider la commande ?")) { cart = []; saveCart(); updateCartUI(); document.getElementById("cartOverlay").classList.remove("open"); showToast("Commande confirmée !"); } };
  document.getElementById("contactForm")?.addEventListener("submit", (e) => { e.preventDefault(); showToast("Message envoyé !"); e.target.reset(); });

  renderProducts(); renderOffers(); loadCart();
  window.updateQuantity = updateQuantity; window.removeItem = removeItem;
</script>
</body>
</html>
