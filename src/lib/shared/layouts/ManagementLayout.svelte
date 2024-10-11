<script lang="ts">
    export let title;
    export let createButton = true;
    export let createButtonUrl;
    export let createButtonLabel;
</script>

<div class="main-content">
    <div class="top-section">
        <h3>{title}</h3>
        {#if createButton}
            <a class="btn btn-primary" href={createButtonUrl}>{createButtonLabel}</a>
        {/if}
    </div>

    <!-- Dummy -->
    <table class="table">
        <thead>
            <tr>
                <th>ID</th>
                <th>Name</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>1</td>
                <td>gg</td>
            </tr>
        </tbody>
    </table>
    <!-- End Dummy -->
</div>

<style>
    .top-section{
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 20px;
    }

</style>