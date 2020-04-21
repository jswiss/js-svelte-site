<script>
  import Nav from "../components/Nav.svelte";
  import Footer from "../components/Footer.svelte";
  import Flex from "../components/Flex.svelte";

  export let segment;
</script>

<style>
  h1 {
    text-align: center;
    font-size: 4rem;
    font-weight: 600;
  }
</style>

<Nav {segment} />

<main>
  <h1>Joshua Swiss</h1>
  <slot />
</main>

<Footer {segment} />
