<script>
  export let project;
  let showInfo = false
</script>

<li class="project">
  <div class="project--heading">
    <h2 on:click={() => (showInfo = !showInfo)}>{project.name}</h2>
    <h3>Project for {project.for}, course {project.course}</h3>
  </div>
  <div class="show {showInfo}">
    <p>{project.synopsis}</p>
    <h3>Technologies used:</h3>
    <ul class="project--list">
      {#each project.tech as tech}
        <li>{tech}</li>
      {/each}
    </ul>
    <h3 class="status">
      Project status: <span class={project.status}>{project.status}</span>
    </h3>
    <div class="links">
      {#if project.github !== null}
        <div class="icon">
          <a href={project.github} target="_blank">
            <h5>ICON</h5>
          </a>
        </div>
      {/if}
      {#if project.deploy !== null}
        <div class="icon">
          <a href={project.deploy}>
            <h5>ICON</h5>
          </a>
        </div>
      {/if}
    </div>
    {#if project.images !== null}
      <ul class="image--list">
        {#each project.images as image}
          <li>
            <img src="" alt={project.image}>
          </li>
        {/each}
      </ul>
    {/if}
  </div>
</li>