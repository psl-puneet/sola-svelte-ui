<script lang="ts">
	import './layout.css';
	import Navbar from '$lib/components/ui/Navbar.svelte';
	import Footer from '$lib/components/ui/Footer.svelte';
	import ContactUs from '$lib/sections/contact-us.svelte';
	let { children }: { children: () => any } = $props();
</script>

<div class="flex flex-col min-h-screen">
	<Navbar />
	<main class="flex-1">
		{@render children()}
	</main>
	<ContactUs/>
	<Footer />
</div>
