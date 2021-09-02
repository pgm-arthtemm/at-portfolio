<script>
  import Nav from '../components/layout/Nav.svelte';
</script>

<Nav />
<div class="container m-auto">
  <slot />
</div>

<style>
  @tailwind base;
  @tailwind components;
  @tailwind utilities;

  :global(:root) {
    background-color: rgb(20, 20, 20);
    color: white;
  }
</style>