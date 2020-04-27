<script context="module">
  export function preload({ params, query }) {
    return this.fetch(`blog.json`)
      .then(r => r.json())
      .then(posts => {
        return { posts };
      });
  }
</script>

<script>
  export let posts;
  export function dateConverter(postDate) {
    const convertedPostDate = new Date(postDate);
    const dateOptions = {
      weekday: "long",
      year: "numeric",
      month: "long",
      day: "numeric"
    };
    return convertedPostDate.toLocaleString("en-UK", dateOptions);
  }
</script>

<style>
  ul {
    margin: 0 0 1em 0;
    line-height: 1.5;
    list-style-type: none;
  }
  li {
    margin-top: 1rem;
  }

  a {
    text-decoration: none;
  }

  a:hover {
    text-decoration: underline;
  }

  .post-title {
    font-style: bold;
    font-size: 1.2rem;
  }
  .post-date {
    font-size: 1rem;
  }
  .blog-separator {
    display: block;
    height: 1px;
    border: 0;
    border-top: 1px solid whitesmoke;
    margin: 0.3em 0;
    padding: 0;
  }
</style>

<svelte:head>
  <title>Blog</title>
</svelte:head>

<ul>
  {#each posts as post}
    <!-- we're using the non-standard `rel=prefetch` attribute to
				tell Sapper to load the data for the page as soon as
				the user hovers over the link or taps it, instead of
				waiting for the 'click' event -->
    <li>
      <a rel="prefetch" href="blog/{post.slug}">
        <span class="post-title">{post.title} -</span>
        <span class="post-date">{dateConverter(post.date)}</span>
      </a>
      <hr class="blog-separator" />
    </li>
  {/each}
</ul>
