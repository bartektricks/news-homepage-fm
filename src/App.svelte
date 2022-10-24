<script lang="ts">
  import Navigation from "./lib/Navigation.svelte";
  import HeroSection from "./lib/HeroSection.svelte";
  import TopThreeSection from "./lib/TopThreeSection.svelte";
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
<main>
  <HeroSection
    image={{
      mobile: "/image-web-3-mobile.jpg",
      desktop: "/image-web-3-desktop.jpg",
    }}
    title="The Bright Future of Web 3.0?"
    body="We dive into the next evolution of the web that claims to put the power of the platforms back into the hands of the people. But is it really fulfilling its promise?"
    link="#web3"
    news={[
      {
        title: "Hydrogen VS Electric Cars",
        body: "Will hydrogen-fueled cars ever catch up to EVs?",
      },
      {
        title: "The Downsides of AI Artistry",
        body: "What are the possible adverse effects of on-demand AI image generation?",
      },
      {
        title: "Is VC Funding Drying Up?",
        body: "Private funding by VC firms is down 50% YOY. We take a look at what that means.",
      },
    ]}
  />
  <TopThreeSection
    news={[
      {
        title: "Reviving Retro PCs",
        body: "What happens when old PCs are given modern upgrades?",
        image: "/image-retro-pcs.jpg",
        link: "#",
      },
      {
        title: "Top 10 Laptops of 2022",
        body: "Our best picks for various needs and budgets.",
        image: "/image-top-laptops.jpg",
        link: "#",
      },
      {
        title: "The Growth of Gaming",
        body: "How the pandemic has sparked fresh opportunities.",
        image: "/image-gaming-growth.jpg",
        link: "#",
      },
    ]}
  />
</main>
