


<script>
import './Hero.sass'
import Mainpagefoto from '../../assets/Mainpagefoto.png' 
  // Hero — главный (первый экран) блок лендинга
  // Все тексты локализованы на русский язык

  export let eyebrow = 'Производство подарочных пакетов';
  export let title = 'Каждый подарок достоин <em>яркого</em> начала';
  export let lead =
    'Мы сами производим голографические и блестящие подарочные пакеты — оптом и в розницу для магазинов, торговых точек и мероприятий.';

  export let primaryBtn = { label: 'Узнать цены', href: '#contact' };
  export let secondaryBtn = { label: 'Смотреть цвета', href: '#products' };

  export let imageAlt = 'Голографический подарочный пакет';

  export let badge = { num: '500+', label: 'довольных клиентов' };
</script>

<section class="hero">
  <div class="hero__decor" aria-hidden="true"></div>

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
</section>

