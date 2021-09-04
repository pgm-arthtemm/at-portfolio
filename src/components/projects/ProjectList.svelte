<script>
  import { onMount } from "svelte";
  import Project from "./Project.svelte";
  
  let data = [];
  const projectsLink = 'data/projects.json';

  onMount(async () => {
    const response = await fetch(projectsLink);
    data = await response.json();
  });
</script>

<div class="m-auto w-11/12 md:container pt-10">
  {#if data !== null}
    <ul>
      {#each data as project}
        <Project {project} />
      {/each}
    </ul>
  {:else}
    <p>No data found.</p>
  {/if}
</div>