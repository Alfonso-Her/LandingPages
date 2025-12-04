<script lang="ts">
  /**
   * @typedef {'primary' | 'secondary' | 'ghost'} Variant
   * @typedef {'sm' | 'md' | 'lg'} Size
   */

  /** @type {{ variant?: Variant, size?: Size, class?: string, children?: import('svelte').Snippet, [key: string]: any }} */
  let {
    variant = "primary",
    size = "md",
    class: className = "",
    children,
    ...rest
  } = $props();
</script>

<button class="btn {variant} {size} {className}" {...rest}>
  {@render children?.()}
</button>

<style>
  .btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    border: 1px solid transparent;
    border-radius: var(--radius-md);
    font-weight: 500;
    cursor: pointer;
    transition:
      background-color 0.2s,
      color 0.2s,
      box-shadow 0.2s;
    font-family: var(--font-sans);
  }

  .btn:focus {
    outline: none;
    box-shadow:
      0 0 0 2px var(--color-bg),
      0 0 0 4px var(--color-primary);
  }

  /* Variants */
  .primary {
    background-color: var(--color-primary);
    color: var(--color-white);
  }
  .primary:hover {
    background-color: var(--color-primary-hover);
  }

  .secondary {
    background-color: var(--color-secondary);
    color: var(--color-text);
  }
  .secondary:hover {
    background-color: var(--color-secondary-hover);
  }

  .ghost {
    background-color: transparent;
    color: var(--color-text);
  }
  .ghost:hover {
    background-color: var(--color-secondary);
  }

  /* Sizes */
  .sm {
    padding: var(--spacing-xs) var(--spacing-sm);
    font-size: 0.875rem;
  }
  .md {
    padding: var(--spacing-sm) var(--spacing-md);
    font-size: 1rem;
  }
  .lg {
    padding: var(--spacing-md) var(--spacing-lg);
    font-size: 1.125rem;
  }
</style>
