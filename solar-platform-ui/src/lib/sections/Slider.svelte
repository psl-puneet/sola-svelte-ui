<script lang="ts">
	import { onMount } from 'svelte';
	import { register } from 'swiper/element/bundle';

	const slides = [
		{
			image: '/images/slider-image.jpg',
			title: 'Top Solar and Renewable Energy',
			description: 'Vero elitr justo clita dolor at sed stet sit diam no.'
		},
		{
			image: '/images/slider-image1.jpg',
			title: 'Clean Energy Solutions',
			description: 'Powering a sustainable future with renewable energy.'
		},
		{
			image: '/images/slider-image2.jpg',
			title: 'Save Energy. Save Earth.',
			description: 'Efficient solutions for homes and businesses.'
		}
	];

	onMount(() => {
		register();
	});
</script>

<svelte:head>
	<link
		rel="stylesheet"
		href="https://cdn.jsdelivr.net/npm/swiper@14/swiper-bundle.min.css"
	/>
</svelte:head>

<swiper-container
	effect="fade"
	loop="true"
	navigation="true"
	pagination="true"
	autoplay-delay="4000"
	speed="1000"
	class="h-screen"
>
	{#each slides as slide}
		<swiper-slide>
			<div
				class="relative flex h-screen items-center bg-cover bg-center"
				style={`background-image:url(${slide.image})`}
			>
				<div class="absolute inset-0 bg-black/50"></div>

				<div class="relative z-10 mx-auto max-w-6xl px-6">
					<h1 class="text-5xl font-bold text-white md:text-7xl">
						{slide.title}
					</h1>

					<p class="mt-6 max-w-xl text-lg text-gray-200">
						{slide.description}
					</p>
				</div>
			</div>
		</swiper-slide>
	{/each}
</swiper-container>