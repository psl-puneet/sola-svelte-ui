<script lang="ts">
	import clsx from 'clsx';
	let {
		number,
		label,
		labelPosition = 'bottom-4 right-1/3 -translate-y-1/2'
	}: {
		number?: string;
		label?: string;
		labelPosition?: string;
	} = $props();
</script>

<div class="relative flex items-center">
	<h2
		style="color:#F9F4EC; -webkit-text-stroke: 1px #E6E1D9;"
		class="text-[130px] font-bold leading-none select-none"
	>
		{number}
	</h2>
	<h6 class={clsx('absolute', labelPosition)}>{label}</h6>
</div>
