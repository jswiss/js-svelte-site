<script>
  import { onMount } from "svelte";

  onMount(() => {
    if (window.netlifyIdentity) {
      window.netlifyIdentity.on("init", user => {
        if (!user) {
          window.netlifyIdentity.on("login", () => {
            document.location.href = "/admin/";
          });
        }
      });
    }
  });
</script>

<style>
  p {
    text-align: center;
    margin: 0 auto;
  }

  p {
    margin: 1em auto;
  }
</style>

<svelte:head>
  <title>Joshua Swiss's Site</title>
  <script src="https://identity.netlify.com/v1/netlify-identity-widget.js">

  </script>
</svelte:head>

<main id="main">
  <p>
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Alias assumenda
    nulla quam fugiat ut natus, mollitia aliquam eum vel, atque facilis expedita
    rerum optio beatae at cumque repellat qui recusandae?
  </p>
</main>
