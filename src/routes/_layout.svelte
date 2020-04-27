<script>
  import Nav from "../components/Nav.svelte";
  import Footer from "../components/Footer.svelte";

  export let segment;
</script>

<style>
  h1 {
    text-align: center;
    font-size: 4rem;
    font-weight: 600;
  }
  #main-border {
    border-radius: 50px;
    box-shadow: 20px 20px 60px #17416d, -20px -20px 60px #1f5793;
    min-width: 50rem;
    min-height: 60%;
    display: flex;
    justify-content: center;
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
