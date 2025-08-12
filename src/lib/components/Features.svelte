<script lang="ts">
	import { 
		Rocket, 
		Shield, 
		Cpu, 
		Server, 
		Clock, 
		FileText 
	} from 'lucide-svelte';

	const features = [
		{
			name: '10-Minute Setup',
			description: 'Automated installation scripts handle everything from Docker setup to SSL certificates. Production-ready in minutes.',
			icon: Clock,
		},
		{
			name: 'Enterprise Grade',
			description: 'Built with CockroachDB for distributed storage, comprehensive monitoring, and enterprise security features.',
			icon: Shield,
		},
		{
			name: '20+ NIPs Supported',
			description: 'Maximum compatibility with Nostr clients through comprehensive protocol implementation and regular updates.',
			icon: Cpu,
		},
		{
			name: 'Multi-Platform',
			description: 'Deploy on Docker, bare metal, or cloud platforms. Supports Linux, macOS, and Windows environments.',
			icon: Rocket,
		},
		{
			name: 'Complete Documentation',
			description: 'Comprehensive guides, API documentation, troubleshooting, and configuration references included.',
			icon: FileText,
		},
	];
</script>

<div id="features" class="py-24 sm:py-32 bg-gray-50">
	<div class="mx-auto max-w-7xl px-6 lg:px-8">
		<div class="mx-auto max-w-2xl lg:text-center">
			<h2 class="text-base font-semibold leading-7 text-shugur-600 font-spartan">Deploy Faster</h2>
			<p class="mt-2 text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">
				Everything you need for production Nostr infrastructure
			</p>
			<p class="mt-6 text-lg leading-8 text-gray-600">
				From automated deployment to enterprise monitoring, Shugur Relay provides battle-tested infrastructure 
				for censorship-resistant social networks.
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
