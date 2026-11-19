
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>TechStore — Магазин техники</title>

  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: Arial, sans-serif;
      background: #f5f6fa;
      color: #181b29;
    }

    a {
      text-decoration: none;
      color: inherit;
    }

    button, input {
      font: inherit;
    }

    button {
      cursor: pointer;
    }

    header {
      position: sticky;
      top: 0;
      z-index: 100;
      background: white;
      box-shadow: 0 3px 15px #00000010;
    }

    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 20px;
    }

    .header-top {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 25px;
      padding: 20px 0;
    }

    .logo {
      font-size: 26px;
      font-weight: 800;
      color: #635bff;
    }

    .search {
      flex: 1;
      max-width: 460px;
      padding: 13px 18px;
      border: 1px solid #ddd;
      border-radius: 12px;
      outline: none;
    }

    .search:focus {
      border-color: #635bff;
    }

    .actions {
      display: flex;
      gap: 12px;
      align-items: center;
    }

    .btn {
      border: none;
      border-radius: 10px;
      padding: 12px 20px;
      background: #635bff;
      color: white;
      font-weight: 600;
      transition: 0.25s;
    }

    .btn:hover {
      background: #4941db;
      transform: translateY(-2px);
    }

    .cart {
      background: #eeeefe;
      color: #554ce0;
    }

    nav {
      display: flex;
      gap: 28px;
      padding: 0 0 17px;
    }

    nav a {
      padding: 8px 0;
      color: #555;
      font-weight: 600;
      transition: 0.2s;
    }

    nav a:hover {
      color: #635bff;
    }

    .hero {
      display: flex;
      align-items: center;
      gap: 40px;
      margin: 35px 0 55px;
      padding: 55px;
      background: linear-gradient(120deg, #181b38, #5144ad);
      color: white;
      border-radius: 25px;
      overflow: hidden;
    }

    .hero-text {
      flex: 1;
    }

    .hero h1 {
      font-size: clamp(32px, 4vw, 50px);
      line-height: 1.15;
      margin-bottom: 20px;
    }

    .hero p {
      font-size: 17px;
      color: #dad8ff;
      line-height: 1.6;
      margin-bottom: 30px;
    }

    .hero img {
      width: 47%;
      height: 300px;
      object-fit: cover;
      border-radius: 20px;
    }

    .hero .btn {
      background: white;
      color: #5144ad;
    }

    .hero .btn:hover {
      background: #e8e5ff;
    }

    section {
      margin-bottom: 60px;
    }

    .section-title {
      font-size: 30px;
      margin-bottom: 25px;
    }

    .products {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 25px;
    }

    .product {
      position: relative;
      background: white;
      padding: 20px;
      border-radius: 20px;
      box-shadow: 0 5px 20px #0000000a;
      margin-bottom: 5px;
      transition: 0.3s;
      overflow: hidden;
    }

    .product:hover {
      transform: translateY(-7px);
      box-shadow: 0 15px 35px #00000018;
    }

    .product img {
      width: 100%;
      height: 220px;
      object-fit: cover;
      border-radius: 12px;
      margin-bottom: 18px;
      background: #f0f0f0;
    }

    .badge {
      position: absolute;
      top: 30px;
      left: 30px;
      padding: 7px 12px;
      border-radius: 8px;
      font-weight: bold;
      font-size: 12px;
      background: #ff4757;
      color: white;
    }

    .badge.hit {
      background: #ff9f1c;
    }

    .product h3 {
      font-size: 19px;
      margin-bottom: 10px;
    }

    .description {
      color: #777;
      font-size: 14px;
      line-height: 1.5;
      min-height: 42px;
      margin-bottom: 18px;
    }

    .old-price {
      text-decoration: line-through;
      color: #999;
      font-size: 14px;
      margin-bottom: 5px;
      min-height: 17px;
    }

    .price {
      font-size: 24px;
      font-weight: 800;
      color: #635bff;
      margin-bottom: 18px;
    }

    .product .btn {
      width: 100%;
    }

    .features {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 25px;
    }

    .feature {
      padding: 30px;
      background: white;
      border-radius: 18px;
      text-align: center;
    }

    .feature span {
      font-size: 35px;
    }

    .feature h3 {
      margin: 15px 0 10px;
    }

    .feature p {
      color: #777;
      line-height: 1.5;
    }

    footer {
      background: #181b29;
      color: white;
      padding: 55px 0 20px;
    }

    .footer-grid {
      display: grid;
      grid-template-columns: 2fr 1fr 1fr;
      gap: 40px;
      margin-bottom: 40px;
    }

    footer h3 {
      margin-bottom: 18px;
    }

    footer p, footer a {
      display: block;
      color: #aeb0c0;
      margin-bottom: 12px;
      line-height: 1.6;
    }

    footer a:hover {
      color: white;
    }

    .copyright {
      border-top: 1px solid #333647;
      padding-top: 20px;
      text-align: center;
      color: #888;
    }

    @media (max-width: 850px) {
      .products {
        grid-template-columns: repeat(2, 1fr);
      }

      .hero {
        padding: 30px;
      }

      .hero img {
        width: 40%;
      }
    }

    @media (max-width: 600px) {
      .header-top {
        flex-wrap: wrap;
        gap: 12px;
      }

      .search {
        order: 3;
        max-width: none;
        flex-basis: 100%;
      }

      nav {
        overflow-x: auto;
        gap: 20px;
        white-space: nowrap;
      }

      .hero {
        flex-direction: column;
        padding: 30px;
      }

      .hero img {
        width: 100%;
        height: 220px;
      }

      .products, .features {
        grid-template-columns: 1fr;
      }

      .footer-grid {
        grid-template-columns: 1fr;
      }

      .section-title {
        font-size: 25px;
      }
    }
  </style>
</head>

<body>

  <header>
    <div class="container">
      <div class="header-top">
        <a href="#" class="logo">TechStore.</a>

        <input
          class="search"
          id="search"
          type="search"
          placeholder="Поиск техники..."
        >

        <div class="actions">
          <button class="btn cart" onclick="showCart()">
            🛒 <span id="cartCount">0</span>
          </button>

          <button class="btn" onclick="login()">
            Войти
          </button>
        </div>
      </div>

      <nav>
        <a href="#">Главная</a>
        <a href="#catalog">Каталог</a>
        <a href="#sales">Акции</a>
        <a href="#about">О нас</a>
        <a href="#contacts">Контакты</a>
      </nav>
    </div>
  </header>

  <main class="container">

    <div class="hero">
      <div class="hero-text">
        <h1>Технологии для твоей жизни</h1>

        <p>
          Открой мир современных гаджетов.
          Смартфоны, ноутбуки, аксессуары
          и другая техника по выгодным ценам.
        </p>

        <a href="#catalog" class="btn">
          Перейти в каталог →
        </a>
      </div>

      <img
        src="https://images.unsplash.com/photo-1519389950473-47ba0277781c?w=1000&auto=format&fit=crop&q=85"
        alt="Современная техника"
      >
    </div>

    <section id="catalog">
      <h2 class="section-title">Популярные товары</h2>

      <div class="products" id="products">

        <article class="product" data-name="Apple MacBook ноутбук">
          <span class="badge hit">ХИТ</span>

          <img
            src="https://images.unsplash.com/photo-1517336714731-489689fd1ca8?w=700&auto=format&fit=crop&q=85"
            alt="MacBook"
            loading="lazy"
          >

          <h3>Apple MacBook Air</h3>
          <p class="description">
            Легкий и мощный ноутбук для учебы,
            работы и творчества.
          </p>

          <div class="old-price">109 990 ₽</div>
          <div class="price">89 990 ₽</div>

          <button class="btn" onclick="addToCart('MacBook Air',89990)">
            В корзину
          </button>
        </article>

        <article class="product" data-name="Apple iPhone смартфон" id="sales">
          <span class="badge">SALE</span>

          <img
            src="https://images.unsplash.com/photo-1592750475338-74b7b21085ab?w=700&auto=format&fit=crop&q=85"
            alt="iPhone"
            loading="lazy"
          >

          <h3>Apple iPhone</h3>
          <p class="description">
            Стильный смартфон с отличной
            камерой и высокой производительностью.
          </p>

          <div class="old-price">99 990 ₽</div>
          <div class="price">79 990 ₽</div>

          <button class="btn" onclick="addToCart('iPhone',79990)">
            В корзину
          </button>
        </article>

        <article class="product" data-name="Sony наушники">
          <span class="badge hit">ХИТ</span>

          <img
            src="https://images.unsplash.com/photo-1505740420928-5e560c06d30e?w=700&auto=format&fit=crop&q=85"
            alt="Наушники"
            loading="lazy"
          >

          <h3>Sony Headphones</h3>
          <p class="description">
            Беспроводные наушники с глубоким
            басом и качественным звуком.
          </p>

          <div class="old-price">24 990 ₽</div>
          <div class="price">19 990 ₽</div>

          <button class="btn" onclick="addToCart('Sony Headphones',19990)">
            В корзину
          </button>
        </article>

        <article class="product" data-name="Apple Watch часы">
          <span class="badge">SALE</span>

          <img
            src="https://images.unsplash.com/photo-1546868871-7041f2a55e12?w=700&auto=format&fit=crop&q=85"
            alt="Умные часы"
            loading="lazy"
          >

          <h3>Apple Watch</h3>
          <p class="description">
            Умные часы для спорта,
            уведомлений и повседневной жизни.
          </p>

          <div class="old-price">39 990 ₽</div>
          <div class="price">32 990 ₽</div>

          <button class="btn" onclick="addToCart('Apple Watch',32990)">
            В корзину
          </button>
        </article>

        <article class="product" data-name="Canon фотоаппарат камера">
          <span class="badge hit">ХИТ</span>

          <img
            src="https://images.unsplash.com/photo-1516035069371-29a1b244cc32?w=700&auto=format&fit=crop&q=85"
            alt="Камера"
            loading="lazy"
          >

          <h3>Canon Camera</h3>
          <p class="description">
            Камера для качественных
            фотографий и видеосъемки.
          </p>

          <div class="old-price"></div>
          <div class="price">64 990 ₽</div>

          <button class="btn" onclick="addToCart('Canon Camera',64990)">
            В корзину
          </button>
        </article>

        <article class="product" data-name="JBL колонка акустика">
          <span class="badge">SALE</span>

          <img
            src="https://images.unsplash.com/photo-1608043152269-423dbba4e7e1?w=700&auto=format&fit=crop&q=85"
            alt="Колонка"
            loading="lazy"
          >

          <h3>JBL Speaker</h3>
          <p class="description">
            Портативная акустика
            с насыщенным звуком.
          </p>

          <div class="old-price">15 990 ₽</div>
          <div class="price">11 990 ₽</div>

          <button class="btn" onclick="addToCart('JBL Speaker',11990)">
            В корзину
          </button>
        </article>

      </div>

      <p id="noResults" style="display:none; margin-top:20px">
        Товары не найдены.
      </p>
    </section>

    <section id="about">
      <h2 class="section-title">Почему выбирают нас?</h2>

      <div class="features">
        <div class="feature">
          <span>🚀</span>
          <h3>Быстрая доставка</h3>
          <p>Доставляем технику по всей России.</p>
        </div>

        <div class="feature">
          <span>🛡️</span>
          <h3>Гарантия качества</h3>
          <p>Проверенная техника и гарантия.</p>
        </div>

        <div class="feature">
          <span>💎</span>
          <h3>Выгодные цены</h3>
          <p>Регулярные акции и скидки.</p>
        </div>
      </div>
    </section>

  </main>

  <footer id="contacts">
    <div class="container">
      <div class="footer-grid">

        <div>
          <h3 class="logo">TechStore.</h3>
          <p>
            Интернет-магазин современной техники.
            Все необходимое для цифровой жизни.
          </p>
        </div>

        <div>
          <h3>Навигация</h3>
          <a href="#">Главная</a>
          <a href="#catalog">Каталог</a>
          <a href="#sales">Акции</a>
          <a href="#about">О нас</a>
        </div>

        <div>
          <h3>Контакты</h3>
          <p>info@techstore.example</p>
          <p>+7 (800) 555-00-00</p>
          <a href="https://t.me/" target="_blank" rel="noopener">Telegram</a>
          <a href="https://vk.com/" target="_blank" rel="noopener">ВКонтакте</a>
        </div>

      </div>

      <div class="copyright">
        © 2026 TechStore. Все права защищены.
      </div>
    </div>
  </footer>

  <script>
    let cart = [];

    function addToCart(name, price) {
      cart.push({ name, price });

      document.getElementById("cartCount").textContent =
        cart.length;

      alert(name + " добавлен в корзину!");
    }

    function showCart() {
      if (cart.length === 0) {
        alert("Корзина пуста");
        return;
      }

      let total = cart.reduce(
        (sum, item) => sum + item.price, 0
      );

      let items = cart.map(
        item => item.name + " — " +
        item.price.toLocaleString("ru-RU") + " ₽"
      ).join("\n");

      alert(
        "Ваша корзина:\n\n" +
        items +
        "\n\nИтого: " +
        total.toLocaleString("ru-RU") + " ₽"
      );
    }

    function login() {
      alert("Авторизация в демонстрационной версии недоступна");
    }

    document.getElementById("search").addEventListener(
      "input",
      function() {
        let query = this.value.toLowerCase().trim();
        let cards = document.querySelectorAll(".product");
        let found = 0;

        cards.forEach(card => {
          let name = card.dataset.name.toLowerCase();
          let visible = name.includes(query);

          card.style.display = visible ? "" : "none";

          if (visible) found++;
        });

        document.getElementById("noResults").style.display =
          found === 0 ? "block" : "none";
      }
    );
  </script>

</body>
</html>
