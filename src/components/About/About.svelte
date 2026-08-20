<script>
  import './About.sass'
  import Aboutpage from '../../assets/Aboutpage.png'

  const features = [
    {
      icon: '✦',
      title: 'Плотная и качественная бумага',
    },
    {
      icon: '✦',
      title: 'Прочные ручки, рассчитанные на вес',
    },
    {
      icon: '✦',
      title: 'Индивидуальный дизайн и размеры',
    },
    {
      icon: '✦',
      title: 'Специальные условия для оптовых заказов',
    }
  ]
</script>

<section class="about" id="about">

  <!-- Background glow -->
  <div class="about__glow about__glow--one"></div>
  <div class="about__glow about__glow--two"></div>

  <div class="about__container">

    <!-- =========================
         IMAGE / VISUAL
    ========================== -->

    <div class="about__visual">

      <div class="about__frame"></div>

      <div class="about__image-wrap">

        <div class="about__shine"></div>

        <img src={Aboutpage} alt="MF Pack Premium Packaging" class="about__image">

      </div>

      <div class="about__label">
        <span>MF PACK</span>
        <small>PREMIUM PACKAGING</small>
      </div>

    </div>


    <!-- =========================
         CONTENT
    ========================== -->

    <div class="about__content">

      <div class="about__topline">
        <span></span>
        <p>О НАС</p>
        <span></span>
      </div>


      <h2 class="about__title">
        MF PACK
        <em>— эстетика и качество</em>
      </h2>


      <div class="about__line"></div>


      <p class="about__text">
        <strong>MF PACK</strong> — компания по производству
        премиальных бумажных пакетов и брендированной упаковки.
        Мы создаём упаковку, которая подчёркивает стиль вашего
        бренда и оставляет приятное впечатление.
      </p>


      <p class="about__text about__text--second">
        Мы работаем с магазинами, бутиками, ресторанами,
        косметическими брендами и компаниями. Для каждого
        клиента подбираем индивидуальное решение — от дизайна
        до готового изделия.
      </p>


      <!-- Features -->

      <div class="about__features">

        {#each features as feature, index}

          <div
            class="about__feature"
            style={`--delay: ${index * 0.12}s`}
          >

            <div class="about__feature-icon">
              {feature.icon}
            </div>

            <p>{feature.title}</p>

            <span class="about__arrow">→</span>

          </div>

        {/each}

      </div>

    </div>

  </div>


  <!-- =========================
        BOTTOM DECORATION
  ========================== -->

  <div class="about__bottom">

    <span></span>

    <div>
      <b>EST.</b>
      <i>MF PACK</i>
      <b>2024</b>
    </div>

    <span></span>

  </div>

</section>