<script>
    import Breadcrumb from "$lib/shared/components/Breadcrumb.svelte";
    import BreadcrumbItem from "$lib/shared/components/BreadcrumbItem.svelte";
    import Card from "$lib/shared/components/Card.svelte";
    import CardBody from "$lib/shared/components/CardBody.svelte";
    import CardHeader from "$lib/shared/components/CardHeader.svelte";
    import FormGroup from "$lib/shared/components/FormGroup.svelte";
    import Input from "$lib/shared/components/Input.svelte";
    import CreateLayout from "$lib/shared/layouts/CreateLayout.svelte";

</script>

<CreateLayout title="Create Announcement">
    <Breadcrumb slot="breadcrumb">
        <BreadcrumbItem href="/announcement">Announcement</BreadcrumbItem>
        <BreadcrumbItem>Create</BreadcrumbItem>
    </Breadcrumb>

    <FormGroup>
        <Input label="Title" type="text" id="title" name="title" />
    </FormGroup>
    <FormGroup>
        <label class="form-label" for="description">Description</label>
        <textarea class="form-control" name="description"></textarea>
    </FormGroup>
    <button class="btn btn-primary">Submit</button>
</CreateLayout>