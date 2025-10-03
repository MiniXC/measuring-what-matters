<script>
    export let title;
    export let content;
    export let tags = [];
    export let timestamp;
    export let emoji = "😊"; // Default emoji
</script>

<div class="card">
    <div class="card-content">
        <div class="media">
            <div class="media-left">
                <figure class="image is-48x48 is-white">
                    <div class="emoji-container">
                        <span class="emoji">{emoji}</span>
                    </div>
                </figure>
            </div>
            <div class="media-content">
                <p class="title is-4">{title}</p>
            </div>
        </div>

        {#if tags && tags.length > 0}
            <div class="field is-grouped is-grouped-multiline">
                {#each tags as tag}
                    <div class="control">
                        <div class="tags has-addons">
                            <span class="tag is-dark">{tag.label}</span>
                            <span class="tag {tag.color}">{tag.value}</span>
                        </div>
                    </div>
                {/each}
            </div>
        {/if}

        <div class="content">
            {@html content}
        </div>
    </div>
</div>

<style>
    .emoji-container {
        width: 48px;
        height: 48px;
        display: flex;
        align-items: center;
        justify-content: center;
        background: linear-gradient(135deg, #232297, #f3a442);
        border-radius: 8px;
        box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
    }

    .emoji {
        font-size: 24px;
        filter: drop-shadow(0 1px 2px rgba(0, 0, 0, 0.2));
    }
</style>
