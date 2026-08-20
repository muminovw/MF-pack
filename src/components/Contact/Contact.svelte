<script lang="ts">
  import './Contact.sass'


  let selectedSize = 'L';
  let selectedColor = '#8B6B58';
  let selectedColorName = 'Олтин';

  const sizeOptions = [
    { id: 'S', label: 'S', dimensions: '15×19×8 см' },
    { id: 'M', label: 'M', dimensions: '23×27×10 см' },
    { id: 'L', label: 'L', dimensions: '28×36×13 см' },
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
    { name: 'Молочный', hex: '#F7F4EE' },
  ];

  let name = '';
  let phone = '+998 ';
  let quantity = '';
  let comment = '';
  let logoFile: File | null = null;
  let logoPreview: string | null = null;

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

  function handleSubmit(event: SubmitEvent) {
    event.preventDefault();
    const orderData = {
      name,
      phone,
      size: selectedSize,
      color: selectedColorName,
      quantity,
      comment,
      logoFile
    };
    console.log('Данные заказа:', orderData);
    alert('Запрос успешно отправлен!');
  }
</script>

<section class="contact-section">
  <div class="contact-container">
    
    <!-- Левая колонка: Конструктор дизайна -->
    <div class="card design-card">
      <div class="section-header">
        <h2>Создайте свой дизайн</h2>
        <p>Выберите размер и цвет, загрузите логотип — здесь отобразится эскиз вашей подарочной упаковки.</p>
      </div>

      <div class="preview-box" style="background-color: {selectedColor}12;">
        <div class="mockup-bag" style="background-color: {selectedColor};">
          {#if logoPreview}
            <img src={logoPreview} alt="Логотип" class="uploaded-logo" />
          {:else}
            <span class="placeholder-text">Ваш логотип</span>
          {/if}
        </div>
        <div class="eskiz-badge">
          <span class="badge-dot"></span> ЭСКИЗ — ПРИМЕРНЫЙ ВИД
        </div>
      </div>

      <div class="control-group">
        <span class="control-label">РАЗМЕР</span>
        <div class="size-options">
          {#each sizeOptions as size}
            <button 
              type="button" 
              class="size-btn {selectedSize === size.id ? 'active' : ''}"
              on:click={() => selectedSize = size.id}
            >
              <span class="size-letter">{size.id}</span>
              <span class="size-dim">{size.dimensions}</span>
            </button>
          {/each}
        </div>
      </div>

      <div class="control-group">
        <span class="control-label">Цвет / узор: <span class="selected-color-name">{selectedColorName}</span></span>
        <div class="color-palette">
          {#each colorPalette as color}
            <button 
              type="button"
              class="color-circle {selectedColor === color.hex ? 'selected' : ''}"
              style="background-color: {color.hex};"
              title={color.name}
              on:click={() => handleColorSelect(color)}
            >
              {#if selectedColor === color.hex}
                <span class="checkmark">✓</span>
              {/if}
            </button>
          {/each}
        </div>
      </div>

      <div class="control-group">
        <span class="control-label">Логотип</span>
        <label class="file-upload-box">
          <input type="file" accept="image/png, image/jpeg" on:change={handleFileChange} hidden />
          <div class="upload-icon">+</div>
          <div class="upload-text">
            <strong>Нажмите для выбора файла</strong>
            <span>PNG или JPG, рекомендуется квадратный формат</span>
          </div>
        </label>
      </div>
    </div>

    <!-- Правая колонка: Форма заявки -->
    <div class="card form-card">
      <div class="form-title-mobile">
        <h2>Оформление заказа</h2>
      </div>
      <form on:submit={handleSubmit}>
        
        <div class="form-row">
          <div class="form-group">
            <label for="name">ИМЯ</label>
            <input 
              id="name" 
              type="text" 
              bind:value={name} 
              placeholder="Ваше имя" 
              required 
            />
          </div>
          <div class="form-group">
            <label for="phone">ТЕЛЕФОН</label>
            <input 
              id="phone" 
              type="text" 
              bind:value={phone} 
              placeholder="+998 _ _ _ _ _ _ _" 
              required 
            />
          </div>
        </div>

        <div class="form-row">
          <div class="form-group">
            <label for="color-select">ЦВЕТ</label>
            <select id="color-select" bind:value={selectedColor}>
              {#each colorPalette as color}
                <option value={color.hex}>{color.name}</option>
              {/each}
            </select>
          </div>
          <div class="form-group">
            <label for="quantity">КОЛИЧЕСТВО (ШТ)</label>
            <input 
              id="quantity" 
              type="text" 
              bind:value={quantity} 
              placeholder="Например, 200 шт" 
              required 
            />
          </div>
        </div>

        <div class="form-group full-width">
          <label for="comment">КОММЕНТАРИЙ</label>
          <textarea 
            id="comment" 
            rows="4" 
            bind:value={comment} 
            placeholder="Ваши дополнительные пожелания"
          ></textarea>
        </div>

        <button type="submit" class="submit-btn">
          Отправить запрос
        </button>

      </form>
    </div>

  </div>
</section>

<style lang="scss">
  @use './Contact.sass';
</style>