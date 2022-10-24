<script lang="ts">
  type SingleNews = {
    title: string;
    body: string;
  };

  export let news: SingleNews[];
</script>

<div class="new-card">
  <h2 class="header">New</h2>
  <ul>
    {#each news as item}
      <li class="news-item">
        <h3 class="news-header">{item.title}</h3>
        <p class="news-body">{item.body}</p>
      </li>
    {/each}
  </ul>
</div>

<style lang="scss">
  @use "../variables" as *;
  @use "sass:math";

  .new-card {
    padding: 2.4rem;
    background-color: var(--very-dark-blue);
  }

  .header {
    margin-bottom: 3.6rem;
    font-size: 3.2rem;
    line-height: 1;
    font-weight: 700;
    color: var(--soft-orange);

    @media (min-width: $tablet) {
      font-size: 4rem;
    }
  }

  .news-item {
    $spacing: math.div(6rem, 2);

    &:not(:first-child) {
      padding-top: $spacing;
    }

    &:not(:last-child) {
      padding-bottom: $spacing;
      border-bottom: 1px solid var(--dark-grayish-blue);
    }
  }

  .news-header {
    margin-bottom: 0.8rem;
    font-size: 2rem;
    line-height: 2.4rem;
    font-weight: 800;
    color: var(--off-white);
  }

  .news-body {
    color: var(--grayish-blue);
  }
</style>
