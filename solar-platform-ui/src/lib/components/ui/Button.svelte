<script lang="ts">
    let { variant = 'primary', href, onclick, children } = $props();
</script>

{#if href}
    <a {href} class="btn btn-{variant}">{@render children()}</a>
{:else}
    <button {onclick} class="btn btn-{variant}">{@render children()}</button>      
{/if}

<style>
    .btn {
      padding: 1rem 2rem;
      border-radius: 60px;
      font-size: 1rem;
      text-transform: uppercase;
      letter-spacing: 0.1rem;
      transition: all 0.4s ease-in-out;
      cursor: pointer;
      border: 1px solid transparent;
      display: inline-block;
    }
    .btn-primary {
      background: var(--color-primary);
      color: #fff;
      border-color: var(--color-primary);
    }
    .btn-primary:hover {
      background: var(--color-primary-hover);
      border-color: var(--color-primary-hover);
    }
    .btn-outline {
      background: transparent;
      color: var(--color-primary);
      border-color: var(--color-primary);
    }
    .btn-outline:hover {
      background: var(--color-primary);
      color: #fff;
    }
</style>