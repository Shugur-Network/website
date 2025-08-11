<script lang="ts">
	import { Github } from 'lucide-svelte';
	const currentYear = new Date().getFullYear();
</script>

<footer class="bg-gray-900">
	<div class="mx-auto max-w-7xl px-6 py-12 md:flex md:items-center md:justify-between lg:px-8">
		<div class="flex justify-center space-x-6 md:order-2">
			<a href="https://github.com/Shugur-Network/Relay" class="text-gray-400 hover:text-gray-300">
				<span class="sr-only">GitHub</span>
				<Github class="h-6 w-6" />
			</a>
		</div>
		<div class="mt-8 md:order-1 md:mt-0">
			<p class="text-center text-xs leading-5 text-gray-400">
				&copy; {currentYear} Shugur Relay. Built for the decentralized web.
			</p>
		</div>
	</div>
</footer>
