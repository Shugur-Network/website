<script lang="ts">
	import { page } from '$app/stores';
	import { ArrowLeft, Home, Github } from 'lucide-svelte';
	
	$: status = $page.status;
	
	// Custom messages for different error types
	$: errorTitle = status === 404 ? 'Page Not Found' : 'Something went wrong';
	$: errorDescription = status === 404 
		? "The page you're looking for doesn't exist or has been moved."
		: "We encountered an unexpected error. Please try again.";
</script>

<svelte:head>
	<title>{status} - {errorTitle} | Shugur Relay</title>
	<meta name="description" content="Page not found or error occurred on Shugur Relay website" />
	<meta name="robots" content="noindex, nofollow" />
</svelte:head>

<div class="min-h-screen bg-gradient-to-br from-gray-50 to-gray-100 flex items-center justify-center px-4">
	<div class="max-w-md w-full text-center">
		<!-- Error Icon -->
		<div class="mx-auto w-24 h-24 bg-shugur-100 rounded-full flex items-center justify-center mb-8">
			<div class="text-6xl text-shugur-600 font-bold">{status}</div>
		</div>
		
		<!-- Error Content -->
		<h1 class="text-3xl font-spartan font-bold text-gray-900 mb-4">
			{errorTitle}
		</h1>
		
		<p class="text-lg text-gray-600 mb-8 leading-relaxed">
			{errorDescription}
		</p>
		
		<!-- Action Buttons -->
		<div class="space-y-4">
			<a
				href="/"
				class="inline-flex items-center justify-center w-full px-6 py-3 bg-shugur-600 text-white font-medium rounded-lg hover:bg-shugur-700 transition-colors duration-200 focus:outline-none focus:ring-2 focus:ring-shugur-500 focus:ring-offset-2"
			>
				<Home class="w-5 h-5 mr-2" />
				Go Home
			</a>
			
			<button
				type="button"
				onclick="history.back()"
				class="inline-flex items-center justify-center w-full px-6 py-3 border border-gray-300 text-gray-700 font-medium rounded-lg hover:bg-gray-50 transition-colors duration-200 focus:outline-none focus:ring-2 focus:ring-shugur-500 focus:ring-offset-2"
			>
				<ArrowLeft class="w-5 h-5 mr-2" />
				Go Back
			</button>
		</div>
		
		<!-- Additional Help -->
		<div class="mt-12 pt-8 border-t border-gray-200">
			<p class="text-sm text-gray-500 mb-4">Need help? Try these options:</p>
			
			<div class="flex justify-center space-x-6">
				<a
					href="https://github.com/Shugur-Network/Relay"
					class="text-gray-400 hover:text-shugur-600 transition-colors duration-200"
					aria-label="GitHub Repository"
				>
					<Github class="w-6 h-6" />
				</a>
			</div>
			
			<p class="text-xs text-gray-400 mt-4">
				If you believe this is an error, please report it on our GitHub repository.
			</p>
		</div>
	</div>
</div>
