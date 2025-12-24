<script lang="ts">
  import '../app.css';
  import Header from '$lib/components/Header.svelte';
  import Footer from '$lib/components/Footer.svelte';
</script>

<svelte:head>
  <title>SvelteKit - Modern Svelte Template</title>
</svelte:head>

<div class="page-container">
  <Header />
  <div class="content-wrapper">
    <slot />
  </div>
  <Footer />
</div>
