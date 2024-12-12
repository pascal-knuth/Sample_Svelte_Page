<script lang="ts">
  import SectionTitle from '../components/SectionTitle.svelte';
  import { fade } from 'svelte/transition';
  import { onMount } from 'svelte';

  let visible = false;
  onMount(() => {
    visible = true;
  });

  const stats = [
    { number: '10+', label: 'Years Experience' },
    { number: '200+', label: 'Projects Completed' },
    { number: '50+', label: 'Team Members' },
    { number: '99%', label: 'Client Satisfaction' }
  ];
</script>

<section id="about" class="section bg-gray-50">
  <div class="container">
    <SectionTitle 
      title="About XYZ"
      subtitle="We're a team of passionate experts dedicated to delivering exceptional digital solutions"
    />

    {#if visible}
      <div class="grid md:grid-cols-2 gap-12 items-center" transition:fade>
        <!-- About Content -->
        <div class="space-y-6">
          <h3 class="text-2xl font-bold text-gray-800">
            Transforming Businesses Through Innovation
          </h3>
          <p class="text-gray-600">
            At XYZ, we combine creativity with technical expertise to help businesses thrive in the digital age. Our approach is rooted in understanding your unique challenges and delivering tailored solutions that drive real results.
          </p>
          <div class="flex gap-4">
            <a href="#services" class="btn btn-primary">Our Services</a>
            <a href="#contact" class="btn bg-white border-2 border-primary text-primary hover:bg-primary hover:text-white">
              Get in Touch
            </a>
          </div>
        </div>

        <!-- Stats Grid -->
        <div class="grid grid-cols-2 gap-6">
          {#each stats as { number, label }}
            <div class="bg-white p-6 rounded-lg shadow-md text-center">
              <div class="text-3xl font-bold text-primary mb-2">{number}</div>
              <div class="text-gray-600">{label}</div>
            </div>
          {/each}
        </div>
      </div>
    {/if}
  </div>
</section>