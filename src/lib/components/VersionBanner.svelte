<script lang="ts">
	import { X } from 'lucide-svelte';
	import { browser } from '$app/environment';
	import { onMount } from 'svelte';

	let showBanner = true;
	const bannerKey = 'shugur-version-banner-v1.3.4';

	onMount(() => {
		if (browser) {
			const dismissed = localStorage.getItem(bannerKey);
			if (dismissed) {
				showBanner = false;
			}
		}
	});

	function dismissBanner() {
		showBanner = false;
		if (browser) {
			localStorage.setItem(bannerKey, 'true');
		}
	}
</script>

{#if showBanner}
	<div class="relative isolate flex items-center gap-x-6 overflow-hidden bg-purple-600 px-6 py-2.5 sm:px-3.5 sm:before:flex-1">
		<div class="flex flex-wrap items-center gap-x-4 gap-y-2">
			<p class="text-sm leading-6 text-white">
				<strong class="font-semibold">Shugur Relay v1.3.4</strong>
				<svg viewBox="0 0 2 2" class="mx-2 inline h-0.5 w-0.5 fill-current" aria-hidden="true">
					<circle cx="1" cy="1" r="1" />
				</svg>
				Now with Nostr Web Pages support - host and validate decentralized static websites on Nostr.
			</p>
			<a
				href="https://github.com/Shugur-Network/relay/releases/tag/v1.3.4"
				target="_blank"
				rel="noopener noreferrer"
				class="flex-none rounded-full bg-purple-900 px-3.5 py-1 text-sm font-semibold text-white shadow-sm hover:bg-purple-700 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-purple-900"
			>
				View Release <span aria-hidden="true">&rarr;</span>
			</a>
		</div>
		<div class="flex flex-1 justify-end">
			<button type="button" class="-m-3 p-3 focus-visible:outline-offset-[-4px]" on:click={dismissBanner}>
				<span class="sr-only">Dismiss</span>
				<X class="h-5 w-5 text-white" aria-hidden="true" />
			</button>
		</div>
	</div>
{/if}