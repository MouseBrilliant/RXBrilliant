<script lang="ts">
	import { page } from '$app/state';
</script>

<div class="flex h-screen items-center justify-center">
	<h1 class="scroll-m-20 text-4xl font-extrabold tracking-tight lg:text-5xl">
		{page.status}: {page.error?.message}
	</h1>
	<p class="leading-7 [&:not(:first-child)]:mt-6">
		Looks like you've ventured into the unknown digital realm.
	</p>
</div>
