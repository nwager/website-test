<script lang="ts">
    import { base } from "$app/paths";

    export let title: string;
</script>

<div id="navbar-container">
    <div class="navbar">
        <div class="inner">
            <a href="{base}/"><span>{title}</span></a>
            <ul>
                <slot />
            </ul>
        </div>
    </div>
</div>

<style lang="scss">
    $navbar-height: 4rem;

    #navbar-container {
        width: 100%;
        height: $navbar-height;
        
        .navbar {
            position: fixed;
            top: 0;
            width: 100%;
            height: $navbar-height;
            font-size: 1.3em;
            background-color: coral;
            
            .inner {
                height: 100%;
                margin: 0 1em;
                display: flex;
                flex-direction: row;
                align-items: center;
            }
        }
    }

    ul {
        height: 100%;
        list-style-type: none;
        padding: 0;
        margin: 0;
        margin-left: auto;
        display: flex;
        flex-direction: row;
    }
</style>