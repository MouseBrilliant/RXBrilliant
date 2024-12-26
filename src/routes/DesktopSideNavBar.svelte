<script>
	import { Home, Search, Gamepad, Info, PanelLeft, Settings, CircleUserRound } from 'lucide-svelte';
	import { page } from '$app/state';
	import { Tooltip, TooltipTrigger, TooltipContent } from '$lib/components/ui/tooltip';
</script>

<aside class="fixed inset-y-0 left-0 z-10 hidden w-14 flex-col border-r bg-background sm:flex">
	<!-- Navigation Bar Items Top Left-->
	<nav class="flex flex-col items-center gap-4 px-2 py-4">
		<!-- Navigation Items-->
		<!-- Logo -->
		<Tooltip>
			<TooltipTrigger asChild let:builder>
				<a
					href="##"
					class="group flex h-9 w-9 shrink-0 items-center justify-center gap-2 rounded-full bg-primary text-lg font-semibold text-primary-foreground md:h-8 md:w-8 md:text-base"
					use:builder.action
					{...builder}
				>
					<Gamepad class="h-4 w-4 transition-all group-hover:scale-110" />
					<span class="sr-only">RX Brilliant</span>
				</a>
			</TooltipTrigger>
			<TooltipContent side="right">RX Brilliant</TooltipContent>
		</Tooltip>
		<!-- Discover -->
		<Tooltip>
			<TooltipTrigger asChild let:builder>
				<a
					href="##"
					class="flex h-9 w-9 items-center justify-center rounded-lg text-muted-foreground transition-colors hover:text-foreground md:h-8 md:w-8"
					use:builder.action
					{...builder}
				>
					<Search class="h-5 w-5" />
					<span class="sr-only">Discover</span>
				</a></TooltipTrigger
			>
			<TooltipContent side="right">Discover</TooltipContent>
		</Tooltip>
		<!-- Home -->
		<Tooltip>
			<TooltipTrigger asChild let:builder>
				<a
					href="##"
					class="flex h-9 w-9 items-center justify-center rounded-lg text-muted-foreground transition-colors hover:text-foreground md:h-8 md:w-8"
					use:builder.action
					{...builder}
				>
					<Home class="h-5 w-5" />
					<span class="sr-only">Home</span>
				</a></TooltipTrigger
			>
			<TooltipContent side="right">Home</TooltipContent>
		</Tooltip>
		<!-- Info -->
		<Tooltip>
			<TooltipTrigger asChild let:builder>
				<a
					href="##"
					class="flex h-9 w-9 items-center justify-center rounded-lg text-muted-foreground transition-colors hover:text-foreground md:h-8 md:w-8"
					use:builder.action
					{...builder}
				>
					<Info class="h-5 w-5" />
					<span class="sr-only">Info</span>
				</a></TooltipTrigger
			>
			<TooltipContent side="right">Info</TooltipContent>
		</Tooltip>
	</nav>
	<!--Navigation Bar Settings-->
	<nav class="mt-auto flex flex-col items-center gap-4 px-2 py-4">
		<Tooltip>
			<TooltipTrigger asChild let:builder>
				<a
					href="##"
					class="flex h-9 w-9 items-center justify-center rounded-lg text-muted-foreground transition-colors hover:text-foreground md:h-8 md:w-8"
					use:builder.action
					{...builder}
				>
					<Settings class="h-5 w-5" />
					<span class="sr-only">Settings</span>
				</a>
			</TooltipTrigger>
			<TooltipContent side="right">Settings</TooltipContent>
		</Tooltip>
	</nav>
</aside>
