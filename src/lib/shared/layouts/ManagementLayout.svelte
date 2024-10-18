<script lang="ts">
    export let title;
</script>

<div class="main-content">
    <div class="top-section">
        <h3>{title}</h3>
    </div>

    <slot></slot>
</div>

<style>
    .top-section{
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 20px;
    }

</style>