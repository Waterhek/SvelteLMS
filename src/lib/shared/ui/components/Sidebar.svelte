<script lang="ts">
    import "remixicon/fonts/remixicon.css";
    import { page } from '$app/stores';

    $: currentRoute = $page.url.pathname;

    export let isOpen: boolean = true;
</script>

<div class="sidebar {isOpen ? 'open' : 'closed'}">
    <div class="logo">
        <img src="dummy/logo.png" alt="logo" />
    </div>
    <ul class="navbar-nav">
        <li class="nav-item">
            <a class="nav-link {currentRoute.startsWith('/student') ? 'active' : ''}" href="/student">
                <i class="ri-graduation-cap-fill"></i>
               <span>Student</span>
            </a>
        </li>
        <li class="nav-item">
            <a class="nav-link {currentRoute.startsWith('/teacher') ? 'active' : ''}" href="/teacher">
                <i class="ri-skip-down-fill"></i>
                <span>Teacher</span>
            </a>
        </li>
    </ul>
</div>

<style>
    .sidebar{
        position: fixed;
        width: 18rem;
        height: 100vh;
        background-color: var(--bs-primary-color);
        padding: 30px 20px;
        transition: all 0.5s ease;
    }

    :global(.sidebar.closed) {
        transform: translateX(-100%);
        width: 0;
        overflow: hidden;
    }

    :global(.sidebar.open) {
        transform: translateX(0);
        width: 18rem;
    }

    .logo{
        margin-bottom: 30px;
    }

    .logo img{
        width: 100%;
        height: 70px;
    }

    .nav-item{
        list-style: none;
        margin-bottom: 10px;
    }

    .nav-link{
        color: white;
        padding: 10px 20px;
        border-radius: 5px;
    }

    .nav-link i{
        margin-right: 10px;
    }

    .nav-link span{
        font-size: 0.9em;
    }

    .nav-link.active{
        background-color: grey;
    }
</style>