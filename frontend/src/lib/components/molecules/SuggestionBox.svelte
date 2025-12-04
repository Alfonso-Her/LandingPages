<script lang="ts">
    import Button from "$lib/components/atoms/Button.svelte";
    import Card from "$lib/components/atoms/Card.svelte";
    import Input from "$lib/components/atoms/Input.svelte";

    let suggestion = $state("");
    let submitted = $state(false);

    function handleSubmit(e) {
        e.preventDefault();
        if (suggestion.trim()) {
            console.log("Suggestion submitted:", suggestion);
            // Here you would send the suggestion to the backend
            submitted = true;
            suggestion = "";
            setTimeout(() => (submitted = false), 3000);
        }
    }
</script>

<Card class="suggestion-card">
    <h3 class="title">¿Te falta algún componente?</h3>
    <p class="subtitle">
        Ayúdanos a mejorar sugiriendo nuevas ideas o componentes.
    </p>

    {#if submitted}
        <div class="success-message">¡Gracias por tu sugerencia!</div>
    {:else}
        <form onsubmit={handleSubmit} class="form">
            <textarea
                bind:value={suggestion}
                placeholder="Describe tu idea..."
                class="textarea"
                rows="3"
            ></textarea>
            <Button variant="primary" type="submit" class="submit-btn">
                Enviar Sugerencia
            </Button>
        </form>
    {/if}
</Card>

<style>
    .suggestion-card {
        max-width: 28rem; /* max-w-md */
        margin-left: auto;
        margin-right: auto;
        background-color: #fffbeb; /* yellow-50 */
        border: 1px solid #fde68a; /* yellow-200 */
    }

    .title {
        font-size: 1.125rem;
        font-weight: 600;
        color: #92400e; /* yellow-800 */
        margin-bottom: var(--spacing-sm);
    }

    .subtitle {
        font-size: 0.875rem;
        color: #b45309; /* yellow-700 */
        margin-bottom: var(--spacing-md);
    }

    .success-message {
        color: var(--color-success);
        font-weight: 500;
        text-align: center;
        padding: var(--spacing-sm) 0;
    }

    .form {
        display: flex;
        flex-direction: column;
        gap: var(--spacing-md);
    }

    .textarea {
        width: 100%;
        padding: var(--spacing-sm) var(--spacing-md);
        border: 1px solid #fcd34d; /* yellow-300 */
        border-radius: var(--radius-md);
        background-color: var(--color-white);
        font-family: var(--font-sans);
    }

    .textarea:focus {
        outline: none;
        box-shadow: 0 0 0 2px #f59e0b; /* yellow-500 */
    }

    :global(.submit-btn) {
        background-color: #d97706; /* yellow-600 */
    }
    :global(.submit-btn:hover) {
        background-color: #b45309; /* yellow-700 */
    }
</style>
