<script>
  export let title;
  export let slug;
  export let postDate;

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
  a {
    text-decoration: none;
  }

  a:hover {
    text-decoration: underline;
  }
  .blog-card {
    display: flex;
    flex-direction: column;
    margin: 0.5rem;
    border: 1px solid #7e30a8;
    border-radius: 1%;
  }
  .title {
    margin: 0.5rem;
    font-size: 2rem;
  }
  .card-footer {
    background-color: #7e30a8;
  }
  .post-date {
    margin: 0.5rem;
    font-size: 1rem;
    font-style: italic;
    color: whitesmoke;
  }
</style>

<div class="blog-card">
  <div class="title">
    <a href="blog/{slug}" rel="prefetch">{title}</a>
  </div>
  <div class="card-footer">
    <p class="post-date">Published: {dateConverter(postDate)}</p>
  </div>
</div>
