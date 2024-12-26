<script>
	import { Sheet, SheetContent, SheetTrigger } from '$lib/components/ui/sheet';
	import { Home, Search, Gamepad, Info, PanelLeft, Settings, CircleUserRound } from 'lucide-svelte';
	import { Button } from '$lib/components/ui/button';
</script>

<!-- Mobile Side Sheet -->
<Sheet>
	<SheetTrigger asChild let:builder>
		<Button builders={[builder]} size="icon" variant="outline" class="sm:hidden">
			<PanelLeft class="h-5 w-5" />
			<span class="sr-only">Toggle Menu</span>
		</Button>
	</SheetTrigger>
	<SheetContent side="left" class="sm:max-w-xs">
		<nav class="grid gap-6 text-lg font-medium">
			<!-- Logo -->
			<a
				href="##"
				class="group flex h-10 w-10 shrink-0 items-center justify-center gap-2 rounded-full bg-primary text-lg font-semibold text-primary-foreground md:text-base"
			>
				<Gamepad class="h-5 w-5 transition-all group-hover:scale-110" />
				<span class="sr-only">RX Brilliant</span>
			</a>
			<!-- Discover -->
			<a href="##" class="flex items-center gap-4 px-2.5 text-foreground">
				<Search class="h-5 w-5" />
				Discover
			</a>
			<!-- Home -->
			<a
				href="##"
				class="flex items-center gap-4 px-2.5 text-muted-foreground hover:text-foreground"
			>
				<Home class="h-5 w-5" />
				Home
			</a>

			<!-- Settings -->
			<a
				href="##"
				class="flex items-center gap-4 px-2.5 text-muted-foreground hover:text-foreground"
			>
				<Settings class="h-5 w-5" />
				Settings
			</a>
		</nav>
	</SheetContent>
</Sheet>
