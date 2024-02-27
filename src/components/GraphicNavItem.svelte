<li class="graphic-nav-item">
    <slot />
</li>

<style lang="scss">
    .graphic-nav-item {
        background-color: red;
        width: 100%;
        overflow: hidden;
        display: flex;
        align-items: center;
        justify-content: center;
        border-radius: 100%;
        
        // stolen from https://spin.atomicobject.com/css-responsive-square/
        &:after {
            content: "";
            display: block;
            padding-bottom: 100%;
        }

        :global(img) {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
    }
</style>