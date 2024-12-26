<script lang="ts">
	import '../app.css';
	import { ModeWatcher } from 'mode-watcher';
	import DesktopSideNavBar from './DesktopSideNavBar.svelte';
	import MobileSideNavBar from './MobileSideNavBar.svelte';
	import GlobalSearch from './GlobalSearch.svelte';

	import { page } from '$app/state';
	import UserButton from './UserButton.svelte';
	let { children } = $props();
</script>

<svelte:head>
	<title>RX Brilliant</title>
</svelte:head>

<!-- Dark Mode / Light Mode Watcher-->
<ModeWatcher />
<!-- Side Navigation Bar -->
<div class="flex min-h-screen w-full flex-col bg-muted/40">
	<DesktopSideNavBar />
	<div class="flex flex-col sm:gap-4 sm:py-4 sm:pl-14">
		<header
			class="sticky top-0 z-30 flex h-14 items-center gap-4 border-b bg-background px-4 sm:static sm:h-auto sm:border-0 sm:bg-transparent sm:px-6"
		>
			<MobileSideNavBar />
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
