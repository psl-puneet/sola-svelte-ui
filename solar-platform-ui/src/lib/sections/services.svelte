<script lang="ts">
	import ServiceCard from '$lib/components/ui/ServiceCard.svelte';
	const services = [
		{
			image: '/images/service1.jpg',
			title: 'Solar Panels',
			description: 'State ste justo dolar sed dui.'
		},
		{
			image: '/images/service2.jpg',
			title: 'Solar Energy',
			description: 'State ste justo dolar sed dui.'
		},
		{
			image: '/images/service3.jpg',
			title: 'Wind Turbines',
			description: 'State ste justo dolar sed dui.'
		},
		{
			image: '/images/service4.jpg',
			title: 'Hydro Power',
			description: 'State ste justo dolar sed dui.'
		}
	];
</script>

<section id="services" class="py-[5rem]">
	<div class="w-full">
		<h6 class="text-center text-primary uppercase tracking-widest text-sm font-medium">
			Our Services
		</h6>
		<h3 class="text-center text-4xl font-bold mt-2 mb-12">Best Services From Us</h3>
		<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4">
			{#each services as service}
				<ServiceCard {...service} href="/services" />
			{/each}
		</div>
	</div>
</section>
