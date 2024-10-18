<script lang="ts">
    export let total = 0;
    export let perPageOptions = [10, 25, 50];
</script>


<div class="per-page-selector">
    <label for="perPage">Showing</label>
    <select id="perPage">
        {#each perPageOptions as option}
            <option value={option}>{option}</option>
        {/each}
    </select>
    <span>of {total}</span>
</div>