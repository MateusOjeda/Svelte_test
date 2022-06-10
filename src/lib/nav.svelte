<script>
  import { page } from "$app/stores";
  import { onMount } from "svelte";

  let hovering = false;

  onMount(async () => {});

  let menuItems = [
    { route: "/", name: "Home" },
    { route: "/1on1", name: "1:1" },
    { route: "/feedback", name: "Feedback" },
    { route: "/map", name: "Mapa" },
    { route: "/pdi", name: "PDI" },
  ];
</script>

<div
  class="nav"
  on:mouseenter={() => (hovering = true)}
  on:mouseleave={() => (hovering = false)}
>
  <div class="vertical-menu {hovering ? '' : 'small'}">
    {#each menuItems as { route, name }}
      <a href={route} class={$page.url.pathname === route ? "active" : ""}>
        <img src="/controller.svg" alt="site logo" />
        {#if hovering}
          {name}
        {/if}
      </a>
    {/each}
  </div>
</div>

<style>
  .nav {
    position: fixed;
    left: 0;
    bottom: 0;
    width: var(--ytd-mini-guide-width);
    height: 100%;
    background-color: rgb(78, 0, 109);
  }
  .vertical-menu {
    width: 200px;
  }

  .small {
    width: 50px;
  }

  .vertical-menu a {
    background-color: #eee;
    color: black;
    display: flex;
    align-items: center;
    padding: 12px;
    text-decoration: none;
  }

  .vertical-menu a:hover {
    background-color: #ccc;
  }

  .vertical-menu a.active {
    background-color: #04aa6d;
    color: white;
  }

  .vertical-menu img {
    margin-right: 10px;
  }
</style>
