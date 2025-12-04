<script lang="ts">
    import Button from "$lib/components/atoms/Button.svelte";
    import Input from "$lib/components/atoms/Input.svelte";
    import Card from "$lib/components/atoms/Card.svelte";
    import Avatar from "$lib/components/atoms/Avatar.svelte";
    import UserSection from "$lib/components/molecules/UserSection.svelte";
    import SuggestionBox from "$lib/components/molecules/SuggestionBox.svelte";
    import Hero from "$lib/components/organisms/Hero.svelte";
    import Features from "$lib/components/organisms/Features.svelte";
    import Pricing from "$lib/components/organisms/Pricing.svelte";
</script>

<div class="design-system">
    <h1 class="page-title">Design System</h1>
    <p class="page-desc">Catálogo de componentes del sistema.</p>

    <section>
        <h2>Atoms</h2>

        <div class="component-block">
            <h3>Buttons</h3>
            <div class="row">
                <Button variant="primary">Primary</Button>
                <Button variant="secondary">Secondary</Button>
                <Button variant="ghost">Ghost</Button>
            </div>
            <div class="row">
                <Button size="sm">Small</Button>
                <Button size="md">Medium</Button>
                <Button size="lg">Large</Button>
            </div>
        </div>

        <div class="component-block">
            <h3>Inputs</h3>
            <div class="row">
                <Input label="Username" placeholder="Enter username" />
                <Input
                    label="Password"
                    type="password"
                    placeholder="Enter password"
                />
            </div>
        </div>

        <div class="component-block">
            <h3>Avatars</h3>
            <div class="row">
                <Avatar size="sm" />
                <Avatar size="md" />
                <Avatar size="lg" />
                <Avatar
                    src="https://api.dicebear.com/7.x/avataaars/svg?seed=Felix"
                />
            </div>
        </div>

        <div class="component-block">
            <h3>Cards</h3>
            <Card>
                <p>This is a basic card component.</p>
            </Card>
        </div>
    </section>

    <section>
        <h2>Molecules</h2>

        <div class="component-block">
            <h3>User Section</h3>
            <div class="col">
                <UserSection />
                <UserSection
                    user={{
                        name: "John Doe",
                        email: "john@example.com",
                        avatar: "https://api.dicebear.com/7.x/avataaars/svg?seed=John",
                    }}
                />
            </div>
        </div>

        <div class="component-block">
            <h3>Suggestion Box</h3>
            <SuggestionBox />
        </div>
    </section>

    <section>
        <h2>Organisms</h2>

        <div class="component-block">
            <h3>Hero</h3>
            <Hero
                title="Hero Title"
                subtitle="This is a subtitle for the hero section."
                ctaText="Call to Action"
                onCtaClick={() => {}}
            />
        </div>

        <div class="component-block">
            <h3>Features</h3>
            <Features
                title="Features Section"
                features={[
                    {
                        title: "Feature 1",
                        description: "Description 1",
                        icon: "★",
                    },
                    {
                        title: "Feature 2",
                        description: "Description 2",
                        icon: "★",
                    },
                    {
                        title: "Feature 3",
                        description: "Description 3",
                        icon: "★",
                    },
                ]}
            />
        </div>

        <div class="component-block">
            <h3>Pricing</h3>
            <Pricing
                title="Pricing Section"
                plans={[
                    {
                        name: "Basic",
                        price: "$10",
                        features: ["Feature A", "Feature B"],
                    },
                    {
                        name: "Pro",
                        price: "$20",
                        features: ["Feature A", "Feature B", "Feature C"],
                        recommended: true,
                    },
                ]}
            />
        </div>
    </section>
</div>

<style>
    .design-system {
        padding-bottom: var(--spacing-2xl);
    }

    .page-title {
        font-size: 2.5rem;
        color: var(--color-primary);
        margin-bottom: var(--spacing-sm);
    }

    .page-desc {
        font-size: 1.25rem;
        color: var(--color-text-light);
        margin-bottom: var(--spacing-2xl);
    }

    section {
        margin-bottom: var(--spacing-2xl);
        border-top: 1px solid var(--color-border);
        padding-top: var(--spacing-xl);
    }

    h2 {
        font-size: 2rem;
        margin-bottom: var(--spacing-xl);
    }

    .component-block {
        margin-bottom: var(--spacing-xl);
    }

    h3 {
        font-size: 1.25rem;
        color: var(--color-text-light);
        margin-bottom: var(--spacing-md);
        border-bottom: 1px solid var(--color-border);
        padding-bottom: var(--spacing-sm);
        display: inline-block;
    }

    .row {
        display: flex;
        gap: var(--spacing-md);
        margin-bottom: var(--spacing-lg);
        align-items: center;
        flex-wrap: wrap;
    }

    .col {
        display: flex;
        flex-direction: column;
        gap: var(--spacing-md);
        margin-bottom: var(--spacing-lg);
        max-width: 24rem;
    }
</style>
