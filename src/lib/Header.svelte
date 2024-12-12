<script lang="ts">
  import { onMount } from 'svelte';
  import { fade, fly } from 'svelte/transition';
  
  let isScrolled = false;
  let isMenuOpen = false;

  onMount(() => {
    const handleScroll = () => {
      isScrolled = window.scrollY > 50;
    };
    
    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  });

  const toggleMenu = () => {
    isMenuOpen = !isMenuOpen;
    if (isMenuOpen) {
      document.body.style.overflow = 'hidden';
    } else {
      document.body.style.overflow = 'auto';
    }
  };
</script>

<header class="fixed w-full z-50 transition-all duration-300" class:bg-white={isScrolled} class:shadow-lg={isScrolled}>
  <div class="container mx-auto px-4">
    <nav class="flex items-center h-20">
      <a href="/" class="text-2xl font-bold text-primary">XYZ</a>
      
      <!-- Desktop Menu -->
      <div class="hidden md:flex items-center justify-end flex-1 space-x-8">
        <a href="#about" class="hover:text-primary transition-colors">About</a>
        <a href="#services" class="hover:text-primary transition-colors">Services</a>
        <a href="#testimonials" class="hover:text-primary transition-colors">Testimonials</a>
        <a href="#faq" class="hover:text-primary transition-colors">FAQ</a>
        <a href="#contact" class="btn btn-primary">Contact Us</a>
      </div>

      <!-- Modern Burger Menu Button -->
      <button 
        class="md:hidden flex items-center justify-center w-12 h-20 relative focus:outline-none ml-auto"
        on:click={toggleMenu}
        aria-label="Toggle menu"
      >
        <div class="w-6 h-5 relative">
          <span
            class="absolute h-0.5 w-full bg-primary transform transition-all duration-300 ease-in-out"
            class:rotate-45={isMenuOpen}
            class:translate-y-2={isMenuOpen}
            style="top: 0;"
          ></span>
          <span
            class="absolute h-0.5 w-full bg-primary transform transition-all duration-300 ease-in-out"
            class:opacity-0={isMenuOpen}
            style="top: 50%; transform: translateY(-50%);"
          ></span>
          <span
            class="absolute h-0.5 w-full bg-primary transform transition-all duration-300 ease-in-out"
            class:-rotate-45={isMenuOpen}
            class:-translate-y-2={isMenuOpen}
            style="bottom: 0;"
          ></span>
        </div>
      </button>
    </nav>
  </div>

  <!-- Off-Canvas Mobile Menu -->
  {#if isMenuOpen}
    <div 
      class="fixed inset-0 bg-black/50 z-40"
      on:click={toggleMenu}
      transition:fade={{ duration: 200 }}
    ></div>
    
    <div
      class="fixed top-0 right-0 w-[300px] h-full bg-white z-50 shadow-2xl"
      transition:fly={{ x: 300, duration: 300, opacity: 1 }}
    >
      <div class="flex flex-col h-full">
        <!-- Menu Header -->
        <div class="p-6 border-b border-gray-100">
          <h2 class="text-xl font-bold text-primary">Menu</h2>
        </div>

        <!-- Menu Items -->
        <nav class="flex-1 overflow-y-auto py-6">
          <div class="flex flex-col space-y-2 px-6">
            <a 
              href="#about" 
              class="py-3 text-lg hover:text-primary transition-colors border-b border-gray-100"
              on:click={toggleMenu}
            >
              About
            </a>
            <a 
              href="#services" 
              class="py-3 text-lg hover:text-primary transition-colors border-b border-gray-100"
              on:click={toggleMenu}
            >
              Services
            </a>
            <a 
              href="#testimonials" 
              class="py-3 text-lg hover:text-primary transition-colors border-b border-gray-100"
              on:click={toggleMenu}
            >
              Testimonials
            </a>
            <a 
              href="#faq" 
              class="py-3 text-lg hover:text-primary transition-colors border-b border-gray-100"
              on:click={toggleMenu}
            >
              FAQ
            </a>
          </div>
        </nav>

        <!-- Menu Footer -->
        <div class="p-6 border-t border-gray-100">
          <a 
            href="#contact" 
            class="btn btn-primary w-full text-center"
            on:click={toggleMenu}
          >
            Contact Us
          </a>
        </div>
      </div>
    </div>
  {/if}
</header>

<style>
  /* Prevent content shifting when scrollbar disappears */
  :global(body) {
    padding-right: var(--scrollbar-width, 0px);
  }
  
  :global(body.no-scroll) {
    overflow: hidden;
  }
</style>