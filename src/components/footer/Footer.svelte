<script>
  const currentYear = new Date().getFullYear();
  import './Footer.sass'
</script>

<footer class="mf-footer">
  <!-- Orqa fondagi xira nurlar -->
  <div class="footer-glow glow-one"></div>
  <div class="footer-glow glow-two"></div>

  <div class="footer-container">
    <!-- Asosiy Grid qismi -->
    <div class="footer-grid">
      
      <!-- 1-Ustun: Brend va Ma'lumot -->
      <div class="footer-col brand-col">
        <div class="footer-logo">
          MF<span>Pack</span>
        </div>
        <p class="brand-desc">
          Экологичная и высококачественная бумажная упаковка. Самые надежные и современные упаковочные решения для вашего бизнеса.
        </p>
        <div class="social-links">
          <a href="#" aria-label="Instagram" class="social-icon">IG</a>
          <a href="#" aria-label="Telegram" class="social-icon">TG</a>
          <a href="#" aria-label="Facebook" class="social-icon">FB</a>
        </div>
      </div>

      <!-- 2-Ustun: Katalog -->
      <div class="footer-col">
        <h4 class="col-title">Каталог</h4>
        <ul class="footer-links">
          <li><a href="#boxes">Бумажные коробки</a></li>
          <li><a href="#kraft">Крафт-пакеты</a></li>
          <li><a href="#bestsellers">Бестселлеры</a></li>
          <li><a href="#new">Новинки</a></li>
        </ul>
      </div>

      <!-- 3-Ustun: Kompaniya -->
      <div class="footer-col">
        <h4 class="col-title">Компания</h4>
        <ul class="footer-links">
          <li><a href="#about">О нас</a></li>
          <li><a href="#stats">Статистика</a></li>
          <li><a href="#partners">Сотрудничество</a></li>
          <li><a href="#contact">Контакты</a></li>
        </ul>
      </div>

      <!-- 4-Ustun: Obuna va Yangiliklar -->
      <div class="footer-col newsletter-col">
        <h4 class="col-title">Подписка на новости</h4>
        <p class="newsletter-text">Узнавайте первыми об акциях и новых поступлениях.</p>
        <form class="newsletter-form" on:submit|preventDefault>
          <input type="email" placeholder="Ваш Email" required />
          <button type="submit" aria-label="Отправить">
            <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round">
              <line x1="5" y1="12" x2="19" y2="12"></line>
              <polyline points="12 5 19 12 12 19"></polyline>
            </svg>
          </button>
        </form>
      </div>

    </div>

    <!-- Pastki qism: Copyright va Havolalar -->
    <div class="footer-bottom">
      <p>&copy; {currentYear} MF Pack. Все права защищены.</p>
      <div class="bottom-links">
        <a href="#terms">Условия использования</a>
        <a href="#privacy">Политика конфиденциальности</a>
      </div>
    </div>
  </div>
</footer>