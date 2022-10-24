<script lang="ts">
  export let href: string;
</script>

<a class="button" {href}><slot /></a>

<style lang="scss">
  @use "../_variables" as *;

  .button {
    display: inline-block;
    padding: 1.2rem 3rem;
    background-color: var(--soft-red);
    border: 0;
    font-size: 1.4rem;
    line-height: 2.4rem;
    font-weight: 700;
    letter-spacing: 4px;
    color: var(--off-white);
    text-decoration: none;
    text-transform: uppercase;

    &:hover,
    &:focus {
      background-color: var(--very-dark-blue);
    }
  }
</style>
