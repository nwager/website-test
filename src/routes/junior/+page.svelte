<script lang="ts">
    import { base } from "$app/paths";
    import ImageBlock from "components/ImageBlock.svelte";
</script>

<ImageBlock>
    <img src="{base}/images/butters.jpeg" alt="butters page title" class="left"
        style="width: 45%; aspect-ratio: 4/3;"
    >
    <h1>Autumn Quarter</h1>
    <ul>
        <li>Class 1</li>
        <li>Class 2</li>
        <li>Class 3</li>
        <li>Class 4</li>
    </ul>
</ImageBlock>

<hr>

<ImageBlock title="Another block">
    <img src="{base}/images/butters.jpeg" alt="desc" class="left">
    <p>Some placeholder text.</p>
</ImageBlock>
