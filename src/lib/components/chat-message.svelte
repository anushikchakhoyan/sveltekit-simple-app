<script>
	import SendIcon from '$lib/icons/send-icon.svelte';
	import { goto } from '$app/navigation';

	const navigateTo = (path) => {
		goto(path);
	};
</script>

<div
	class="rounded-10 flex w-full items-center justify-between border border-cyan-500 bg-gray-800 p-4"
>
	<!-- Heading for the message box -->
	<div class="flex flex-col items-start">
		<p class="font-inter font-sm leading-5 font-bold text-white">Send us a message</p>
		<p class="font-inter text-sm leading-5 font-normal text-gray-500">
			We typically reply within a day
		</p>
	</div>
	<!-- Button to navigate to the messages page -->
	<button
		on:click={() => navigateTo('/messages')}
		class="flex h-10 w-10 cursor-pointer items-center justify-end text-cyan-500"
	>
		<SendIcon />
	</button>
</div>
