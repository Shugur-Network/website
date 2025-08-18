<script lang="ts">
	// Enhanced About Nostr page with better SEO and design system
</script>

<svelte:head>
	<title>About Nostr Relays - The Infrastructure of Decentralized Social Networks | Shugur Relay</title>
	<meta name="description" content="Deep dive into Nostr relays: how they work, their role in decentralized networks, and why they're essential for censorship-resistant communication. Learn about the technology behind Shugur Relay." />
	<meta name="keywords" content="nostr, relay, decentralized, social media, blockchain, censorship-resistant, infrastructure, protocol, events, websocket" />
	<meta name="author" content="Shugur Network" />
	
	<!-- Open Graph -->
	<meta property="og:title" content="About Nostr Relays - The Infrastructure of Decentralized Social Networks" />
	<meta property="og:description" content="Deep dive into Nostr relays: how they work, their role in decentralized networks, and why they're essential for censorship-resistant communication." />
	<meta property="og:url" content="https://shugur.com/about-nostr" />
	<meta property="og:type" content="article" />
	
	<!-- Twitter -->
	<meta name="twitter:title" content="About Nostr Relays - The Infrastructure of Decentralized Social Networks" />
	<meta name="twitter:description" content="Deep dive into Nostr relays: how they work, their role in decentralized networks, and why they're essential for censorship-resistant communication." />
	
	<!-- Canonical URL -->
	<link rel="canonical" href="https://shugur.com/about-nostr" />
</svelte:head>

<div class="bg-white px-6 py-32 lg:px-8">
	<div class="mx-auto max-w-4xl text-base leading-7 text-gray-700">
		<nav class="mb-8" aria-label="Breadcrumb">
			<ol class="flex items-center space-x-2 text-sm text-gray-500">
				<li><a href="/" class="hover:text-shugur-600 transition-colors duration-200">Home</a></li>
				<li><span class="mx-2">/</span></li>
				<li class="text-gray-900">About Nostr</li>
			</ol>
		</nav>
		
		<h1 class="mt-2 text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">
			Understanding Nostr Relays: The Backbone of Decentralized Communication
		</h1>
		
		<p class="mt-6 text-xl leading-8 text-gray-600">
			Nostr relays are the critical infrastructure that powers censorship-resistant social networks. 
			Unlike traditional servers, they enable true decentralization while maintaining performance and simplicity.
		</p>
		
		<div class="mt-16 max-w-3xl">
			<h2 class="text-2xl font-bold tracking-tight text-gray-900">What is a Nostr Relay?</h2>
			
			<p class="mt-6">
				A Nostr relay is a server that accepts, stores, and redistributes events in the Nostr protocol ecosystem. 
				Think of relays as the post offices of the decentralized web - they receive messages, hold them temporarily, 
				and deliver them to anyone who requests them.
			</p>
			
			<div class="mt-8 rounded-lg bg-shugur-50 p-6 border border-shugur-200">
				<h3 class="text-lg font-semibold text-shugur-900">Key Characteristics</h3>
				<ul class="mt-4 space-y-2 text-shugur-800">
					<li>• <strong>Stateless:</strong> Relays don't maintain user sessions or authentication state</li>
					<li>• <strong>Simple:</strong> Uses WebSocket connections for real-time communication</li>
					<li>• <strong>Event-driven:</strong> Everything is an "event" - posts, likes, follows, messages</li>
					<li>• <strong>Cryptographically signed:</strong> All events are signed by users' private keys</li>
				</ul>
			</div>
			
			<h2 class="mt-16 text-2xl font-bold tracking-tight text-gray-900">How Relays Work in the Nostr Ecosystem</h2>
			
			<div class="mt-8 space-y-12">
				<div class="grid gap-8 lg:grid-cols-3">
					<div class="rounded-lg border border-gray-200 p-6 hover:border-shugur-300 transition-colors duration-200">
						<div class="text-center">
							<div class="mx-auto h-12 w-12 rounded-full bg-green-100 flex items-center justify-center">
								<span class="text-xl font-bold text-green-600">1</span>
							</div>
							<h3 class="mt-4 font-semibold text-gray-900">Event Creation</h3>
							<p class="mt-2 text-sm text-gray-600">
								Users create and sign events (posts, reactions, etc.) using their private keys
							</p>
						</div>
					</div>
					
					<div class="rounded-lg border border-gray-200 p-6 hover:border-shugur-300 transition-colors duration-200">
						<div class="text-center">
							<div class="mx-auto h-12 w-12 rounded-full bg-shugur-100 flex items-center justify-center">
								<span class="text-xl font-bold text-shugur-600">2</span>
							</div>
							<h3 class="mt-4 font-semibold text-gray-900">Relay Distribution</h3>
							<p class="mt-2 text-sm text-gray-600">
								Events are sent to multiple relays for redundancy and wider distribution
							</p>
						</div>
					</div>
					
					<div class="rounded-lg border border-gray-200 p-6 hover:border-shugur-300 transition-colors duration-200">
						<div class="text-center">
							<div class="mx-auto h-12 w-12 rounded-full bg-purple-100 flex items-center justify-center">
								<span class="text-xl font-bold text-purple-600">3</span>
							</div>
							<h3 class="mt-4 font-semibold text-gray-900">Client Consumption</h3>
							<p class="mt-2 text-sm text-gray-600">
								Other users' clients query relays to retrieve and display events
							</p>
						</div>
					</div>
				</div>
			</div>
			
			<h2 class="mt-16 text-2xl font-bold tracking-tight text-gray-900">Types of Relay Operations</h2>
			
			<div class="mt-8 space-y-6">
				<div class="rounded-lg bg-gray-50 p-6 border border-gray-200">
					<h3 class="text-lg font-semibold text-gray-900">READ Operations</h3>
					<p class="mt-2">
						Clients send <code class="bg-gray-200 px-2 py-1 rounded text-sm">REQ</code> messages to request events. 
						Relays respond with matching events and send <code class="bg-gray-200 px-2 py-1 rounded text-sm">EOSE</code> 
						(End of Stored Events) when the initial query is complete.
					</p>
				</div>
				
				<div class="rounded-lg bg-gray-50 p-6 border border-gray-200">
					<h3 class="text-lg font-semibold text-gray-900">WRITE Operations</h3>
					<p class="mt-2">
						Clients send <code class="bg-gray-200 px-2 py-1 rounded text-sm">EVENT</code> messages to publish new content. 
						Relays validate the signature and respond with <code class="bg-gray-200 px-2 py-1 rounded text-sm">OK</code> 
						messages indicating acceptance or rejection.
					</p>
				</div>
				
				<div class="rounded-lg bg-gray-50 p-6 border border-gray-200">
					<h3 class="text-lg font-semibold text-gray-900">CLOSE Operations</h3>
					<p class="mt-2">
						Clients can close subscriptions using <code class="bg-gray-200 px-2 py-1 rounded text-sm">CLOSE</code> 
						messages to stop receiving events for specific queries.
					</p>
				</div>
			</div>
			
			<h2 class="mt-16 text-2xl font-bold tracking-tight text-gray-900">Why Relays Are Essential</h2>
			
			<div class="mt-8 grid gap-8 lg:grid-cols-2">
				<div class="rounded-lg border border-gray-200 p-6 hover:border-shugur-300 transition-colors duration-200">
					<h3 class="font-semibold text-gray-900 text-lg">Redundancy & Resilience</h3>
					<p class="mt-3">
						Users connect to multiple relays simultaneously. If one relay goes down or censors content, 
						users can still access their social graph through other relays. This creates a robust, 
						fault-tolerant network.
					</p>
				</div>
				
				<div class="rounded-lg border border-gray-200 p-6 hover:border-shugur-300 transition-colors duration-200">
					<h3 class="font-semibold text-gray-900 text-lg">Geographic Distribution</h3>
					<p class="mt-3">
						Relays can be deployed globally, reducing latency and providing local data sovereignty. 
						Users can choose relays based on location, policies, or trust relationships.
					</p>
				</div>
				
				<div class="rounded-lg border border-gray-200 p-6 hover:border-shugur-300 transition-colors duration-200">
					<h3 class="font-semibold text-gray-900 text-lg">Specialized Services</h3>
					<p class="mt-3">
						Different relays can offer specialized features: some focus on performance, others on specific 
						content types, privacy features, or community moderation policies.
					</p>
				</div>
				
				<div class="rounded-lg border border-gray-200 p-6 hover:border-shugur-300 transition-colors duration-200">
					<h3 class="font-semibold text-gray-900 text-lg">Economic Sustainability</h3>
					<p class="mt-3">
						Relays can implement various business models: subscription fees, micropayments, 
						or community funding, creating sustainable infrastructure without advertising.
					</p>
				</div>
			</div>
			
			<h2 class="mt-16 text-2xl font-bold tracking-tight text-gray-900">Relay Implementation Considerations</h2>
			
			<div class="mt-8 space-y-8">
				<div>
					<h3 class="text-lg font-semibold text-gray-900">Performance Requirements</h3>
					<div class="mt-4 grid gap-4 md:grid-cols-3">
						<div class="rounded-lg bg-yellow-50 p-4 border border-yellow-200">
							<h4 class="font-medium text-yellow-900">High Throughput</h4>
							<p class="mt-1 text-sm text-yellow-800">Handle thousands of simultaneous WebSocket connections</p>
						</div>
						<div class="rounded-lg bg-shugur-50 p-4 border border-shugur-200">
							<h4 class="font-medium text-shugur-900">Low Latency</h4>
							<p class="mt-1 text-sm text-shugur-800">Real-time event distribution for live conversations</p>
						</div>
						<div class="rounded-lg bg-green-50 p-4 border border-green-200">
							<h4 class="font-medium text-green-900">Scalability</h4>
							<p class="mt-1 text-sm text-green-800">Horizontal scaling to support growing user bases</p>
						</div>
					</div>
				</div>
				
				<div>
					<h3 class="text-lg font-semibold text-gray-900">Security & Spam Prevention</h3>
					<ul class="mt-4 space-y-2">
						<li>• <strong>Rate Limiting:</strong> Prevent spam and DoS attacks through connection and event limits</li>
						<li>• <strong>Signature Validation:</strong> Verify cryptographic signatures on all incoming events</li>
						<li>• <strong>Content Filtering:</strong> Optional filtering based on relay policies and user preferences</li>
						<li>• <strong>Authentication:</strong> Optional user authentication for private or paid relays</li>
					</ul>
				</div>
				
				<div>
					<h3 class="text-lg font-semibold text-gray-900">Data Management</h3>
					<ul class="mt-4 space-y-2">
						<li>• <strong>Event Storage:</strong> Efficient database design for fast queries and writes</li>
						<li>• <strong>Retention Policies:</strong> Configurable data retention based on relay capacity</li>
						<li>• <strong>Backup & Recovery:</strong> Data redundancy and disaster recovery procedures</li>
						<li>• <strong>Query Optimization:</strong> Fast event retrieval with proper indexing strategies</li>
					</ul>
				</div>
			</div>
			
			<div class="mt-16 rounded-lg bg-shugur-50 p-8 border border-shugur-200">
				<h3 class="text-xl font-semibold text-shugur-900">Shugur Relay: Distributed High-Availability Nostr Infrastructure</h3>
				<p class="mt-4 text-shugur-800">
					Shugur Relay is built specifically for production environments, offering high-performance distributed 
					relay infrastructure with automatic failover and data redundancy. Connect to a single endpoint and 
					get access to the entire distributed network - no more managing multiple relay connections. 
					Deploy your own censorship-resistant social network infrastructure in minutes, not months.
				</p>
				<div class="mt-6">
					<a 
						href="/#installation" 
						class="inline-flex items-center rounded-md bg-shugur-600 px-4 py-2 text-sm font-semibold text-white shadow-sm hover:bg-shugur-700 transition-colors duration-200"
					>
						Get Started with Shugur Relay
					</a>
				</div>
			</div>

			<div class="mt-16 rounded-lg bg-blue-50 p-8 border border-blue-200">
				<h3 class="text-xl font-semibold text-blue-900">Why Choose Shugur's Distributed Architecture?</h3>
				<p class="mt-4 text-blue-800">
					Unlike traditional multi-relay setups that require complex client-side management, Shugur provides a 
					distributed relay cluster that eliminates single points of failure while maintaining simplicity for developers.
				</p>
				
				<div class="mt-6 grid gap-6 md:grid-cols-2">
					<div class="rounded-lg bg-white p-4 border border-blue-200">
						<h4 class="font-semibold text-blue-900 mb-2">Traditional Multi-Relay Setup</h4>
						<ul class="text-sm text-blue-800 space-y-1">
							<li>• Client manages multiple connections manually</li>
							<li>• Complex failover handling in application code</li>
							<li>• Data inconsistency between different relays</li>
							<li>• Increased development and maintenance complexity</li>
						</ul>
					</div>
					
					<div class="rounded-lg bg-white p-4 border border-blue-200">
						<h4 class="font-semibold text-blue-900 mb-2">Shugur Distributed Cluster</h4>
						<ul class="text-sm text-blue-800 space-y-1">
							<li>• Single connection point for all clients</li>
							<li>• Transparent automatic failover and load balancing</li>
							<li>• Real-time data synchronization across nodes</li>
							<li>• Simple client implementation and maintenance</li>
						</ul>
					</div>
				</div>
				
				<div class="mt-6 p-4 bg-blue-100 rounded-lg">
					<p class="text-sm text-blue-900">
						<strong>Key Benefit:</strong> The Shugur distributed relay architecture means you no longer need to implement 
						complex multi-relay management in your applications. Connect to a single endpoint and get automatic 
						high availability, load distribution, and data redundancy - all transparent to your client code while 
						ensuring your users can always access their data.
					</p>
				</div>
			</div>
		</div>
	</div>
</div>
