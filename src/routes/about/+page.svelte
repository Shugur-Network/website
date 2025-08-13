<script>
  import { 
    Wrench, 
    Target, 
    Users, 
    ExternalLink 
  } from 'lucide-svelte';
  import BuildIcon from '$lib/components/BuildIcon.svelte';
  import OptimizeIcon from '$lib/components/OptimizeIcon.svelte';
  import ConnectIcon from '$lib/components/ConnectIcon.svelte';
</script>

<svelte:head>
  <title>About - Shugur</title>
  <meta name="description" content="Learn about Shugur's mission to build open, resilient technology for everyone." />
</svelte:head>

<div class="mx-auto max-w-6xl px-4 py-16">
  <!-- Hero Section -->
  <div class="text-center mb-20">
    <h1 class="text-5xl md:text-6xl font-bold text-gray-900 mb-6 font-spartan">About Shugur</h1>
    <div class="text-2xl md:text-3xl font-semibold text-shugur-600 mb-8">
      "Build open, resilient tech for everyone."
    </div>
  </div>

  <!-- Simple where it matters Section -->
  <section class="mb-20">
    <header class="text-center mb-12">
      <h2 class="text-3xl font-bold text-gray-900 mb-4 font-spartan">Simple where it matters, open where it counts.</h2>
      <p class="text-gray-600 max-w-2xl mx-auto">
        We focus on building things that solve real problems with simple and elegant solutions.
      </p>
    </header>
    
    <div class="grid md:grid-cols-3 gap-8">
      <div 
        class="p-8 border border-gray-200 rounded-2xl bg-white hover:shadow-lg hover:border-shugur-500/20 transition-all duration-300 transform hover:-translate-y-1"
      >
        <div class="flex items-center gap-4 mb-6">
          <div class="w-14 h-14 bg-shugur-500/10 rounded-xl flex items-center justify-center flex-shrink-0">
            <BuildIcon className="w-7 h-7 text-shugur-500" />
          </div>
          <div class="font-bold text-2xl text-gray-900">Build</div>
        </div>
        <div class="text-gray-600 text-sm leading-relaxed">
          Tools that solve one problem extremely well.
        </div>
      </div>
      
      <div 
        class="p-8 border border-gray-200 rounded-2xl bg-white hover:shadow-lg hover:border-shugur-500/20 transition-all duration-300 transform hover:-translate-y-1"
      >
        <div class="flex items-center gap-4 mb-6">
          <div class="w-14 h-14 bg-shugur-500/10 rounded-xl flex items-center justify-center flex-shrink-0">
            <OptimizeIcon className="w-7 h-7 text-shugur-500" />
          </div>
          <div class="font-bold text-2xl text-gray-900">Optimize</div>
        </div>
        <div class="text-gray-600 text-sm leading-relaxed">
          Better performance, lower cost, fewer moving parts.
        </div>
      </div>
      
      <div 
        class="p-8 border border-gray-200 rounded-2xl bg-white hover:shadow-lg hover:border-shugur-500/20 transition-all duration-300 transform hover:-translate-y-1"
      >
        <div class="flex items-center gap-4 mb-6">
          <div class="w-14 h-14 bg-shugur-500/10 rounded-xl flex items-center justify-center flex-shrink-0">
            <ConnectIcon className="w-7 h-7 text-shugur-500" />
          </div>
          <div class="font-bold text-2xl text-gray-900">Connect</div>
        </div>
        <div class="text-gray-600 text-sm leading-relaxed">
          Integrations that make services work as one.
        </div>
      </div>
    </div>
  </section>

  <!-- Mission Section -->
  <section class="mb-20">
    <div class="grid md:grid-cols-2 gap-12 items-center">
      <div>
        <h2 class="text-3xl font-bold text-gray-900 mb-6">Our Mission</h2>
        <p class="text-gray-600 leading-relaxed mb-4">
          In a world where technology is increasingly centralized and fragile, we believe in building 
          systems that are open, resilient, and designed to last.
        </p>
        <p class="text-gray-600 leading-relaxed">
          We believe in building tools that solves real problems with simple, elegant solutions. 
          We create tools that everyone can trust and rely on.
        </p>
      </div>
      <div class="bg-shugur-50 rounded-3xl p-8">
        <h3 class="text-xl font-semibold text-gray-900 mb-4">Core Principles</h3>
        <ul class="space-y-3 text-gray-600">
          <li class="flex items-start gap-3">
            <div class="w-2 h-2 bg-shugur-500 rounded-full mt-2 flex-shrink-0"></div>
            <span>Resilient and fault-tolerant</span>
          </li>
          <li class="flex items-start gap-3">
            <div class="w-2 h-2 bg-shugur-500 rounded-full mt-2 flex-shrink-0"></div>
            <span>Simple where it matters</span>
          </li>
          <li class="flex items-start gap-3">
            <div class="w-2 h-2 bg-shugur-500 rounded-full mt-2 flex-shrink-0"></div>
            <span>Built for the long term</span>
          </li>
        </ul>
      </div>
    </div>
  </section>

  <!-- Values Section -->
  <section class="mb-20">
    <h2 class="text-3xl font-bold text-gray-900 text-center mb-12">What We Value</h2>
    <div class="grid md:grid-cols-3 gap-8">
      <div class="text-center p-6">
        <div class="w-16 h-16 bg-shugur-100 rounded-full flex items-center justify-center mx-auto mb-4">
          <Wrench class="w-8 h-8 text-shugur-600" />
        </div>
        <h3 class="text-xl font-semibold text-gray-900 mb-3">Quality</h3>
        <p class="text-gray-600">
          We build things that work, and keep working. Every line of code is written with care and consideration.
        </p>
      </div>
      
      <div class="text-center p-6">
        <div class="w-16 h-16 bg-shugur-100 rounded-full flex items-center justify-center mx-auto mb-4">
          <Target class="w-8 h-8 text-shugur-600" />
        </div>
        <h3 class="text-xl font-semibold text-gray-900 mb-3">Simplicity</h3>
        <p class="text-gray-600">
          Complex problems don't always need complex solutions. We prefer elegant, straightforward approaches.
        </p>
      </div>
      
      <div class="text-center p-6">
        <div class="w-16 h-16 bg-shugur-100 rounded-full flex items-center justify-center mx-auto mb-4">
          <Users class="w-8 h-8 text-shugur-600" />
        </div>
        <h3 class="text-xl font-semibold text-gray-900 mb-3">Community</h3>
        <p class="text-gray-600">
          We believe in the power of working together. Our projects grow stronger through shared knowledge and collaboration.
        </p>
      </div>
    </div>
  </section>

  <!-- Team Section -->
  <section class="mb-20">
    <h2 class="text-3xl font-bold text-gray-900 text-center mb-12">Our Team</h2>
    <div class="text-center">
      <p class="text-gray-600 max-w-2xl mx-auto mb-8">
        A team of engineers and designers who believe in the power of 
        open, resilient technology to solve real-world problems.
      </p>
      <div class="bg-shugur-50 rounded-3xl p-8">
        <h3 class="text-xl font-semibold text-gray-900 mb-4">Join Us</h3>
        <p class="text-gray-600">
          We're always looking for talented people who share our vision. 
          Whether you're a developer, designer, or just passionate about building better technology.
        </p>
      </div>
    </div>
  </section>

  <!-- Contact CTA -->
  <section class="text-center">
    <div class="bg-gray-900 text-white rounded-3xl p-12">
      <h2 class="text-3xl md:text-4xl font-bold mb-4">Ready to build something amazing?</h2>
      <p class="text-lg text-gray-300 mb-8 max-w-2xl mx-auto">
        Let's discuss how we can help you build resilient, open technology that makes a difference.
      </p>
      <div class="flex gap-4 justify-center flex-wrap">
        <a href="mailto:contact@shugur.com" class="px-6 py-3 rounded-2xl bg-shugur-500 text-white font-medium hover:bg-shugur-600 transition-all duration-300 hover:scale-105">
          Start a Conversation
        </a>
        <a href="https://github.com/Shugur-Network" target="_blank" class="px-6 py-3 rounded-2xl border border-white text-white font-medium hover:bg-white hover:text-gray-900 transition-all duration-300 flex items-center gap-2">
          View Our Work
          <ExternalLink class="w-4 h-4" />
        </a>
      </div>
    </div>
  </section>
</div>
