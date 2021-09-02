<script>
  import { onMount } from "svelte";
  import { gsap } from "gsap";
  import Typewriter from "./Typewriter.svelte";

  let start = 0;

  onMount(() => {
    gsap.to(".first", {top: "-200%", duration: 2, delay: start})
    gsap.to(".second", {top: "-200%", duration: 2, delay: start + 0.2})
    gsap.to(".third", {top: "-200%", duration: 2, delay: start + 0.4})
    gsap.to(".text", {y: '0%', duration: 1})
  })
</script>
<div class="overlays">
  <div class="first"></div>
  <div class="second text-center">
    <div class="intro">
      <h1 class="hide bg-red-700 overflow-hidden">
        <span class="text">Arthur Temmerman</span>
      </h1>
      <h1 class="hide bg-red-700 overflow-hidden">
        <span class="text text-black">Portfolio</span>
      </h1>
    </div>
  </div>
  <div class="third"></div>
</div>

<div class="hero text-6xl leading-snug font-bold">

  <div class="hidetext">
    <h2 class="text-9xl">Hello<span class="text-red-700">!</span></h2>
    <h2>My name is</h2>
    <h2>Arthur <span class="text-red-700">Temmerman</span></h2>
    <Typewriter />
  </div>
</div>

<style>
  .hero {
    position: absolute;
    width: 70%;
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
    font-size: 3rem;
  }
  .intro .hide span {
    transform: translateY(100%);
    display: inline-block;
  }
</style>