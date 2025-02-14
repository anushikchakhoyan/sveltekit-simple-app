<script lang="ts">
	import { goto } from '$app/navigation';
	import SendIcon from '$lib/icons/send-icon.svelte';
	import avatar from '$lib/images/user1.png';
</script>

<div
	class="relative flex h-80 flex-col justify-between rounded-lg border border-cyan-500 bg-gray-800 p-1"
>
	<!-- Message Display Section -->
	<div class="flex flex-col">
		<button
			on:click={() => goto('/')}
			class="absolute top-1 right-1 h-10 w-10 cursor-pointer text-sm text-white/80">X</button
		>
		<div class="flex items-center gap-3 px-3 py-6 text-white">
			<img src={avatar} alt="User" class="h-12 w-12" />
			<div>
				<p class="text-base">Chat with us!</p>
				<p class="font-inter text-sm leading-5 font-normal text-gray-500">
					We typically reply within a day
				</p>
			</div>
		</div>
	</div>
	<!-- Message Input Section -->
	<div class="relative flex items-center gap-1 border-t border-gray-900/50 p-1">
		<textarea
			class="h-10 flex-1 resize-none p-2 pr-8 text-sm text-white
			placeholder-gray-500 focus:ring-0 focus:outline-none"
			placeholder="Type your message..."
		></textarea>
		<!-- Button to send the message -->
		<button
			class="absolute right-1 flex h-10 w-10 cursor-pointer items-center justify-center
			  text-white transition hover:text-cyan-500"
		>
			<SendIcon />
		</button>
	</div>
</div>
