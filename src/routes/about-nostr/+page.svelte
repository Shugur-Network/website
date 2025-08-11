<script>
	import { base } from '$app/paths';
</script>

<svelte:head>
	<title>About Nostr Relays - The Infrastructure of Decentralized Social Networks | Shugur Relay</title>
	<meta name="description" content="Deep dive into Nostr relays: how they work, their role in decentralized networks, and why they're essential for censorship-resistant communication." />
</svelte:head>

<div class="bg-white px-6 py-32 lg:px-8">
	<div class="mx-auto max-w-4xl text-base leading-7 text-gray-700">
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
			
			<div class="mt-8 rounded-lg bg-blue-50 p-6">
				<h3 class="text-lg font-semibold text-blue-900">Key Characteristics</h3>
				<ul class="mt-4 space-y-2 text-blue-800">
					<li>• <strong>Stateless:</strong> Relays don't maintain user sessions or authentication state</li>
					<li>• <strong>Simple:</strong> Uses WebSocket connections for real-time communication</li>
					<li>• <strong>Event-driven:</strong> Everything is an "event" - posts, likes, follows, messages</li>
					<li>• <strong>Cryptographically signed:</strong> All events are signed by users' private keys</li>
				</ul>
			</div>
			
			<h2 class="mt-16 text-2xl font-bold tracking-tight text-gray-900">How Relays Work in the Nostr Ecosystem</h2>
			
			<div class="mt-8 space-y-12">
				<div class="grid gap-8 lg:grid-cols-3">
					<div class="rounded-lg border border-gray-200 p-6">
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
					
					<div class="rounded-lg border border-gray-200 p-6">
						<div class="text-center">
							<div class="mx-auto h-12 w-12 rounded-full bg-blue-100 flex items-center justify-center">
								<span class="text-xl font-bold text-blue-600">2</span>
							</div>
							<h3 class="mt-4 font-semibold text-gray-900">Relay Distribution</h3>
							<p class="mt-2 text-sm text-gray-600">
								Events are sent to multiple relays for redundancy and wider distribution
							</p>
						</div>
					</div>
					
					<div class="rounded-lg border border-gray-200 p-6">
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
				<div class="rounded-lg bg-gray-50 p-6">
					<h3 class="text-lg font-semibold text-gray-900">READ Operations</h3>
					<p class="mt-2">
						Clients send <code class="bg-gray-200 px-2 py-1 rounded">REQ</code> messages to request events. 
						Relays respond with matching events and send <code class="bg-gray-200 px-2 py-1 rounded">EOSE</code> 
						(End of Stored Events) when the initial query is complete.
					</p>
				</div>
				
				<div class="rounded-lg bg-gray-50 p-6">
					<h3 class="text-lg font-semibold text-gray-900">WRITE Operations</h3>
					<p class="mt-2">
						Clients send <code class="bg-gray-200 px-2 py-1 rounded">EVENT</code> messages to publish new content. 
						Relays validate the signature and respond with <code class="bg-gray-200 px-2 py-1 rounded">OK</code> 
						messages indicating acceptance or rejection.
					</p>
				</div>
				
				<div class="rounded-lg bg-gray-50 p-6">
					<h3 class="text-lg font-semibold text-gray-900">CLOSE Operations</h3>
					<p class="mt-2">
						Clients can close subscriptions using <code class="bg-gray-200 px-2 py-1 rounded">CLOSE</code> 
						messages to stop receiving events for specific queries.
					</p>
				</div>
			</div>
			
			<h2 class="mt-16 text-2xl font-bold tracking-tight text-gray-900">Why Relays Are Essential</h2>
			
			<div class="mt-8 grid gap-8 lg:grid-cols-2">
				<div class="rounded-lg border border-gray-200 p-6">
					<h3 class="font-semibold text-gray-900 text-lg">Redundancy & Resilience</h3>
					<p class="mt-3">
						Users connect to multiple relays simultaneously. If one relay goes down or censors content, 
						users can still access their social graph through other relays. This creates a robust, 
						fault-tolerant network.
					</p>
				</div>
				
				<div class="rounded-lg border border-gray-200 p-6">
					<h3 class="font-semibold text-gray-900 text-lg">Geographic Distribution</h3>
					<p class="mt-3">
						Relays can be deployed globally, reducing latency and providing local data sovereignty. 
						Users can choose relays based on location, policies, or trust relationships.
					</p>
				</div>
				
				<div class="rounded-lg border border-gray-200 p-6">
					<h3 class="font-semibold text-gray-900 text-lg">Specialized Services</h3>
					<p class="mt-3">
						Different relays can offer specialized features: some focus on performance, others on specific 
						content types, privacy features, or community moderation policies.
					</p>
				</div>
				
				<div class="rounded-lg border border-gray-200 p-6">
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
						<div class="rounded-lg bg-yellow-50 p-4">
							<h4 class="font-medium text-yellow-900">High Throughput</h4>
							<p class="mt-1 text-sm text-yellow-800">Handle thousands of simultaneous WebSocket connections</p>
						</div>
						<div class="rounded-lg bg-blue-50 p-4">
							<h4 class="font-medium text-blue-900">Low Latency</h4>
							<p class="mt-1 text-sm text-blue-800">Real-time event distribution for live conversations</p>
						</div>
						<div class="rounded-lg bg-green-50 p-4">
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
			
			<div class="mt-16 rounded-lg bg-green-50 p-8">
				<h3 class="text-xl font-semibold text-green-900">Shugur Relay: Enterprise-Grade Nostr Infrastructure</h3>
				<p class="mt-4 text-green-800">
					Shugur Relay is built specifically for production environments, offering high-performance Nostr 
					relay infrastructure with enterprise features like monitoring, analytics, and managed scaling. 
					Deploy your own censorship-resistant social network infrastructure in minutes, not months.
				</p>
				<div class="mt-6">
					<a 
						href="{base}/#installation" 
						class="inline-flex items-center rounded-md bg-green-600 px-4 py-2 text-sm font-semibold text-white shadow-sm hover:bg-green-500"
					>
						Get Started with Shugur Relay
					</a>
				</div>
			</div>
		</div>
	</div>
</div>
