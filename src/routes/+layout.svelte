<script lang="ts">
    import Header from '$lib/shared/ui/components/Header.svelte';
    import Sidebar from '$lib/shared/ui/components/Sidebar.svelte';
    import '../styles/app.css';

    let showSidebar = true;

    const toggleSidebar = () => {
        showSidebar = !showSidebar;
    };
</script>

<main>
    <Sidebar isOpen={showSidebar}/>
    <div class="main-section">
        <Header {showSidebar} on:toggleSidebar={toggleSidebar} />
        <div class="main-body">
            <slot />
        </div>
    </div>
</main>

<style>
    .main-body{
        padding: 30px 0;
    }

    .main-section{
        margin-left: 18rem;
    }

    :global(.sidebar.open ~ .main-section) {
        margin-left: 18rem;
        transition: all 0.5s;
    }

    :global(.sidebar.closed ~ .main-section) {
        margin-left: 0;
        transition: all 0.5s;
    }
</style>