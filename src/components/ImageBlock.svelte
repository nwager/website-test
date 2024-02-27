<script lang="ts">
    export let title: string | null = null;
</script>

<div class="image-block-container">
    {#if title}
        <h2>{title}</h2>
    {/if}
    <div class="inner">
        <slot />
    </div>
</div>

<style lang="scss">
    .image-block-container {
        border-top: 1px solid black;

        // clearfix hack to stop floating image overflow
        &::after {
            content: "";
            clear: both;
            display: table;
        }
        
        .inner {
            margin: 0.5em;
            :global(img) {
                margin-bottom: 0.5em;
                object-fit: cover;
                width: 25%;
                min-width: 11em;
                aspect-ratio: 1 / 1;
            }

            :global(img.left) {
                float: left;
                margin-right: 1em;
            }

            :global(img.right) {
                float: right;
                margin-left: 1em;
            }
        }

    }
</style>