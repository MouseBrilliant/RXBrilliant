<script lang="ts">
	import '../app.css';
	import { ModeWatcher } from 'mode-watcher';
	import GlobalSearch from './GlobalSearch.svelte';
	import UserButton from './UserButton.svelte';

	import { page } from '$app/state';
	import { afterNavigate } from '$app/navigation';

	import { Home, Search, Gamepad, Info, PanelLeft, Settings } from 'lucide-svelte';
	import { Tooltip, TooltipTrigger, TooltipContent } from '$lib/components/ui/tooltip';
	import { Sheet, SheetContent, SheetTrigger } from '$lib/components/ui/sheet';
	import { Button } from '$lib/components/ui/button';

	let atDiscoverPage = $state(page.url.pathname === '/discover');
	let atHomePage = $state(page.url.pathname === '/home');
	let atInfoPage = $state(page.url.pathname === '/info');
	let atSettingsPage = $state(page.url.pathname === '/settings');

	afterNavigate(() => {
		atDiscoverPage = page.url.pathname === '/discover';
		atHomePage = page.url.pathname === '/home';
		atInfoPage = page.url.pathname === '/info';
		atSettingsPage = page.url.pathname === '/settings';
	});

	let { children } = $props();
</script>

<svelte:head>
	<title>RX Brilliant</title>
</svelte:head>

<!-- Dark Mode / Light Mode Watcher-->
<ModeWatcher />
<!-- Side Navigation Bar -->
<div class="flex min-h-screen w-full flex-col bg-muted/40">
	<aside class="fixed inset-y-0 left-0 z-10 hidden w-14 flex-col border-r bg-background sm:flex">
		<!-- Navigation Bar Items Top Left-->
		<nav class="flex flex-col items-center gap-4 px-2 py-4">
			<!-- Navigation Items-->
			<!-- Logo -->
			<Tooltip>
				<TooltipTrigger asChild let:builder>
					<a
						href="/"
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
						href="/discover"
						class="{atDiscoverPage
							? 'text-action-foreground bg-accent'
							: 'text-muted-foreground'} flex h-9 w-9 items-center justify-center rounded-lg transition-colors hover:text-foreground md:h-8 md:w-8"
						use:builder.action
						{...builder}
					>
						<Search class="h-5 w-5" />
						<span class="sr-only">Discover</span>
					</a>
				</TooltipTrigger>
				<TooltipContent side="right">Discover</TooltipContent>
			</Tooltip>
			<!-- Home -->
			<Tooltip>
				<TooltipTrigger asChild let:builder>
					<a
						href="/home"
						class="{atHomePage
							? 'text-action-foreground bg-accent'
							: 'text-muted-foreground'} flex h-9 w-9 items-center justify-center rounded-lg transition-colors hover:text-foreground md:h-8 md:w-8"
						use:builder.action
						{...builder}
					>
						<Home class="h-5 w-5" />
						<span class="sr-only">Home</span>
					</a>
				</TooltipTrigger>
				<TooltipContent side="right">Home</TooltipContent>
			</Tooltip>
			<!-- Info -->
			<Tooltip>
				<TooltipTrigger asChild let:builder>
					<a
						href="/info"
						class="{atInfoPage
							? 'text-action-foreground bg-accent'
							: 'text-muted-foreground'} flex h-9 w-9 items-center justify-center rounded-lg transition-colors hover:text-foreground md:h-8 md:w-8"
						use:builder.action
						{...builder}
					>
						<Info class="h-5 w-5" />
						<span class="sr-only">Info</span>
					</a>
				</TooltipTrigger>
				<TooltipContent side="right">Info</TooltipContent>
			</Tooltip>
		</nav>
		<!--Navigation Bar Settings-->
		<nav class="mt-auto flex flex-col items-center gap-4 px-2 py-4">
			<Tooltip>
				<TooltipTrigger asChild let:builder>
					<a
						href="/settings"
						class="{atSettingsPage
							? 'text-action-foreground bg-accent'
							: 'text-muted-foreground'} flex h-9 w-9 items-center justify-center rounded-lg transition-colors hover:text-foreground md:h-8 md:w-8"
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

	<div class="flex flex-col sm:gap-4 sm:py-4 sm:pl-14">
		<header
			class="sticky top-0 z-30 flex h-14 items-center gap-4 border-b bg-background px-4 sm:static sm:h-auto sm:border-0 sm:bg-transparent sm:px-6"
		>
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
							href="/"
							class="group flex h-10 w-10 shrink-0 items-center justify-center gap-2 rounded-full bg-primary text-lg font-semibold text-primary-foreground md:text-base"
						>
							<Gamepad class="h-5 w-5 transition-all group-hover:scale-110" />
							<span class="sr-only">RX Brilliant</span>
						</a>
						<!-- Discover -->
						<a
							href="/discover"
							class="{atDiscoverPage
								? 'text-foreground'
								: 'text-muted-foreground'} flex items-center gap-4 px-2.5"
						>
							<Search class="h-5 w-5" />
							Discover
						</a>
						<!-- Home -->
						<a
							href="/home"
							class="{atHomePage
								? 'text-foreground'
								: 'text-muted-foreground'} flex items-center gap-4 px-2.5 hover:text-foreground"
						>
							<Home class="h-5 w-5" />
							Home
						</a>

						<!-- Settings -->
						<a
							href="/settings"
							class="{atSettingsPage
								? 'text-foreground'
								: 'text-muted-foreground'} flex items-center gap-4 px-2.5 hover:text-foreground"
						>
							<Settings class="h-5 w-5" />
							Settings
						</a>
					</nav>
				</SheetContent>
			</Sheet>

			<GlobalSearch />
			<UserButton />
		</header>
		<main
			class="grid flex-1 items-start gap-4 p-4 sm:px-6 sm:py-0 md:gap-8 lg:grid-cols-3 xl:grid-cols-3"
		>
			{@render children()}
		</main>
		<footer></footer>
	</div>
</div>
