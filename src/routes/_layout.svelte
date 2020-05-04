<script>
  import Nav from "../components/Nav.svelte";
  import Footer from "../components/Footer.svelte";

  export let segment;
</script>

<style>
  @font-face {
    font-family: "Swansea";
    src: url("/fonts/Swansea-q3pd.ttf");
  }
  @font-face {
    font-family: "Gilroy";
    src: url("/fonts/gilroy-extrabold.otf");
  }
  h1 {
    display: inline;
    text-align: center;
    font-size: 4rem;
    font-family: "Gilroy";
  }

  main {
    display: grid;
    grid-template-rows: auto 1fr;
  }

  #main-border {
    color: whitesmoke;
    font-family: "Swansea";
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
