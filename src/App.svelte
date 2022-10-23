<script lang="ts">
  import Counter from "./lib/Counter.svelte";
  import Navigation from "./lib/Navigation.svelte";
</script>

<Navigation
  links={[
    { name: "Home", href: "/" },
    { name: "New", href: "#new" },
    { name: "Popular", href: "#popular" },
    { name: "Trending", href: "#trending" },
    { name: "Categories", href: "#categories" },
  ]}
/>
<main><Counter /></main>
