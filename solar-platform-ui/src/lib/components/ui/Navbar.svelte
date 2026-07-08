<script lang="ts">
	import { page } from '$app/stores';
	import { MapPin, Phone, Clock, Menu, X as XIcon } from 'lucide-svelte';
	import {
		SiFacebook as Facebook,
		SiInstagram as Instagram,
		SiYoutube as Youtube
	} from '@icons-pack/svelte-simple-icons';
	import Linkedin from '$lib/components/icons/LinkedIn.svelte';
	import Button from '$lib/components/ui/Button.svelte';

	const links = [
		{ label: 'Home', href: '/' },
		{ label: 'About', href: '/about' },
		{ label: 'Services', href: '/services' },
		{ label: 'Blog', href: '/blog' },
		{ label: 'Contact', href: '/contact' }
	];

	const socials = [
		{ icon: Facebook, href: '#' },
		{ icon: XIcon, href: '#' },
		{ icon: Linkedin, href: '#' },
		{ icon: Instagram, href: '#' },
		{ icon: Youtube, href: '#' }
	];

	let open = $state(false);
</script>

<!-- Top bar -->
<div class="bg-sola-black text-white text-xs py-2">
	<div class="container mx-auto flex flex-wrap justify-between items-center px-4">
		<ul class="flex flex-wrap gap-4 list-none m-0 p-0">
			<li class="flex items-center gap-1">
				<MapPin size={13} class="text-primary" />
				State Road 54 Trinity, Florida
			</li>
			<li class="flex items-center gap-1">
				<Phone size={13} class="text-primary" />
				+666 333 9999
			</li>
			<li class="flex items-center gap-1">
				<Clock size={13} class="text-primary" />
				8:00-18:00, Sat: Closed
			</li>
		</ul>
		<ul class="flex gap-3 list-none m-0 p-0">
			{#each socials as { icon: Icon, href }}
				<li>
					<a {href} class="text-white hover:text-primary transition-colors">
						<Icon size={15} />
					</a>
				</li>
			{/each}
		</ul>
	</div>
</div>

<!-- Main nav -->
<nav class="bg-white shadow-sm py-4">
	<div class="container mx-auto flex justify-between items-center px-4">
		<!-- Logo -->
		<a href="/" class="text-2xl font-bold font-heading text-sola-black">Sola</a>

		<!-- Desktop links -->
		<ul class="hidden lg:flex items-center gap-6 list-none m-0 p-0">
			{#each links as { label, href }}
				<li>
					<a
						{href}
						class="text-sm uppercase tracking-wider font-medium transition-colors hover:text-primary
							{$page.url.pathname === href ? 'text-primary' : 'text-sola-dark'}"
					>
						{label}
					</a>
				</li>
			{/each}
		</ul>

		<!-- CTA + hamburger -->
		<div class="flex items-center gap-4">
			<div class="hidden lg:block">
				<Button variant="outline" href="/contact">Get a Quote</Button>
			</div>
			<button
				class="lg:hidden text-sola-black"
				onclick={() => (open = !open)}
				aria-label="Toggle menu"
			>
				{#if open}
					<XIcon size={28} />
				{:else}
					<Menu size={28} />
				{/if}
			</button>
		</div>
	</div>

	<!-- Mobile menu -->
	{#if open}
		<ul class="lg:hidden flex flex-col px-6 pb-4 gap-4 list-none m-0 p-0 pt-4 border-t">
			{#each links as { label, href }}
				<li>
					<a
						{href}
						onclick={() => (open = false)}
						class="text-lg uppercase tracking-wider font-medium transition-colors hover:text-primary
							{$page.url.pathname === href ? 'text-primary' : 'text-sola-dark'}"
					>
						{label}
					</a>
				</li>
			{/each}
			<li class="pt-2">
				<Button variant="outline" href="/contact">Get a Quote</Button>
			</li>
		</ul>
	{/if}
</nav>
