<script lang="ts">
  import { fade } from 'svelte/transition';
  import { onMount } from 'svelte';

  let visible = false;
  onMount(() => {
    visible = true;
  });
</script>

<section class="section bg-white">
  <div class="container">
    {#if visible}
      <!-- Feature 1: Image Left, Text Right -->
      <div class="grid md:grid-cols-2 gap-12 items-center mb-32" transition:fade>
        <div class="relative">
          <div class="aspect-w-4 aspect-h-3 rounded-2xl overflow-hidden">
            <img 
              src="https://images.unsplash.com/photo-1551434678-e076c223a692?auto=format&fit=crop&q=80" 
              alt="Enterprise Solutions"
              class="w-full h-full object-cover"
            />
          </div>
          <div class="absolute -bottom-6 -right-6 w-32 h-32 bg-primary/10 rounded-full blur-2xl"></div>
        </div>
        <div class="space-y-6">
          <h2 class="text-4xl font-bold">Enterprise-Grade Solutions</h2>
          <p class="text-gray-600 leading-relaxed">
            Our enterprise solutions are built to handle the most demanding business requirements. With a focus on scalability, security, and performance, we ensure your digital infrastructure can support your organization's growth.
          </p>
          <ul class="space-y-4">
            {#each ['Scalable Architecture', 'Enterprise Security', '24/7 Support', 'Custom Integration'] as feature}
              <li class="flex items-center space-x-3">
                <svg class="w-5 h-5 text-primary" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path>
                </svg>
                <span>{feature}</span>
              </li>
            {/each}
          </ul>
          <a href="#contact" class="btn btn-primary inline-block">Learn More</a>
        </div>
      </div>

      <!-- Feature 2: Text Left, Image Right -->
      <div class="grid md:grid-cols-2 gap-12 items-center" transition:fade>
        <div class="space-y-6 order-2 md:order-1">
          <h2 class="text-4xl font-bold">Digital Innovation Hub</h2>
          <p class="text-gray-600 leading-relaxed">
            Stay ahead of the curve with our innovative digital solutions. We leverage cutting-edge technologies to create unique competitive advantages for your business, ensuring you're always at the forefront of digital transformation.
          </p>
          <ul class="space-y-4">
            {#each ['AI & Machine Learning', 'IoT Integration', 'Blockchain Solutions', 'Cloud Architecture'] as feature}
              <li class="flex items-center space-x-3">
                <svg class="w-5 h-5 text-primary" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path>
                </svg>
                <span>{feature}</span>
              </li>
            {/each}
          </ul>
          <a href="#contact" class="btn btn-primary inline-block">Discover More</a>
        </div>
        <div class="relative order-1 md:order-2">
          <div class="aspect-w-4 aspect-h-3 rounded-2xl overflow-hidden">
            <img 
              src="https://images.unsplash.com/photo-1451187580459-43490279c0fa?auto=format&fit=crop&q=80" 
              alt="Digital Innovation"
              class="w-full h-full object-cover"
            />
          </div>
          <div class="absolute -bottom-6 -left-6 w-32 h-32 bg-primary/10 rounded-full blur-2xl"></div>
        </div>
      </div>
    {/if}
  </div>
</section>