<script>
  import './About.sass'
  import AboutImage from '../../assets/Aboutpage.png'

  const featuresList = [
    {
      symbol: '✦',
      heading: 'Плотная и качественная бумага',
    },
    {
      symbol: '✦',
      heading: 'Прочные ручки, рассчитанные на вес',
    },
    {
      symbol: '✦',
      heading: 'Индивидуальный дизайн и размеры',
    },
    {
      symbol: '✦',
      heading: 'Специальные условия для оптовых заказов',
    }
  ]
</script>

<section class="mf-about" id="about">
  <!-- Background glow effects -->
  <div class="mf-about__glow mf-about__glow--primary"></div>
  <div class="mf-about__glow mf-about__glow--secondary"></div>

  <div class="mf-about__wrapper">
    <!-- Visual / Image Section -->
    <div class="mf-about__media">
      <div class="mf-about__frame"></div>
      <div class="mf-about__screen">
        <div class="mf-about__shimmer"></div>
        <img src={AboutImage} alt="MF Pack Premium Packaging" class="mf-about__img">
      </div>
      <div class="mf-about__badge">
        <span class="mf-about__badge-title">MF PACK</span>
        <small class="mf-about__badge-subtitle">PREMIUM PACKAGING</small>
      </div>
    </div>

    <!-- Text / Content Section -->
    <div class="mf-about__body">
      <div class="mf-about__header">
        <span class="mf-about__rule"></span>
        <p class="mf-about__subtitle">О НАС</p>
        <span class="mf-about__rule"></span>
      </div>

      <h2 class="mf-about__heading">
        MF PACK
        <em class="mf-about__em">— эстетика и качество</em>
      </h2>

      <div class="mf-about__divider"></div>

      <p class="mf-about__desc">
        <strong class="mf-about__strong">MF PACK</strong> — компания по производству
        премиальных бумажных пакетов и брендированной упаковки.
        Мы создаём упаковку, которая подчёркивает стиль вашего
        бренда и оставляет приятное впечатление.
      </p>

      <p class="mf-about__desc mf-about__desc--muted">
        Мы работаем с магазинами, бутиками, ресторанами,
        косметическими брендами и компаниями. Для каждого
        клиента подбираем индивидуальное решение — от дизайна
        до готового изделия.
      </p>

      <!-- Features List -->
      <div class="mf-about__features">
        {#each featuresList as item, index}
          <div class="mf-about__card" style={`--delay: ${index * 0.12}s`}>
            <div class="mf-about__icon">{item.symbol}</div>
            <p class="mf-about__card-text">{item.heading}</p>
            <span class="mf-about__arrow">→</span>
          </div>
        {/each}
      </div>
    </div>
  </div>

  <!-- Bottom Copyright / Est -->
  <div class="mf-about__footer">
    <span class="mf-about__footer-line"></span>
    <div class="mf-about__footer-info">
      <b class="mf-about__est">EST.</b>
      <i class="mf-about__brand-name">MF PACK</i>
      <b class="mf-about__year">2024</b>
    </div>
    <span class="mf-about__footer-line"></span>
  </div>
</section>