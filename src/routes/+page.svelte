<script lang="ts">
	import { onMount } from 'svelte';

	// Icons
	const ArrowRight = `<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"/><path d="m12 5 7 7-7 7"/></svg>`;
	const Paperclip = `<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m21.44 11.05-9.19 9.19a6 6 0 0 1-8.49-8.49l8.57-8.57A4 4 0 1 1 18 8.84l-8.59 8.57a2 2 0 0 1-2.83-2.83l8.49-8.48"/></svg>`;
	const Send = `<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m22 2-7 20-4-9-9-4Z"/><path d="M22 2 11 13"/></svg>`;
	const ChevronLeft = `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m15 18-6-6 6-6"/></svg>`;
	const ChevronRight = `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m9 18 6-6-6-6"/></svg>`;

	// Data
	const navLinks = [
		{ name: 'Services', href: '#' },
		{ name: 'Company', href: '#' },
		{ name: 'Careers', href: '#', badge: '2' },
		{ name: 'Security', href: '#' }
	];
</script>

<div class="min-h-screen bg-white text-gray-900 font-sans selection:bg-gray-200">
	<!-- Navbar -->
	<nav class="fixed top-0 left-0 right-0 z-50 bg-white/90 backdrop-blur-sm border-b border-transparent transition-all duration-300">
		<div class="max-w-[1400px] mx-auto px-6 h-20 flex items-center justify-between">
			<a href="/" class="text-2xl font-serif font-bold tracking-tight flex items-center gap-2">
				<svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor" class="hidden">
					<path d="M3 21h18v-2H3v2zm0-4h18v-2H3v2zm0-4h18v-2H3v2zm0-4h18V7H3v2zm0-6v2h18V3H3z"/>
				</svg>
				Build.
			</a>

			<div class="hidden md:flex items-center gap-8">
				{#each navLinks as link}
					<a href={link.href} class="text-sm font-medium text-gray-600 hover:text-gray-900 transition-colors relative">
						{link.name}
						{#if link.badge}
							<span class="absolute -top-2 -right-3 bg-red-100 text-red-600 text-[10px] font-bold px-1.5 py-0.5 rounded-full border border-red-200">{link.badge}</span>
						{/if}
					</a>
				{/each}
			</div>

			<div class="flex items-center gap-6">
				<a href="#" class="text-sm font-medium text-gray-900 hover:text-gray-600">Log In</a>
				<a href="#" class="bg-black text-white text-sm font-medium px-5 py-2.5 rounded-full hover:bg-gray-800 transition-colors">Get Started</a>
			</div>
		</div>
	</nav>

	<!-- Hero Section -->
	<section class="pt-32 pb-20 px-6">
		<div class="max-w-4xl mx-auto text-center mb-16">
			<h1 class="text-5xl md:text-7xl font-serif mb-6 leading-[1.1]">
				The Agentic Development Firm<br />
				<span class="text-gray-400 italic">Built for Execution</span>
			</h1>
			<p class="text-gray-600 text-lg md:text-xl max-w-2xl mx-auto mb-10 leading-relaxed">
				The first AI native operating partner for institutional real estate, with output verified and delivered by domain experts with decades of experience.
			</p>
			<a href="#" class="inline-flex items-center justify-center bg-black text-white text-sm font-medium px-8 py-3 rounded-full hover:bg-gray-800 transition-colors">
				Partner with Build
			</a>
		</div>

		<!-- Hero Image with Overlay -->
		<div class="max-w-[1400px] mx-auto relative group">
			<div class="relative aspect-[21/9] overflow-hidden rounded-sm bg-gray-100">
				<img 
					src="https://images.unsplash.com/photo-1486406146926-c627a92ad1ab?q=80&w=2670&auto=format&fit=crop" 
					alt="Skyscrapers looking up" 
					class="w-full h-full object-cover grayscale opacity-90"
				/>
				<!-- Overlay Gradient -->
				<div class="absolute inset-0 bg-gradient-to-t from-black/20 to-transparent"></div>
			</div>

			<!-- Floating Input UI -->
			<div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-full max-w-lg">
				<div class="bg-white rounded-lg shadow-2xl p-2 border border-gray-200/50 backdrop-blur-sm bg-white/95">
					<div class="flex flex-col gap-2 p-2">
						<div class="text-sm text-gray-800 font-medium leading-relaxed">
							Pull zoning overlays, entitlement status, and floodplain risk for a 40-ac<span class="animate-pulse">|</span>
						</div>
						<div class="flex items-center justify-between mt-2 pt-2 border-t border-gray-100">
							<button class="text-gray-400 hover:text-gray-600 p-1">
								{@html Paperclip}
							</button>
							<button class="bg-black text-white p-1.5 rounded-md hover:bg-gray-800">
								{@html Send}
							</button>
						</div>
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Value Prop Section -->
	<section class="py-24 px-6 border-b border-gray-100">
		<div class="max-w-[1400px] mx-auto grid grid-cols-1 lg:grid-cols-2 gap-16 items-start">
			<div class="max-w-xl">
				<h2 class="text-4xl md:text-5xl font-serif leading-tight mb-6">
					Build accelerates development on the world's most important projects.
				</h2>
				<p class="text-gray-600 text-lg mb-8">
					The world has sped up. Development should too.
				</p>
				<a href="#" class="inline-flex items-center justify-center bg-black text-white text-sm font-medium px-6 py-3 rounded-full hover:bg-gray-800 transition-colors">
					Get Started
				</a>
			</div>

			<div class="space-y-12">
				<div class="pl-6 border-l border-gray-200">
					<p class="text-lg text-gray-800 leading-relaxed mb-4">
						"Build is the first application of AI into the vertical that is able to execute on all of the complexities across our different markets."
					</p>
					<p class="text-sm text-gray-500">
						Due Diligence & Site Selection EMEA, JV
					</p>
				</div>
				<div class="pl-6 border-l border-gray-200">
					<p class="text-lg text-gray-800 leading-relaxed mb-4">
						"The ROI with Build was immediate. We had buy-box ready, fully vetted opportunities delivered to us within a day."
					</p>
					<p class="text-sm text-gray-500">
						Director, Head of Industrials US, Developer
					</p>
				</div>
			</div>
		</div>
	</section>

	<!-- Features Grid -->
	<section class="py-24 px-6 border-b border-gray-100">
		<div class="max-w-[1400px] mx-auto grid grid-cols-1 md:grid-cols-3 gap-12">
			<!-- Item 1 -->
			<div class="group">
				<div class="text-xs font-mono text-gray-400 mb-6">001</div>
				<h3 class="text-2xl font-serif mb-4 group-hover:text-gray-600 transition-colors">Speed that creates advantage</h3>
				<p class="text-gray-600 leading-relaxed text-sm">
					Our agentic AI, Dougie, never sleeps and our systems are built for processing speed and scale.
				</p>
			</div>
			<!-- Item 2 -->
			<div class="group">
				<div class="text-xs font-mono text-gray-400 mb-6">002</div>
				<h3 class="text-2xl font-serif mb-4 group-hover:text-gray-600 transition-colors">Expertise you can trust</h3>
				<p class="text-gray-600 leading-relaxed text-sm">
					Each insight carefully verified and grounded by our in-house experts.
				</p>
			</div>
			<!-- Item 3 -->
			<div class="group">
				<div class="text-xs font-mono text-gray-400 mb-6">003</div>
				<h3 class="text-2xl font-serif mb-4 group-hover:text-gray-600 transition-colors">Upfront pricing</h3>
				<p class="text-gray-600 leading-relaxed text-sm">
					Fixed rates by the deliverable, not by the hour. Do more with less spend.
				</p>
			</div>
		</div>
	</section>

	<!-- The New Standard Section -->
	<section class="py-24 px-6">
		<div class="max-w-[1400px] mx-auto mb-20">
			<h2 class="text-4xl md:text-5xl font-serif mb-12">The New Standard for Development</h2>
		</div>

		<div class="max-w-[1400px] mx-auto grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
			<!-- Left Image Area -->
			<div class="relative bg-gray-100 aspect-square md:aspect-[4/3] rounded-sm overflow-hidden">
				<img 
					src="https://images.unsplash.com/photo-1486325212027-8081e485255e?q=80&w=2670&auto=format&fit=crop" 
					alt="Building detail" 
					class="w-full h-full object-cover grayscale opacity-80"
				/>
				<!-- Overlay Cards -->
				<div class="absolute inset-0 flex flex-col items-center justify-center gap-4 p-8">
					<div class="bg-white/90 backdrop-blur-sm p-4 w-full max-w-xs text-center shadow-lg border border-gray-200/50 rounded-sm">
						<span class="text-sm font-medium text-gray-500">Real-time Web Search</span>
					</div>
					<div class="bg-white p-6 w-full max-w-sm text-center shadow-xl border border-gray-200 rounded-sm flex items-center gap-4 justify-center">
						<div class="w-10 h-10 bg-black text-white flex items-center justify-center rounded-sm">
							<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polygon points="1 6 1 22 8 18 16 22 23 18 23 2 16 6 8 2 1 6"/></svg>
						</div>
						<span class="text-lg font-medium text-gray-900">Geospatial Data</span>
					</div>
					<div class="bg-white/90 backdrop-blur-sm p-4 w-full max-w-xs text-center shadow-lg border border-gray-200/50 rounded-sm">
						<span class="text-sm font-medium text-gray-500">National Databases</span>
					</div>
				</div>
			</div>

			<!-- Right Content -->
			<div class="max-w-lg">
				<h2 class="text-4xl md:text-5xl font-serif leading-tight mb-6">
					Time is money.<br />Save both.
				</h2>
				<p class="text-gray-600 text-lg mb-8 leading-relaxed">
					Build pairs agentic AI with industry expertise to 10x development workflows end to end. Delivered to your inbox.
				</p>
				<a href="#" class="inline-flex items-center justify-center bg-black text-white text-sm font-medium px-6 py-3 rounded-full hover:bg-gray-800 transition-colors mb-12">
					Get Started
				</a>

				<ul class="space-y-4">
					<li class="flex items-start gap-3 text-sm text-gray-600">
						<span class="w-1.5 h-1.5 rounded-full bg-gray-400 mt-2"></span>
						Leverage your Firm's Workflows
					</li>
					<li class="flex items-start gap-3 text-sm text-gray-600">
						<span class="w-1.5 h-1.5 rounded-full bg-gray-400 mt-2"></span>
						Embed AI Into your Firm's DNA
					</li>
					<li class="flex items-start gap-3 text-sm text-gray-600">
						<span class="w-1.5 h-1.5 rounded-full bg-black mt-2"></span>
						<span class="text-gray-900 font-medium">Accurate and Grounded</span>
					</li>
					<li class="flex items-start gap-3 text-sm text-gray-600">
						<span class="w-1.5 h-1.5 rounded-full bg-gray-400 mt-2"></span>
						Interoperable Data Platform
					</li>
				</ul>
			</div>
		</div>
	</section>

	<!-- Sub-features Grid -->
	<section class="py-12 px-6 border-b border-gray-100">
		<div class="max-w-[1400px] mx-auto grid grid-cols-1 md:grid-cols-3 gap-12">
			<!-- Item 1 -->
			<div class="bg-gray-50/50 p-8 rounded-sm border border-gray-100">
				<div class="flex items-center gap-2 mb-4">
					<div class="p-1.5 bg-gray-200 rounded-sm">
						<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect width="18" height="18" x="3" y="3" rx="2"/><path d="M3 9h18"/><path d="M9 21V9"/></svg>
					</div>
					<span class="text-xs font-bold uppercase tracking-wider text-gray-500">Workflows</span>
				</div>
				<p class="text-sm font-medium text-gray-900 mb-2">Mission-critical automation for your workflows.</p>
				<p class="text-sm text-gray-600 leading-relaxed">
					Build deploys AI agents to produce complete development documents from diligence to design, 90% faster than humans with an expert human-in-the-loop for QA.
				</p>
			</div>
			<!-- Item 2 -->
			<div class="bg-gray-50/50 p-8 rounded-sm border border-gray-100">
				<div class="flex items-center gap-2 mb-4">
					<div class="p-1.5 bg-gray-200 rounded-sm">
						<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect width="18" height="18" x="3" y="3" rx="2"/><path d="M7 7h10"/><path d="M7 12h10"/><path d="M7 17h10"/></svg>
					</div>
					<span class="text-xs font-bold uppercase tracking-wider text-gray-500">Platform</span>
				</div>
				<p class="text-sm font-medium text-gray-900 mb-2">Real time insights on the world's CRE data.</p>
				<p class="text-sm text-gray-600 leading-relaxed">
					From interoperability across the unstructured world of CRE data, to real-time tracking of assets and their markets, Build's ontology and agentic layer is the foundation to your portfolio.
				</p>
			</div>
			<!-- Item 3 -->
			<div class="bg-gray-50/50 p-8 rounded-sm border border-gray-100">
				<div class="flex items-center gap-2 mb-4">
					<div class="p-1.5 bg-gray-200 rounded-sm">
						<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 2a10 10 0 1 0 10 10 4 4 0 0 1-5-5 4 4 0 0 1-5-5c0-2 2-2 2-2"/><path d="M12 2v2"/><path d="M12 22v-2"/><path d="m17 17-1.4-1.4"/><path d="m7 7-1.4-1.4"/><path d="m17 7-1.4 1.4"/><path d="m7 17-1.4 1.4"/></svg>
					</div>
					<span class="text-xs font-bold uppercase tracking-wider text-gray-500">Assistant</span>
				</div>
				<p class="text-sm font-medium text-gray-900 mb-2">Meet Dougie — your most productive teammate.</p>
				<p class="text-sm text-gray-600 leading-relaxed">
					Activate Dougie through an email, triggering workflows, data retrieval and sharing context across project stakeholders. Dougie builds up memory across projects as they develop.
				</p>
			</div>
		</div>
	</section>

	<!-- Better Results Section -->
	<section class="py-24 px-6 border-b border-gray-100">
		<div class="max-w-[1400px] mx-auto mb-16">
			<h2 class="text-4xl md:text-5xl font-serif">Better results, next-day delivery</h2>
		</div>

		<div class="max-w-[1400px] mx-auto grid grid-cols-1 md:grid-cols-3 gap-12">
			<!-- Item 1 -->
			<div>
				<h3 class="text-2xl font-serif mb-4 flex items-baseline gap-2">
					<span class="text-gray-300 font-sans text-lg">1.</span> Email Dougie
				</h3>
				<p class="text-gray-600 leading-relaxed text-sm">
					Project to move forward? Send a request via email and Dougie will execute.
				</p>
			</div>
			<!-- Item 2 -->
			<div>
				<h3 class="text-2xl font-serif mb-4 flex items-baseline gap-2">
					<span class="text-gray-300 font-sans text-lg">2.</span> Dougie Processes
				</h3>
				<p class="text-gray-600 leading-relaxed text-sm">
					Dougie runs workflows from start to finish, outputting a professional-grade document.
				</p>
			</div>
			<!-- Item 3 -->
			<div>
				<h3 class="text-2xl font-serif mb-4 flex items-baseline gap-2">
					<span class="text-gray-300 font-sans text-lg">3.</span> Expert Judgment
				</h3>
				<p class="text-gray-600 leading-relaxed text-sm">
					In-house professionals weigh in on tricky issues and ensure accuracy and the stamp of excellence.
				</p>
			</div>
		</div>
	</section>

	<!-- Security Section -->
	<section class="py-24 px-6 border-b border-gray-100">
		<div class="max-w-[1400px] mx-auto grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
			<!-- Left Image -->
			<div class="relative aspect-[4/3] rounded-sm overflow-hidden bg-gray-100">
				<img 
					src="https://images.unsplash.com/photo-1541888946425-d81bb19240f5?q=80&w=2670&auto=format&fit=crop" 
					alt="Construction workers on beam" 
					class="w-full h-full object-cover grayscale"
				/>
			</div>

			<!-- Right Content -->
			<div class="max-w-lg">
				<h2 class="text-4xl md:text-5xl font-serif mb-6">
					Secure, accurate, & trustworthy
				</h2>
				<p class="text-gray-600 text-lg mb-8 leading-relaxed">
					Build's security is made for Enterprise needs - segmenting customer data with private cloud and jurisdictional data storage available. We're SOC 2 Type II compliant and backed by regular pen testing.
				</p>
				<a href="#" class="inline-flex items-center justify-center bg-black text-white text-sm font-medium px-6 py-3 rounded-full hover:bg-gray-800 transition-colors mb-12">
					Get Started
				</a>

				<ul class="space-y-4">
					<li class="flex items-center gap-3 text-sm text-gray-600">
						<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>
						SOC 2 Type II
					</li>
					<li class="flex items-center gap-3 text-sm text-gray-600">
						<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect width="18" height="18" x="3" y="3" rx="2"/><path d="M3 9h18"/><path d="M9 21V9"/></svg>
						Regional data storage
					</li>
					<li class="flex items-center gap-3 text-sm text-gray-600">
						<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M17.5 19c0-1.7-1.3-3-3-3h-5c-1.7 0-3 1.3-3 3"/><path d="M16 13h-8"/><path d="M16 9h-8"/></svg>
						Private cloud on request
					</li>
					<li class="flex items-center gap-3 text-sm text-gray-600">
						<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"/><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"/></svg>
						SSO
					</li>
				</ul>
			</div>
		</div>
	</section>

	<!-- Data Sources Section -->
	<section class="py-24 px-6 border-b border-gray-100">
		<div class="max-w-[1400px] mx-auto mb-16">
			<h2 class="text-4xl md:text-5xl font-serif mb-12">Trusted & Comprehensive Data across Jurisdictions</h2>
			
			<!-- Data Grid -->
			<div class="grid grid-cols-1 md:grid-cols-3 gap-px bg-gray-200 border border-gray-200 mb-16">
				<div class="bg-white p-8 flex items-center gap-4">
					<div class="p-2 bg-gray-50 rounded-sm">
						<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><polygon points="1 6 1 22 8 18 16 22 23 18 23 2 16 6 8 2 1 6"/></svg>
					</div>
					<span class="text-sm font-medium text-gray-700">Maps & Geospatial Data</span>
				</div>
				<div class="bg-white p-8 flex items-center gap-4">
					<div class="p-2 bg-gray-50 rounded-sm">
						<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M3 21h18v-2H3v2zm0-4h18v-2H3v2zm0-4h18v-2H3v2zm0-4h18V7H3v2zm0-6v2h18V3H3z"/></svg>
					</div>
					<span class="text-sm font-medium text-gray-700">Municipal & Government Portals</span>
				</div>
				<div class="bg-white p-8 flex items-center gap-4">
					<div class="p-2 bg-gray-50 rounded-sm">
						<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M16 18l6-6-6-6"/><path d="M8 6l-6 6 6 6"/></svg>
					</div>
					<span class="text-sm font-medium text-gray-700">APIs</span>
				</div>
				<div class="bg-white p-8 flex items-center gap-4">
					<div class="p-2 bg-gray-50 rounded-sm">
						<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="3" width="20" height="14" rx="2" ry="2"/><line x1="8" y1="21" x2="16" y2="21"/><line x1="12" y1="17" x2="12" y2="21"/></svg>
					</div>
					<span class="text-sm font-medium text-gray-700">Real time Web & News</span>
				</div>
				<div class="bg-white p-8 flex items-center gap-4">
					<div class="p-2 bg-gray-50 rounded-sm">
						<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M4 19.5A2.5 2.5 0 0 1 6.5 17H20"/><path d="M6.5 2H20v20H6.5A2.5 2.5 0 0 1 4 19.5v-15A2.5 2.5 0 0 1 6.5 2z"/></svg>
					</div>
					<span class="text-sm font-medium text-gray-700">National Databases</span>
				</div>
				<div class="bg-white p-8 flex items-center gap-4">
					<div class="p-2 bg-gray-50 rounded-sm">
						<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/><polyline points="14 2 14 8 20 8"/><line x1="16" y1="13" x2="8" y2="13"/><line x1="16" y1="17" x2="8" y2="17"/><polyline points="10 9 9 9 8 9"/></svg>
					</div>
					<span class="text-sm font-medium text-gray-700">Proprietary Datasets</span>
				</div>
				<div class="bg-white p-8 flex items-center gap-4">
					<div class="p-2 bg-gray-50 rounded-sm">
						<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M6 9H4.5a2.5 2.5 0 0 1 0-5H6"/><path d="M18 9h1.5a2.5 2.5 0 0 0 0-5H18"/><path d="M4 22h16"/><path d="M10 14.66V17c0 .55-.47.98-.97 1.21C7.85 18.75 7 20.24 7 22"/><path d="M14 14.66V17c0 .55.47.98.97 1.21C16.15 18.75 17 20.24 17 22"/><path d="M10 2v2a2 2 0 0 1-2 2"/><path d="M14 2v2a2 2 0 0 0 2 2"/></svg>
					</div>
					<span class="text-sm font-medium text-gray-700">Utility Records</span>
				</div>
				<div class="bg-white p-8 flex items-center gap-4">
					<div class="p-2 bg-gray-50 rounded-sm">
						<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M12 20h9"/><path d="M16.5 3.5a2.121 2.121 0 0 1 3 3L7 19l-4 1 1-4L16.5 3.5z"/></svg>
					</div>
					<span class="text-sm font-medium text-gray-700">Calls & Transcripts</span>
				</div>
				<div class="bg-white p-8 flex items-center gap-4">
					<div class="p-2 bg-gray-50 rounded-sm">
						<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M4 22h14a2 2 0 0 0 2-2V7.5L14.5 2H6a2 2 0 0 0-2 2v4"/><polyline points="14 2 14 8 20 8"/><path d="M2 15h10"/><path d="m9 18 3-3-3-3"/></svg>
					</div>
					<span class="text-sm font-medium text-gray-700">Your Firms Data</span>
				</div>
			</div>

			<!-- Map Placeholder -->
			<div class="w-full relative">
				<!-- Legend -->
				<div class="flex items-center justify-center gap-6 mb-8 text-xs text-gray-500">
					<div class="flex items-center gap-2">
						<span class="w-2 h-2 rounded-full bg-gray-200"></span> Not available
					</div>
					<div class="flex items-center gap-2">
						<span class="w-2 h-2 rounded-full bg-gray-300"></span> In progress
					</div>
					<div class="flex items-center gap-2">
						<span class="w-2 h-2 rounded-full bg-black"></span> Online
					</div>
				</div>
				
				<!-- Simple SVG Map Representation -->
				<div class="w-full aspect-[2/1] bg-gray-50 rounded-sm relative overflow-hidden">
					<img 
						src="https://upload.wikimedia.org/wikipedia/commons/8/80/World_map_-_low_resolution.svg" 
						alt="World Map" 
						class="w-full h-full object-cover opacity-20"
					/>
					<!-- Highlighted Areas (Fake) -->
					<div class="absolute top-[30%] left-[15%] w-[20%] h-[30%] bg-black mix-blend-multiply opacity-80 rounded-full blur-3xl"></div>
					<div class="absolute top-[25%] left-[48%] w-[10%] h-[20%] bg-black mix-blend-multiply opacity-80 rounded-full blur-3xl"></div>
				</div>
			</div>
		</div>
	</section>

	<!-- Asset Classes Section -->
	<section class="py-24 px-6 border-b border-gray-100">
		<div class="max-w-[1400px] mx-auto mb-12 flex items-end justify-between">
			<h2 class="text-4xl md:text-5xl font-serif">Across Asset-Classes</h2>
			<div class="flex gap-2">
				<button class="w-10 h-10 rounded-full border border-gray-200 flex items-center justify-center hover:bg-gray-50 transition-colors">
					{@html ChevronLeft}
				</button>
				<button class="w-10 h-10 rounded-full border border-gray-200 flex items-center justify-center hover:bg-gray-50 transition-colors">
					{@html ChevronRight}
				</button>
			</div>
		</div>

		<div class="max-w-[1400px] mx-auto grid grid-cols-1 md:grid-cols-3 gap-6">
			<div class="aspect-[3/4] bg-gray-100 relative group overflow-hidden">
				<img 
					src="https://images.unsplash.com/photo-1558494949-ef526b0042a0?q=80&w=2670&auto=format&fit=crop" 
					alt="Server Room" 
					class="w-full h-full object-cover grayscale group-hover:scale-105 transition-transform duration-500"
				/>
			</div>
			<div class="aspect-[3/4] bg-gray-100 relative group overflow-hidden">
				<img 
					src="https://images.unsplash.com/photo-1486406146926-c627a92ad1ab?q=80&w=2670&auto=format&fit=crop" 
					alt="Office Building" 
					class="w-full h-full object-cover grayscale group-hover:scale-105 transition-transform duration-500"
				/>
			</div>
			<div class="aspect-[3/4] bg-gray-100 relative group overflow-hidden">
				<img 
					src="https://images.unsplash.com/photo-1553413077-190dd305871c?q=80&w=2670&auto=format&fit=crop" 
					alt="Industrial" 
					class="w-full h-full object-cover grayscale group-hover:scale-105 transition-transform duration-500"
				/>
			</div>
		</div>
	</section>

	<!-- Testimonial Section -->
	<section class="py-24 px-6 border-b border-gray-100">
		<div class="max-w-[1400px] mx-auto mb-16">
			<h2 class="text-4xl md:text-5xl font-serif">For All Different Kinds of Firm</h2>
		</div>

		<div class="max-w-[1400px] mx-auto grid grid-cols-1 lg:grid-cols-2 gap-16">
			<div class="flex flex-col justify-between">
				<div>
					<h3 class="text-4xl font-bold mb-12">Aston</h3>
					<p class="text-2xl md:text-3xl font-medium leading-tight mb-12">
						"I was writing 6 figure contracts to do the work that Build is now doing for us for much less and much faster - Build is the reason in why we can keep increasing deal capacity without increasing headcount."
					</p>
				</div>
				<div>
					<p class="text-lg font-medium text-gray-900">Doug Chambers</p>
					<p class="text-gray-500">Head of Development, Aston</p>
				</div>
			</div>
			<div class="aspect-square bg-gray-100 overflow-hidden">
				<img 
					src="https://images.unsplash.com/photo-1487958449943-2429e8be8625?q=80&w=2670&auto=format&fit=crop" 
					alt="Abstract Architecture" 
					class="w-full h-full object-cover grayscale"
				/>
			</div>
		</div>
	</section>

	<!-- Footer -->
	<footer class="py-24 px-6">
		<div class="max-w-[1400px] mx-auto grid grid-cols-1 lg:grid-cols-2 gap-24 mb-24">
			<div>
				<div class="flex items-center gap-2 mb-8">
					<svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor" class="hidden">
						<path d="M3 21h18v-2H3v2zm0-4h18v-2H3v2zm0-4h18v-2H3v2zm0-4h18V7H3v2zm0-6v2h18V3H3z"/>
					</svg>
					<span class="text-2xl font-serif font-bold tracking-tight">Build.</span>
				</div>
				<h2 class="text-4xl md:text-5xl font-serif mb-8">Ready to Build?</h2>
				<a href="#" class="inline-flex items-center justify-center bg-black text-white text-sm font-medium px-8 py-3 rounded-full hover:bg-gray-800 transition-colors">
					Get Started
				</a>
			</div>

			<div class="flex flex-col lg:items-end justify-between gap-12">
				<div class="text-right text-sm text-gray-600 space-y-2">
					<p>2261 Market Street, STE 22610</p>
					<p>San Francisco, CA 94114</p>
					<div class="h-4"></div>
					<p class="flex items-center justify-end gap-2">
						1 S 1st St, Brooklyn, NY 11249 
						<span class="bg-gray-100 text-gray-500 text-[10px] px-1.5 py-0.5 rounded-sm">soon</span>
					</p>
					<p>140 Goswell Rd.,</p>
					<p>London EC1V 7DY</p>
				</div>

				<div class="flex items-center gap-4">
					<div class="w-12 h-12 rounded-full border border-gray-300 flex items-center justify-center text-[10px] font-bold text-gray-500 text-center leading-tight">
						AICPA<br/>SOC
					</div>
					<div class="w-12 h-12 rounded-full border border-gray-300 flex items-center justify-center text-[10px] font-bold text-gray-500 text-center leading-tight">
						SOC 2<br/>TYPE II<br/>CERTIFIED
					</div>
				</div>
			</div>
		</div>

		<div class="max-w-[1400px] mx-auto flex items-center justify-between pt-8 border-t border-gray-100 text-xs text-gray-400">
			<p>© 2025 Build Technologies, Inc.</p>
			<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="currentColor" class="text-gray-200"><path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"/></svg>
		</div>
	</footer>

</div>

