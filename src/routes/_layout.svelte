<script>
  import Nav from "../components/Nav.svelte";
  import Footer from "../components/Footer.svelte";

  export let segment;
</script>

<style>
  h1 {
    display: inline;
    text-align: center;
    font-size: 4rem;
    font-weight: 600;
  }

  main {
    display: grid;
    grid-template-rows: auto 1fr;
    width: 80%;
  }

  #main-border {
    border-radius: 3%;
    box-shadow: 20px 20px 60px #143a62, -20px -20px 60px #35679d;
    background-color: #d1dbe5;
    color: #17416d;
  }
</style>

<Nav {segment} />

<main>
  <h1>Joshua Swiss</h1>
  <div id="main-border">
    <slot />
  </div>
</main>

<Footer />
