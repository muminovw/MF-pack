<script>
  import { onMount } from 'svelte';
  import Navbar from "./components/Navbar/Navbar.svelte";
  import Hero from "./components/Hero/Hero.svelte";
  import About from "./components/About/About.svelte";
  import Product from "./components/Product/Product.svelte";
  import Format from "./components/Format/Format.svelte";
  import WhyUs from "./components/Whyus/WhyUs.svelte";
  
  import Contact from "./components/Contact/Contact.svelte";
  import Footer  from './components/footer/Footer.svelte';

  let isLoading = true;

  onMount(() => {
    const timer = setTimeout(() => {
      isLoading = false;
    }, 3000); // 3 soniya

    return () => clearTimeout(timer);
  });
</script>

{#if isLoading}
  <div class="loader-container">
    <div class="dots">
      <span class="dot"></span>
      <span class="dot"></span>
      <span class="dot"></span>
    </div>
  </div>
{:else}
  <main>
    <Navbar />
    <Hero />
    <About />
    <Product />
    <Format />
    <WhyUs /> 
    <Contact />
    <Footer/>
  </main>
{/if}

<style>
  /* Loader ekrani dizayni */
  .loader-container {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    background-color: #ffffff; /* Fon rangi, xohishga ko'ra o'zgartirishingiz mumkin */
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 9999;
  }

  .dots {
    display: flex;
    gap: 12px;
  }

  .dot {
    width: 16px;
    height: 16px;
    background-color: #8B4513; /* Jigarrang rang (SaddleBrown) */
    border-radius: 50%;
    animation: bounce 0.6s infinite alternate;
  }

  .dot:nth-child(2) {
    animation-delay: 0.2s;
  }

  .dot:nth-child(3) {
    animation-delay: 0.4s;
  }

  @keyframes bounce {
    to {
      transform: translateY(-15px);
      opacity: 0.4;
    }
  }
</style>