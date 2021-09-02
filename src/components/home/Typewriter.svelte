<script lang="typescript">
  import { onMount } from 'svelte';

  let wait:number = 3000;
  const words: string[] = ["Front End Developer", "Designer", "Full Stack JS Developer"];

  const TypeWriter = function(txtElement: any, words: string[], wait: number = 3000) {
    this.txtElement = txtElement;
    this.words = words,
    this.txt = '';
    this.wordIndex = 0;
    this.wait = wait;
    this.type();
    this.isDeleting = false;
  };

  TypeWriter.prototype.type = function() {
    const current = this.wordIndex % this.words.length;
    const fullText = this.words[current];

    if (this.isDeleting) {
      this.txt = fullText.substring(0, this.txt.length - 1);
    } else {
      this.txt = fullText.substring(0, this.txt.length + 1);
    }

    this.txtElement.innerHTML = `<span class="border-r-4 border-red-700">${this.txt}</span>`;

    let typeSpeed: number = 150;

    if (this.isDeleting) {
      typeSpeed /= 2;
    };

    if (!this.isDeleting && this.txt === fullText) {
      typeSpeed = this.wait;
      this.isDeleting = true;
    } else if (this.isDeleting && this.txt === '') {
      this.isDeleting = false;
      this.wordIndex++;
      typeSpeed = 300;
    }

    setTimeout(() => {
      this.type()
    }, typeSpeed);
  }

  onMount(() => {
    const txtElement = document.querySelector('.txt-type');

    const init = () => {
      new TypeWriter(txtElement, words, wait);
    }
    init(); 
  });
</script>

<div class="flex flex-col content-center h-full">
  <span class="txt-type"></span>
</div>