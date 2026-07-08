<script lang="ts">
    let {
		value,
		label,
		children
	}: {
		value?: string;
		label?: string;
		children?: () => any;
	} = $props();
</script>

<div class="text-center">
    <h3 class="text-7xl font-bold text-primary">{value}</h3>
    <h6>{label}</h6>
</div>