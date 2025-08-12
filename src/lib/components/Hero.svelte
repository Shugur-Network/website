<script lang="ts">
	import { ArrowRight } from 'lucide-svelte';
</script>

<div class="relative isolate px-6 pt-14 lg:px-8">
	<div class="mx-auto max-w-2xl py-32 sm:py-48 lg:py-56">
		<div class="text-center animate-slide-up">
			<h1 class="text-4xl font-bold tracking-tight text-gray-900 sm:text-6xl">
				Production-Ready
				<span class="text-shugur-500 font-spartan"> Nostr Relay</span>
			</h1>
			<p class="mt-6 text-lg leading-8 text-gray-600">
				Deploy censorship-resistant social networks with enterprise-grade reliability. 
				High-performance relay built with Go and CockroachDB, ready in 10 minutes.
			</p>
			<div class="mt-10 flex items-center justify-center gap-x-6">
				<a
					href="/#installation"
					class="rounded-md bg-shugur-500 px-3.5 py-2.5 text-sm font-semibold text-white shadow-sm hover:bg-shugur-600 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-shugur-600 transition-colors duration-200"
					aria-label="Get started with Shugur Relay installation"
				>
					Quick Start
				</a>
				<a 
					href="https://docs.relay.shugur.com" 
					class="text-sm font-semibold leading-6 text-gray-900 hover:text-shugur-600 flex items-center gap-1 transition-colors duration-200"
					aria-label="View Shugur Relay documentation"
				>
					View Documentation <ArrowRight class="h-4 w-4" />
				</a>
			</div>
		</div>
	</div>
</div>
