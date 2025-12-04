<script lang="ts">
    import Button from "$lib/components/atoms/Button.svelte";
    import Card from "$lib/components/atoms/Card.svelte";
    import LandingPageSection from "$lib/components/molecules/LandingPageSection.svelte";

    /** @type {{ title: string, plans: { name: string, price: string, features: string[], recommended?: boolean }[] }} */
    let { title, plans } = $props();
</script>

<LandingPageSection {title}>
    <div class="pricing-grid">
        {#each plans as plan}
            <Card class="pricing-card {plan.recommended ? 'recommended' : ''}">
                {#if plan.recommended}
                    <div class="badge">Recomendado</div>
                {/if}
                <h3 class="plan-name">{plan.name}</h3>
                <div class="plan-price">{plan.price}</div>
                <ul class="features-list">
                    {#each plan.features as feature}
                        <li class="feature-item">
                            <svg
                                class="check-icon"
                                fill="none"
                                stroke="currentColor"
                                viewBox="0 0 24 24"
                            >
                                <path
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="2"
                                    d="M5 13l4 4L19 7"
                                ></path>
                            </svg>
                            {feature}
                        </li>
                    {/each}
                </ul>
                <Button
                    variant={plan.recommended ? "primary" : "secondary"}
                    class="select-btn">Elegir Plan</Button
                >
            </Card>
        {/each}
    </div>
</LandingPageSection>

<style>
    .pricing-grid {
        display: grid;
        grid-template-columns: 1fr;
        gap: var(--spacing-xl);
    }

    @media (min-width: 768px) {
        .pricing-grid {
            grid-template-columns: repeat(3, 1fr);
        }
    }

    :global(.pricing-card) {
        position: relative;
        display: flex;
        flex-direction: column;
    }

    :global(.pricing-card.recommended) {
        border: 2px solid var(--color-primary);
        transform: scale(1.05);
        z-index: 1;
    }

    .badge {
        position: absolute;
        top: 0;
        right: 0;
        background-color: var(--color-primary);
        color: var(--color-white);
        font-size: 0.75rem;
        font-weight: 700;
        padding: 0.25rem 0.5rem;
        border-bottom-left-radius: var(--radius-lg);
        border-top-right-radius: var(--radius-lg);
    }

    .plan-name {
        font-size: 1.5rem;
        font-weight: 700;
        margin-bottom: var(--spacing-sm);
    }

    .plan-price {
        font-size: 2.25rem;
        font-weight: 700;
        color: var(--color-primary);
        margin-bottom: var(--spacing-lg);
    }

    .features-list {
        list-style: none;
        padding: 0;
        margin: 0 0 var(--spacing-xl) 0;
        flex: 1;
        text-align: left;
    }

    .feature-item {
        display: flex;
        align-items: center;
        color: var(--color-text-light);
        margin-bottom: var(--spacing-sm);
    }

    .check-icon {
        width: 1.25rem;
        height: 1.25rem;
        color: var(--color-success);
        margin-right: var(--spacing-sm);
    }

    :global(.select-btn) {
        width: 100%;
    }
</style>
