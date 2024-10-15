<script lang="ts">
    import "remixicon/fonts/remixicon.css";
    import { page } from '$app/stores';

    $: currentRoute = $page.url.pathname;
    let isCollapsed = true;

    function handleToggle(){
        isCollapsed = !isCollapsed;
    }
</script>

<div class="sidebar" class:collapsed={isCollapsed} role="navigation">
    <div class="logo">
        <img src="dummy/logo.png" alt="logo" />
        <button class="btn btn-toggle" type="button" on:click={handleToggle}>
            <i class="ri-menu-line"></i>
        </button>
    </div>
    <ul class="navbar-nav">
        <li class="nav-item">
            <a class="nav-link {currentRoute.startsWith('/dashboard') ? 'active' : ''}" href="/dashboard">
                <i class="ri-dashboard-line"></i>
               <span class="nav-text">Dashboard</span>
            </a>
        </li>
        <li class="nav-item">
            <a class="nav-link {currentRoute.startsWith('/course') ? 'active' : ''}" href="/course">
                <i class="ri-book-fill"></i>
               <span class="nav-text">Courses</span>
            </a>
        </li>
        <li class="nav-item">
            <a class="nav-link {currentRoute.startsWith('/student') ? 'active' : ''}" href="/student">
                <i class="ri-graduation-cap-fill"></i>
               <span class="nav-text">Student</span>
            </a>
        </li>
        <li class="nav-item">
            <a class="nav-link {currentRoute.startsWith('/teacher') ? 'active' : ''}" href="/teacher">
                <i class="ri-user-line"></i>
                <span class="nav-text">Teacher</span>
            </a>
        </li>
        <li class="nav-item">
            <a class="nav-link {currentRoute.startsWith('/announcement') ? 'active' : ''}" href="/announcement">
                <i class="ri-bell-fill"></i>
                <span class="nav-text">Announcement</span>
            </a>
        </li>
        <li class="nav-item">
            <a class="nav-link nav-menu collapsed {currentRoute.startsWith('/setting') ? 'active' : ''}" data-bs-toggle="collapse" href="#collapseSetting" role="button">
                <div class="menu-info">
                    <i class="ri-settings-line"></i>
                    <span class="nav-text">Setting</span>
                </div>
                <span class="menu-arrow">
                    <i class="ri-arrow-down-s-line"></i>
                </span>
            </a>
            <div class="menu collapse" id="collapseSetting">
                <ul class="navbar-nav">
                    <li class="nav-item">
                        <a class="nav-link" href="/setting/configuration">Configuration</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="/setting/logo">Logo</a>
                    </li>
                </ul>
            </div>
        </li>
    </ul>
</div>

<style>
    .sidebar{
        width: 16rem;
        height: 100vh;
        background-color: var(--bs-primary-color);
        padding: 30px 20px;
        transition: all 0.5s ease;
    }

    .sidebar.collapsed{
        width: 4.5rem;
        padding: 30px 10px;
    }

    :global(.sidebar.open) {
        transform: translateX(0);
        width: 18rem;
    }

    .logo{
        margin-bottom: 30px;
        display: flex;
        align-items: center;
        justify-content: space-between;
        color: white;
    }

    .collapsed .logo img{
        display: none;
    }

    .logo img{
        width: auto;
        height: 25px;
    }

    .nav-item{
        list-style: none;
        margin-bottom: 10px;
    }

    .nav-link{
        color: white;
        padding: 10px 20px;
        border-radius: 5px;
        white-space: nowrap;
    }

    .nav-link.nav-menu{
        display: flex;
        justify-content: space-between;
    }

    .sidebar.collapsed .nav-link.nav-menu .menu-arrow{
        display: none;
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

    .sidebar.collapsed .nav-text{
        display: none;
    }

    .btn-toggle{
        color: white;
    }

    .menu{
        padding-top: 5px;
        transition: all 0.3s ease;
    }

    .menu ul li{
        padding-left: 40px;
        margin-bottom: 0;
    }

    .menu ul li a{
        font-size: 0.75rem;
        padding: 10px 20px;
    }

    .menu-arrow i{
        display: inline-block;
        transition: all 0.3s ease;
    }

    .nav-menu.collapsed .menu-arrow i{
        transform: rotate(-90deg);
    }
</style>