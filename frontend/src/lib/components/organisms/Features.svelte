<script lang="ts">
    import Card from "$lib/components/atoms/Card.svelte";
    import LandingPageSection from "$lib/components/molecules/LandingPageSection.svelte";

    /** @type {{ title: string, features: { title: string, description: string, icon?: string }[] }} */
    let { title, features } = $props();
</script>

<LandingPageSection {title}>
    <div class="features-grid">
        {#each features as feature}
            <Card class="feature-card">
                {#if feature.icon}
                    <div class="icon">{feature.icon}</div>
                {/if}
                <h3 class="feature-title">{feature.title}</h3>
                <p class="feature-desc">{feature.description}</p>
            </Card>
        {/each}
    </div>
</LandingPageSection>

<style>
    .features-grid {
        display: grid;
        grid-template-columns: 1fr;
        gap: var(--spacing-xl);
    }

    @media (min-width: 768px) {
        .features-grid {
            grid-template-columns: repeat(3, 1fr);
        }
    }

    :global(.feature-card) {
        text-align: left;
        transition: box-shadow 0.2s;
    }
    :global(.feature-card:hover) {
        box-shadow: var(--shadow-lg);
    }

    .icon {
        font-size: 2.25rem;
        margin-bottom: var(--spacing-md);
    }

    .feature-title {
        font-size: 1.25rem;
        font-weight: 600;
        margin-bottom: var(--spacing-sm);
    }

    .feature-desc {
        color: var(--color-text-light);
    }
</style>
