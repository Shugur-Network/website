<script lang="ts">
	import { Zap, Database, ShieldCheck } from 'lucide-svelte';
</script>

<div id="architecture" class="py-24 sm:py-32 bg-gray-50">
	<div class="mx-auto max-w-7xl px-6 lg:px-8">
		<div class="mx-auto max-w-2xl lg:text-center">
			<h2 class="text-base font-semibold leading-7 text-shugur-600 font-spartan">Architecture</h2>
			<p class="mt-2 text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">
				Built for scale and reliability
			</p>
			<p class="mt-6 text-lg leading-8 text-gray-600">
				Shugur Relay uses a stateless architecture with CockroachDB for distributed storage, 
				ensuring high performance and horizontal scalability.
			</p>
		</div>

		<div class="mt-16 grid grid-cols-1 gap-8 lg:grid-cols-3">
			<div class="text-center animate-slide-up">
				<div class="mx-auto h-12 w-12 rounded-lg bg-shugur-100 flex items-center justify-center shadow-sm">
					<Zap class="h-6 w-6 text-shugur-600" />
				</div>
				<h3 class="mt-4 text-lg font-semibold text-gray-900">High Performance</h3>
				<p class="mt-2 text-sm text-gray-600">
					Go-based implementation with optimized WebSocket handling and efficient event processing.
				</p>
			</div>

			<div class="text-center animate-slide-up" style="animation-delay: 100ms">
				<div class="mx-auto h-12 w-12 rounded-lg bg-green-100 flex items-center justify-center shadow-sm">
					<Database class="h-6 w-6 text-green-600" />
				</div>
				<h3 class="mt-4 text-lg font-semibold text-gray-900">Distributed Storage</h3>
				<p class="mt-2 text-sm text-gray-600">
					CockroachDB provides ACID transactions, automatic sharding, and built-in replication.
				</p>
			</div>

			<div class="text-center animate-slide-up" style="animation-delay: 200ms">
				<div class="mx-auto h-12 w-12 rounded-lg bg-purple-100 flex items-center justify-center shadow-sm">
					<ShieldCheck class="h-6 w-6 text-purple-600" />
				</div>
				<h3 class="mt-4 text-lg font-semibold text-gray-900">Enterprise Security</h3>
				<p class="mt-2 text-sm text-gray-600">
					Built-in rate limiting, event validation, and comprehensive monitoring capabilities.
				</p>
			</div>
		</div>

		<div class="mt-16 text-center">
			<a
				href="https://docs.shugur.com/architecture"
				class="inline-flex items-center rounded-md bg-shugur-500 px-3.5 py-2.5 text-sm font-semibold text-white shadow-sm hover:bg-shugur-600 transition-colors duration-200"
			>
				Learn More About Architecture
			</a>
		</div>
	</div>
</div>
