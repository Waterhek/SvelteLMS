<script lang="ts">
    export let label;
    export let id;
    export let name;
    export let type;
</script>

<label class="form-label" for={id}>{label}</label>
<input class="form-control" {type} {name} {id} />