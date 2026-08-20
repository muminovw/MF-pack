<script lang="ts">
    import "./Navbar.sass";
    import logo from "../../assets/logo.png";

    let menuOpen = false;

    const navItems = [
        { title: "О компании", href: "#about" },
        { title: "Продукция", href: "#products" },
        { title: "Форматы", href: "#formats" },
        { title: "Галерея", href: "#gallery" },
        { title: "Адрес", href: "#location" },
        { title: "Контакты", href: "#contact" },
    ];

    function closeMenu() {
        menuOpen = false;
    }

    function toggleMenu() {
        menuOpen = !menuOpen;
    }
</script>

<svelte:head>
    <title>MF Pack — Gift Bags</title>
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="anonymous" />
    <link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display&family=Fraunces:opsz,wght@9..144,300;9..144,400;9..144,500;9..144,600&family=Manrope:wght@400;500;600;700&display=stylesheet" rel="stylesheet" />
</svelte:head>

<header class:menu-open={menuOpen}>
    <nav class="navbar">
        <!-- BRAND -->
        <a href="/" class="brand" aria-label="MF Pack — главная" onclick={closeMenu}>
            <div class="brand-bag">
                <img src={logo} alt="MF Pack" />
            </div>
            <span class="brand-divider"></span>
            <div class="brand-text">
                <div class="brand-name">
                    <span class="mf">MF</span>
                    <span class="pack">pack</span>
                </div>
                <div class="brand-subtitle">GIFT BAGS</div>
            </div>
        </a>

        <!-- DESKTOP NAVIGATION -->
        <ul class="nav-list">
            {#each navItems as item}
                <li>
                    <a href={item.href}>{item.title}</a>
                </li>
            {/each}
        </ul>

        <!-- RIGHT SIDE -->
        <div class="nav-right">
            <!-- SOCIALS -->
            <div class="socials">
                <a href="https://instagram.com/yaltiroq.uz" target="_blank" rel="noopener noreferrer" aria-label="Instagram" class="social-link">
                    <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7">
                        <rect x="3" y="3" width="18" height="18" rx="5" />
                        <circle cx="12" cy="12" r="4" />
                        <circle cx="17.2" cy="6.8" r="1" />
                    </svg>
                </a>
                <a href="https://t.me/yaltiroq_uz" target="_blank" rel="noopener noreferrer" aria-label="Telegram" class="social-link">
                    <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7">
                        <path d="M21 4L2.5 11.2c-.9.35-.9 1.65.02 1.98l4.6 1.65 1.8 5.6c.28.86 1.36 1.1 1.98.45l2.6-2.7 4.7 3.5c.75.56 1.83.16 2.03-.75L22 4.7c.18-.85-.65-1.55-1.4-1.2z" />
                        <path d="M8.9 14.6L18 6.8" />
                    </svg>
                </a>
            </div>

            <!-- CTA -->
            <a href="#contact" class="nav-cta" onclick={closeMenu}>Заказать</a>

            <!-- MOBILE MENU BUTTON -->
            <button type="button" class="menu-button" class:active={menuOpen} aria-label={menuOpen ? "Закрыть меню" : "Открыть меню"} aria-expanded={menuOpen} onclick={toggleMenu}>
                <span></span>
                <span></span>
                <span></span>
            </button>
        </div>
    </nav>

    <!-- MOBILE MENU DROPDOWN -->
    <div class="mobile-menu" aria-hidden={!menuOpen}>
        <div class="mobile-menu-inner">
            <nav class="mobile-nav">
                {#each navItems as item}
                    <a href={item.href} onclick={closeMenu}>
                        <span>{item.title}</span>
                        <span class="mobile-arrow">→</span>
                    </a>
                {/each}
            </nav>

            <a href="#contact" class="mobile-cta" onclick={closeMenu}>
                <span>Заказать</span>
                <span>→</span>
            </a>

            <div class="mobile-socials">
                <a href="https://instagram.com/yaltiroq.uz" target="_blank" rel="noopener noreferrer">Instagram</a>
                <span></span>
                <a href="https://t.me/yaltiroq_uz" target="_blank" rel="noopener noreferrer">Telegram</a>
            </div>
        </div>
    </div>

    <!-- GOLD LINE -->
    <div class="holo-line"></div>
</header>