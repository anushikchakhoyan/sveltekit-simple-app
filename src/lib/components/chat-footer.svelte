<script>
	import HomeIcon from '$lib/icons/home-icon.svelte';
	import HelpIcon from '$lib/icons/help-icon.svelte';
	import MessageIcon from '$lib/icons/message-icon.svelte';
	import { goto } from '$app/navigation';
	import { page } from '$app/stores';

	const navigateTo = (path) => {
		goto(path);
	};

	const navigationItems = [
		{
			title: 'Home',
			url: '/',
			Icon: HomeIcon
		},
		{
			title: 'Messages',
			url: '/messages',
			Icon: MessageIcon
		},
		{
			title: 'Help',
			url: '/help',
			Icon: HelpIcon
		}
	];
</script>

<div
	class="flex w-full items-center justify-between rounded-lg border border-black bg-gray-900 py-3.5"
>
	{#each navigationItems as { title, url, Icon }}
		<button
			on:click={() => navigateTo(url)}
			class="flex flex-1 cursor-pointer flex-col items-center gap-2 text-white transition-colors hover:text-cyan-500"
			class:active={$page.url.pathname === url}
		>
			<Icon />
			<p class="text-sm leading-snug font-normal tracking-normal">{title}</p>
		</button>
	{/each}
</div>

<style lang="postcss">
	@reference "tailwindcss";
	.active p {
		@apply font-bold;
	}
</style>
