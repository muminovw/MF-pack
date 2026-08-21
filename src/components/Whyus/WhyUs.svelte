<script>
  import './WhyUs.sass'
  // Dynamic features data (Russian translation)
  const features = [
    {
      id: '01',
      title: 'Собственное производство',
      text: 'Без посредников, напрямую из цеха — сами контролируем цены и качество.'
    },
    {
      id: '02',
      title: 'Прочная бумага',
      text: 'Плотная основа и надежные ручки-шнуры выдержат даже тяжелые подарки.'
    },
    {
      id: '03',
      title: 'Индивидуальный дизайн',
      text: 'Возможность заказа с особым цветом и логотипом вашего магазина.'
    },
    {
      id: '04',
      title: 'Быстрая доставка',
      text: 'Доставляем по Ташкенту и областям на собственном транспорте.'
    }
  ]

  // Dynamic process steps (Russian translation)
  const steps = [
    {
      step: '1',
      title: 'Выбор бумаги',
      text: 'Подбирается плотная и устойчивая к изгибам основа.'
    },
    {
      step: '2',
      title: 'Голографическая печать',
      text: 'Узор наносится по специальной технологии фольгирования.'
    },
    {
      step: '3',
      title: 'Вырубка и сборка',
      text: 'Вырезается форма пакета, укрепляется дно и крепятся ручки.'
    },
    {
      step: '4',
      title: 'Контроль и упаковка',
      text: 'Каждая партия проверяется, связывается и упаковывается.'
    }
  ]
</script>

<div class="features-wrapper">
  <!-- LIGHT SECTION: Why Us -->
  <section class="why-us">
    <div class="why-us__container">
      <div class="why-us__header">
        <svg class="why-us__flower" viewBox="0 0 24 24" fill="currentColor">
          <path d="M12 2C12 2 14.5 7 19 7.5C19 7.5 14.5 10.5 12 16C9.5 10.5 5 7.5 5 7.5C9.5 7 12 2 12 2Z" />
        </svg>
        <h2 class="why-us__title">Почему именно мы</h2>
        <p class="why-us__subtitle">В каждом пакете — качество и внимание к деталям.</p>
      </div>

      <div class="why-us__grid">
        {#each features as item, index}
          <div class="why-us__card">
            <span class="why-us__number">{item.id}</span>
            <div class="why-us__icon-box">
              {#if index === 0}
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5">
                  <path d="M15.232 5.232l3.536 3.536m-2.036-5.036a2.5 2.5 0 113.536 3.536L6.5 21.036H3v-3.572L16.732 3.732z" />
                </svg>
              {:else if index === 1}
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5">
                  <path d="M16 11V7a4 4 0 00-8 0v4M5 9h14l1 12H4L5 9z" />
                </svg>
              {:else if index === 2}
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5">
                  <path d="M12 19l9 2-9-18-9 18 9-2zm0 0v-8" />
                </svg>
              {:else}
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5">
                  <path d="M9 17a2 2 0 11-4 0 2 2 0 014 0zM19 17a2 2 0 11-4 0 2 2 0 014 0z" />
                  <path d="M13 16V6a1 1 0 00-1-1H4a1 1 0 00-1 1v10a1 1 0 001 1h1m8-1a1 1 0 01-1 1H9m4-1V8h4l3 3v5h-2m0 0h-1" />
                </svg>
              {/if}
            </div>
            <h3 class="why-us__card-title">{item.title}</h3>
            <p class="why-us__card-text">{item.text}</p>
          </div>

          {#if index < features.length - 1}
            <div class="why-us__divider">✦</div>
          {/if}
        {/each}
      </div>
    </div>
  </section>

  <!-- DARK SECTION: Process -->
  <section class="process">
    <div class="process__dots process__dots--left"></div>
    <div class="process__dots process__dots--right"></div>

    <div class="process__container">
      <div class="process__header">
        <h2 class="process__title">Процесс производства</h2>
        <svg class="process__flower" viewBox="0 0 24 24" fill="currentColor">
          <path d="M12 2C12 2 14.5 7 19 7.5C19 7.5 14.5 10.5 12 16C9.5 10.5 5 7.5 5 7.5C9.5 7 12 2 12 2Z" />
        </svg>
        <p class="process__subtitle">От бумаги до готового пакета — четыре шага.</p>
      </div>

      <div class="process__timeline">
        <div class="process__line"></div>

        <div class="process__grid">
          {#each steps as item, index}
            <div class="process__item">
              <div class="process__node">
                <span class="process__circle">{item.step}</span>
                <div class="process__icon-box">
                  {#if index === 0}
                    <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5">
                      <path d="M7 21h10a2 2 0 002-2V9.414a1 1 0 00-.293-.707l-5.414-5.414A1 1 0 0012.586 3H7a2 2 0 00-2 2v14a2 2 0 002 2z" />
                    </svg>
                  {:else if index === 1}
                    <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5">
                      <path d="M4 16l4.586-4.586a2 2 0 012.828 0L16 16m-2-2l1.586-1.586a2 2 0 012.828 0L20 14m-6-6h.01M6 20h12a2 2 0 002-2V6a2 2 0 00-2-2H6a2 2 0 00-2 2v12a2 2 0 002 2z" />
                    </svg>
                  {:else if index === 2}
                    <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5">
                      <path d="M16 11V7a4 4 0 00-8 0v4M5 9h14l1 12H4L5 9z" />
                    </svg>
                  {:else}
                    <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5">
                      <path d="M20 7l-8-4-8 4m16 0l-8 4m8-4v10l-8 4m0-10L4 7m8 4v10M4 7v10l8 4" />
                    </svg>
                  {/if}
                </div>
              </div>

              <h3 class="process__item-title">{item.title}</h3>
              <p class="process__item-text">{item.text}</p>
            </div>
          {/each}
        </div>
      </div>
    </div>
  </section>
</div>