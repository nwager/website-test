<script lang="ts">
    import { page } from "$app/stores";
    import classNames from "classnames";

    export let text: string;
    export let href: string;
</script>

<li class={classNames('navbar-item', { 'active': $page.url.pathname == href })}>
    <a href={href}>
        <span>{text}</span>
    </a>
</li>

<style lang="scss">
    .navbar-item {
        a {
            height: 100%;
            padding: 0 0.5em;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        &.active {
            background-color: aqua;
        }
    }
</style>