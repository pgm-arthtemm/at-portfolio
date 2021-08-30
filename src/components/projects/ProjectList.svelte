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

<div class="projects">
  {#if data !== null}
    <ul class="project--list">
      {#each data as project}
        <Project {project} />
      {/each}
    </ul>
  {:else}
    <p>No data found.</p>
  {/if}
</div>