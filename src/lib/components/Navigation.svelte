<script lang="ts">
	import { Menu, X } from 'lucide-svelte';
	
	let mobileMenuOpen = false;

	function toggleMobileMenu() {
		mobileMenuOpen = !mobileMenuOpen;
	}

	function closeMobileMenu() {
		mobileMenuOpen = false;
	}

	function handleKeydown(event: KeyboardEvent) {
		if (event.key === 'Escape') {
			closeMobileMenu();
		}
	}
</script>

<header class="bg-white shadow-sm sticky top-0 z-50">
	<div class="max-w-7xl mx-auto px-4 py-2 flex items-center justify-between" aria-label="Global navigation">
		<div class="flex lg:flex-1">
			<a href="/" class="logo" aria-label="Shugur Relay Homepage">
				<img src="/shugur-logo-full.svg" alt="Shugur Relay Logo" class="logo-img" style="width: 170px; height: auto;" />
			</a>
		</div>
		<div class="flex lg:hidden">
			<button
				type="button"
				class="-m-2.5 inline-flex items-center justify-center rounded-md p-2.5 text-gray-700 hover:text-shugur-600 transition-colors duration-200"
				on:click={toggleMobileMenu}
				aria-expanded={mobileMenuOpen}
				aria-controls="mobile-menu"
				aria-label="Toggle mobile menu"
			>
				<Menu class="h-6 w-6" aria-hidden="true" />
			</button>
		</div>
		<nav class="hidden lg:flex lg:gap-x-12" aria-label="Main navigation">
			<a href="/#features" class="text-sm font-semibold leading-6 text-gray-900 hover:text-shugur-600 transition-colors duration-200">
				Features
			</a>
			<a href="/#installation" class="text-sm font-semibold leading-6 text-gray-900 hover:text-shugur-600 transition-colors duration-200">
				Installation
			</a>
			<a href="https://docs.shugur.com" class="text-sm font-semibold leading-6 text-gray-900 hover:text-shugur-600 transition-colors duration-200" target="_blank" rel="noopener noreferrer">
				Documentation
			</a>
			<a href="/about-nostr" class="text-sm font-semibold leading-6 text-gray-900 hover:text-shugur-600 transition-colors duration-200">
				About Nostr
			</a>
		</nav>
		<div class="hidden lg:flex lg:flex-1 lg:justify-end">
			<a
				href="https://github.com/Shugur-Network/Relay"
				class="text-sm font-semibold leading-6 text-gray-900 hover:text-shugur-600 transition-colors duration-200"
				aria-label="View Shugur Relay on GitHub"
				target="_blank" 
				rel="noopener noreferrer"
			>
				GitHub <span aria-hidden="true">&rarr;</span>
			</a>
		</div>
	</div>

	{#if mobileMenuOpen}
		<!-- Mobile menu overlay -->
		<div class="lg:hidden fixed inset-0 z-50" id="mobile-menu">
			<!-- Background overlay -->
			<div 
				class="fixed inset-0 bg-black bg-opacity-25 transition-opacity"
				on:click={closeMobileMenu}
				on:keydown={handleKeydown}
				role="button"
				tabindex="-1"
				aria-label="Close mobile menu overlay"
			></div>
			
			<!-- Mobile menu panel -->
			<nav 
				class="fixed inset-y-0 right-0 z-50 w-full overflow-y-auto bg-white px-6 py-6 sm:max-w-sm sm:ring-1 sm:ring-gray-900/10 shadow-xl"
				role="dialog" 
				aria-modal="true"
				aria-labelledby="mobile-menu-heading"
			>
				<div class="flex items-center justify-between">
					<a href="/" class="logo" aria-label="Shugur Relay Homepage" on:click={closeMobileMenu}>
						<img src="/shugur-logo-full.svg" alt="Shugur Relay Logo" class="logo-img" style="width: 120px; height: auto;" />
					</a>
					<button 
						type="button" 
						class="-m-2.5 rounded-md p-2.5 text-gray-700 hover:text-shugur-600 transition-colors duration-200" 
						on:click={closeMobileMenu}
						aria-label="Close mobile menu"
					>
						<X class="h-6 w-6" aria-hidden="true" />
					</button>
				</div>
				
				<div class="mt-6 flow-root">
					<div class="-my-6 divide-y divide-gray-500/10">
						<h2 id="mobile-menu-heading" class="sr-only">Mobile Navigation Menu</h2>
						<div class="space-y-2 py-6">
							<a
								href="/#features"
								class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50 transition-colors duration-200"
								on:click={closeMobileMenu}
							>
								Features
							</a>
							<a
								href="/#installation"
								class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50 transition-colors duration-200"
								on:click={closeMobileMenu}
							>
								Installation
							</a>
							<a
								href="https://docs.shugur.com"
								class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50 transition-colors duration-200"
								on:click={closeMobileMenu}
								target="_blank" 
								rel="noopener noreferrer"
							>
								Documentation
							</a>
							<a
								href="/about-nostr"
								class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50 transition-colors duration-200"
								on:click={closeMobileMenu}
							>
								About Nostr
							</a>
						</div>
						<div class="py-6">
							<a
								href="https://github.com/Shugur-Network/Relay"
								class="-mx-3 block rounded-lg px-3 py-2.5 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50 transition-colors duration-200"
								aria-label="View Shugur Relay on GitHub"
								on:click={closeMobileMenu}
								target="_blank" 
								rel="noopener noreferrer"
							>
								GitHub
							</a>
						</div>
					</div>
				</div>
			</nav>
		</div>
	{/if}
</header>
