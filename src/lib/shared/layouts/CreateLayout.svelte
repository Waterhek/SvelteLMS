<script lang="ts">
    import { Card, CardBody, CardHeader } from '$lib/shared/components';
    export let title = "";
</script>

<div class="container-fluid">
    <slot name="breadcrumb"></slot>
    <Card>
        <CardHeader>
            <span>{title}</span>
        </CardHeader>
        <CardBody>
            <slot />
        </CardBody>
    </Card>
</div>