<script lang="ts">
    import { onMount } from "svelte";
    import { Alert, PerPageSelector, Pagination, IconButton } from '$lib/shared/components';


    export let columns;
    export let api:string;

    let loading = false;
    let total = 0;
    let perPage = 10;
    let rows:any = [];
    let error:any;
    let currentPage = 1;

    onMount(async () => {
        loading = true;
        
        try {
            const response = await fetch(`${api}?page=${currentPage}&per_page=${perPage}`);
            if (!response.ok) throw new Error('Failed to load data');
            const result = await response.json();
            rows = result.data;
            total = result.total;
            perPage = result.per_page;

        } catch (err: any) {
            error = err.message;
        } finally {
            loading = false;
        }
    });

</script>

<div class="table-container">
    <table class="table table-hover">
        <thead>
            <tr>
                {#each columns as column}
                    <th>
                        {column.label}
                    </th>
                {/each}
                <th>Action</th>
            </tr>
        </thead>
        <tbody>
            {#if loading}
                <tr>
                    <td colspan={columns.length + 1}>
                        <div class="d-flex justify-content-center">
                            <div class="spinner-border" role="status">
                            <span class="visually-hidden">Loading...</span>
                            </div>
                        </div>
                    </td>
                </tr>
            {:else if error}
                <tr>
                    <td colspan={columns.length + 1}>
                        <Alert severity="danger">
                            Error while fetching data
                        </Alert>
                    </td>
                </tr>
            {:else}
                {#if rows.length > 0}
                    {#each rows as row}
                        <tr>
                            {#each columns as column}
                                <td>{row[column.key]}</td>
                            {/each}
                            <td class="action">
                                <IconButton>
                                    <i class="ri-delete-bin-line"></i>
                                </IconButton>
                                <IconButton>
                                    <i class="ri-edit-line"></i>
                                </IconButton>
                            </td>
                        </tr>
                    {/each}
                {:else}
                    <td class="no-data" colspan={columns.length + 1}>
                        <span>No data available</span>
                    </td>
                {/if}
            {/if}
        </tbody>
    </table>
</div>

<div class="pagination-container">
    <Pagination />
    <PerPageSelector total={total} />
</div>

<style>
    .no-data{
        text-align: center;
        padding: 20px;
        background-color: white;
    }

    .table{
        font-family: 'Poppins';
        margin-bottom: 0;
        overflow-x: auto;
    }

    .table th{
        font-weight: 600;
        font-size: 0.9rem;
        background-color: #eee;
        color: grey;
    }

    .table td{
        font-size: 0.8rem;
        padding: 0.8rem;
    }

    .table td, .table th{
        align-content: center;
    }

    .table-container{
        border-radius: 8px;
        overflow: hidden;
        margin-bottom: 1rem;
    }

    .pagination-container{
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    .action{
        display: flex;
        gap: 0.5rem;
    }

    .table-container table th:last-child,
    .table-container table td:last-child {
        width: 150px;
    }
</style>