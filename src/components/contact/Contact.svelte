<script>
  import { onMount } from 'svelte';
  import { gsap } from 'gsap';
  import FaCheck from 'svelte-icons/fa/FaCheck.svelte';

  let name;
  let email;
  let message;

  onMount(() => {
    const formElement = document.querySelector('#contact-form');
    formElement.addEventListener('submit', (e) => {
      e.preventDefault();
      const data = new URLSearchParams(new FormData(formElement));
      fetch("https://getform.io/f/8aaa0fda-1db2-40e2-89da-7fd6856e5a68", {
        method: "post",
        body: data,
      });
      gsap.to(".circle", {y: "80vh", duration: .5})
      gsap.to(".circle", {y: "-80vh", duration: 2, delay: 2})
      name = email = message = '';
    });
  });
  const testing = () => {
      gsap.to(".circle", {y: "80vh", duration: .5, rotation: 360})
      gsap.to(".circle", {y: "-80vh", duration: 2, delay: 2})
      gsap.to(".circle", {rotation: -360, delay: 2.5})
    }
</script>

<div class="contact pt-16 m-auto w-11/12 md:w-7/12 text-center">
  <div class="circle">
    <div class="icon">
      <FaCheck />
    </div>
  </div>
  <h2 class="text-4xl font-bold mb-4 lg:text-5xl">Get in <span class="text-red-700">contact:</span></h2>
  <form class="flex flex-wrap pt-2" id="contact-form" action="https://getform.io/f/8aaa0fda-1db2-40e2-89da-7fd6856e5a68" method="POST">
    <div class="w-full mb-4 lg:mb-8">
      <label class="block font-bold text-2xl mb-1" for="fullname">Your full <span class="text-red-700">name:</span></label>
      <input bind:value={name} class="w-10/12 rounded-md h-8 pl-2 lg:h-10" required type="text" id="fullname" name="fullname">
    </div>  
    
    <div class="w-full mb-4 lg:mb-8">
      <label class="block font-bold text-2xl mb-1" for="email">Your <span class="text-red-700">email:</span></label>
      <input bind:value={email} class="w-10/12 rounded-md h-8 pl-2 lg:h-10" required type="email" id="email" name="email">
    </div>
    
    <div class="w-full mb-4 lg:mb-8">
      <label class="block font-bold text-2xl mb-1" for="message">Your <span class="text-red-700">message:</span></label>
      <textarea bind:value={message} class="max-h-28 min-h-28 w-10/12 rounded-md md:max-h-52 md:min-h-52 pl-2 pt-2" name="message" required id="message" cols="30" rows="10"></textarea>
    </div>
    
    <button on:click={testing} class="bg-red-700 m-auto hover:bg-red-500 text-white text-2xl mt-2 font-bold py-2 px-4 border-b-4 border-red-800 hover:border-red-500 rounded">
      Send message
    </button>
  </form>
</div>

<style>
  form {
    color: black;
  }
  form label {
    color: white;
  }
  .circle {
    position: absolute;
    width: 10rem;
    height: 10rem;
    border-radius: 50%;
    background: green;
    top: -40%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
  .icon {
    position: absolute;
    width: 5.5rem;
    height: 5.5rem;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
</style>