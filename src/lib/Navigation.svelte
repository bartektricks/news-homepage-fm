<script lang="ts">
  import Hamburger from "./Hamburger.svelte";
  import LogoSvg from "./Logo.svelte";

  type Link = {
    name: string;
    href: string;
  };

  export let links: Link[];

  let isMenuOpened = false;
  $: isOpenedClass = isMenuOpened ? "is-opened" : "";
</script>

<nav class={`navigation ${isOpenedClass} container`}>
  <a href="/"><LogoSvg /></a>
  <ul class={`nav-list ${isOpenedClass}`}>
    {#each links as link}
      <li>
        <a
          on:click={() => {
            isMenuOpened = false;
          }}
          class="list-link"
          href={link.href}>{link.name}</a
        >
      </li>
    {/each}
  </ul>
  <span class="hamburger-wrapper">
    <Hamburger
      isActive={isMenuOpened}
      on:click={() => {
        isMenuOpened = !isMenuOpened;
      }}
    />
  </span>
</nav>

<style lang="scss">
  @use "../variables" as *;

  .navigation {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding-top: 2.8rem;
    padding-bottom: 2.8rem;

    @media (min-width: $tablet) {
      align-items: flex-end;
      padding-top: 6rem;
      padding-bottom: 6rem;
    }

    &.is-opened {
      &::before {
        visibility: visible;
        opacity: 50%;

        @media (min-width: $tablet) {
          display: none;
        }
      }
    }

    &::before {
      position: fixed;
      content: "";
      inset: 0;
      background-color: var(--very-dark-blue);
      visibility: hidden;
      opacity: 0;
      transition: all 0.2s;
    }
  }

  .hamburger-wrapper {
    position: relative;
    z-index: 1;

    @media (min-width: $tablet) {
      display: none;
    }
  }

  .nav-list {
    position: fixed;
    display: flex;
    flex-direction: column;
    gap: 24px;
    padding: 20vh 2.4rem 0;
    inset: 0 0 0 32%;
    background-color: var(--off-white);
    visibility: hidden;
    opacity: 0;
    transform: translateX(100%);
    transition: all 0.2s;
    z-index: 1;

    &.is-opened {
      visibility: visible;
      opacity: 1;
      transform: translateX(0);
    }

    @media (min-width: $tablet) {
      position: static;
      flex-direction: row;
      gap: 40px;
      padding: 0;
      visibility: visible;
      opacity: 1;
      transform: initial;
    }
  }

  .list-link {
    font-size: 1.8rem;
    line-height: 2.4rem;
    color: var(--very-dark-blue);
    text-decoration: none;

    &:hover,
    &:focus {
      color: var(--soft-red);
    }

    @media (min-width: $tablet) {
      font-size: 1.5rem;
      line-height: 2.6rem;
      color: var(--dark-grayish-blue);
    }
  }
</style>
