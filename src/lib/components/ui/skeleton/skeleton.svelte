<script lang="ts">
	import type { HTMLAttributes } from 'svelte/elements';

	import { type WithElementRef, type WithoutChildren, cn } from '$lib/utils.js';

	let {
		ref = $bindable(null),
		class: className,
		...restProps
	}: WithoutChildren<WithElementRef<HTMLAttributes<HTMLDivElement>>> = $props();
</script>

<div
	bind:this={ref}
	data-slot="skeleton"
	class={cn('bg-accent animate-pulse rounded-md', className)}
	{...restProps}
></div>
