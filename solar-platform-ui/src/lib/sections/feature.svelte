<script lang="ts">
	import FeatureItem from '$lib/components/ui/FeatureItem.svelte';
</script>

<section id="feature" class="pt-0 py-[5rem]">
	<div class="conatiner mx-auto px-[10rem]">
		<h6 class="text-primary uppercase tracking-widest text-sm font-medium">Why Choose Us!</h6>
		<h3 class="text-4xl font-bold mt-2 mb-4">Our motive to change world</h3>
		<p>
			Aliqu diam amet diam et dolor diam ipsum sit tet lorem sit clita duo eos. <br /> Clita erat ipsum
			et lorem et sit, sed tempor erat elitr rebum at clita.
		</p>
		<div class="grid grid-cols-2 lg:grid-cols-4">
			<FeatureItem number="01" label="Quality Services" />
			<FeatureItem number="02" label="Expertise workers" />
			<FeatureItem number="03" label="Free consulting" />
			<FeatureItem number="04" label="Customer support" />
		</div>
	</div>
</section>
