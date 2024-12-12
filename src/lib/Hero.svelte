<script lang="ts">
  import { onMount } from 'svelte';
  
  let videoLoaded = false;
  
  onMount(() => {
    setTimeout(() => {
      videoLoaded = true;
    }, 100);
  });
</script>

<section class="relative h-screen flex items-center justify-center overflow-hidden">
  <!-- Video Background -->
  <div class="absolute inset-0 w-full h-full">
    <video
      class="object-cover w-full h-full"
      autoplay
      muted
      loop
      playsinline
      poster="https://images.unsplash.com/photo-1504384764586-bb4cdc1707b0?auto=format&fit=crop&q=80"
    >
      <source src="https://player.vimeo.com/external/449759244.sd.mp4?s=d5f3da46ddc17aa69a7de84f1e420610ecd2108d&profile_id=165&oauth2_token_id=57447761" type="video/mp4">
    </video>
    <div class="absolute inset-0 bg-black/50"></div>
  </div>

  <!-- Content -->
  <div class="container relative z-10 text-white text-center px-4">
    <h1 class="text-4xl md:text-6xl font-bold mb-6 animate-fade-in">
      Transform Your Business with XYZ
    </h1>
    <p class="text-xl md:text-2xl mb-8 max-w-2xl mx-auto animate-slide-up">
      Elevate your digital presence with our premium solutions tailored for modern businesses.
    </p>
    <a href="#contact" class="btn btn-primary text-lg animate-slide-up">
      Get Started Today
    </a>
  </div>

  <!-- Scroll Indicator -->
  <div class="absolute bottom-8 left-1/2 transform -translate-x-1/2 animate-bounce">
    <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3" />
    </svg>
  </div>
</section>