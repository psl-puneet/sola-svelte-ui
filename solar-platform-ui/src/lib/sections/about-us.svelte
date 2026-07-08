<script lang="ts">
	import { CirclePlay as Play } from 'lucide-svelte';
	import Button from '$lib/components/ui/Button.svelte';
	import SectionLabel from '$lib/components/ui/SectionLabel.svelte';
</script>

<section id="about-us" class="py-[10rem]">
	<div class="container mx-auto px-4">
		<div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
			<!-- Image and Play Button -->
			<div class="relative">
				<img src="/images/about.png" alt="About Us" class="w-full h-auto" />
				<a
					href="https://www.youtube.com/embed/W_tIumKa8VY"
					target="_blank"
					class="play-btn absolute top-1/2 left-1/2 text-primary"
					aria-label="Play Video"
				>
					<Play size={70} class="animate-pulse" />
				</a>
			</div>
			<!-- Text -->
			<div>
				<SectionLabel>About Us</SectionLabel>
				<h2 class="text-4xl font-bold mb-4">Among the Top 10 Solar & Renewable Energy Industry</h2>
				<p class="mb-6">
					Lorem ipsum dolor sit amet consectetur adipisicing elit. Veniam similique modi earum
					soluta doloribus. Sunt, vel tenetur doloremque porro architecto cum animi, repellendus
					illum aliquam eum nulla odit voluptatum iste.
				</p>
				<Button href="/about">About Us</Button>
			</div>
		</div>
	</div>
</section>

<style>
	@keyframes play {
		0% {
			transform: translate(-50%, -50%) scale(0.8);
		}
        100% {
            transform: translate(-50%, -50%) scale(1.1);
        }
	}

    a.play-btn{
        animation: play 1.5s alternate infinite ease-in
    }
</style>
