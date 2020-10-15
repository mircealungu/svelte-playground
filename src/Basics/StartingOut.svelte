<script>
    /* This tag contains all our javascript for this component as well as all import statements for other components. */
    let helloHTML = "<h1> Hello{name} </h1>",
    scripttag = "<script>", 
    styletag = "<style>", 
    importString = "import MyComponent from ./MyComponent.svelte", 
    myComponent = "<MyComponent />", 
    htmlString = "where string = “this string contains some <strong>HTML</strong>” with <p>{@html string}</p>";
</script>

<style>
    /* This tag contains the CSS for this component */
    p{
        color: red;
    }

    code {
        color: blue;
    }

    div {
        background-color: whitesmoke;
        height: 80%;
        width: 80%;
    }

</style>

<!-- And here is all our HTML code for the component with sweet Svelte shit going on. -->
<h1>01: Starting Out</h1>

<div>
    <p>
        A svelte component is made out of a <code>{scripttag}</code> and <code>{styletag}</code> tags followed by HTML.
        You can only have one <code>{scripttag}</code> tag, but several other tags, doesn’t matter where you put them.
        You can have variables in the HTML, inserted with curly braces, similar to React:
    </p>

    <code>{helloHTML}</code>

    <p>Use the <code>{styletag}</code> tag to create local CSS rules for the component. ‘They are scoped to your component’.</p>

    <p>Svelte applications are made of components. Some components contain other components!</p>

    <p>You import other components in the <code>{scripttag}</code> tag, with this terminology:</p>

    <code>{importString}</code>

    <p>You insert the component in the HTML area, using the same terminology as React:</p>

    <code>{myComponent}</code>

    <p>Add String variables as HTML:</p>

    <code>{htmlString}</code>

    <p>This will render the string as HTML.</p>
</div>