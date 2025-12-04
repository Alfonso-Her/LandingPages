<script lang="ts">
    /** @type {{ title: string, description?: string, class?: string, children?: import('svelte').Snippet }} */
    let { title, description, class: className = "", children } = $props();
</script>

<section class="section {className}">
    <div class="container">
        <div class="header">
            <h2 class="title">{title}</h2>
            {#if description}
                <p class="description">{description}</p>
            {/if}
        </div>
        {@render children?.()}
    </div>
</section>

<style>
    .section {
        padding-top: var(--spacing-2xl);
        padding-bottom: var(--spacing-2xl);
    }

    .container {
        width: 100%;
        max-width: 1200px;
        margin-left: auto;
        margin-right: auto;
        padding-left: var(--spacing-md);
        padding-right: var(--spacing-md);
    }

    .header {
        max-width: 48rem; /* max-w-3xl */
        margin-left: auto;
        margin-right: auto;
        text-align: center;
        margin-bottom: var(--spacing-2xl);
    }

    .title {
        font-size: 2.25rem; /* 3xl/4xl */
        font-weight: 700;
        color: var(--color-text);
        margin-bottom: var(--spacing-md);
    }

    .description {
        font-size: 1.25rem; /* xl */
        color: var(--color-text-light);
    }
</style>
