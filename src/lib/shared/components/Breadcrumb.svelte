<script lang="ts">
    export let crumbs;
</script>

<nav aria-label="breadcrumb">
    <ol class="breadcrumb">
        {#each crumbs as { href, label }, index}
            {#if index < crumbs.length - 1}
                <li class="breadcrumb-item">
                    <a href={href}>{label}</a>
                </li>
            {:else}
                <li class="breadcrumb-item active" aria-current="page">
                    {label}
                </li>
            {/if}
        {/each}
    </ol>
</nav>

<style>
    .breadcrumb-item{
        font-size: 0.875rem;
    }

    .breadcrumb-item a{
        color: #878787;
        text-decoration: none;
    }

    .breadcrumb-item a:hover{
        text-decoration: underline;
    }
</style>