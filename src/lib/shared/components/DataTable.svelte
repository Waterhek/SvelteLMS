<script lang="ts">
    export let rows;
    export let columns;
</script>

<table class="table">
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
        {#if rows.length > 0}
            {#each rows as row}
                <tr>
                    {#each columns as column}
                        <td>{row[column.key]}</td>
                    {/each}
                </tr>
            {/each}
        {:else}
            <td class="no-data" colspan={columns.length}>
                <span>No data available</span>
            </td>
        {/if}
    </tbody>
</table>

<style>
    .no-data{
        text-align: center;
        padding: 20px;
        background-color: white;
    }
</style>