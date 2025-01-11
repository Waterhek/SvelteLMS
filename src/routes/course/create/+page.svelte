<script lang="ts">
    import CreateLayout from "$lib/shared/layouts/CreateLayout.svelte";
    import FormGroup from "$lib/shared/components/FormGroup.svelte";
    import Input from "$lib/shared/components/Input.svelte";
    import Breadcrumb from "$lib/shared/components/Breadcrumb.svelte";
    import Swal from 'sweetalert2';
    import { goto } from "$app/navigation";

    let isSubmitting = false;

    async function handleSubmit(event: Event){
        isSubmitting = true;

        const form = event.target as HTMLFormElement;
        const data = new FormData(form);

        const response = await fetch('http://127.0.0.1:8000/api/course/create', {
            headers: {
                'Accept': 'application/json',
            },
            method: 'POST',
            body: data
        });

        isSubmitting = false;

        if(response.ok){
            Swal.fire({
                title: 'Success!',
                text: 'Course created successfully!',
                icon: 'success',
                confirmButtonText: 'OK'
            }).then(() => {
                goto('/course');
            });
        } /* else if(response.status === 422){
            const errorResponse = await response.json();
            const errorMsg = Object.values(errorResponse.errors).flat().shift();

            Swal.fire({
                title: 'Error!',
                text: errorMsg || "gg",
                icon: 'error',
                confirmButtonText: 'Try Again'
            });
        } */
        else {
            Swal.fire({
                title: 'Error!',
                text: 'Something went wrong while creating the course.',
                icon: 'error',
                confirmButtonText: 'Try Again'
            });
        }
    }
</script>

<CreateLayout title="Create Course">
    <Breadcrumb slot="breadcrumb">
    </Breadcrumb>
    <form on:submit|preventDefault={handleSubmit}>
        <FormGroup>
            <Input label="Course Title" type="text" name="title" id="title" />
        </FormGroup>
        <FormGroup>
            <Input label="Course Code" type="text" name="code" id="code" />
        </FormGroup>
        <button type="submit" disabled={isSubmitting} class="btn btn-primary">
            {#if isSubmitting}
                <span class="spinner-border spinner-border-sm" aria-hidden="true"></span>
                <span role="status">Submitting...</span>
            {:else}
                <span>Submit</span>
            {/if}
        </button>
    </form>
</CreateLayout>