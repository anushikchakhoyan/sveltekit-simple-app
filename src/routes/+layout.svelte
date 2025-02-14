<script lang="ts">
	import { i18n } from '$lib/i18n';
	import { ParaglideJS } from '@inlang/paraglide-sveltekit';
	import ChatFooter from '$lib/components/chat-footer.svelte';
	import ChatHeader from '$lib/components/chat-header.svelte';

	import '../app.css';

	let { children } = $props();
</script>

<ParaglideJS {i18n}>
	<div
		class="m-4 flex h-full min-h-[600px] w-25 flex-col overflow-hidden rounded-2xl border border-black shadow-lg"
	>
		<div class="black-to-cyan-gradient flex h-96 flex-col justify-between bg-gray-400 p-3.5">
			<!-- Chat Header -->
			<ChatHeader />
		</div>
		<div class="black-gradient flex flex-1 flex-col justify-end gap-4 bg-gray-900 px-3.5 py-4">
			<div class="-mt-35">
				{@render children()}
			</div>
			<!-- Chat Footer -->
			<ChatFooter />
		</div>
	</div>
</ParaglideJS>
