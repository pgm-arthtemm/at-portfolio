<nav class="bg-transparent hidden md:block w-11/12 m-auto">
  <div class="flex py-5 justify-between items-center">
    <a href="/">
      <div class="head flex items-center">
        <div>
          <img class="w-14 mr-6" src="/ico.png" alt="logo">
        </div>
        <h2 class="text-white transition duration-100 ease-in font-bold text-2xl">Arthur <span class="text-red-700 transition duration-100 ease-in">Temmerman</span></h2>
      </div>
    </a>
    
    <div>
      <ul class="flex items-center">
        <li class="transition duration-100 ease-in font-bold text-2xl ml-12 hover:text-red-700"><a sveltekit:prefetch href="/">Home</a></li>
        <li class="transition duration-100 ease-in font-bold text-2xl ml-12 hover:text-red-700"><a sveltekit:prefetch href="/projects">Projects</a></li>
        <li class="transition duration-100 ease-in font-bold text-2xl ml-12 hover:text-red-700"><a sveltekit:prefetch href="/info">Info</a></li>
        <li class="transition duration-100 ease-in font-bold text-2xl ml-12 hover:text-red-700"><a sveltekit:prefetch href="/contact">Contact</a></li>
      </ul>
    </div>
  </div>
</nav>

<style>
  .head:hover h2 {
    color: rgba(185, 28, 28, var(--tw-text-opacity));
  }
  .head:hover span {
    color: white;
  }
</style>
