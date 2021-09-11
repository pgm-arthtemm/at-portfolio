<script>
  import { onMount } from "svelte";
  import { gsap } from "gsap";

  import TypeWriter from './Typewriter.svelte';

  // Lower start = faster
  let start = 1.5;
  let wordArray = ["H", "e", "l", "l", "o", "!"];

  onMount(() => {
    gsap.to(".first", {top: "-100%", duration: 1, delay: start})
    gsap.to(".second", {top: "-100%", duration: 1, delay: start + 0.2})
    gsap.to(".third", {top: "-100%", duration: 1, delay: start + 0.4})
    gsap.to(".mobile-intro", {left: "-100%", duration: 1, delay: start})
    gsap.to(".text", {y: '0%', duration: 1})
    gsap.to(".mobile-text", {y: '0%', duration: 1})
    gsap.from(".hello", {x: "-100%", duration: 1 , delay: start + 1})
    gsap.from(".info", {y: "100vh", duration: 1.5, delay: start + 1.2})
  })
</script>

<div class="mobile--overlay md:hidden">
  <div class="mobile-intro absolute bg-red-700 w-screen h-screen z-50 overflow-hidden top-0 left-0">
    <div class="intro-text">
      <h1 class="hide overflow-hidden">
        <span class="mobile-text">Arthur Temmerman</span>
      </h1>
      <h1 class="hide overflow-hidden">
        <span class="mobile-text text-black">Portfolio</span>
      </h1>
    </div>
  </div>
</div>
<div class="overlays hidden md:block">
  <div class="first"></div>
  <div class="second text-center">
    <div class="intro">
      <h1 class="hide bg-red-700 overflow-hidden">
        <span class="text text-4xl xl:text-5xl">Arthur Temmerman</span>
      </h1>
      <h1 class="hide bg-red-700 overflow-hidden">
        <span class="text text-4xl xl:text-5xl text-black">Portfolio</span>
      </h1>
    </div>
  </div>
  <div class="third"></div>
</div>

<div class="hero w-11/12 md:w-9/12 text-6xl leading-snug font-bold">
  <div class="hidetext">
    <h2 class="hello text-center text-7xl md:text-8xl md:text-left lg:text-9xl">
        {#each wordArray as letter, index}
          {#if index === 5}
          <span class="text-red-700 transition duration-300 ease-in-out hover:text-white cursor-pointer">{letter}</span>
          {:else}
          <span class="transition duration-300 ease-in-out hover:text-red-700 cursor-pointer">{letter}</span>
          {/if}  
        {/each}
    </h2>
    <div class="info text-center md:text-left">
      <h2 class="text-4xl mt-16 md:mt-4 md:text-5xl xl:text-6xl mb-6">My name is</h2>
      <h2 class="text-4xl md:text-5xl xl:text-6xl mb-6">Arthur <span class="text-red-700 text-4xl md:text-5xl xl:text-6xl mb-6">Temmerman</span></h2>
      <Typewriter />
    </div>
  </div>
</div>

<style>
  .hero {
    overflow: hidden;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
  .overlays > div {
    position: absolute;
    top: 0;
    width: 33.3vw;
    height: 100vh;
    z-index: 99;
    background: rgb(185, 28, 28);
  }
  .first {
    left: 0;
  }
  .second {
    left: 33.3vw;
  }
  .third {
    left: 66.6%;
  }
  .intro {
    font-weight: bold;
    width: 30vw;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
  .intro .hide span {
    transform: translateY(100%);
    display: inline-block;
  }
  .mobile-intro .hide span {
    transform: translateY(100%);
    display: inline-block;
  }
  .intro-text {
    font-weight: bold;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -90%);
    font-size: 2.5rem;
    text-align: center;
  }
</style>