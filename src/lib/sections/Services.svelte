<script lang="ts">
  import SectionTitle from '../components/SectionTitle.svelte';
  import InfoCard from '../components/InfoCard.svelte';
  import { fade } from 'svelte/transition';
  import { onMount } from 'svelte';

  let visible = false;
  onMount(() => {
    visible = true;
  });

  const services = [
    {
      icon: `<svg class="w-16 h-16" fill="currentColor" viewBox="0 0 24 24">
        <path d="M12 6V4m0 2a2 2 0 100 4m0-4a2 2 0 110 4m-6 8a2 2 0 100-4m0 4a2 2 0 110-4m0 4v2m0-6V4m6 6v10m6-2a2 2 0 100-4m0 4a2 2 0 110-4m0 4v2m0-6V4"></path>
      </svg>`,
      title: 'Digital Strategy',
      description: 'We develop comprehensive digital strategies that align with your business objectives and drive measurable results through data-driven insights.'
    },
    {
      icon: `<svg class="w-16 h-16" fill="currentColor" viewBox="0 0 24 24">
        <path d="M4 5a1 1 0 011-1h14a1 1 0 011 1v2a1 1 0 01-1 1H5a1 1 0 01-1-1V5zM4 13a1 1 0 011-1h6a1 1 0 011 1v6a1 1 0 01-1 1H5a1 1 0 01-1-1v-6zM16 13a1 1 0 011-1h2a1 1 0 011 1v6a1 1 0 01-1 1h-2a1 1 0 01-1-1v-6z"></path>
      </svg>`,
      title: 'Enterprise Solutions',
      description: 'Custom enterprise-grade solutions built with cutting-edge technologies, ensuring scalability, security, and exceptional performance.'
    },
    {
      icon: `<svg class="w-16 h-16" fill="currentColor" viewBox="0 0 24 24">
        <path d="M12 18h.01M8 21h8a2 2 0 002-2V5a2 2 0 00-2-2H8a2 2 0 00-2 2v14a2 2 0 002 2z"></path>
      </svg>`,
      title: 'Digital Transformation',
      description: 'Comprehensive digital transformation services that modernize your business processes and create seamless digital experiences.'
    },
    {
      icon: `<svg class="w-16 h-16" fill="currentColor" viewBox="0 0 24 24">
        <path d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z"></path>
      </svg>`,
      title: 'Innovation Lab',
      description: 'Our innovation lab explores emerging technologies and develops pioneering solutions that keep your business ahead of the curve.'
    }
  ];
</script>

<section id="services" class="section bg-gray-50">
  <div class="container">
    <SectionTitle 
      title="Enterprise Solutions"
      subtitle="Comprehensive digital solutions engineered for enterprise-scale performance and reliability"
      align="left"
    />

    {#if visible}
      <div class="grid md:grid-cols-2 gap-px bg-gray-200" transition:fade>
        {#each services as service}
          <InfoCard {...service} />
        {/each}
      </div>

      <div class="mt-20">
        <a href="#contact" class="btn btn-primary">
          Schedule a Consultation
        </a>
      </div>
    {/if}
  </div>
</section>