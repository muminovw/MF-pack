<script>
  import './Product.sass'

  import product1 from '../../assets/pink.png'
  import product2 from '../../assets/image.png'
  import product3 from '../../assets/Victoriasecret.png'
  import product4 from '../../assets/Glamour.png'

  const products = [
    {
      id: 1,
      image: product1,
      category: 'PREMIUM',
      title: 'Pink Collection',
      description: 'Современный и яркий дизайн. Особенный премиальный выбор для подарков.',
      accent: '#e83b87',
      tags: ['Премиум', 'Элегант', 'Яркий']
    },
    {
      id: 2,
      image: product2,
      category: 'RED',
      title: 'Red Passion',
      description: 'Страстная и привлекающая внимание эксклюзивная коллекция в насыщенных красных тонах.',
      accent: '#d63031',
      tags: ['Красный', 'Страсть', 'Яркий']
    },
    {
      id: 3,
      image: product3,
      category: 'LUXURY',
      title: 'Victoria Secret',
      description: 'Изысканный и утонченный стиль — для особенных и незабываемых моментов.',
      accent: '#e83b87',
      tags: ['Люкс', 'Секрет', 'Классика']
    },
    {
      id: 4,
      image: product4,
      category: 'SPECIAL',
      title: 'Your Collection',
      description: 'Специальное место для вашего нового дизайна. Эту карточку можно изменить позже.',
      accent: '#8f7b68',
      tags: ['Особый', 'Модерн', 'Уникальный']
    }
  ]

  // Svelte 5 Runes state
  let activeProduct = $state(null)

  function openProduct(product) {
    activeProduct = product
  }

  function closeProduct() {
    activeProduct = null
  }
</script>

<section class="products-section" id="product">
  <div class="background-decoration decoration-one"></div>
  <div class="background-decoration decoration-two"></div>

  <div class="products-container">

    <!-- HEADER -->
    <div class="section-header">
      <div class="eyebrow">
        <span class="eyebrow-line"></span>
        <span>OUR COLLECTION</span>
        <span class="eyebrow-line"></span>
      </div>

      <h2>
        Цвета и
        <span>дизайны</span>
      </h2>

      <p>
        Выберите подходящий цвет для любого мероприятия или сезона —
        премиальная коллекция, созданная специально для вас.
      </p>
    </div>

    <!-- PRODUCTS -->
    <div class="products-grid">
      {#each products as product, index}
        <article
          class="product-card"
          style={`--accent: ${product.accent}; --delay: ${index * 80}ms`}
        >
          <!-- IMAGE AREA -->
          <div class="product-image">
            <div class="image-glow"></div>

            <span class="product-number">
              0{product.id}
            </span>

            <div class="product-category">
              <span class="category-dot"></span>
              {product.category}
            </div>

            <img
              src={product.image}
              alt={product.title}
            />

            <div class="image-overlay"></div>

            <button
              type="button"
              class="view-button"
              aria-label={`View ${product.title}`}
              onclick={() => openProduct(product)}
            >
              <span>Смотреть</span>

              <svg viewBox="0 0 24 24" fill="none" aria-hidden="true">
                <path
                  d="M5 12h14M13 6l6 6-6 6"
                  stroke="currentColor"
                  stroke-width="1.8"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                />
              </svg>
            </button>
          </div>

          <!-- CONTENT -->
          <div class="product-content">
            <div class="title-row">
              <div>
                <span class="small-label">COLLECTION</span>
                <h3>{product.title}</h3>
              </div>

              <div class="arrow-icon">
                <svg viewBox="0 0 24 24" fill="none" aria-hidden="true">
                  <path
                    d="M7 17L17 7M8 7h9v9"
                    stroke="currentColor"
                    stroke-width="1.7"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  />
                </svg>
              </div>
            </div>

            <p class="description">
              {product.description}
            </p>

            <!-- TAGS -->
            <div class="product-tags">
              {#each product.tags as tag}
                <span>{tag}</span>
              {/each}
            </div>

            <!-- BOTTOM -->
            <div class="product-footer">
              <div class="available">
                <span class="available-dot"></span>
                В наличии


              </div>

              <button
                type="button"
                class="details-button"
                onclick={() => openProduct(product)}
              >
                Подробнее

                <svg viewBox="0 0 24 24" fill="none" aria-hidden="true">
                  <path
                    d="M5 12h14M13 6l6 6-6 6"
                    stroke="currentColor"
                    stroke-width="1.7"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  />
                </svg>
              </button>
            </div>
          </div>
        </article>
      {/each}
    </div>

    <!-- BOTTOM INFO -->
    <div class="collection-info">
      <div class="info-item">
        <div class="info-icon">
          <svg viewBox="0 0 24 24" fill="none">
            <path d="M4 7h16v13H4zM8 7V4h8v3M8 12h8" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </div>
        <div>
          <strong>Премиум качество</strong>
          <span>Качественные материалы и красивый дизайн</span>
        </div>
      </div>

      <div class="info-item">
        <div class="info-icon">
          <svg viewBox="0 0 24 24" fill="none">
            <path d="M12 3l2.5 5.5L20 10l-4 4 1 6-5-2.8L7 20l1-6-4-4 5.5-1.5L12 3z" stroke="currentColor" stroke-width="1.5" stroke-linejoin="round"/>
          </svg>
        </div>
        <div>
          <strong>Особый дизайн</strong>
          <span>Каждая коллекция уникальна</span>
        </div>
      </div>

      <div class="info-item">
        <div class="info-icon">
          <svg viewBox="0 0 24 24" fill="none">
            <path d="M12 3l7 3v5c0 4.5-3 7.5-7 10-4-2.5-7-5.5-7-10V6l7-3z" stroke="currentColor" stroke-width="1.5" stroke-linejoin="round"/>
            <path d="M9 12l2 2 4-4" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </div>
        <div>
          <strong>Надежный выбор</strong>
          <span>Подходит для любого мероприятия</span>
        </div>
      </div>

      <div class="info-item">
        <div class="info-icon">
          <svg viewBox="0 0 24 24" fill="none">
            <path d="M20 12v8H4v-8M2 7h20v5H2zM12 7v13M12 7H7.5a2.5 2.5 0 1 1 0-5C10 2 12 7 12 7zM12 7h4.5a2.5 2.5 0 1 0 0-5C14 2 12 7 12 7z" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </div>
        <div>
          <strong>Идеальный подарок</strong>
          <span>Ваш подарок будет выглядеть еще красивее</span>
        </div>
      </div>
    </div>

  </div>
</section>

<!-- PRODUCT MODAL -->
{#if activeProduct}
  <!-- svelte-ignore a11y_click_events_have_key_events -->
  <!-- svelte-ignore a11y_no_static_element_interactions -->
  <div
    class="product-modal"
    onclick={closeProduct}
  >
    <div
      class="modal-card"
      onclick={(event) => event.stopPropagation()}
    >
      <button
        type="button"
        class="modal-close"
        aria-label="Close"
        onclick={closeProduct}
      >
        <svg viewBox="0 0 24 24" fill="none">
          <path d="M6 6l12 12M18 6L6 18" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"/>
        </svg>
      </button>

      <div class="modal-image">
        <img
          src={activeProduct.image}
          alt={activeProduct.title}
        />
      </div>

      <div class="modal-content">
        <span class="modal-label">
          {activeProduct.category}
        </span>

        <h3>{activeProduct.title}</h3>

        <p>{activeProduct.description}</p>

        <div class="modal-tags">
          {#each activeProduct.tags as tag}
            <span>{tag}</span>
          {/each}
        </div>

        <div class="modal-stock">
          <span></span>
          В наличии
        </div>
      </div>
    </div>
  </div>
{/if}