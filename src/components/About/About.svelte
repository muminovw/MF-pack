<script>
  import './About.sass'

  const features = [
    {
      icon: '✦',
      title: "Zich, yirtilmaydigan qog‘oz asos",
    },
    {
      icon: '✦',
      title: "Mustahkam ip dastak, og‘irlikka bardosh beradi",
    },
    {
      icon: '✦',
      title: "Har bir dizayn 3 xil o‘lchamda mavjud",
    },
    {
      icon: '✦',
      title: "Ulgurji xaridlarda maxsus chegirmalar",
    }
  ]
</script>

<section class="about" id="about">

  <!-- Background shine -->
  <div class="about__glow about__glow--one"></div>
  <div class="about__glow about__glow--two"></div>

  <div class="about__container">

    <!-- IMAGE -->
    <div class="about__visual">

      <div class="about__frame"></div>

      <div class="about__image-wrap">

        <div class="about__shine"></div>

        <img
          src="/assets/logo.png"
          alt="Yaltirqo mahsulotlari"
          class="about__image"
        />

      </div>

      <div class="about__label">
        <span>YALTIRQO</span>
        <small>Premium Packaging</small>
      </div>

    </div>


    <!-- CONTENT -->
    <div class="about__content">

      <div class="about__topline">
        <span></span>
        <p>BIZ HAQIMIZDA</p>
        <span></span>
      </div>


      <h2 class="about__title">
        YALTIRQO
        <em>— nafislik va sifat</em>
      </h2>


      <div class="about__line"></div>


      <p class="about__text">
        <strong>YALTIRQO</strong> — holografik va yaltirroq bezakli
        sovg‘a paketlarini o‘z korxonamizda ishlab chiqaradigan kompaniya.
        Har bir paket zich qog‘ozdan tayyorlanib, ustiga maxsus
        holografik bosma naqsh tushiriladi.
      </p>


      <p class="about__text about__text--second">
        Bizning mijozlarimiz — gullar do‘konlari, sovg‘a-do‘konlar,
        salonlar va tadbir tashkilotchilari. Katta va kichik hajmdagi
        buyurtmalarni bir xil mas’uliyat bilan bajaramiz.
      </p>


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


  <!-- Bottom decorative line -->
  <div class="about__bottom">

    <span></span>

    <div>
      <b>EST.</b>
      <i>YALTIRQO</i>
      <b>2024</b>
    </div>

    <span></span>

  </div>

</section>