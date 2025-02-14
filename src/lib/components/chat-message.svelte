<script>
	import SendIcon from '$lib/icons/send-icon.svelte';
</script>

<div
	class="rounded-10 flex w-full items-center justify-between border border-cyan-500 bg-gray-800 p-4"
>
	<div class="flex flex-col items-start">
		<p class="text-white">Send us a message</p>
		<p class="text-sm leading-5 font-normal text-gray-500">We typically reply within a day</p>
	</div>
	<button class="flex h-10 w-10 cursor-pointer items-center justify-end text-cyan-500">
		<SendIcon />
	</button>
</div>
