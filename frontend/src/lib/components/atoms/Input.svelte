<script lang="ts">
  /** @type {{ label?: string, id?: string, class?: string, [key: string]: any }} */
  let { label, id, class: className = "", ...rest } = $props();
</script>

<div class="input-group {className}">
  {#if label}
    <label for={id} class="label">{label}</label>
  {/if}
  <input {id} class="input" {...rest} />
</div>

<style>
  .input-group {
    display: flex;
    flex-direction: column;
    gap: var(--spacing-xs);
  }

  .label {
    font-size: 0.875rem;
    font-weight: 500;
    color: var(--color-text);
  }

  .input {
    padding: var(--spacing-sm) var(--spacing-md);
    border: 1px solid var(--color-border);
    border-radius: var(--radius-md);
    font-size: 1rem;
    transition:
      border-color 0.2s,
      box-shadow 0.2s;
    width: 100%;
  }

  .input:focus {
    outline: none;
    border-color: var(--color-primary);
    box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.1); /* Primary color with opacity */
  }
</style>
