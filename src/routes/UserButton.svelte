<script>
	import { Button } from '$lib/components/ui/button';
	import { CircleUserRound } from 'lucide-svelte';
	import {
		DropdownMenu,
		DropdownMenuTrigger,
		DropdownMenuItem,
		DropdownMenuContent,
		DropdownMenuSeparator,
		DropdownMenuLabel
	} from '$lib/components/ui/dropdown-menu';
</script>

<DropdownMenu>
	<DropdownMenuTrigger asChild let:builder>
		<Button variant="outline" size="icon" class="overflow-hidden rounded-full" builders={[builder]}>
			<CircleUserRound width={36} height={36} class="overflow-hidden rounded-full" />
		</Button>
	</DropdownMenuTrigger>
	<DropdownMenuContent align="end">
		<DropdownMenuLabel>My Account</DropdownMenuLabel>
		<DropdownMenuSeparator />
		<DropdownMenuItem>Settings</DropdownMenuItem>
		<DropdownMenuItem>Support</DropdownMenuItem>
		<DropdownMenuSeparator />
		<DropdownMenuItem>Logout</DropdownMenuItem>
	</DropdownMenuContent>
</DropdownMenu>
