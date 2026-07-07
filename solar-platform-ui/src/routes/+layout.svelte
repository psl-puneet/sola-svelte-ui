<script lang="ts">
	import './layout.css';
	import Navbar from '$lib/components/ui/Navbar.svelte';
	let { children }: { children: () => any } = $props();
</script>

<Navbar />
{@render children()}
