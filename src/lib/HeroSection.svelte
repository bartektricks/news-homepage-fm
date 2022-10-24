<script lang="ts">
  import NewCard from "./NewCard.svelte";
  import Button from "./Button.svelte";
  import type { ComponentProps } from "svelte";

  export let title: string;
  export let body: string;
  export let link: string;
  export let image: {
    mobile: string;
    desktop: string;
  };
  export let news: ComponentProps<NewCard>["news"];
</script>

<section class="hero container">
  <picture>
    <source srcset={image.desktop} media="(min-width: 768px)" />
    <img class="image" src={image.mobile} alt={title} />
  </picture>
  <h1 class="title">{title}</h1>
  <div class="wrapper-item">
    <p class="body">{body}</p>
    <Button href={link}>Read more</Button>
  </div>
  <div class="news">
    <NewCard {news} />
  </div>
</section>

<style lang="scss">
  @use "../variables" as *;

  .hero {
    margin-bottom: 3.2rem;

    @media (min-width: $tablet) {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      grid-template-rows: 30rem 1fr;
      gap: 3rem;
    }
  }

  .image {
    height: 30rem;
    width: 100%;
    object-fit: cover;
    margin-bottom: 2.4rem;
  }

  picture {
    grid-column: 1 / span 2;
  }

  .news {
    display: flex;
    grid-row: 1 / span 2;
    grid-column: 3 / span 1;
  }

  .title {
    margin-bottom: 1.6rem;
    font-size: 4rem;
    line-height: 1;
    font-weight: 800;

    @media (min-width: $tablet) {
      margin-bottom: 0;
      font-size: 5.6rem;
    }
  }

  .wrapper-item {
    margin-bottom: 6.4rem;

    @media (min-width: $tablet) {
      margin-bottom: 0;
    }
  }

  .body {
    margin-bottom: 2.4rem;

    @media (min-width: $tablet) {
      margin-bottom: 3rem;
    }
  }
</style>
