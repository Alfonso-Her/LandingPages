<script lang="ts">
  /** @type {{ class?: string, children?: import('svelte').Snippet }} */
  let { class: className = "", children } = $props();
</script>

<div class="card {className}">
  {@render children?.()}
</div>

<style>
  .card {
    background-color: var(--color-white);
    border-radius: var(--radius-lg);
    box-shadow: var(--shadow-md);
    padding: var(--spacing-lg);
  }
</style>
