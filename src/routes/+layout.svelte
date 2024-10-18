<script lang="ts">
    import Header from '$lib/shared/ui/components/Header.svelte';
    import Sidebar from '$lib/shared/ui/components/Sidebar.svelte';
    import '../styles/app.css';

    let isCollapsed = false;

    function handleToggle() {
        isCollapsed = !isCollapsed;
    }
</script>

<main>
    <Sidebar {isCollapsed} on:toggle={handleToggle}/>
    <div class="main-section"  class:collapsed={isCollapsed}>
        <Header />
        <div class="main-body">
            <slot />
        </div>
    </div>
</main>

<style>
    main{
        display: flex;
    }

    .main-section{
        flex: 1;
        width: 100%;
        margin-left: 16rem;
        overflow-y: auto;
        transition: all 0.5s;
    }

    .main-body{
        padding: 20px 2rem;
    }

    :global(.sidebar.open ~ .main-section) {
        transition: all 0.5s;
    }

    .main-section.collapsed {
        margin-left: 4.5rem;
    }
</style>