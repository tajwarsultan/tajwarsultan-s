<script lang="ts">
  import '../app.css';
  import Navbar from '$lib/components/Navbar.svelte';
  import Footer from '$lib/components/Footer.svelte';
</script>

<div class="min-h-screen bg-gradient-to-b from-gray-900 to-black text-white">
  <Navbar />
  <main>
    <slot />
  </main>
  <Footer />
</div>

<style>
  :global(html) {
    scroll-behavior: smooth;
  }
</style>