<script lang="ts">
    export let title: string = "navbar";
</script>

<div class="navbar-container">
    <div class="navbar">
        <div class="inner">
            <span>{title}</span>
            <ul>
                <slot />
            </ul>
        </div>
    </div>
</div>

<style lang="scss">
    $navbar-height: 2.2em;

    .navbar-container {
        width: 100%;
        height: $navbar-height;
        
        .navbar {
            position: fixed;
            top: 0;
            width: inherit;
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
        list-style-type: none;
        padding: 0;
        margin: 0;
        margin-left: auto;
        display: flex;
        flex-direction: row;
        gap: 1em;
    }
</style>