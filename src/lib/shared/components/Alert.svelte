<script lang="ts">
    type Severity = 'success' | 'danger' | 'warning' | 'info';
    export let severity: Severity = "info";

    let icon = 'ri-information-line';
    let alertClass = 'alert-info';

    $: {
        switch (severity) {
            case 'success':
                icon = 'ri-check-line';
                alertClass = 'alert-success';
                break;
            case 'danger':
                icon = 'ri-error-warning-line';
                alertClass = 'alert-danger';
                break;
            case 'warning':
                icon = 'ri-alert-line';
                alertClass = 'alert-warning';
                break;
            case 'info':
                icon = 'ri-information-line';
                alertClass = 'alert-info';
                break;
            default:
                icon = 'ri-information-line';
                alertClass = 'alert-info';
        }
    }
</script>

<div class={`alert ${alertClass} d-flex align-items-center`} role="alert">
    <i class={`${icon} me-2`}></i>
    <div>
        <slot />
    </div>
</div>

<style>
    .alert{
        margin-bottom: 0;
    }
</style>