<script lang="ts">
	let {
		image,
		title,
		description,
		href
	}: {
		image: string;
		title: string;
		description: string;
		href: string;
	} = $props();
</script>

<div
	class="relative overflow-hidden group bg-white hover:bg-primary transition-colors duration-500"
>
	<img
		src={image}
		alt={title}
		class="w-full h-full object-cover transition-opacity duration-500 group-hover:opacity-20"
	/>
	<div class="absolute bottom-0 p-8 text-white">
		<h5 class="text-white">{title}</h5>
		<p class="text-white text-sm">{description}</p>
		<a {href} class="text-white underline">
			<h6 class="text-white">Read more</h6>
		</a>
	</div>
</div>
