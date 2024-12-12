<script lang="ts">
  import Header from './lib/Header.svelte';
  import Hero from './lib/Hero.svelte';
  import About from './lib/sections/About.svelte';
  import Services from './lib/sections/Services.svelte';
  import Features from './lib/sections/Features.svelte';
  import Portfolio from './lib/sections/Portfolio.svelte';
  import Trust from './lib/sections/Trust.svelte';
  import Testimonials from './lib/sections/Testimonials.svelte';
  import FAQ from './lib/sections/FAQ.svelte';
  import Contact from './lib/sections/Contact.svelte';
  import Footer from './lib/Footer.svelte';
</script>

<Header />
<main>
  <Hero />
  <About />
  <Services />
  <Features />
  <Portfolio />
  <Trust />
  <Testimonials />
  <FAQ />
  <Contact />
</main>
<Footer />

<style>
  :global(html) {
    scroll-behavior: smooth;
  }
</style>