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
  import BlogCard from "../../components/BlogCard.svelte";
  export let posts;
</script>

<style>
  section {
    display: flex;
    flex-direction: column;
    margin: 0 0 1em 0;
    line-height: 1.5;
    list-style-type: none;
  }
</style>

<svelte:head>
  <title>Blog</title>
</svelte:head>

<section>
  {#each posts as post}
    <!-- we're using the non-standard `rel=prefetch` attribute to
				tell Sapper to load the data for the page as soon as
				the user hovers over the link or taps it, instead of
				waiting for the 'click' event -->
    <BlogCard title={post.title} postDate={post.date} slug={post.slug} />
  {/each}
</section>
