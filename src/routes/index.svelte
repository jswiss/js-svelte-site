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
  section {
    margin-bottom: 1rem;
  }

  p {
    margin: 1em auto;
    font-size: 1.3em;
  }

  .italic {
    font-style: italic;
  }
</style>

<svelte:head>
  <title>Joshua Swiss's Site</title>
  <script src="https://identity.netlify.com/v1/netlify-identity-widget.js">

  </script>
</svelte:head>

<main id="main">
  <section>
    <p>
      Hey there! I'm Josh, a software engineer based in Glasgow. This is my site
      to showcase my professional skillz &trade; and blather about whatever I
      find interesting, whether that be code or anything else.
    </p>
  </section>
  <section>
    <p>
      I came into this profession in a bit of an abnormal way; not many devs
      start off as carpenters, get a policy degree and become a management
      consultant, then move abroad and work in the humanitarian aid and
      development sector across sub-Saharan Africa, only to
      <span class="italic">then</span>
      decide learning to write code seemed interesting. Five years later and I'm
      still at it!
    </p>
  </section>
  <section>
    <p>
      If you want to learn more about my work and expertise, please check out
      the
      <a href="about">About</a>
      page. If you want to read about whatever; JavaScript, Rust, fermentation,
      running, life, etc., please check out my
      <a href="blog">Blog</a>
      .
    </p>
  </section>
</main>
