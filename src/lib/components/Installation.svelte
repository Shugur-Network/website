<script lang="ts">
	import { Check, Copy } from 'lucide-svelte';
	
	let copiedIndex: number | null = null;

	const installations = [
		{
			title: 'Standalone Installation',
			subtitle: 'Perfect for development, testing, or small-scale production',
			command: 'curl -fsSL https://github.com/Shugur-Network/relay/raw/main/scripts/install.standalone.sh | sudo bash',
			features: [
				'Single-node deployment',
				'All services on one server',
				'Automatic SSL certificates',
				'Web interface included',
			],
		},
		{
			title: 'Distributed Installation',
			subtitle: 'Production-ready, high-availability multi-node setup',
			command: 'curl -fsSL https://github.com/Shugur-Network/relay/raw/main/scripts/install.distributed.sh | sudo bash',
			features: [
				'Multi-node cluster',
				'High availability',
				'Load balancing',
				'Automatic failover',
			],
		},
	];

	async function copyToClipboard(text: string, index: number) {
		try {
			await navigator.clipboard.writeText(text);
			copiedIndex = index;
			setTimeout(() => {
				copiedIndex = null;
			}, 2000);
		} catch (err) {
			console.error('Failed to copy text: ', err);
		}
	}
</script>

<div id="installation" class="py-24 sm:py-32">
	<div class="mx-auto max-w-7xl px-6 lg:px-8">
		<div class="mx-auto max-w-2xl lg:text-center">
			<h2 class="text-base font-semibold leading-7 text-blue-600">Quick Start</h2>
			<p class="mt-2 text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">
				Deploy in minutes, not hours
			</p>
			<p class="mt-6 text-lg leading-8 text-gray-600">
				Choose your deployment strategy and get started with a single command. 
				Both options include automated setup and production-ready configurations.
			</p>
		</div>

		<div class="mx-auto mt-16 grid max-w-2xl grid-cols-1 gap-6 sm:mt-20 lg:mx-0 lg:max-w-none lg:grid-cols-2 lg:gap-8">
			{#each installations as installation, index}
				<div class="flex flex-col justify-between rounded-3xl bg-white p-8 ring-1 ring-gray-200 xl:p-10">
					<div>
						<h3 class="text-lg font-semibold leading-8 text-gray-900">{installation.title}</h3>
						<p class="mt-4 text-sm leading-6 text-gray-600">{installation.subtitle}</p>
						<ul class="mt-8 space-y-3 text-sm leading-6 text-gray-600">
							{#each installation.features as feature}
								<li class="flex gap-x-3">
									<Check class="h-6 w-5 flex-none text-blue-600" />
									{feature}
								</li>
							{/each}
						</ul>
					</div>
					<div class="mt-8">
						<div class="rounded-lg bg-gray-900 p-4">
							<div class="flex items-center justify-between">
								<code class="text-sm text-gray-300 break-all">{installation.command}</code>
								<button
									on:click={() => copyToClipboard(installation.command, index)}
									class="ml-4 flex-shrink-0 rounded-md bg-gray-800 p-2 text-gray-300 hover:text-white"
								>
									{#if copiedIndex === index}
										<Check class="h-4 w-4" />
									{:else}
										<Copy class="h-4 w-4" />
									{/if}
								</button>
							</div>
						</div>
					</div>
				</div>
			{/each}
		</div>

		<div class="mt-16 text-center">
			<p class="text-sm text-gray-600">
				Need help choosing? Check out our
				<a href="https://docs.relay.shugur.com/installation" class="text-blue-600 hover:text-blue-500">
					detailed installation guide
				</a>
				or
				<a href="https://docs.relay.shugur.com/getting-started" class="text-blue-600 hover:text-blue-500">
					system requirements
				</a>
			</p>
		</div>
	</div>
</div>
