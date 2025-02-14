<script>
	import SearchIcon from '$lib/icons/search-icon.svelte';
	import ArrowLeftIcon from '$lib/icons/arrow-left-icon.svelte';

	export let suggestions = [
		'In-game bonuses and free spins',
		'Crypto deposit still not credited?',
		'EigerX VIP program overview',
		'Achievements and awards'
	];
</script>

<div class="w-full rounded-lg border border-black bg-gray-900 p-1.5">
	<div class="relative flex items-center">
		<input
			type="text"
			placeholder="Search for help"
			class="font-inter w-full rounded-lg bg-gray-800 py-2 pr-7 pl-2 text-white
			placeholder-white focus:ring-1 focus:ring-cyan-500 focus:outline-none"
		/>
		<p class="absolute top-3 right-3"><SearchIcon /></p>
	</div>

	<ul class="mt-2 space-y-2">
		{#each suggestions as item}
			<li class="group flex cursor-pointer items-center justify-between px-3 py-2">
				<span class="font-inter text-sm font-normal text-white group-hover:text-cyan-500"
					>{item}</span
				>
				<p class="flex h-4 w-4 items-center justify-center"><ArrowLeftIcon /></p>
			</li>
		{/each}
	</ul>
</div>
