<script lang="ts">
	import { MapPin, Phone, Mail, X as XIcon, Send } from 'lucide-svelte';
	import {
		SiFacebook as Facebook,
		SiInstagram as Instagram,
		SiYoutube as Youtube
	} from '@icons-pack/svelte-simple-icons';
	import Linkedin from '$lib/components/icons/LinkedIn.svelte';
	import Button from '$lib/components/ui/Button.svelte';
	const socials = [
		{ icon: Facebook, href: '#' },
		{ icon: XIcon, href: '#' },
		{ icon: Linkedin, href: '#' },
		{ icon: Instagram, href: '#' },
		{ icon: Youtube, href: '#' }
	];

	const quickLinks = [
		{ label: 'About Us', href: '/about' },
		{ label: 'Our Services', href: '/services' },
		{ label: 'Privacy Policy', href: '/privacy' },
		{ label: 'Contact Us', href: '/contact' },
		{ label: 'Support', href: '/support' }
	];

	const gallery = [
		'/images/post1.jpg',
		'/images/post2.jpg',
		'/images/post3.jpg',
		'/images/post4.jpg',
		'/images/post5.jpg',
		'/images/post6.jpg'
	];

	let email = $state('');
</script>

<section id="footer" class="bg-sola-cream border-t border-gray-200 mt-10">
	<div class="container mx-auto px-4">
		<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8 py-16">
			<!-- Address -->
			<div>
				<h5 class="py-3 text-[20px]">Our Address</h5>
				<ul class="space-y-2 text-sm list-none p-0 m-0">
					<li class="flex items-center gap-2">
						<MapPin size={16} class="text-primary shrink-0" />
						State Road 54 Trinity, Florida
					</li>
					<li class="flex items-center gap-2">
						<Phone size={16} class="text-primary shrink-0" />
						+666 333 9999
					</li>
					<li class="flex items-center gap-2">
						<Mail size={16} class="text-primary shrink-0" />
						yourdomain@email.com
					</li>
				</ul>
				<ul class="flex gap-4 list-none p-0 mt-6">
					{#each socials as { icon: Icon, href }}
						<li>
							<a {href} class="text-sola-dark hover:text-primary transition-colors">
								<Icon size={16} />
							</a>
						</li>
					{/each}
				</ul>
			</div>

			<!-- Quick Links -->
			<div>
				<h5 class="py-3 text-[20px]">Quick Links</h5>
				<ul class="space-y-2 list-none p-0 m-0">
					{#each quickLinks as { label, href }}
						<li>
							<a
								{href}
								class="text-sm uppercase text-sola-dark hover:text-primary transition-colors"
							>
								{label}
							</a>
						</li>
					{/each}
				</ul>
			</div>

			<!-- Gallery -->
			<div>
				<h5 class="py-3 text-[20px]">Project Gallery</h5>
				<div class="grid grid-cols-3 gap-1">
					{#each gallery as src}
						<a href={src}>
							<img {src} alt="project" class="w-full h-20 object-cover" />
						</a>
					{/each}
				</div>
			</div>

			<!-- Newsletter -->
			<div>
				<h5 class="py-3 text-[20px]">Our Newsletter</h5>
				<p class="text-sm mb-4">Dolor amet sit justo amet elitr clita ipsum elitr est.</p>
				<div class="relative">
					<input
						type="email"
						bind:value={email}
						placeholder="Your email address"
						class="w-full rounded-full px-4 py-2 bg-transparent border border-gray-300 text-sm pr-12 focus:outline-none focus:border-primary"
					/>
					<Button
						variant="raw"
						class="absolute top-1/2 right-1 -translate-y-1/2 bg-primary rounded-full p-1.5 
						text-white hover:opacity-90 transition-opacity cursor-pointer"
						aria-label="Subscribe"
					>
						<Send size={16} />
					</Button>
				</div>
			</div>
		</div>
	</div>

	<hr class="border-gray-300" />

	<div class="container mx-auto px-4">
		<div class="flex flex-col md:flex-row justify-between items-center py-4 text-sm text-sola-dark">
			<p>© 2026 Sola - All rights reserved</p>
		</div>
	</div>
</section>
