<script lang="ts">
	import { cn } from '$lib/utils';
	import type { Snippet } from 'svelte';
	type NonEmptyString = string;

	let {
		variant = 'primary',
		href,
		onclick,
		class: cls = '',
		'aria-label': ariaLabel,
		children
	}: {
		variant?: 'primary' | 'outline' | 'raw';
		href?: NonEmptyString;
		onclick?: () => void;
		class?: string;
		'aria-label'?: string;
		children: Snippet;
	} = $props();

	const base =
		'inline-block px-8 py-4 rounded-full text-sm uppercase tracking-widest transition-all duration-300 cursor-pointer border';
	const variants: Record<string, string> = {
		primary: 'bg-primary text-primary-foreground border-primary hover:opacity-90',
		outline:
			'bg-transparent text-primary border-primary hover:bg-primary hover:text-primary-foreground',
		raw: ''
	};

	const classes = $derived(
		variant === 'raw' ? cn(cls) : cn(base, variants[variant] ?? variants.primary, cls)
	);
</script>

{#if href}
	<a {href} class={classes} aria-label={ariaLabel}>{@render children()}</a>
{:else}
	<button {onclick} class={classes} aria-label={ariaLabel}>{@render children()}</button>
{/if}
