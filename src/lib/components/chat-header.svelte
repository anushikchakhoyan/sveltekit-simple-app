<script>
	import Logo from '$lib/icons/logo.svelte';
	import ChatTitle from '$lib/components/chat-title.svelte';

	import user1 from '$lib/images/user1.png';
	import user2 from '$lib/images/user2.png';
	import user3 from '$lib/images/user3.png';

	export let avatars = [user1, user2, user3];
</script>

<div class="flex flex-1 flex-col justify-between py-7.5">
	<div class="flex items-center justify-between px-5">
		<Logo />
		<div class="flex -space-x-2">
			{#each avatars as avatar, index}
				<img src={avatar} alt="User" class="h-10 w-10" style="z-index: {3 - index};" />
			{/each}
		</div>
	</div>
	<ChatTitle />
</div>
