<script lang="ts">
    import { base } from "$app/paths";
    import Navbar from "components/Navbar.svelte";
    import NavbarItem from "components/NavbarItem.svelte";
</script>

<Navbar title="portfolio">
    <NavbarItem text="About" href="{base}/about" />
    <NavbarItem text="Freshman" href="{base}/freshman" />
    <NavbarItem text="Sophomore" href="{base}/sophomore" />
    <NavbarItem text="Junior" href="{base}/junior" />
    <NavbarItem text="Senior" href="{base}/senior" />
</Navbar>
<main>
    <slot />
</main>

<style lang="scss">
    @import "../global.scss";

    main {
        min-height: 100%;
        margin: 0;
        width: 65vw;
        margin-top: 3em;
    }

    @media screen and (max-width: $screen-width-small) {
        main {
            width: auto;
            padding: 0 1em;
        }
    }

</style>