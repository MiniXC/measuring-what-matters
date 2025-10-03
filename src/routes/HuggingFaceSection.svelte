<script>
    // Placeholder for HuggingFace space integration
    let isLoaded = false;

    function loadHuggingFaceSpace() {
        // This would be replaced with actual HuggingFace space embedding
        setTimeout(() => {
            isLoaded = true;
        }, 1000);
    }
</script>

<section class="section" id="huggingface">
    <div class="container">
        <h2 class="title is-2 has-text-centered">Interactive Demo</h2>

        <div class="columns is-centered">
            <div class="column is-10">
                <div class="card">
                    <div class="card-content">
                        {#if !isLoaded}
                            <div class="has-text-centered">
                                <div class="notification is-info">
                                    <h3 class="title is-4">
                                        🚀 HuggingFace Space Placeholder
                                    </h3>
                                    <p>
                                        This section is reserved for embedding a
                                        HuggingFace Space.
                                    </p>
                                    <p>
                                        Click the button below to simulate
                                        loading the space.
                                    </p>
                                    <button
                                        class="button is-primary"
                                        on:click={loadHuggingFaceSpace}
                                    >
                                        ✨ Load Demo Space
                                    </button>
                                </div>
                            </div>
                        {:else}
                            <div class="has-text-centered">
                                <div class="notification is-success">
                                    <h3 class="title is-4">
                                        🎉 Demo Space Loaded
                                    </h3>
                                    <p>
                                        This is where your HuggingFace Space
                                        would be embedded.
                                    </p>
                                    <p>
                                        You can replace this placeholder with an
                                        actual iframe or widget integration.
                                    </p>
                                    <div class="box has-background-light">
                                        <p class="has-text-grey">
                                            iframe
                                            src="https://huggingface.co/spaces/your-username/your-space"
                                        </p>
                                    </div>
                                </div>
                            </div>
                        {/if}
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>

<style>
    .box {
        font-family: monospace;
        font-size: 0.9em;
        padding: 1rem;
        border-radius: 4px;
    }
</style>
