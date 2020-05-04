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
    /* font-weight: 600; */
    font-family: "Gilroy";
  }

  main {
    display: grid;
    grid-template-rows: auto 1fr;
    width: 80%;
  }

  #main-border {
    /* border-radius: 3%;
    box-shadow: 20px 20px 60px #143a62, -20px -20px 60px #35679d;
    background-color: #d1dbe5; */
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
