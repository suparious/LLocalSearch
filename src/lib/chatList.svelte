<script lang="ts">
	import { type ChatListItem } from '$lib/types/types';
	import ChatListItemElem from './chatListItemElem.svelte';

	export let chatListItems: ChatListItem[] = [];
	export let session: string;
	export let loadHistory: Function;
</script>

<div class="flex flex-col gap-2">
	{#each chatListItems as chatListItem}
		{#if chatListItem}
			<ChatListItemElem item={chatListItem} bind:session {loadHistory} />
		{/if}
	{/each}
</div>
