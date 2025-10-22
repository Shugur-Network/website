<script lang="ts">
	import { onMount } from 'svelte';
	import { ExternalLink, FileText, Download, Sparkles, ChevronLeft, ChevronRight } from 'lucide-svelte';

	let currentSlide = 0;
	let carouselInterval: ReturnType<typeof setInterval> | null = null;
	let cardsPerView = 2; // Show 2 cards at a time on desktop

	const announcements = [
		{
			id: 'relay-v134',
			badge: 'Latest Release',
			title: 'Shugur Relay v1.3.5',
			description: 'Comprehensive Nostr Web Pages support - host and validate decentralized static websites on Nostr.',
			primaryCTA: {
				text: 'Install',
				url: '/#installation',
				icon: Download
			},
			secondaryCTA: {
				text: 'Changelog',
				url: 'https://github.com/Shugur-Network/relay/releases/tag/v1.3.5',
				icon: FileText
			},
			badgeColor: 'bg-blue-50 text-blue-700 border-blue-200',
			iconBg: 'bg-blue-50',
			iconColor: 'text-blue-600',
			primaryBg: 'bg-blue-100 hover:bg-blue-200 text-blue-800'
		},
		{
			id: 'nostr-web-pages',
			badge: 'New Innovation',
			title: 'Nostr Web Pages NIP',
			description: 'Revolutionary decentralized websites built on Nostr. Publish censorship-resistant web content.',
			primaryCTA: {
				text: 'Try It',
				url: 'https://nweb.shugur.com',
				icon: Sparkles
			},
			secondaryCTA: {
				text: 'GitHub',
				url: 'https://github.com/Shugur-Network/nw-nips',
				icon: FileText
			},
			badgeColor: 'bg-purple-50 text-purple-700 border-purple-200',
			iconBg: 'bg-purple-50',
			iconColor: 'text-purple-600',
			primaryBg: 'bg-purple-100 hover:bg-purple-200 text-purple-800'
		},
		{
			id: 'time-capsules',
			badge: 'New Innovation',
			title: 'Time Capsules NIP',
			description: 'Revolutionary scheduled message delivery for Nostr. Build time-based communications into your applications.',
			primaryCTA: {
				text: 'Try It',
				url: 'https://capsules.shugur.com',
				icon: Sparkles
			},
			secondaryCTA: {
				text: 'NIP Specs',
				url: 'https://github.com/Shugur-Network/NIP-XX_Time-Capsules',
				icon: FileText
			},
			badgeColor: 'bg-purple-50 text-purple-700 border-purple-200',
			iconBg: 'bg-purple-50',
			iconColor: 'text-purple-600',
			primaryBg: 'bg-purple-100 hover:bg-purple-200 text-purple-800'
		}
	];

	function nextSlide() {
		const maxSlide = Math.max(0, announcements.length - cardsPerView);
		currentSlide = currentSlide >= maxSlide ? 0 : currentSlide + 1;
	}

	function prevSlide() {
		const maxSlide = Math.max(0, announcements.length - cardsPerView);
		currentSlide = currentSlide <= 0 ? maxSlide : currentSlide - 1;
	}

	function goToSlide(index: number) {
		const maxSlide = Math.max(0, announcements.length - cardsPerView);
		currentSlide = Math.min(index, maxSlide);
	}

	function updateCardsPerView() {
		if (typeof window !== 'undefined') {
			cardsPerView = window.innerWidth >= 1024 ? 2 : 1;
		}
	}

	onMount(() => {
		updateCardsPerView();
		
		// Auto-advance carousel every 8 seconds if more cards than visible
		if (announcements.length > cardsPerView) {
			carouselInterval = setInterval(nextSlide, 8000);
		}

		const handleResize = () => updateCardsPerView();
		window.addEventListener('resize', handleResize);

		return () => {
			if (carouselInterval) {
				clearInterval(carouselInterval);
			}
			window.removeEventListener('resize', handleResize);
		};
	});

	$: maxSlide = Math.max(0, announcements.length - cardsPerView);
	$: visibleAnnouncements = announcements.slice(currentSlide, currentSlide + cardsPerView);
</script>

<div class="bg-gradient-to-b from-white to-gray-50 py-16">
	<div class="mx-auto max-w-7xl px-6 lg:px-8">
		<div class="relative">
			<div class="grid grid-cols-1 lg:grid-cols-2 gap-6 max-w-4xl mx-auto">
				{#each visibleAnnouncements as announcement}
					<div class="relative bg-white rounded-xl shadow-md hover:shadow-lg transition-all duration-300 border border-gray-200 hover:border-gray-300 overflow-hidden group">
						<!-- Card Header - Clean White with Subtle Border -->
						<div class="bg-white px-4 py-3 border-b border-gray-100">
							<div class="flex items-center justify-between">
								<span class="inline-flex items-center gap-1.5 rounded-full {announcement.badgeColor} border px-2.5 py-1 text-xs font-medium">
									<span class="relative flex h-1.5 w-1.5">
										<span class="animate-ping absolute inline-flex h-full w-full rounded-full {announcement.iconColor.replace('text-', 'bg-')} opacity-40"></span>
										<span class="relative inline-flex rounded-full h-1.5 w-1.5 {announcement.iconColor.replace('text-', 'bg-')}"></span>
									</span>
									{announcement.badge}
								</span>
								<div class="{announcement.iconBg} p-1.5 rounded-lg border border-gray-100">
									<svelte:component this={announcement.primaryCTA.icon} class="h-4 w-4 {announcement.iconColor}" />
								</div>
							</div>
						</div>
						
						<!-- Card Content -->
						<div class="p-4">
							<h3 class="text-lg font-semibold text-gray-900 mb-2">
								{announcement.title}
							</h3>
							<p class="text-sm text-gray-600 mb-4 leading-relaxed">
								{announcement.description}
							</p>
							
							<!-- CTAs -->
							<div class="flex flex-col sm:flex-row gap-3">
								<a
									href={announcement.primaryCTA.url}
									target={announcement.primaryCTA.url.startsWith('http') ? '_blank' : undefined}
									rel={announcement.primaryCTA.url.startsWith('http') ? 'noopener noreferrer' : undefined}
									class="flex-1 inline-flex items-center justify-center gap-2 rounded-lg {announcement.primaryBg} px-4 py-3 text-sm font-medium hover:shadow-lg transition-all duration-200 transform hover:-translate-y-0.5"
								>
									<svelte:component this={announcement.primaryCTA.icon} class="h-4 w-4" />
									{announcement.primaryCTA.text}
									{#if announcement.primaryCTA.url.startsWith('http')}
										<ExternalLink class="h-3 w-3" />
									{/if}
								</a>
								<a
									href={announcement.secondaryCTA.url}
									target={announcement.secondaryCTA.url.startsWith('http') ? '_blank' : undefined}
									rel={announcement.secondaryCTA.url.startsWith('http') ? 'noopener noreferrer' : undefined}
									class="flex-1 inline-flex items-center justify-center gap-2 rounded-lg border border-gray-300 bg-white px-4 py-3 text-sm font-medium text-gray-700 hover:bg-gray-50 hover:border-gray-400 transition-all duration-200"
								>
									<svelte:component this={announcement.secondaryCTA.icon} class="h-4 w-4" />
									{announcement.secondaryCTA.text}
									{#if announcement.secondaryCTA.url.startsWith('http')}
										<ExternalLink class="h-3 w-3" />
									{/if}
								</a>
							</div>
						</div>
						
						<!-- Hover effect overlay -->
						<div class="absolute inset-0 bg-gradient-to-br from-transparent via-transparent to-black/5 opacity-0 group-hover:opacity-100 transition-opacity duration-300 pointer-events-none"></div>
					</div>
				{/each}
			</div>

			<!-- Navigation Controls - Always Visible -->
			<!-- Previous/Next Buttons -->
			<button
				on:click={prevSlide}
				disabled={currentSlide === 0}
				class="absolute left-0 top-1/2 -translate-y-1/2 -translate-x-6 p-2.5 rounded-full bg-white/80 backdrop-blur-sm shadow-md hover:shadow-lg hover:bg-white/90 transition-all duration-200 border border-gray-200/50 hover:border-gray-300 disabled:opacity-30 disabled:cursor-not-allowed z-10"
				aria-label="Previous announcements"
			>
				<ChevronLeft class="h-5 w-5 text-gray-600" />
			</button>

			<button
				on:click={nextSlide}
				disabled={currentSlide >= maxSlide}
				class="absolute right-0 top-1/2 -translate-y-1/2 translate-x-6 p-2.5 rounded-full bg-white/80 backdrop-blur-sm shadow-md hover:shadow-lg hover:bg-white/90 transition-all duration-200 border border-gray-200/50 hover:border-gray-300 disabled:opacity-30 disabled:cursor-not-allowed z-10"
				aria-label="Next announcements"
			>
				<ChevronRight class="h-5 w-5 text-gray-600" />
			</button>

			<!-- Dots Indicator - Always Visible -->
			<div class="flex justify-center gap-2 mt-8">
				{#each Array(Math.max(maxSlide + 1, 2)) as _, index}
					<button
						on:click={() => goToSlide(index)}
						disabled={index > maxSlide}
						class="w-2.5 h-2.5 rounded-full transition-all duration-300 {index === currentSlide ? 'bg-shugur-500 scale-110' : index <= maxSlide ? 'bg-gray-300 hover:bg-gray-400' : 'bg-gray-200'}"
						aria-label="Go to slide {index + 1}"
					/>
				{/each}
			</div>
		</div>
	</div>
</div>