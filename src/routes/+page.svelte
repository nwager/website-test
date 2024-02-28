<script lang="ts">
    import { base } from "$app/paths";
    import Column from "components/Column.svelte";
    import ColumnContainer from "components/ColumnContainer.svelte";
    import GraphicNav from "components/GraphicNav.svelte";
    import GraphicNavItem from "components/GraphicNavItem.svelte";
    import ImageBlock from "components/ImageBlock.svelte";
    import Title from "components/Title.svelte";
</script>

<Title title="home page" subtitle="home subtitle" imgSrc="{base}/images/butters.jpeg" />

<hr>

<ImageBlock title="Body 1">
    <img src="{base}/images/butters.jpeg" class="left" alt="Butters in body text">
    <p class="first-letter">Some body paragraph text.</p>
    <p>
        Paragraph break to demonstrate block-ness. If that's the correct term.
        Which it's definitely not.
    </p>
    <p>
        I'm gonna ramble with some line breaks to test the behavior
        <br/>
        with
        <br/>
        lots
        <br/>
        of
        <br/>
        lines.
    </p>
    <p>
        Alrighty, we should be nearing the bottom of the image soon.
    </p>
    <p>Aaaaaand there we go.</p>
</ImageBlock>

<ImageBlock>
    <p>Another body, but without an image.</p>
</ImageBlock>

<ColumnContainer>
    <Column>
        <ImageBlock>
            <img src="{base}/images/butters.jpeg" class="left" alt="Butters to the left">
            <p>Block of text in a column.</p>
        </ImageBlock>
    </Column>
    <Column>
        <h2>Nav</h2>
        <GraphicNav>
            <GraphicNavItem><p>One</p></GraphicNavItem>
            <GraphicNavItem><p>Two</p></GraphicNavItem>
            <GraphicNavItem><img src="{base}/images/butters.jpeg" alt="Butters in a circle"></GraphicNavItem>
            <GraphicNavItem><p>Four</p></GraphicNavItem>
            <GraphicNavItem><p>Five</p></GraphicNavItem>
        </GraphicNav>
    </Column>
</ColumnContainer>