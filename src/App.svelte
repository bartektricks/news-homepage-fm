<script lang="ts">
  import Navigation from "./lib/Navigation.svelte";

  import heroPostMobile from "./assets/image-web-3-mobile.jpg";
  import heroPostDesktop from "./assets/image-web-3-desktop.jpg";
  import HeroSection from "./lib/HeroSection.svelte";
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
      mobile: heroPostMobile,
      desktop: heroPostDesktop,
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
</main>
