<script>
    import DataGrid from "$lib/shared/components/DataGrid.svelte";
    import ManagementLayout from "$lib/shared/layouts/ManagementLayout.svelte";

    let columns = [
        { label: 'ID', key: 'id' },
        { label: 'Name', key: 'name' },
        { label: 'Email', key: 'email'},
    ];

    let api = 'http://127.0.0.1:8000/api/student';

</script>

<div class="container-fluid">
    <ManagementLayout title="Student">
        <DataGrid
            columns={columns}
            api={api}
            tools={{
                create: {href: "/student/create"}
            }}
        />
    </ManagementLayout>
</div>