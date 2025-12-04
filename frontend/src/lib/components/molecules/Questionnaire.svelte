<script lang="ts">
    import Button from "$lib/components/atoms/Button.svelte";
    import Card from "$lib/components/atoms/Card.svelte";

    /**
     * @typedef {{ id: string, text: string, options: { label: string, nextId: string }[] }} Question
     */

    /** @type {{ questions: Question[], initialQuestionId: string, onComplete: (answers: any) => void }} */
    let { questions, initialQuestionId, onComplete } = $props();

    let currentQuestionId = $state(initialQuestionId);
    let answers = $state({});

    let currentQuestion = $derived(
        questions.find((q) => q.id === currentQuestionId),
    );

    function handleOptionClick(option) {
        answers[currentQuestionId] = option.label;
        if (option.nextId === "DONE") {
            onComplete(answers);
        } else {
            currentQuestionId = option.nextId;
        }
    }
</script>

<Card class="questionnaire-card">
    {#if currentQuestion}
        <h3 class="question-text">{currentQuestion.text}</h3>
        <div class="options-list">
            {#each currentQuestion.options as option}
                <Button
                    variant="secondary"
                    onclick={() => handleOptionClick(option)}
                    class="option-btn"
                >
                    {option.label}
                </Button>
            {/each}
        </div>
    {:else}
        <p class="error">Error: Question not found.</p>
    {/if}
</Card>

<style>
    .questionnaire-card {
        max-width: 32rem; /* max-w-lg */
        margin-left: auto;
        margin-right: auto;
    }

    .question-text {
        font-size: 1.25rem;
        font-weight: 600;
        margin-bottom: var(--spacing-xl);
    }

    .options-list {
        display: flex;
        flex-direction: column;
        gap: var(--spacing-md);
    }

    /* Deep selector to target the button component's internal class if needed, 
     but passing class="option-btn" appends it to the button element */
    :global(.option-btn) {
        width: 100%;
        justify-content: flex-start;
        text-align: left;
    }

    .error {
        color: var(--color-danger);
    }
</style>
