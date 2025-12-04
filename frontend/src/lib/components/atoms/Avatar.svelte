<script lang="ts">
    /** @type {{ src?: string, alt?: string, size?: 'sm' | 'md' | 'lg', class?: string }} */
    let { src, alt = "Avatar", size = "md", class: className = "" } = $props();
</script>

<div class="avatar {size} {className}">
    {#if src}
        <img {src} {alt} class="image" />
    {:else}
        <div class="placeholder">
            <svg class="icon" fill="currentColor" viewBox="0 0 24 24">
                <path
                    d="M24 20.993V24H0v-2.996A14.977 14.977 0 0112.004 15c4.904 0 9.26 2.354 11.996 5.993zM16.002 8.999a4 4 0 11-8 0 4 4 0 018 0z"
                />
            </svg>
        </div>
    {/if}
</div>

<style>
    .avatar {
        border-radius: var(--radius-full);
        overflow: hidden;
        background-color: var(--color-secondary);
        display: inline-block;
    }

    .image {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

    .placeholder {
        width: 100%;
        height: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
        color: var(--color-text-light);
    }

    .icon {
        width: 50%;
        height: 50%;
    }

    /* Sizes */
    .sm {
        width: 2rem;
        height: 2rem;
    }
    .md {
        width: 3rem;
        height: 3rem;
    }
    .lg {
        width: 4rem;
        height: 4rem;
    }
</style>
