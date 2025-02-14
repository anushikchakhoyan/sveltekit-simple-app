<script lang="ts">
	import SearchIcon from '$lib/icons/search-icon.svelte';
	import ArrowLeftIcon from '$lib/icons/arrow-left-icon.svelte';
	import { slide } from 'svelte/transition';

	export let suggestions = [
		{
			title: 'In-game bonuses and free spins',
			details: 'Learn how to claim bonuses and get free spins.'
		},
		{
			title: 'Crypto deposit still not credited?',
			details: 'Check common issues and solutions for crypto deposits.'
		},
		{
			title: 'EigerX VIP program overview',
			details: 'Discover the benefits of the VIP program at EigerX.'
		},
		{ title: 'Achievements and awards', details: 'View your in-game achievements and rewards.' }
	];

	let searchQuery = '';
	let expandedIndex = null as null | number;

	$: filteredSuggestions = suggestions.filter((item) =>
		item.title.toLowerCase().includes(searchQuery.toLowerCase())
	);

	function toggleExpand(index: number): void {
		expandedIndex = expandedIndex === index ? null : index;
	}
</script>

<div class="min-h-14.375 w-full rounded-lg border border-black bg-gray-900 p-1.5">
	<!-- Search Input -->
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

	<!-- Collapsible Search content -->
	{#if filteredSuggestions.length > 0}
		<ul class="mt-2 space-y-2">
			{#each filteredSuggestions as item, index}
				<li class="group rounded-lg px-3 py-2 transition-colors duration-300">
					<button
						type="button"
						on:click={() => toggleExpand(index)}
						class="flex w-full cursor-pointer items-center justify-between"
					>
						<span class="font-inter text-sm font-normal text-white group-hover:text-cyan-500">
							{item.title}
						</span>
						<p
							class="flex h-4 w-4 items-center justify-center transition-transform duration-300"
							style="transform: rotate({expandedIndex === index ? 90 : 0}deg);"
						>
							<ArrowLeftIcon />
						</p>
					</button>
					<!-- Collapsible Content -->
					{#if expandedIndex === index}
						<div class="mt-2 text-sm text-gray-400" transition:slide>
							{item.details}
						</div>
					{/if}
				</li>
			{/each}
		</ul>
	{:else}
		<p class="font-inter py-5 text-center text-sm text-white">No results found.</p>
	{/if}
</div>
