<script>
	import ChatHeader from './chat-header.svelte';
	import ChatTitle from './chat-title.svelte';
	import ChatSearch from './chat-search.svelte';
	import ChatMessage from './chat-message.svelte';
	import ChatFooter from './chat-footer.svelte';
</script>

<div class="m-4 flex w-25 flex-col overflow-hidden rounded-2xl border border-black shadow-lg">
	<div class="chat-top flex min-h-96 flex-1 flex-col justify-between bg-gray-400 p-3.5">
		<!-- Chat Header -->
		<ChatHeader />
		<div class="grid gap-4 py-8">
			<ChatTitle />
			<!-- Chat Message -->
			<ChatMessage />
		</div>
	</div>
	<div class="chat-bottom flex flex-col justify-end gap-4 bg-gray-900 p-3.5">
		<!-- Chat Search -->
		<ChatSearch />
		<!-- Chat Footer -->
		<ChatFooter />
	</div>
</div>

<style>
	.chat-top {
		background: linear-gradient(135deg, #0b0b0f 0%, #162729);
	}

	.chat-bottom {
		/* bg-gradient-to-r from-purple-500 to-pink-500 */
		background: linear-gradient(132.15deg, #0b0b0f 0%, rgba(26, 26, 34, 0.9) 95.96%);
	}
</style>
