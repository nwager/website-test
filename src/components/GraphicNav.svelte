<ul class="graphic-nav-container">
    <slot />
</ul>

<style lang="scss">
    .graphic-nav-container {
        list-style-type: none;
        margin: 0;
        padding: 0;
        width: 80%;

        // stolen from https://css-tricks.com/an-auto-filling-css-grid-with-max-columns/
        --grid-layout-gap: 2em;
        --grid-max-columns: 3;
        --grid-item--min-width: 10em;

        --gap-count: calc(var(--grid-max-columns) - 1);
        --total-gap-width: calc(var(--gap-count) * var(--grid-layout-gap));
        --grid-item--max-width: calc((100% - var(--total-gap-width)) / var(--grid-max-columns));

        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(max(var(--grid-item--min-width), var(--grid-item--max-width)), 1fr));
        grid-gap: var(--grid-layout-gap);
    }
</style>