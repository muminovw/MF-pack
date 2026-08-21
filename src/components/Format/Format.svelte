<script lang="ts">
  import FormatImg from '../../assets/Format.png';
  import './Format.sass'

  const sizes = [
    { size: 'S', width: '15', height: '19', depth: '8' },
    { size: 'M', width: '23', height: '27', depth: '10' },
    { size: 'L', width: '28', height: '36', depth: '13' }
  ];

  const features = [
    { icon: '♢', title: 'Mustahkam', text: 'va bardoshli' },
    { icon: '⌁', title: 'Ekologik', text: 'toza material' },
    { icon: '♡', title: 'Har qanday', text: 'sovg‘a uchun ideal' },
    { icon: '✦', title: 'Chiroyli', text: 'zamonaviy dizayn' }
  ];
</script>

<section class="fmt-section">
  <div class="fmt-section__decor fmt-section__decor--top"></div>
  <div class="fmt-section__decor fmt-section__decor--bottom"></div>

  <div class="fmt-container">
    <!-- LEFT CONTENT -->
    <div class="fmt-content">
      <div class="fmt-eyebrow">
        <span class="fmt-eyebrow__icon">✦</span>
        <span class="fmt-eyebrow__text">SIFAT VA ELEGANTLIK</span>
      </div>

      <div class="fmt-title-wrap">
        <h2 class="fmt-title-wrap__heading">O‘lchamlar</h2>
        <svg
          class="fmt-title-wrap__leaf"
          viewBox="0 0 80 80"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
          aria-hidden="true"
        >
          <path d="M16 65C27 49 42 30 67 13" stroke="currentColor" stroke-width="1.5" />
          <path d="M28 50C25 39 27 32 35 27C38 36 36 43 28 50Z" stroke="currentColor" stroke-width="1.4" />
          <path d="M40 38C38 27 41 20 50 16C52 25 49 33 40 38Z" stroke="currentColor" stroke-width="1.4" />
          <path d="M48 31C56 30 62 25 63 17C55 18 50 22 48 31Z" stroke="currentColor" stroke-width="1.4" />
        </svg>
      </div>

      <div class="fmt-divider">
        <span class="fmt-divider__line"></span>
        <i class="fmt-divider__star">✦</i>
        <span class="fmt-divider__line"></span>
      </div>

      <p class="fmt-description">
        Har bir dizayn uchta o‘lchamda ishlab chiqariladi — kichik sovg‘alardan tortib katta buyumlargacha.
      </p>

      <!-- SIZE TABLE -->
      <div class="fmt-sizes">
        <div class="fmt-sizes__header">
          <div class="fmt-sizes__heading">
            <span class="fmt-sizes__heading-icon">♧</span>
            <span>O‘LCHAM</span>
          </div>
          <div class="fmt-sizes__heading">
            <span class="fmt-sizes__heading-icon">↔</span>
            <span>KENGLIGI</span>
          </div>
          <div class="fmt-sizes__heading">
            <span class="fmt-sizes__heading-icon">↕</span>
            <span>BALANDLIGI</span>
          </div>
          <div class="fmt-sizes__heading">
            <span class="fmt-sizes__heading-icon">◇</span>
            <span>CHUQURLIGI</span>
          </div>
        </div>

        <div class="fmt-sizes__body">
          {#each sizes as item}
            <div class="fmt-sizes__row">
              <div class="fmt-sizes__size">
                <span>{item.size}</span>
              </div>
              <div class="fmt-sizes__value">
                {item.width} <small>sm</small>
              </div>
              <div class="fmt-sizes__value">
                {item.height} <small>sm</small>
              </div>
              <div class="fmt-sizes__value">
                {item.depth} <small>sm</small>
              </div>
            </div>
          {/each}
        </div>
      </div>

      <!-- QUALITY CARD -->
      <div class="fmt-quality-card">
        <div class="fmt-quality-card__icon">
          <svg viewBox="0 0 48 48" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M24 5L39 12V23C39 32.5 32.7 40.4 24 43C15.3 40.4 9 32.5 9 23V12L24 5Z" stroke="currentColor" stroke-width="1.6" />
            <path d="M16.5 24L21.5 29L32 18.5" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round" />
          </svg>
        </div>

        <div class="fmt-quality-card__content">
          <h3>Sifat & Mustahkamlik</h3>
          <p>
            Zich qog‘oz, mustahkam ip dastak va yuqori sifatli bosma. Har bir detal siz uchun.
          </p>
        </div>

        <div class="fmt-quality-card__leaf">
          <svg viewBox="0 0 80 80" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M18 70C31 52 46 30 67 12" stroke="currentColor" stroke-width="1.3" />
            <path d="M30 51C27 41 30 34 38 29C40 38 37 45 30 51Z" stroke="currentColor" stroke-width="1.2" />
            <path d="M42 37C40 28 43 21 51 17C53 26 50 32 42 37Z" stroke="currentColor" stroke-width="1.2" />
          </svg>
        </div>
      </div>
    </div>

    <!-- RIGHT PRODUCT VISUAL -->
    <div class="fmt-visual">
      <div class="fmt-visual__badge">
        <span class="fmt-visual__badge-icon">◇</span>
        <span>
          PREMIUM
          <strong>DIZAYN</strong>
        </span>
      </div>

      <div class="fmt-visual__background"></div>
      <div class="fmt-visual__light fmt-visual__light--one"></div>
      <div class="fmt-visual__light fmt-visual__light--two"></div>

      <div class="fmt-visual__leaf fmt-visual__leaf--left">
        <svg viewBox="0 0 120 180" fill="none">
          <path d="M10 170C38 130 67 76 109 10" stroke="currentColor" stroke-width="1.5" />
          <path d="M42 119C31 104 31 91 41 79C51 94 50 106 42 119Z" stroke="currentColor" stroke-width="1.2" />
          <path d="M62 84C52 69 53 57 64 45C73 59 72 72 62 84Z" stroke="currentColor" stroke-width="1.2" />
          <path d="M78 57C91 56 100 48 102 36C89 38 81 44 78 57Z" stroke="currentColor" stroke-width="1.2" />
        </svg>
      </div>

      <!-- PRODUCT IMAGE -->
      <div class="fmt-visual__product-img">
        <img src={FormatImg} alt="Format Preview" />
      </div>

      <div class="fmt-visual__info">
        {#each features as feature}
          <div class="fmt-feature">
            <div class="fmt-feature__icon">
              {feature.icon}
            </div>
            <div class="fmt-feature__text">
              <strong>{feature.title}</strong>
              <span>{feature.text}</span>
            </div>
          </div>
        {/each}
      </div>
    </div>
  </div>

  <!-- BOTTOM PREMIUM CARD -->
  <div class="fmt-premium-card">
    <div class="fmt-premium-card__brand">
      <div class="fmt-premium-card__circle">
        <span>♕</span>
      </div>
    </div>

    <div class="fmt-premium-card__main">
      <span class="fmt-premium-card__label">DIZAYN — SIFAT — NAFOSAT</span>
      <h3>
        Har bir sumka — ehtiyotkorlik bilan yaratilgan <em>san’at asari.</em>
      </h3>
    </div>

    <div class="fmt-premium-card__details">
      <div class="fmt-detail">
        <span class="fmt-detail__icon">✦</span>
        <span>Yuqori sifatli<br />bosma</span>
      </div>
      <div class="fmt-detail">
        <span class="fmt-detail__icon">◇</span>
        <span>Zich va mustahkam<br />qog‘oz asos</span>
      </div>
      <div class="fmt-detail">
        <span class="fmt-detail__icon">⌁</span>
        <span>Mustahkam ip<br />dastak</span>
      </div>
      <div class="fmt-detail">
        <span class="fmt-detail__icon">♡</span>
        <span>Sevgi bilan<br />yaratilgan</span>
      </div>
    </div>

    <svg
      class="fmt-premium-card__leaf"
      viewBox="0 0 100 130"
      fill="none"
      aria-hidden="true"
    >
      <path d="M12 120C33 91 54 54 86 12" stroke="currentColor" stroke-width="1.4" />
      <path d="M32 91C25 80 27 70 36 63C42 73 40 83 32 91Z" stroke="currentColor" stroke-width="1.2" />
      <path d="M49 67C44 56 47 47 57 40C61 51 58 59 49 67Z" stroke="currentColor" stroke-width="1.2" />
      <path d="M64 45C74 45 81 39 84 30C74 31 67 35 64 45Z" stroke="currentColor" stroke-width="1.2" />
    </svg>
  </div>
</section>