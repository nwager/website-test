<div class="column-container">
    <slot />
</div>

<style lang="scss">
    @import "../global.scss";

    .column-container {
        display: flex;
        flex-direction: row;
        gap: 4em;

        @media screen and (max-width: $screen-width-small) {
            flex-direction: column;
            gap: 0;
        }
    }
</style>