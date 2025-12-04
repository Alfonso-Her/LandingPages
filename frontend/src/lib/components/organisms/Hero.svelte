<script lang="ts">
    import Button from "$lib/components/atoms/Button.svelte";
    import LandingPageSection from "$lib/components/molecules/LandingPageSection.svelte";

    /** @type {{ title: string, subtitle: string, ctaText: string, onCtaClick: () => void }} */
    let { title, subtitle, ctaText, onCtaClick } = $props();
</script>

<LandingPageSection {title} description={subtitle} class="hero-section">
    <div class="cta-container">
        <Button size="lg" onclick={onCtaClick}>{ctaText}</Button>
    </div>
</LandingPageSection>

<style>
    :global(.hero-section) {
        background-color: #eff6ff; /* blue-50 */
    }

    .cta-container {
        margin-top: var(--spacing-xl);
        display: flex;
        justify-content: center;
    }
</style>
