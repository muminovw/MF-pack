<script>
  import './Hero.sass';
  import Mainpagefoto from '../../assets/Mainpagefoto.png'; 

  export let eyebrow = 'Производство подарочных пакетов';
  export let title = 'Каждый подарок достоин <em>яркого</em> начала';
  export let lead =
    'Мы сами производим голографические и блестящие подарочные пакеты — оптом и в розницу для магазинов, торговых точек и мероприятий.';

  export let primaryBtn = { label: 'Узнать цены', href: '#contact' };
  export let secondaryBtn = { label: 'Смотреть цвета', href: '#product' };

  export let imageAlt = 'Голографический подарочный пакет';

  export let badge = { num: '500+', label: 'довольных клиентов' };
</script>

<section class="hero">
  <div class="hero__decor" aria-hidden="true"></div>

  <!-- Asosiy Hero Grid qismi -->
  <div class="wrap hero__grid">
    <div class="hero__content">
      <p class="hero__eyebrow">{eyebrow}</p>

      <h1 class="hero__title">{@html title}</h1>

      <p class="hero__lead">{lead}</p>

      <div class="hero__actions">
        <a href={primaryBtn.href} class="btn btn--primary">{primaryBtn.label}</a>
        <a href={secondaryBtn.href} class="btn btn--ghost">{secondaryBtn.label}</a>
      </div>
    </div>

    <div class="hero__visual">
      <img src={Mainpagefoto} alt={imageAlt} loading="eager" />

      {#if badge}
        <div class="hero__badge">
          <span class="hero__badge-num">{badge.num}</span>
          <span class="hero__badge-label">{badge.label}</span>
        </div>
      {/if}
    </div>
  </div>

  <!-- Stats (Statistika) qismi -->
  <div class="wrap stats__container">
    <div class="stats__grid">
      <div class="stats__item">
        <div class="stats__number">6+</div>
        <div class="stats__label">цветов и дизайнов</div>
      </div>
      <div class="stats__item">
        <div class="stats__number">3</div>
        <div class="stats__label">размера: S / M / L</div>
      </div>
      <div class="stats__item">
        <div class="stats__number">1 800+</div>
        <div class="stats__label">выполненных заказов</div>
      </div>
      <div class="stats__item">
        <div class="stats__number">100%</div>
        <div class="stats__label">перерабатываемая бумага</div>
      </div>
    </div>
  </div>
</section>