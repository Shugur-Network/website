<script lang="ts">
  import Hero from "$lib/components/Hero.svelte";
  import Features from "$lib/components/Features.svelte";
  import Installation from "$lib/components/Installation.svelte";
  import Architecture from "$lib/components/Architecture.svelte";
</script>

<svelte:head>
  <title>Shugur Relay - Production-Ready Nostr Relay | Enterprise-Grade Performance</title>
  <meta name="description" content="Deploy high-performance, scalable Nostr relay with enterprise-grade reliability in 10 minutes. Built with Go and CockroachDB for maximum performance and fault tolerance." />
  <meta name="keywords" content="nostr relay, nostr, decentralized, relay, go, cockroachdb, enterprise, performance, scalability, nostr protocol, nostr implementation, nostr infrastructure" />
  
  <!-- Canonical URL -->
  <link rel="canonical" href="https://relay.shugur.net" />
  
  <!-- Open Graph / Facebook -->
  <meta property="og:title" content="Shugur Relay - Production-Ready Nostr Relay" />
  <meta property="og:description" content="Deploy high-performance, scalable Nostr relay with enterprise-grade reliability in 10 minutes. Built with Go and CockroachDB." />
  <meta property="og:url" content="https://relay.shugur.net" />
  <meta property="og:image" content="https://relay.shugur.net/shugur-logo-full.svg" />
  <meta property="og:image:alt" content="Shugur Relay Logo" />
  <meta property="og:type" content="website" />
  <meta property="og:site_name" content="Shugur Relay" />
  
  <!-- Twitter -->
  <meta name="twitter:title" content="Shugur Relay - Production-Ready Nostr Relay" />
  <meta name="twitter:description" content="Deploy high-performance, scalable Nostr relay with enterprise-grade reliability in 10 minutes." />
  <meta name="twitter:image" content="https://relay.shugur.net/shugur-logo-full.svg" />
  <meta name="twitter:image:alt" content="Shugur Relay Logo" />
  
  <!-- Additional SEO -->
  <meta name="robots" content="index, follow, max-image-preview:large, max-snippet:-1, max-video-preview:-1" />
  <meta name="googlebot" content="index, follow" />
  <meta name="bingbot" content="index, follow" />
  
  <!-- Brand and Company -->
  <meta name="author" content="Shugur Network" />
  <meta name="publisher" content="Shugur Network" />
  <meta name="copyright" content="Shugur Network" />
  
  <!-- Technical -->
  <meta name="generator" content="SvelteKit" />
  <meta name="language" content="en" />
  <meta name="revisit-after" content="7 days" />
</svelte:head>

<Hero />
<Features />
<Installation />
<Architecture />
