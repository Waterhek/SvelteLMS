<script lang="ts">
</script>

<div class="header">
    <div class="container-fluid">
        <div class="header-content">
            <div></div>
            <ul class="navbar-nav">
                <div class="profile-container" data-bs-toggle="dropdown" data-bs-target="#profile-dropdown">
                    <img src="" alt="avatar" />
                </div>
                <!-- Dummy -->
                <div class="dropdown-menu dropdown-menu-end"  id="profile-dropdown">
                    <div class="card">
                        <div class="card-header">
                            Waterhek
                        </div>
                        <div class="card-body">
                            <ul class="dropdown navbar-nav">
                                <li>
                                    <a class="dropdown-item" href="/">Profile</a>
                                </li>
                                <li><a class="dropdown-item" href="/">Menu item</a></li>
                                <li><a class="dropdown-item" href="/">Menu item</a></li>
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