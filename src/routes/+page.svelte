<script>
    import Navbar from "./navbar.svelte";
    import Card from "./card.svelte";
    import QASection from "./QASection.svelte";
    import HuggingFaceSection from "./HuggingFaceSection.svelte";
    import pitfallsData from "../data/pitfalls.json";

    // Convert pitfalls data to card format
    const cards = pitfallsData.pitfalls.map((pitfall, index) => ({
        title: pitfall.name,
        emoji: pitfall.emoji,
        content: pitfall.description,
        tags: [
            { label: "Category", value: pitfall.category, color: "is-info" },
            {
                label: "Type",
                value: pitfall.subjective_objective,
                color: "is-success",
            },
        ],
        timestamp: `Added ${new Date().toLocaleDateString()}`,
    }));
</script>

<Navbar />

<section class="section" id="home">
    <div class="container">
        <div class="has-text-centered">
            <h1 class="title is-1 has-text-white">Measuring What Matters</h1>
            <p class="subtitle is-4 has-text-info">
                Condensed guidelines on GenAI evaluation.
            </p>
        </div>
    </div>
</section>

<section class="section" id="cards">
    <div class="container">
        <h2 class="title is-2 has-text-centered">Evaluation Pitfalls</h2>

        <div class="columns is-multiline">
            {#each cards as card}
                <div class="column is-one-third">
                    <Card
                        title={card.title}
                        content={card.content}
                        tags={card.tags}
                        timestamp={card.timestamp}
                        emoji={card.emoji}
                    />
                </div>
            {/each}
        </div>
    </div>
</section>

<QASection />

<HuggingFaceSection />

<style>
    .section {
        padding: 3rem 1.5rem;
    }

    .title.is-1 {
        margin-bottom: 2rem;
    }

    .title.is-2 {
        margin-bottom: 2rem;
    }

    .subtitle.is-4 {
        margin-bottom: 3rem;
    }

    #home {
        background: #232297;
        color: white;
    }

    #cards {
        background: #f3a442;
        color: #333;
    }

    #qa {
        background: #232297;
        color: white;
    }

    #huggingface {
        background: #f3a442;
        color: #333;
    }
</style>
