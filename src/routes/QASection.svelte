<script>
    let expandedQuestion = null;

    const questions = [
        {
            id: 1,
            question: "Who is this website for?",
            answer: "This website is for anyone who is interested in GenAI evaluation. For people interested in a more detailed guide, please refer to the Measuring What Matters repository (link coming soon).",
        },
        {
            id: 2,
            question: "How do I use the pitfall checker?",
            answer: "The pitfall checker is a tool that helps you check if a paper could have potential evaluation pitfalls. However, it is not perfect and lacks the nuance and context of a human evaluator.",
        },
        // {
        //     id: 3,
        //     question: "Why was this website created?",
        //     answer: "This website is built using Svelte for the frontend framework, Bulma for CSS styling, and includes responsive design principles with bright, cheerful colors for mobile and desktop viewing.",
        // },
    ];

    function toggleQuestion(questionId) {
        expandedQuestion = expandedQuestion === questionId ? null : questionId;
    }
</script>

<section class="section" id="qa">
    <div class="container">
        <h2 class="title is-2 has-text-centered">Frequently Asked Questions</h2>

        <div class="columns is-centered">
            <div class="column is-8">
                {#each questions as question}
                    <div class="card mb-4">
                        <header
                            class="card-header"
                            role="button"
                            tabindex="0"
                            on:click={() => toggleQuestion(question.id)}
                            on:keydown={(e) =>
                                e.key === "Enter" &&
                                toggleQuestion(question.id)}
                            style="cursor: pointer;"
                        >
                            <p class="card-header-title">
                                {question.question}
                            </p>
                            <button
                                class="card-header-icon"
                                aria-label="more options"
                            >
                                <span class="icon">
                                    <i
                                        class="fas {expandedQuestion ===
                                        question.id
                                            ? 'fa-angle-up'
                                            : 'fa-angle-down'}"
                                        aria-hidden="true"
                                    ></i>
                                </span>
                            </button>
                        </header>

                        {#if expandedQuestion === question.id}
                            <div class="card-content">
                                <div class="content">
                                    {question.answer}
                                </div>
                            </div>
                        {/if}
                    </div>
                {/each}
            </div>
        </div>
    </div>
</section>

<style>
    .card-header {
        transition: background-color 0.2s ease;
    }

    .card-header:hover {
        background-color: #f5f5f5;
    }

    .mb-4 {
        margin-bottom: 1.5rem;
    }
</style>
