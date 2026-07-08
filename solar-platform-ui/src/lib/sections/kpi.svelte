<script lang="ts">
	import KpiCard from '$lib/components/ui/KpiCard.svelte';
	const stats = [
		{ value: '1999', label: 'Happy Customer' },
		{ value: '1721', label: 'Project Done' },
		{ value: '97', label: 'Award win' },
		{ value: '1650', label: 'expert worker' }
	];
</script>

<section id="info" class="py-[10rem]">
	<div class="container mx-auto px-4">
		<div class="grid grid-cols-1 md:grid-cols-4 gap-8">
			{#each stats as { value, label }}
				<KpiCard {value} {label} />
			{/each}
		</div>
	</div>
</section>
