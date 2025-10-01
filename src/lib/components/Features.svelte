<script lang="ts">
	import { 
		Rocket, 
		Shield, 
		Cpu, 
		Clock, 
		FileText 
	} from 'lucide-svelte';

	const features = [
		{
			name: 'Quick Setup',
			description: 'Enhanced automated installation scripts with interactive modes, error handling, and port availability checks. Production-ready in minutes.',
			icon: Clock,
		},
		{
			name: 'Distributed Network',
			description: 'Connect to a single endpoint and access the entire distributed network with real-time synchronization, automatic failover and data redundancy.',
			icon: Shield,
		},
		{
			name: 'Universal Compatibility',
			description: 'Works with all major Nostr clients through comprehensive protocol implementation, from basic messaging to advanced financial features.',
			icon: Cpu,
		},
		{
			name: 'Enterprise Ready',
			description: 'Real-time metrics, enhanced event processing, cross-node synchronization, and configurable limits for production environments.',
			icon: Rocket,
		},
		{
			name: 'Complete Documentation',
			description: 'Comprehensive guides, API documentation, troubleshooting, and configuration references with detailed setup instructions.',
			icon: FileText,
		},
	];
</script>

<div id="features" class="py-24 sm:py-32 bg-gray-50">
	<div class="mx-auto max-w-7xl px-6 lg:px-8">
		<div class="mx-auto max-w-2xl lg:text-center">
			<h2 class="text-base font-semibold leading-7 text-shugur-600 font-spartan">Deploy Faster</h2>
			<p class="mt-2 text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">
				Everything you need for production Nostr Relay
			</p>
			<p class="mt-6 text-lg leading-8 text-gray-600">
				From automated deployment to distributed relay networks, Shugur provides battle-tested nostr relay 
				infrastructure with high availability and censorship resistance.
			</p>
		</div>
		<div class="mx-auto mt-16 max-w-2xl sm:mt-20 lg:mt-24 lg:max-w-4xl">
			<dl class="grid max-w-xl grid-cols-1 gap-x-8 gap-y-10 lg:max-w-none lg:grid-cols-2 lg:gap-y-16">
				{#each features as feature, index}
					<div class="relative pl-16 animate-slide-up" style="animation-delay: {index * 100}ms">
						<dt class="text-base font-semibold leading-7 text-gray-900">
							<div class="absolute left-0 top-0 flex h-10 w-10 items-center justify-center rounded-lg bg-shugur-500 shadow-sm">
								<svelte:component this={feature.icon} class="h-6 w-6 text-white" />
							</div>
							{feature.name}
						</dt>
						<dd class="mt-2 text-base leading-7 text-gray-600">{feature.description}</dd>
					</div>
				{/each}
			</dl>
		</div>
	</div>
</div>
