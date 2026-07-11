<script lang="ts">
	const projects = [
		{
			image: '/images/project1.jpg',
			category: 'energy',
			title: 'Houston Roof Solaring',
			href: '/projects/1'
		},
		{
			image: '/images/project2.jpg',
			category: 'wind',
			title: 'City Solar Light',
			href: '/projects/2'
		},
		{
			image: '/images/project3.jpg',
			category: 'renew',
			title: 'Soar Power House',
			href: '/projects/3'
		},
		{
			image: '/images/project4.jpg',
			category: 'wind',
			title: 'Rooftop Solaring',
			href: '/projects/4'
		},
		{
			image: '/images/project5.jpg',
			category: 'energy',
			title: 'Adjustment Solaring',
			href: '/projects/5'
		},
		{
			image: '/images/project6.jpg',
			category: 'enew',
			title: 'Wind Turnining',
			href: '/projects/6'
		}
	];
	const filters = [
		{ label: 'All', value: 'all' },
		{ label: 'Energy', value: 'energy' },
		{ label: 'Wind Turbines', value: 'wind' },
		{ label: 'Renewable', value: 'renew' }
	];
	let active = $state('all');
	const filtered = $derived(
		active === 'all' ? projects : projects.filter((p) => p.category === active)
	);
</script>

<section id="projects" class="py-[10rem]">
	<div class="container mx-auto px-[10rem]">
		<h6 class="text-primary uppercase tracking-widest text-sm font-medium text-center">
			Our Projects
		</h6>
		<h3 class="text-4xl font-bold mt-2 mb-4 text-center">View our Latest Projects</h3>
		<div class="flex flex-wrap justify-center gap-3 mt-8">
			{#each filters as f}
				<button
					onclick={() => (active = f.value)}
					class="px-4 py-1 rounded-full uppercase text-sm tracking-wider transition-all duration-300 border {active ===
					f.value
						? 'bg-primary text-white'
						: 'text-sola-dark hover:bg-primary hover:text-white'}">{f.label}</button
				>
			{/each}
		</div>
		<div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6 mt-8">
			{#each filtered as project}
				<div>
					<a href={project.href}>
						<img src={project.image} alt={project.title} class="w-full h-auto" />
					</a>
					<h6 class="text-primary mt-3 uppercase">{project.category}</h6>
					<h3 class="text-xl font-bold">
						<a href={project.href} class="hover:text-primary transition-colors">{project.title}</a>
					</h3>
				</div>
			{/each}
		</div>
	</div>
</section>
