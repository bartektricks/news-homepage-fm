<script lang="ts">
  export let mobile: string;
  export let desktop: string;
  export let alt: string;
</script>

<picture>
  <source srcset={desktop} media="(min-width: 768px)" />
  <img class="image" src={mobile} {alt} />
</picture>

<style>
  .image {
    height: 100%;
    width: 100%;
    object-fit: cover;
  }
</style>
