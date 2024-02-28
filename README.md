# gillian-portfolio

This is the Svelte app powering Gillian's UW Honors portfolio.

## Editing the website

### Pages

Each webpage is housed in `src/routes/{name}/+page.svelte` where `{name}` is the name of the page, or in the case of the home page, `src/routes/+page.svelte`.
The page will be visible by the route `{website base URL}/{name}`.

For example, on a local server with the base URL `http://localhost:5173`, the "Freshman" page will be visible at `http://localhost:5173/freshman`. To add content to this page, edit `src/routes/freshman/+page.svelte`.

This means a new page can be added by creating a new folder `src/routes/{name}` and creating a `+page.svelte` file in the folder.

### Content

Content uses regular HTML tags like `<p>`, `<h2>`, and `<img>`. To simplify the page layout, these should usually be placed within custom Svelte components.

However, some custom components have extra fields to specify data, like text or an image URL.

All these components are described in the "Components" section.

### Components

#### `<Title>`

This is the main title card on the home page. It renders a large rectangle with a title, optional subtitle, and optional image. No content should be placed inside this component.

**Fields:**

 - `title`: title text
 - `subtitle` (optional): subtitle text
 - `imgSrc` (optional): URL of image to display

**Example:**

```html
<Title title="Main title" subtitle="Subtitle" imgSrc="path/to/image" />
```

#### `<ImageBlock>`

This is the main building block of each page. It contains HTML content and optionally one image (maybe more, but it might get wonky). This image can be placed inline with the rest of the content, or it can float left or right by adding `class="left"` or `class="right"` to the `<img>` tag respectively.

Basically, most of the website text and image content will be placed inside these blocks.

**Fields:**

 - `title` (optional): title text that appears above the block

 **Example:**

 ```html
<ImageBlock title="TITLE">
    <img src="path/to/image" class="left">
    <h2>Header</h2>
    <p>Paragraph text.</p>
    <p>More paragraphs.</p>
</ImageBlock>
 ```

#### `<ColumnContainer>` and `<Column>`

These components create columns in which content can be placed. First, add a `<ColumnContainer>`. Inside, add a `<Column>` for each desired column. Inside each column, any HTML or custom content can be inserted, and it will render within the specified column.

**Example:**

```html
<ColumnContainer>

    <!-- column 1 -->
    <Column>
        <h2>Column 1 header outside block.</h2>
        <ImageBlock>
            <p>Text-only ImageBlock.</p>
        </ImageBlock>
    </Column>

    <!-- column 2 -->
    <Column>
        <p>Column 2 paragraph text.</p>
    </Column>

</ColumnContainer>
```

#### `<GraphicNav>` and `<GraphicNavItem>`

These components create the grid-like "album" navigation menu. Each `<GraphicNavItem>` inside the `<GraphicNav>` container will render a circular element in the grid. HTML content inside the `<GraphicNavItem>` will be centered inside the circle. The content will most likely be an image link, as shown in the example.

**Example:**

```html
<GraphicNav>

    <!-- item 1 -->
    <GraphicNavItem>
        <a href="path/to/target1"><img src="path/to/image1"></a>
    </GraphivNavItem>

    <!-- item 2 -->
    <GraphicNavItem>
        <a href="path/to/target2"><img src="path/to/image2"></a>
    </GraphivNavItem>

</GraphicNav>
```

#### `<Navbar>` and `<NavbarItem>`

Similar to the `<GraphicNav>` but displays a navbar at the top of the page. The single instance of `<Navbar>` should be placed in `+layout.svelte` so it appears on every page. To add an item on the right side of the navbar, add a `<NavbarItem>` with the following fields:

**NavbarItem Fields:**

 - `text`: text to display
 - `href`: link to target

### HTML Tips

The most common HTLM components are likely the header, paragraph, and image tags (`<h1>...<h6>`, `<p>`, `<img>`).

Another useful element is the horizontal line tag (`<hr>`). This will create a horizontal line divider across the page or column.

Anchor tags (`<a>`) are used to create hyperlinks.

Line breaks can be inserted into paragaphs with `<br>`.

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Building

To create a production version of your app:

```bash
npm run build
```

You can preview the production build with `npm run preview`.

## Deploying

To publish the production version of the app to Github Pages:

```bash
npm run gh-pages
```

This will push the build to the `gh-pages` branch. Make sure this branch is selected in your repository's Pages settings.
