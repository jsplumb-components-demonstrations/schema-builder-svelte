
<script>
    import {onMount} from "svelte"
    import {SchemaComponent, PaletteComponent, InspectorComponent} from "@jsplumb-components/schema-svelte"

    let schemaBuilder;

    onMount(async () => {
        schemaBuilder.loadUrl("./schema-1.json", () => {
            schemaBuilder.zoomToFit()
        })
    })

</script>


<div id="canvas">
    <SchemaComponent id="mySchema" bind:this={schemaBuilder}/>
</div>

<div id="rhs">
    <PaletteComponent schemaId="mySchema"></PaletteComponent>
    <InspectorComponent schemaId="mySchema"></InspectorComponent>
</div>

