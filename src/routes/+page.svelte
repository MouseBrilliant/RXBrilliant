<script>
	import { Sun, Moon } from 'lucide-svelte';
	import { Button } from '$lib/components/ui/button';
	import {
		DropdownMenuTrigger,
		DropdownMenuContent,
		DropdownMenu
	} from '$lib/components/ui/dropdown-menu/';
	import { resetMode, setMode } from 'mode-watcher';
	import { Trigger } from '$lib/components/ui/collapsible';
	import DropdownMenuItem from '$lib/components/ui/dropdown-menu/dropdown-menu-item.svelte';
</script>

<h1 class="scroll-m-20 text-4xl font-extrabold tracking-tight lg:text-5xl">Welcome to SvelteKit</h1>
<p class="leading-7 [&:not(:first-child)]:mt-6">
	Visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the documentation
</p>

<DropdownMenu>
	<DropdownMenuTrigger asChild let:builder>
		<Button builders={[builder]} variant="outline" size="icon">
			<Sun
				class="h-[1.2rem] w-[1.2rem] rotate-0 scale-100 transition-all dark:-rotate-90 dark:scale-0"
			/>
			<Moon
				class="absolute h-[1.2rem] w-[1.2rem] rotate-90 scale-0 transition-all dark:rotate-0 dark:scale-100"
			/>
			<span class="sr-only">Toggle theme</span>
		</Button>
	</DropdownMenuTrigger>
	<DropdownMenuContent align="end">
		<DropdownMenuItem on:click={() => setMode('light')}>Light</DropdownMenuItem>
		<DropdownMenuItem on:click={() => setMode('dark')}>Dark</DropdownMenuItem>
		<DropdownMenuItem on:click={() => resetMode()}>System</DropdownMenuItem>
	</DropdownMenuContent>
</DropdownMenu>
