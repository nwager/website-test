<script lang="ts">
    export let title: string;
    export let subtitle: string | null = null
    export let imgSrc: string | null = null
</script>

<div class="title-container">
    <div class="text-container">
        <h1>{title}</h1>
        {#if subtitle}
            <h2>{subtitle}</h2>
        {/if}
    </div>
    {#if imgSrc}
        <img src={imgSrc} alt={imgSrc}>
    {/if}
</div>

<style lang="scss">
    .title-container {
        display: flex;
        flex-direction: row;
        padding: 10% 6%;
        margin-bottom: 2em;
        border: 1px solid red;
    }

    .text-container {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        flex-grow: 1;
    }

    img {
        width: 50%;
        aspect-ratio: 4 / 3;
        object-fit: cover;
    }
</style>