<script lang="ts">
	import { Menu, X } from 'lucide-svelte';
	import { base } from '$app/paths';
	
	let mobileMenuOpen = false;

	function toggleMobileMenu() {
		mobileMenuOpen = !mobileMenuOpen;
	}
</script>

<header class="bg-white shadow-sm sticky top-0 z-50">
	<nav class="mx-auto flex max-w-7xl items-center justify-between p-6 lg:px-8" aria-label="Global">
		<div class="flex lg:flex-1">
			<a href="https://shugur.com" class="logo">
				<img src="{base}/shugur-logo.svg" alt="Shugur" class="logo-img" />
				<div class="logo-text">
					<span class="logo-main">Shugur</span>
				</div>
			</a>
		</div>
		<div class="flex lg:hidden">
			<button
				type="button"
				class="-m-2.5 inline-flex items-center justify-center rounded-md p-2.5 text-gray-700"
				on:click={toggleMobileMenu}
			>
				<Menu class="h-6 w-6" />
			</button>
		</div>
		<div class="hidden lg:flex lg:gap-x-12">
			<a href="{base}/#features" class="text-sm font-semibold leading-6 text-gray-900 hover:text-blue-600">
				Features
			</a>
			<a href="{base}/#installation" class="text-sm font-semibold leading-6 text-gray-900 hover:text-blue-600">
				Installation
			</a>
			<a href="https://docs.relay.shugur.com" class="text-sm font-semibold leading-6 text-gray-900 hover:text-blue-600">
				Documentation
			</a>
			<a href="{base}/about-nostr" class="text-sm font-semibold leading-6 text-gray-900 hover:text-blue-600">
				About Nostr
			</a>
		</div>
		<div class="hidden lg:flex lg:flex-1 lg:justify-end">
			<a
				href="https://github.com/Shugur-Network/Relay"
				class="text-sm font-semibold leading-6 text-gray-900 hover:text-blue-600"
			>
				GitHub <span aria-hidden="true">&rarr;</span>
			</a>
		</div>
	</nav>

	{#if mobileMenuOpen}
		<div class="lg:hidden">
			<div class="fixed inset-0 z-50"></div>
			<div class="fixed inset-y-0 right-0 z-50 w-full overflow-y-auto bg-white px-6 py-6 sm:max-w-sm sm:ring-1 sm:ring-gray-900/10">
				<div class="flex items-center justify-between">
					<a href="https://shugur.com" class="logo">
						<img src="{base}/shugur-logo.svg" alt="Shugur" class="logo-img" />
						<div class="logo-text">
							<span class="logo-main">Shugur</span>
						</div>
					</a>
					<button type="button" class="-m-2.5 rounded-md p-2.5 text-gray-700" on:click={toggleMobileMenu}>
						<X class="h-6 w-6" />
					</button>
				</div>
				<div class="mt-6 flow-root">
					<div class="-my-6 divide-y divide-gray-500/10">
						<div class="space-y-2 py-6">
							<a
								href="{base}/#features"
								class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50"
								on:click={toggleMobileMenu}
							>
								Features
							</a>
							<a
								href="{base}/#installation"
								class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50"
								on:click={toggleMobileMenu}
							>
								Installation
							</a>
							<a
								href="https://docs.relay.shugur.com"
								class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50"
								on:click={toggleMobileMenu}
							>
								Documentation
							</a>
							<a
								href="{base}/about-nostr"
								class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50"
								on:click={toggleMobileMenu}
							>
								About Nostr
							</a>
						</div>
						<div class="py-6">
							<a
								href="https://github.com/Shugur-Network/Relay"
								class="-mx-3 block rounded-lg px-3 py-2.5 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50"
							>
								GitHub
							</a>
						</div>
					</div>
				</div>
			</div>
		</div>
	{/if}
</header>
