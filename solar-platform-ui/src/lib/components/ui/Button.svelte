<script lang="ts">
	let {
		variant = 'primary',
		href,
		onclick,
		children
	}: {
		variant?: 'primary' | 'outline';
		href?: string;
		onclick?: () => void;
		children: () => any;
	} = $props();

	const base =
		'inline-block px-8 py-4 rounded-full text-sm uppercase tracking-widest transition-all duration-300 cursor-pointer border';
	const variants: Record<string, string> = {
		primary: 'bg-primary text-primary-foreground border-primary hover:opacity-90',
		outline:
			'bg-transparent text-primary border-primary hover:bg-primary hover:text-primary-foreground'
	};

	const cls = `${base} ${variants[variant] ?? variants.primary}`;
</script>

{#if href}
	<a {href} class={cls}>{@render children()}</a>
{:else}
	<button {onclick} class={cls}>{@render children()}</button>
{/if}
