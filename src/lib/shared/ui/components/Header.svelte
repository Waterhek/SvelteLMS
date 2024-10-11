<script lang="ts">
    import { createEventDispatcher } from 'svelte';
    export let showSidebar: boolean; // Sidebar visibility is passed as a prop

    // Dispatch an event to toggle sidebar visibility
    const dispatch = createEventDispatcher();

    function handleToggle() {
        dispatch('toggleSidebar');
    }
</script>

<div class="header">
    <div class="container-fluid">
        <div class="header-content">
            <button class="btn" type="button" on:click={handleToggle}>
                <i class="ri-menu-line"></i>
            </button>

            <ul class="navbar-nav">
                <div class="profile-container" data-bs-toggle="dropdown" data-bs-target="#profile-dropdown">
                    <img src="favicon.png" alt="avatar" />
                </div>
                <!-- Dummy -->
                <div class="dropdown-menu dropdown-menu-end"  id="profile-dropdown">
                    <div class="card">
                        <div class="card-header">
                            Chin Chee Onn
                        </div>
                        <div class="card-body">
                            <ul class="dropdown">
                                <li><a class="dropdown-item" href="#">Menu item</a></li>
                                <li><a class="dropdown-item" href="#">Menu item</a></li>
                                <li><a class="dropdown-item" href="#">Menu item</a></li>
                            </ul>
                        </div>
                        <div class="card-footer"></div>
                    </div>
                </div>
                <!-- End Dummy -->
            </ul>
        </div>
    </div>
</div>

<style>
    .header{
        border-bottom:  1px solid grey;
        padding: 10px 0;
    }

    .header-content{
        display: flex;
        align-items: center;
        justify-content: space-between;
    }

    .profile-container img{
        width: 50px;
        height: 50px;
        border-radius: 50%;
    }

    .dropdown-menu{
        padding: 0;
        border: none;
    }
</style>