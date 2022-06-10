<script>
  import Nav from "../lib/nav.svelte";
  import "../styles/global.css";
</script>

<header />
<main>
  <Nav />
  <slot />
</main>
<footer>
  <p>Copyright 2022 Mateus Ojeda</p>
</footer>

<style>
  header {
    display: flex;
    justify-content: center;
  }
  main {
    max-width: 960px;
    margin: 20px auto;
  }
  footer {
    text-align: center;
  }
</style>
