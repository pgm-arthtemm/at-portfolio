<script>
  import { onMount } from 'svelte';

  onMount(() => {
    const formElement = document.querySelector('#contact-form');
    formElement.addEventListener('submit', (e) => {
      e.preventDefault();
      const data = new URLSearchParams(new FormData(formElement));
      fetch("https://getform.io/f/8aaa0fda-1db2-40e2-89da-7fd6856e5a68", {
        method: "post",
        body: data,
      });
      alert("Thanks for submitting");
    });
  });
</script>

<form id="contact-form" action="https://getform.io/f/8aaa0fda-1db2-40e2-89da-7fd6856e5a68" method="POST">
  <label for="fullname">Your full name</label>
  <input type="text" id="fullname" name="fullname">

  <label for="email">Your email</label>
  <input type="email" id="email" name="email">

  <label for="message">Your message</label>
  <textarea name="message" id="message" cols="30" rows="10"></textarea>

  <button>Submit</button>
</form>

<style>
  form {
    color: black;
  }

  form label {
    color: white;
  }
</style>