<script lang="ts">
    import Questionnaire from "$lib/components/molecules/Questionnaire.svelte";
    import Hero from "$lib/components/organisms/Hero.svelte";
    import Features from "$lib/components/organisms/Features.svelte";
    import Pricing from "$lib/components/organisms/Pricing.svelte";
    import SuggestionBox from "$lib/components/molecules/SuggestionBox.svelte";

    let showLandingPage = $state(false);

    // Sample data simulating "I Love PDF" validation
    let landingPageData = $state({
        title: "Herramientas PDF Online",
        subtitle: "Une, divide, comprime y convierte PDF totalmente gratis.",
        cta: "Probar Ahora",
        features: [],
        pricing: [],
    });

    const questions = [
        {
            id: "q1",
            text: "¿Qué herramienta PDF necesitas validar?",
            options: [
                { label: "Unir PDF", nextId: "q2_merge" },
                { label: "Dividir PDF", nextId: "q2_split" },
                { label: "Comprimir PDF", nextId: "q2_compress" },
            ],
        },
        {
            id: "q2_merge",
            text: "¿Cuál es el principal beneficio de Unir PDF?",
            options: [
                { label: "Organización de documentos", nextId: "DONE" },
                { label: "Envío de archivos únicos", nextId: "DONE" },
                { label: "Gestión de reportes", nextId: "DONE" },
            ],
        },
        {
            id: "q2_split",
            text: "¿Para qué usarías Dividir PDF?",
            options: [
                { label: "Extraer páginas", nextId: "DONE" },
                { label: "Separar capítulos", nextId: "DONE" },
                { label: "Reducir tamaño", nextId: "DONE" },
            ],
        },
        {
            id: "q2_compress",
            text: "¿Qué buscas al comprimir?",
            options: [
                { label: "Enviar por correo", nextId: "DONE" },
                { label: "Ahorrar espacio", nextId: "DONE" },
                { label: "Carga web rápida", nextId: "DONE" },
            ],
        },
    ];

    function handleComplete(answers) {
        console.log("Answers:", answers);
        // In a real app, we would customize the data based on answers.
        // For now, we show the "I Love PDF" style landing page.
        showLandingPage = true;
    }
</script>

{#if !showLandingPage}
    <div class="questionnaire-container">
        <h1 class="main-title">Validador de Ideas SaaS</h1>
        <p class="subtitle-text">
            Responde para generar tu landing page de prueba.
        </p>
        <Questionnaire
            {questions}
            initialQuestionId="q1"
            onComplete={handleComplete}
        />
    </div>
{:else}
    <div class="landing-page">
        <Hero
            title={landingPageData.title}
            subtitle={landingPageData.subtitle}
            ctaText={landingPageData.cta}
            onCtaClick={() => alert("Funcionalidad en desarrollo")}
        />

        <Features
            title="Todo lo que necesitas para tus PDF"
            features={[
                {
                    title: "Unir PDF",
                    description: "Une PDFs y ponlos en el orden que prefieras.",
                    icon: "🔗",
                },
                {
                    title: "Dividir PDF",
                    description: "Extrae páginas o separa documentos.",
                    icon: "✂️",
                },
                {
                    title: "Comprimir PDF",
                    description: "Consigue la menor cantidad de peso posible.",
                    icon: "📉",
                },
            ]}
        />

        <Pricing
            title="Planes Flexibles"
            plans={[
                {
                    name: "Gratis",
                    price: "$0",
                    features: [
                        "Todas las herramientas",
                        "Límites básicos",
                        "Con anuncios",
                    ],
                },
                {
                    name: "Premium",
                    price: "$6/mes",
                    features: [
                        "Sin límites",
                        "Sin anuncios",
                        "Soporte prioritario",
                        "Escritorio y Móvil",
                    ],
                    recommended: true,
                },
                {
                    name: "Business",
                    price: "Contactar",
                    features: ["API Access", "SSO", "Contratos personalizados"],
                },
            ]}
        />

        <div class="suggestion-container">
            <SuggestionBox />
        </div>
    </div>
{/if}

<style>
    .questionnaire-container {
        max-width: 42rem;
        margin: 0 auto;
        padding: var(--spacing-2xl) 0;
        text-align: center;
    }

    .main-title {
        font-size: 2.5rem;
        font-weight: 700;
        color: var(--color-primary);
        margin-bottom: var(--spacing-sm);
    }

    .subtitle-text {
        font-size: 1.25rem;
        color: var(--color-text-light);
        margin-bottom: var(--spacing-xl);
    }

    .landing-page {
        display: flex;
        flex-direction: column;
        gap: var(--spacing-2xl);
    }

    .suggestion-container {
        padding: var(--spacing-2xl) var(--spacing-md);
    }
</style>
