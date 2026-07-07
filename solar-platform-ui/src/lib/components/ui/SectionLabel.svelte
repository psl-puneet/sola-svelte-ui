<script lang="ts">
    import {cn} from '$lib/utils'
	let { children, class: cls = '' }: { children: () => any; class?: string } = $props();
</script>

<p class={cn('text-primary text-sm font-medium uppercase tracking-widest mt-3', cls)}>
	{@render children()}
</p>
