<script lang="ts">
    export let placeholder = "Search...";
    export let icon = "ri-search-line";
</script>

<div class="form-group">
    <i class={icon}></i>
    <input class="form-control" type="search" placeholder={placeholder} />
</div>

<style>
    .form-group{
        display: flex;
        align-items: center;
        position: relative;
        margin-bottom: 0 !important;
        flex: 1;
    }

    .form-group i{
        position: absolute;
        left: 1rem;
        top: 50%;
        transform: translateY(-50%);
    }

    .form-group input{
        padding-top: 0.7rem;
        padding-bottom: 0.7rem;
        padding-left: 3rem;
        font-size: 0.9rem;
        border-radius: 12px;
    }
</style>