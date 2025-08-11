<script lang="ts">
	import '../app.css';
	import Navigation from '$lib/components/Navigation.svelte';
	import Footer from '$lib/components/Footer.svelte';
</script>

<svelte:head>
	<title>Shugur Relay - Production-Ready Nostr Infrastructure</title>
	<meta
		name="description"
		content="Deploy censorship-resistant social networks with enterprise-grade reliability. High-performance Nostr relay built with Go and CockroachDB."
	/>
	<meta
		name="keywords"
		content="nostr, relay, decentralized, social media, blockchain, censorship-resistant"
	/>
</svelte:head>

<div class="min-h-screen bg-white">
	<Navigation />
	<main>
		<slot />
	</main>
	<Footer />
</div>
