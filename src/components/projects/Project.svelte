<script>
  import FaGithub from 'svelte-icons/fa/FaGithub.svelte';
  import GoLinkExternal from 'svelte-icons/go/GoLinkExternal.svelte';

  export let project;
  let showInfo = false
</script>

<li class="project mt-8 mb-24">
  <div class="project--heading mb-4">
    <h2 class="mb-4 block transition-all duration-350 ease-in-out text-5xl md:text-6xl lg:text-7xl xl:text-8xl font-bold hover:cursor-pointer hover:ml-8" on:click={() => (showInfo = !showInfo)}>{project.name}</h2>
    <h3 class="text-red-700 text-2xl">Project for {project.for}, course {project.course}</h3>
  </div>
  <div class="show {showInfo} text-2xl">
    <p class="mb-4">{project.synopsis}</p>
    <h3 class="text-red-700 mb-4">Technologies used:</h3>
    <ul class="flex flex-wrap md:flex-auto sm:w-full">
      {#each project.tech as tech}
        <li class="pb-4 md:pb-0 md:pt-0 pr-8 text-gray-400">{tech}</li>
      {/each}
    </ul>
    <h3 class="status text-2xl mb-4">
      Project status: <span class={project.status}>{project.status}</span>
    </h3>
    <div class="flex mb-4">
      {#if project.github !== null}
      <a href={project.github} target="_blank">
        <div class="w-10 h-10 hover:text-gray-400 mr-4">
            <FaGithub />
          </div>
        </a>
      {/if}
      {#if project.deploy !== null}
      <a href={project.deploy} target="_blank">
        <div class="w-10 h-10 hover:text-gray-400 mr-4">
            <GoLinkExternal />
          </div>
        </a>
      {/if}
    </div>
    {#if project.images !== null}
      <ul class="md:flex justify-between">
        {#each project.images as image}
          <li class="w-full m-auto mb-12 md:w-1/2 md:mb-0">
            <img class="w-full md:w-11/12" src="data/images/projects/{project.imagefolder}/{image}.jpg" alt={project.image}>
          </li>
        {/each}
      </ul>
    {/if}
  </div>
</li>

<style>
  .false {
    display: none;
  }
  .true {
    display: block;
  }
  .in.development {
    color: #ffa600;
  }
  .finished {
    color: #008000;
  }
</style>