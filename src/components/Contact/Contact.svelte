<script lang="ts">
  import './Contact.sass';
  import emailjs from '@emailjs/browser';

  let selectedSize = $state('L');
  let selectedColor = $state('#8B6B58');
  let selectedColorName = $state('Олтин');

  const sizeOptions = [
    { id: 'S', label: 'S', dimensions: '15×19×8 см' },
    { id: 'M', label: 'M', dimensions: '23×27×10 см' },
    { id: 'L', label: 'L', dimensions: '28×36×13 см' }
  ];

  const colorPalette = [
    { name: 'Олтин', hex: '#8B6B58' },
    { name: 'Зелёный', hex: '#2A7B6C' },
    { name: 'Розовый', hex: '#D8A7A0' },
    { name: 'Серо-голубой', hex: '#B8C0C2' },
    { name: 'Бежевый', hex: '#D7C4A5' },
    { name: 'Тёмно-зелёный', hex: '#205445' },
    { name: 'Синий', hex: '#284162' },
    { name: 'Фиолетовый', hex: '#6B5B7B' },
    { name: 'Бордовый', hex: '#7A2E3B' },
    { name: 'Терракотовый', hex: '#D47C2F' },
    { name: 'Черный', hex: '#1C1C1C' },
    { name: 'Молочный', hex: '#F7F4EE' }
  ];

  let name = $state('');
  let phone = $state('+998 ');
  let quantity = $state('');
  let comment = $state('');
  let logoFile = $state<File | null>(null);
  let logoPreview = $state<string | null>(null);
  let isSubmitting = $state(false);

  function handleColorSelect(color: { name: string; hex: string }) {
    selectedColor = color.hex;
    selectedColorName = color.name;
  }

  function handleFileChange(event: Event) {
    const target = event.target as HTMLInputElement;
    if (target.files && target.files[0]) {
      logoFile = target.files[0];
      logoPreview = URL.createObjectURL(logoFile);
    }
  }

  async function handleSubmit(event: SubmitEvent) {
    event.preventDefault();
    isSubmitting = true;

    const templateParams = {
      name: name,
      phone: phone,
      size: selectedSize,
      color: selectedColorName,
      quantity: quantity,
      comment: comment ? comment : 'Izoh yozilmagan'
    };

    try {
      const SERVICE_ID = 'service_ukkc6a5';
      const TEMPLATE_ID = 'template_txe570g';
      const PUBLIC_KEY = 'yrrqKAEMUbbpp5PgA';

      await emailjs.send(SERVICE_ID, TEMPLATE_ID, templateParams, PUBLIC_KEY);
      alert('Buyurtmangiz muvaffaqiyatli yuborildi! Tez orada siz bilan bog‘lanamiz.');
      
      name = '';
      phone = '+998 ';
      quantity = '';
      comment = '';
      logoFile = null;
      logoPreview = null;
    } catch (error) {
      console.error('EmailJS xatoligi:', error);
      alert('Xatolik yuborishda xatolik yuz berdi. Iltimos, qaytadan urinib ko‘ring.');
    } finally {
      isSubmitting = false;
    }
  }
</script>

<section class="cnt-section" id="contact">
  <div class="cnt-container">
    <!-- LEFT: CONSTRUCTOR -->
    <div class="cnt-card cnt-design-card">
      <div class="cnt-section-header">
        <div class="cnt-badge-top">PREMIUM CONSTRUCTOR</div>
        <h2>Создайте свой дизайн</h2>
        <p>Выберите размер и цвет, загрузите логотип — здесь отобразится эскиз вашей подарочной упаковки.</p>
      </div>

      <!-- DIE-CUT ESKIZ PREVIEW -->
      <div class="cnt-preview-box">
        <div class="cnt-die-cut-container">
          <svg class="cnt-die-cut-svg" viewBox="0 0 1000 700" fill="none" xmlns="http://www.w3.org/2000/svg">
            <rect x="20" y="20" width="920" height="660" fill={selectedColor} opacity="0.15" rx="4" />
            
            <g stroke="#2b2623" stroke-width="1.5" fill="none">
              <rect x="20" y="20" width="920" height="660" stroke-width="2" />
              <line x1="480" y1="20" x2="480" y2="680" />
              <line x1="20" y1="100" x2="940" y2="100" stroke-dasharray="5 5" />
              <line x1="120" y1="20" x2="120" y2="680" stroke-dasharray="5 5" />
              <line x1="590" y1="20" x2="590" y2="680" stroke-dasharray="5 5" />
              <line x1="20" y1="530" x2="940" y2="530" stroke-dasharray="5 5" />
              <line x1="20" y1="530" x2="120" y2="680" stroke-dasharray="3 3" />
              <line x1="120" y1="530" x2="20" y2="680" stroke-dasharray="3 3" />
              <line x1="480" y1="530" x2="590" y2="680" stroke-dasharray="3 3" />
              <line x1="590" y1="530" x2="480" y2="680" stroke-dasharray="3 3" />
              <circle cx="230" cy="60" r="4" fill="#ffffff" />
              <circle cx="370" cy="60" r="4" fill="#ffffff" />
              <circle cx="700" cy="60" r="4" fill="#ffffff" />
              <circle cx="840" cy="60" r="4" fill="#ffffff" />
            </g>

            <!-- DYNAMIC LOGO & TEXT (Left Side) -->
            <g transform="translate(300, 300) rotate(-90)">
              {#if logoPreview}
                <image href={logoPreview} x="-60" y="-80" width="120" height="80" preserveAspectRatio="xMidYMid meet" />
              {:else}
                <text x="0" y="-30" font-family="Georgia, serif" font-size="28" font-weight="bold" text-anchor="middle" fill="#2b2623">
                  LOGOTIP
                </text>
              {/if}
              <text x="0" y="20" font-family="sans-serif" font-size="14" letter-spacing="3" text-anchor="middle" fill="#2b2623">
                BRAND NAME
              </text>
              <text x="0" y="40" font-family="sans-serif" font-size="10" letter-spacing="1" text-anchor="middle" fill="#6e6761">
                • FASHION BOUTIQUE •
              </text>
            </g>

            <!-- DYNAMIC LOGO & TEXT (Right Side) -->
            <g transform="translate(770, 300) rotate(-90)">
              {#if logoPreview}
                <image href={logoPreview} x="-60" y="-80" width="120" height="80" preserveAspectRatio="xMidYMid meet" />
              {:else}
                <text x="0" y="-30" font-family="Georgia, serif" font-size="28" font-weight="bold" text-anchor="middle" fill="#2b2623">
                  LOGOTIP
                </text>
              {/if}
              <text x="0" y="20" font-family="sans-serif" font-size="14" letter-spacing="3" text-anchor="middle" fill="#2b2623">
                BRAND NAME
              </text>
              <text x="0" y="40" font-family="sans-serif" font-size="10" letter-spacing="1" text-anchor="middle" fill="#6e6761">
                • FASHION BOUTIQUE •
              </text>
            </g>

            <!-- SIDE INFO TEXT -->
            <g transform="translate(60, 300) rotate(-90)">
              <text x="0" y="0" font-family="sans-serif" font-size="10" fill="#6e6761" text-anchor="middle">
                {phone !== '+998 ' ? phone : '+998 90 123-45-67'} | @your_brand | website.uz
              </text>
            </g>
            <g transform="translate(530, 300) rotate(-90)">
              <text x="0" y="0" font-family="sans-serif" font-size="10" fill="#6e6761" text-anchor="middle">
                {phone !== '+998 ' ? phone : '+998 90 123-45-67'} | @your_brand | website.uz
              </text>
            </g>
          </svg>
        </div>

        <div class="cnt-eskiz-badge">
          <span class="cnt-badge-dot"></span> ЭСКИЗ (DIE-CUT TEMPLATE)
        </div>
      </div>

      <!-- CONTROLS -->
      <div class="cnt-control-group">
        <span class="cnt-control-label">РАЗМЕР</span>
        <div class="cnt-size-options">
          {#each sizeOptions as size}
            <button
              type="button"
              class="cnt-size-btn {selectedSize === size.id ? 'active' : ''}"
              onclick={() => (selectedSize = size.id)}
            >
              <span class="cnt-size-letter">{size.id}</span>
              <span class="cnt-size-dim">{size.dimensions}</span>
            </button>
          {/each}
        </div>
      </div>

      <div class="cnt-control-group">
        <span class="cnt-control-label">Цвет / узор: <span class="cnt-selected-color-name">{selectedColorName}</span></span>
        <div class="cnt-color-palette">
          {#each colorPalette as color}
            <button
              type="button"
              class="cnt-color-circle {selectedColor === color.hex ? 'selected' : ''}"
              style="background-color: {color.hex};"
              title={color.name}
              onclick={() => handleColorSelect(color)}
            >
              {#if selectedColor === color.hex}
                <span class="cnt-checkmark">✓</span>
              {/if}
            </button>
          {/each}
        </div>
      </div>

      <div class="cnt-control-group">
        <span class="cnt-control-label">Логотип</span>
        <label class="cnt-file-upload-box">
          <input type="file" accept="image/png, image/jpeg" onchange={handleFileChange} hidden />
          <div class="cnt-upload-icon">+</div>
          <div class="cnt-upload-text">
            <strong>Нажмите для выбора файла</strong>
            <span>PNG или JPG, рекомендуется квадратный формат</span>
          </div>
        </label>
      </div>

      <!-- QO'SHIMCHA PROFESSIONEL BLOCK (Bo'sh joy uchun) -->
      <div class="cnt-extra-info-box">
        <div class="cnt-extra-icon">🛡️</div>
        <div>
          <h4>Гарантия качества и экологии</h4>
          <p>100% биоразлагаемые материалы, премиальная печать и надежная фурнитура для вашего бренда.</p>
        </div>
      </div>
    </div>

    <!-- RIGHT: ORDER FORM (STICKY & FIXED) -->
    <div class="cnt-card cnt-form-card">
      <div class="cnt-form-title-mobile">
        <h2>Оформление заказа</h2>
      </div>
      <div class="cnt-form-header-desktop">
        <h2>Оформление заказа</h2>
        <p>Заполните данные для расчета стоимости и запуска тиража</p>
      </div>

      <form onsubmit={handleSubmit}>
        <div class="cnt-form-row">
          <div class="cnt-form-group">
            <label for="cnt-name">ИМЯ</label>
            <input id="cnt-name" type="text" bind:value={name} placeholder="Ваше имя" required />
          </div>
          <div class="cnt-form-group">
            <label for="cnt-phone">ТЕЛЕФОН</label>
            <input id="cnt-phone" type="text" bind:value={phone} placeholder="+998 _ _ _ _ _ _ _" required />
          </div>
        </div>

        <div class="cnt-form-row">
          <div class="cnt-form-group">
            <label for="cnt-color-select">ЦВЕТ</label>
            <select id="cnt-color-select" bind:value={selectedColor}>
              {#each colorPalette as color}
                <option value={color.hex}>{color.name}</option>
              {/each}
            </select>
          </div>
          <div class="cnt-form-group">
            <label for="cnt-quantity">КОЛИЧЕСТВО (ШТ)</label>
            <input id="cnt-quantity" type="text" bind:value={quantity} placeholder="Например, 200 шт" required />
          </div>
        </div>

        <div class="cnt-form-group cnt-full-width">
          <label for="cnt-comment">КОММЕНТАРИЙ</label>
          <textarea id="cnt-comment" rows="4" bind:value={comment} placeholder="Ваши дополнительные пожелания"></textarea>
        </div>

        <button type="submit" class="cnt-submit-btn" disabled={isSubmitting}>
          {#if isSubmitting}
            <span class="cnt-spinner"></span> Yuborilmoqda...
          {:else}
            <span>Отправить запрос</span>
            <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="5" y1="12" x2="19" y2="12"></line><polyline points="12 5 19 12 12 19"></polyline></svg>
          {/if}
        </button>
      </form>
    </div>
  </div>
</section>