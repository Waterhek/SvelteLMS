<script lang="ts">
    import DataTable from "./DataTable.svelte";
    import SearchBar from "./SearchBar.svelte";

    export let api: string;
    export let columns: any;
    export let tools: {
        search?: boolean,
        export?: boolean,
        filter?: boolean,
        create?: { href: string, label?: string }
    } = {};

    const defaultTools = {
        search: true,
        export: true,
        filter: true,
        create: { href: "#", label: "Add New" }
    }

    $: initialTools = {...defaultTools, ...tools};
</script>

<div class="tool-container">
    {#if initialTools.search}
        <SearchBar />
    {/if}
    {#if initialTools.export}
        <button class="btn btn-secondary">
            <i class="ri-export-line"></i>
            <span>Export</span>
        </button>
    {/if}
    {#if initialTools.filter}
        <button class="btn btn-secondary">
            <i class="ri-filter-line"></i>
            <span>Filters</span>
        </button>
    {/if}
    {#if tools.create}
        <a class="btn btn-primary" href={initialTools.create.href}>
            <i class="ri-add-line"></i>
            <span>Add New</span>
        </a>
    {/if}
</div>
<DataTable api={api} columns={columns}/>

<style>
    .tool-container{
        display: flex;
        gap: 1rem;
        align-items: center;
        margin-bottom: 1rem;
    }

    .tool-container .btn{
        font-size: 0.9rem;
        padding: 0.5rem 1rem;
    }
</style>