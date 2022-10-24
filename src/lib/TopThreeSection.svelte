<script lang="ts">
  type SingleNews = {
    title: string;
    body: string;
    image: string;
    link: string;
  };

  export let news: SingleNews[];
</script>

<section class="section container">
  <ul class="top-list">
    {#each news as singleNews, index}
      <li class="news-item">
        <img class="image" src={singleNews.image} alt={singleNews.title} />
        <div class="news-content">
          <span class="counter">{String(index).padStart(2, "0")}</span>
          <a href={singleNews.link} class="link">{singleNews.title}</a>
          <p>{singleNews.body}</p>
        </div>
      </li>
    {/each}
  </ul>
</section>

<style lang="scss">
  @use "../variables" as *;

  .top-list {
    display: flex;
    flex-direction: column;
    gap: 2.4rem;

    @media (min-width: $tablet) {
      flex-direction: row;
    }
  }

  .news-item {
    display: flex;
    flex: 1 1 100%;
  }

  .image {
    height: 100%;
    width: 10rem;
    object-fit: cover;
    margin-right: 2.4rem;
  }

  .news-content {
    display: inline-flex;
    flex-direction: column;
    justify-content: space-between;
  }

  .counter {
    font-size: 3.2rem;
    line-height: 1;
    font-weight: 700;
    color: var(--grayish-blue);
  }

  .link {
    font-size: 1.8rem;
    line-height: 2.4rem;
    font-weight: 800;
    color: var(--very-dark-blue);
    text-decoration: none;

    &:focus,
    &:hover {
      color: var(--soft-red);
    }
  }
</style>
