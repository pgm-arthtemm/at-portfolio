<script>
  import Nav from '$lib/layout/Nav.svelte';
  import MobileNav from '$lib/layout/MobileNav.svelte';
</script>

<div class="block md:hidden">
  <MobileNav />
</div>

<div class="hidden md:block">
  <Nav />
</div>

<div class="container m-auto">
  <slot />
</div>

<style>
  @tailwind base;
  @tailwind components;
  @tailwind utilities;

  :global(:root) {
    background-color: #141414;
    color: white;
  }
</style>