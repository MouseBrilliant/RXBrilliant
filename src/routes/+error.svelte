<script lang="ts">
	import { page } from '$app/state';
	import { Button } from '$lib/components/ui/button';
	import { Gamepad } from 'lucide-svelte';
</script>

<div class="container mx-auto">
	<h1 class="scroll-m-20 pb-4 text-4xl font-extrabold tracking-tight lg:text-5xl">
		{page.status}
	</h1>
	{#if page.error}
		<code class="relative rounded bg-muted px-[0.3rem] py-[0.2rem] font-mono text-sm font-semibold">
			{page.error?.message}
		</code>
	{/if}
	<p class="pb-8 leading-7 [&:not(:first-child)]:mt-6">
		Looks like you've ventured into the unknown digital realm.
	</p>
	<Button variant="destructive" href="/">
		<Gamepad class="mr-2 h-4 w-4" />
		Return to RX Brilliant
	</Button>
</div>
