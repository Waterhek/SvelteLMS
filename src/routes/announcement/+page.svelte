<script>
    import DataGrid from "$lib/shared/components/DataGrid.svelte";
    import ManagementLayout from "$lib/shared/layouts/ManagementLayout.svelte";

    const columns = [
        {label: "ID", key: "id"},
        {label: "Title", key: "title"},
    ];

    let api = 'http://127.0.0.1:8000/api/announcement';

</script>
<ManagementLayout title="Announcement">
    <DataGrid
        columns={columns}
        api={api}
        tools={{
            create: {href: "/announcement/create"}
        }}
    />
</ManagementLayout>