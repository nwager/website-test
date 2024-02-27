<script lang="ts">
    import Navbar from "../components/Navbar.svelte";
</script>

<Navbar title="portfolio">
    <li><a href="/">Home</a></li>
    <li><a href="/about">About</a></li>
</Navbar>
<main>
    <slot />
</main>

<style lang="scss">
    main {
        min-height: 100%;
        margin: 0 10%;
    }
</style>