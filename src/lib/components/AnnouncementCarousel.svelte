<script lang="ts">
	import { onMount } from 'svelte';
	import { ExternalLink, FileText, Code, Download, Sparkles, ChevronLeft, ChevronRight } from 'lucide-svelte';

	let currentSlide = 0;
	let carouselInterval: ReturnType<typeof setInterval> | null = null;
	let cardsPerView = 2; // Show 2 cards at a time on desktop
	let containerRef: HTMLElement;

	const announcements = [
		{
			id: 'relay-v133',
			badge: 'Latest Release',
			title: 'Shugur Relay v1.3.3',
			description: 'Enhanced performance, improved stability, and new enterprise features for production deployments.',
			primaryCTA: {
				text: 'Download',
				url: '/#installation',
				icon: Download
			},
			secondaryCTA: {
				text: 'Changelog',
				url: 'https://github.com/Shugur-Network/relay/releases/tag/v1.3.3',
				icon: FileText
			},
			badgeColor: 'bg-shugur-50 text-shugur-700 border-shugur-200',
			iconBg: 'bg-shugur-50',
			iconColor: 'text-shugur-600',
			primaryBg: 'bg-shugur-500 hover:bg-shugur-600'
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
			primaryBg: 'bg-purple-500 hover:bg-purple-600'
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
	$: showNavigation = announcements.length > cardsPerView;
	$: visibleAnnouncements = announcements.slice(currentSlide, currentSlide + cardsPerView);
</script>

<div class="bg-white py-16">
	<div class="mx-auto max-w-7xl px-6 lg:px-8">
		<div class="relative" bind:this={containerRef}>
			<div class="grid grid-cols-1 lg:grid-cols-2 gap-8 max-w-5xl mx-auto">
				{#each visibleAnnouncements as announcement}
					<div class="relative bg-white rounded-2xl shadow-lg hover:shadow-xl transition-all duration-300 border border-gray-200 hover:border-gray-300 overflow-hidden group">
						<!-- Card Header - Clean White with Subtle Border -->
						<div class="bg-white px-6 py-4 border-b border-gray-100">
							<div class="flex items-center justify-between">
								<span class="inline-flex items-center gap-2 rounded-full {announcement.badgeColor} border px-3 py-1 text-xs font-medium">
									<span class="relative flex h-2 w-2">
										<span class="animate-ping absolute inline-flex h-full w-full rounded-full {announcement.iconColor.replace('text-', 'bg-')} opacity-40"></span>
										<span class="relative inline-flex rounded-full h-2 w-2 {announcement.iconColor.replace('text-', 'bg-')}"></span>
									</span>
									{announcement.badge}
								</span>
								<div class="{announcement.iconBg} p-2 rounded-lg border border-gray-100">
									<svelte:component this={announcement.primaryCTA.icon} class="h-5 w-5 {announcement.iconColor}" />
								</div>
							</div>
						</div>
						
						<!-- Card Content -->
						<div class="p-6">
							<h3 class="text-xl font-semibold text-gray-900 mb-3">
								{announcement.title}
							</h3>
							<p class="text-gray-600 mb-6 leading-relaxed">
								{announcement.description}
							</p>
							
							<!-- CTAs -->
							<div class="flex flex-col sm:flex-row gap-3">
								<a
									href={announcement.primaryCTA.url}
									target={announcement.primaryCTA.url.startsWith('http') ? '_blank' : undefined}
									rel={announcement.primaryCTA.url.startsWith('http') ? 'noopener noreferrer' : undefined}
									class="flex-1 inline-flex items-center justify-center gap-2 rounded-lg {announcement.primaryBg} px-4 py-3 text-sm font-medium text-white hover:shadow-lg transition-all duration-200 transform hover:-translate-y-0.5"
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

			<!-- Navigation Controls -->
			{#if showNavigation}
				<!-- Previous/Next Buttons -->
				<button
					on:click={prevSlide}
					disabled={currentSlide === 0}
					class="absolute left-0 top-1/2 -translate-y-1/2 -translate-x-4 p-3 rounded-full bg-white shadow-lg hover:shadow-xl transition-all duration-200 border border-gray-200 hover:border-gray-300 disabled:opacity-50 disabled:cursor-not-allowed z-10"
					aria-label="Previous announcements"
				>
					<ChevronLeft class="h-6 w-6 text-gray-700" />
				</button>

				<button
					on:click={nextSlide}
					disabled={currentSlide >= maxSlide}
					class="absolute right-0 top-1/2 -translate-y-1/2 translate-x-4 p-3 rounded-full bg-white shadow-lg hover:shadow-xl transition-all duration-200 border border-gray-200 hover:border-gray-300 disabled:opacity-50 disabled:cursor-not-allowed z-10"
					aria-label="Next announcements"
				>
					<ChevronRight class="h-6 w-6 text-gray-700" />
				</button>

				<!-- Dots Indicator -->
				<div class="flex justify-center gap-2 mt-8">
					{#each Array(maxSlide + 1) as _, index}
						<button
							on:click={() => goToSlide(index)}
							class="w-3 h-3 rounded-full transition-all duration-300 {index === currentSlide ? 'bg-shugur-600 scale-110' : 'bg-gray-300 hover:bg-gray-400'}"
							aria-label="Go to slide {index + 1}"
						/>
					{/each}
				</div>
			{/if}
		</div>
	</div>
</div>