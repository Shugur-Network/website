<script lang="ts">
	import '../app.css';
	import Navigation from '$lib/components/Navigation.svelte';
	import Footer from '$lib/components/Footer.svelte';
</script>

<svelte:head>
	<title>Shugur Relay - Production-Ready Nostr Infrastructure</title>
	<meta
		name="description"
		content="Deploy High-Performance, Scalable Nostr Relay with enterprise-grade reliability in 10 minutes."
	/>
	<meta
		name="keywords"
		content="nostr, relay, decentralized, social media, blockchain, censorship-resistant, go, cockroachdb, enterprise, infrastructure"
	/>
	<meta name="author" content="Shugur Network" />
	<meta name="robots" content="index, follow" />
	
	<!-- Open Graph -->
	<meta property="og:title" content="Shugur Relay - Production-Ready Nostr Infrastructure" />
	<meta property="og:description" content="Deploy High-Performance, Scalable Nostr Relay with enterprise-grade reliability in 10 minutes." />
	<meta property="og:url" content="https://shugur-network.github.io/Relay-Website/" />
	<meta property="og:type" content="website" />
	
	<!-- Twitter -->
	<meta name="twitter:title" content="Shugur Relay - Production-Ready Nostr Infrastructure" />
	<meta name="twitter:description" content="Deploy High-Performance, Scalable Nostr Relay with enterprise-grade reliability in 10 minutes." />
	
	<!-- Canonical URL -->
	<link rel="canonical" href="https://shugur-network.github.io/Relay-Website/" />
</svelte:head>

<div class="min-h-screen bg-white">
	<Navigation />
	<main class="animate-fade-in">
		<slot />
	</main>
	<Footer />
</div>
