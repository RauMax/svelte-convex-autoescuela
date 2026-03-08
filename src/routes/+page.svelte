<script lang="ts">
  import Navbar from "$lib/components/landing/Navbar.svelte";
  import Hero from "$lib/components/landing/Hero.svelte";
  import Features from "$lib/components/landing/Features.svelte";
  import Pricing from "$lib/components/landing/Pricing.svelte";
  import Footer from "$lib/components/landing/Footer.svelte";
</script>

<div class="min-h-screen bg-white">
  <Navbar />

  <main>
    <Hero />
    <Features />
    <Pricing />
  </main>

  <Footer />
</div>
