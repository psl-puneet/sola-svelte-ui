<script lang="ts">
	import Button from '$lib/components/ui/Button.svelte';
	import SectionLabel from '$lib/components/ui/SectionLabel.svelte';
</script>

<div class="p-10 space-y-12">
	<section>
		<h2 class="mb-4">Button</h2>
		<div class="flex gap-4">
			<Button>Get a Quote</Button>
			<Button variant="outline">Learn More</Button>
		</div>
	</section>

	<section>
		<h2 class="mb-4">SectionLabel</h2>
		<SectionLabel>Why Choose Us</SectionLabel>
		<SectionLabel class="text-[#6C63FF]">Overridden</SectionLabel>
	</section>
</div>
