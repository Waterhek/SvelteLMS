<script lang="ts">
    import ManagementLayout from "$lib/shared/layouts/ManagementLayout.svelte";
    import DataGrid from "$lib/shared/components/DataGrid.svelte";

    let api = 'http://127.0.0.1:8000/api/course';

    let columns = [
        {label: "#", key: "id"},
        {label: "Title", key: "title"},
        {label: "Code", key: "code"}
    ]
</script>
<ManagementLayout title="Course">
    <DataGrid
        api={api}
        columns={columns}
        tools={{
            create: {href: "/course/create"}
        }}
    />
</ManagementLayout>