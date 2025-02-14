<script>
	import SearchIcon from '$lib/icons/search-icon.svelte';
	import ArrowLeftIcon from '$lib/icons/arrow-left-icon.svelte';

	export let suggestions = [
		'In-game bonuses and free spins',
		'Crypto deposit still not credited?',
		'EigerX VIP program overview',
		'Achievements and awards'
	];

	let searchQuery = '';
	$: filteredSuggestions = searchQuery
		? suggestions.filter((item) => item.toLowerCase().includes(searchQuery.toLowerCase()))
		: suggestions;
</script>

<div class="min-height-14.375 w-full rounded-lg border border-black bg-gray-900 p-1.5">
	<div class="relative flex items-center">
		<input
			type="text"
			placeholder="Search for help"
			bind:value={searchQuery}
			class="font-inter w-full rounded-lg bg-gray-800 py-2 pr-7 pl-2 text-white
			placeholder-white focus:ring-1 focus:ring-cyan-500 focus:outline-none"
		/>
		<p class="absolute top-3 right-3"><SearchIcon /></p>
	</div>
	{#if filteredSuggestions.length > 0}
		<ul class="mt-2 space-y-2">
			{#each filteredSuggestions as item}
				<li class="group flex cursor-pointer items-center justify-between px-3 py-2">
					<span class="font-inter text-sm font-normal text-white group-hover:text-cyan-500">
						{item}
					</span>
					<p class="flex h-4 w-4 items-center justify-center"><ArrowLeftIcon /></p>
				</li>
			{/each}
		</ul>
	{:else}
		<p class="font-inter py-5 text-center text-sm text-white">No results found.</p>
	{/if}
</div>
