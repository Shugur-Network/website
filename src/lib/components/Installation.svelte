<script lang="ts">
	import { Check, Copy, AlertCircle } from 'lucide-svelte';
	
	let copiedIndex: number | null = null;
	let copyError: string | null = null;

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

	function copyToClipboard(text: string, index: number) {
		if (typeof window !== 'undefined' && window.navigator && window.navigator.clipboard) {
			window.navigator.clipboard.writeText(text)
				.then(() => {
					copiedIndex = index;
					copyError = null;
					setTimeout(() => {
						copiedIndex = null;
					}, 2000);
				})
				.catch((err) => {
					console.error('Failed to copy text: ', err);
					copyError = 'Failed to copy to clipboard. Please copy manually.';
					setTimeout(() => {
						copyError = null;
					}, 3000);
				});
		} else {
			copyError = 'Clipboard not supported. Please copy manually.';
			setTimeout(() => {
				copyError = null;
			}, 3000);
		}
	}
</script>

<div id="installation" class="py-24 sm:py-32">
	<div class="mx-auto max-w-7xl px-6 lg:px-8">
		<div class="mx-auto max-w-2xl lg:text-center">
			<h2 class="text-base font-semibold leading-7 text-shugur-600 font-spartan">Quick Start</h2>
			<p class="mt-2 text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">
				Deploy in minutes, not hours
			</p>
			<p class="mt-6 text-lg leading-8 text-gray-600">
				Choose your deployment strategy and get started with a single command. 
				Both options include automated setup and production-ready configurations.
			</p>
		</div>

		{#if copyError}
			<div class="mx-auto mt-8 max-w-2xl">
				<div class="rounded-md bg-red-50 p-4 border border-red-200">
					<div class="flex">
						<AlertCircle class="h-5 w-5 text-red-400" />
						<div class="ml-3">
							<p class="text-sm text-red-800">{copyError}</p>
						</div>
					</div>
				</div>
			</div>
		{/if}

		<div class="mx-auto mt-16 grid max-w-2xl grid-cols-1 gap-6 sm:mt-20 lg:mx-0 lg:max-w-none lg:grid-cols-2 lg:gap-8">
			{#each installations as installation, index}
				<div class="flex flex-col justify-between rounded-3xl bg-white p-8 ring-1 ring-gray-200 xl:p-10 hover:ring-2 hover:ring-shugur-200 transition-all duration-200">
					<div>
						<h3 class="text-lg font-semibold leading-8 text-gray-900">{installation.title}</h3>
						<p class="mt-4 text-sm leading-6 text-gray-600">{installation.subtitle}</p>
						<ul class="mt-8 space-y-3 text-sm leading-6 text-gray-600">
							{#each installation.features as feature}
								<li class="flex gap-x-3">
									<Check class="h-6 w-5 flex-none text-shugur-500" />
									{feature}
								</li>
							{/each}
						</ul>
					</div>
					<div class="mt-8">
						<div class="rounded-lg bg-gray-900 p-4">
							<div class="flex items-center justify-between">
								<code class="text-sm text-gray-300 break-all" aria-label="Installation command for {installation.title}">{installation.command}</code>
								<button
									on:click={() => copyToClipboard(installation.command, index)}
									class="ml-4 flex-shrink-0 rounded-md bg-gray-800 p-2 text-gray-300 hover:text-white hover:bg-gray-700 transition-colors duration-200"
									aria-label="Copy installation command"
								>
									{#if copiedIndex === index}
										<Check class="h-4 w-4 text-green-400" />
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
				<a href="https://docs.relay.shugur.com/installation" class="text-shugur-600 hover:text-shugur-500 transition-colors duration-200">
					detailed installation guide
				</a>
				or
				<a href="https://docs.relay.shugur.com/getting-started" class="text-shugur-600 hover:text-shugur-500 transition-colors duration-200">
					system requirements
				</a>
			</p>
		</div>
	</div>
</div>
