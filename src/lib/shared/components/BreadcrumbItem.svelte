<script lang="ts">
    export let href="";
</script>

<li class="breadcrumb-item">
    <a href={href}>
        <slot />
    </a>
</li>

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