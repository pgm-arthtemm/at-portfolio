<script>
  import { gsap } from "gsap";
  import MdMenu from 'svelte-icons/md/MdMenu.svelte';
  import MdClose from 'svelte-icons/md/MdClose.svelte';

  let menuOpen = false;

  const toggleMenu = () => {
    menuOpen = !menuOpen;
    if (menuOpen) {
      gsap.to(".hamburger--menu", {right: 0, duration: 0.7})
    } else {
      gsap.to(".hamburger--menu", {right: "100%", duration: 0.7})
    }
  }
</script>

<nav class="overflow-hidden">
  <div on:click={toggleMenu} class:hidden={menuOpen} class="icon w-10 h-10 absolute top-10 right-10 cursor-pointer">
    <MdMenu />
  </div>
  <div class="hamburger--menu w-screen h-screen absolute bg-black z-50">
    <div on:click={toggleMenu} class:hidden={!menuOpen} class="icon w-10 h-10 absolute top-10 right-10 cursor-pointer">
      <MdClose />
    </div>
    <ul class="mt-10 ml-16">
      <li on:click={toggleMenu} class="text-4xl uppercase font-bold mb-12"><a sveltekit:prefetch href="/">Home</a></li>
      <li on:click={toggleMenu} class="text-4xl uppercase font-bold mb-12"><a sveltekit:prefetch href="/projects">Projects</a></li>
      <li on:click={toggleMenu} class="text-4xl uppercase font-bold mb-12"><a sveltekit:prefetch href="/info">Info</a></li>
      <li on:click={toggleMenu} class="text-4xl uppercase font-bold mb-12"><a sveltekit:prefetch href="/contact">Contact</a></li>
    </ul>
  </div>
</nav>

<style>
  .hamburger--menu {
    right: 100%;
  }
</style>