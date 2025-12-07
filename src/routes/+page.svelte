<script lang="ts">
	import { onMount } from 'svelte';

	// Icons
	const ArrowRight = `<svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M6 12L10 8L6 4" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/></svg>`;
	const LogoIcon = `<svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M12 2L2 22H22L12 2Z" fill="currentColor"/></svg>`; // Placeholder triangle
    const CheckIcon = `<svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"></polyline></svg>`;

    // Data
    const companies = ["Palantir", "Taba", "Decagon", "Meter", "Rippling", "Neros", "Windsurf"];
</script>

<div class="min-h-screen flex flex-col font-sans text-[#111]">
	<!-- Navbar -->
	<nav class="sticky top-0 z-50 bg-[#FBFBF9]/80 backdrop-blur-md border-b border-transparent transition-all duration-300">
		<div class="max-w-[1400px] mx-auto px-6 h-20 flex items-center justify-between">
			<div class="flex items-center gap-2 font-medium text-xl tracking-tight">
				<div class="w-6 h-6 bg-black text-white rounded-full flex items-center justify-center text-[10px]">
                    <!-- Custom Logo Icon -->
                    <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
                        <path d="M12 2L22 20H2L12 2Z" />
                    </svg>
                </div>
				Paraform
			</div>

			<div class="hidden md:flex items-center gap-8 text-sm font-medium text-gray-600">
				<a href="#" class="hover:text-black transition-colors">For companies</a>
				<a href="#" class="hover:text-black transition-colors">For recruiters</a>
				<a href="#" class="hover:text-black transition-colors">Customers</a>
				<a href="#" class="hover:text-black transition-colors">Resources</a>
				<a href="#" class="hover:text-black transition-colors">Careers</a>
			</div>

			<div class="flex items-center gap-4 text-sm font-medium">
				<a href="#" class="hidden md:block hover:text-gray-600 transition-colors">Sign up</a>
				<a href="#" class="bg-black text-white px-5 py-2.5 rounded-full hover:bg-gray-800 transition-colors">Get a demo</a>
			</div>
		</div>
	</nav>

	<!-- Hero Section -->
	<section class="pt-16 pb-24 px-6 flex flex-col items-center text-center">
		<a href="#" class="inline-flex items-center gap-2 bg-white border border-gray-200 rounded-full pl-1 pr-3 py-1 text-xs font-medium text-gray-600 hover:border-gray-300 transition-colors mb-8 shadow-sm">
			<div class="w-5 h-5 rounded-full overflow-hidden bg-gray-100 flex-shrink-0">
                <img src="https://placehold.co/20x20/black/white?text=P" alt="P" class="w-full h-full object-cover" />
            </div>
			Paraform raises $3.6M to build the future of hiring
			<span class="text-gray-400">{@html ArrowRight}</span>
		</a>

		<h1 class="text-5xl md:text-7xl lg:text-[5.5rem] leading-[1.1] tracking-tight max-w-5xl mx-auto mb-6 font-serif">
			Where iconic companies hire their best talent
		</h1>

		<p class="text-lg md:text-xl text-gray-500 max-w-2xl mx-auto mb-10 font-light">
			Match with expert recruiters and fill your hardest roles.
		</p>

		<a href="#" class="bg-black text-white px-8 py-4 rounded-full text-base font-medium hover:bg-gray-800 transition-colors shadow-lg hover:shadow-xl transform hover:-translate-y-0.5 duration-200">
			Get a demo
		</a>

		<!-- Company Logos -->
		<div class="mt-20 w-full max-w-6xl mx-auto">
			<div class="flex flex-wrap justify-center items-center gap-x-12 gap-y-8 opacity-60 grayscale">
				{#each companies as company}
					<span class="text-xl font-semibold font-serif">{company}</span>
				{/each}
			</div>
		</div>
	</section>

    <!-- Feature Cards Section -->
    <section class="px-6 pb-32">
        <div class="max-w-[1400px] mx-auto grid grid-cols-1 lg:grid-cols-2 gap-6">
            
            <!-- Left Card (Dark) -->
            <div class="group relative bg-[#111] rounded-[2rem] overflow-hidden min-h-[500px] flex flex-col text-white">
                <div class="absolute inset-0 bg-gradient-to-b from-black/0 to-black/60 z-10"></div>
                <!-- Image Placeholder -->
                <div class="absolute inset-0 bg-gray-800">
                    <img src="https://images.unsplash.com/photo-1556761175-5973dc0f32e7?q=80&w=1632&auto=format&fit=crop" alt="Working" class="w-full h-full object-cover opacity-60 mix-blend-overlay" />
                </div>
                
                <div class="relative z-20 p-10 flex flex-col h-full justify-between">
                    <h3 class="text-2xl font-medium">Quality candidates, faster</h3>
                    
                    <div class="flex items-end justify-between">
                        <p class="text-2xl font-serif max-w-md leading-snug">
                            Match with expert recruiters and fill your hardest roles in record time.
                        </p>
                        <button class="w-12 h-12 bg-white rounded-full flex items-center justify-center text-black hover:scale-110 transition-transform">
                            {@html ArrowRight}
                        </button>
                    </div>
                </div>
            </div>

            <!-- Right Card (Light) -->
            <div class="group relative bg-white border border-gray-100 rounded-[2rem] overflow-hidden min-h-[500px] flex flex-col shadow-sm">
                <div class="p-10 pb-0">
                    <h3 class="text-2xl font-medium mb-2">Recruiter-first, finally</h3>
                </div>
                
                <!-- UI Mockup -->
                <div class="flex-1 relative mt-8 px-10 overflow-hidden">
                    <div class="bg-white rounded-t-xl shadow-[0_0_40px_rgba(0,0,0,0.05)] border border-gray-100 p-6 w-full h-full transform translate-y-4">
                        <div class="flex justify-between items-center mb-6">
                            <span class="text-xs font-semibold text-gray-400 uppercase tracking-wider">Company</span>
                            <span class="text-xs font-semibold text-gray-400 uppercase tracking-wider">Rate</span>
                        </div>
                        <div class="space-y-4">
                            {#each ['Palantir', 'Anthropic', 'Anduril', 'Railway', 'Spoke'] as item, i}
                                <div class="flex items-center justify-between py-2 border-b border-gray-50 last:border-0">
                                    <div class="flex items-center gap-3">
                                        <div class="w-8 h-8 rounded bg-gray-100 flex items-center justify-center text-xs font-bold">{item[0]}</div>
                                        <span class="font-medium">{item}</span>
                                    </div>
                                    <span class="text-gray-400 text-sm">Private</span>
                                </div>
                            {/each}
                        </div>
                    </div>
                    
                    <!-- Floating Button -->
                     <div class="absolute bottom-10 right-10 z-30">
                        <button class="w-12 h-12 bg-[#111] rounded-full flex items-center justify-center text-white hover:scale-110 transition-transform shadow-lg">
                            {@html ArrowRight}
                        </button>
                    </div>
                </div>
            </div>

        </div>
    </section>

    <!-- Value Prop Section -->
    <section class="py-24 px-6 text-center">
        <span class="inline-block mb-4 text-xs font-medium tracking-widest text-gray-500 uppercase">• Companies</span>
        <h2 class="text-5xl md:text-6xl font-serif mb-6">Made for the roles that<br/>matter most</h2>
        <p class="text-xl text-gray-500 mb-10 font-light">A recruiting partner as selective as you are.</p>
        <a href="#" class="bg-black text-white px-8 py-3.5 rounded-full text-sm font-medium hover:bg-gray-800 transition-colors">
            For companies
        </a>
    </section>

    <!-- 3-Column Grid -->
    <section class="px-6 pb-32">
        <div class="max-w-[1400px] mx-auto grid grid-cols-1 md:grid-cols-3 gap-8 items-center">
            <!-- Col 1 -->
            <div class="pr-8">
                <h3 class="text-2xl font-medium mb-4">Tap into elite recruiter networks</h3>
                <p class="text-gray-500 mb-8 leading-relaxed">
                    Only work with recruiters with a proven track record trusted by world-class companies.
                </p>
                <div class="flex items-center gap-2 mb-12">
                     <!-- Avatars placeholder -->
                    <div class="flex -space-x-3">
                        {#each [1,2,3] as i}
                            <div class="w-10 h-10 rounded-full bg-gray-200 border-2 border-white overflow-hidden">
                                <img src={`https://placehold.co/40x40/gray/white?text=${i}`} alt="" class="w-full h-full object-cover" />
                            </div>
                        {/each}
                    </div>
                </div>
                
                <div>
                    <div class="text-5xl font-serif mb-1">500+</div>
                    <div class="text-sm text-gray-500">Companies hiring</div>
                </div>
            </div>

            <!-- Col 2: Image -->
            <div class="relative h-[400px] bg-gray-100 rounded-2xl overflow-hidden shadow-lg group">
                 <!-- Background Image -->
                 <img src="https://images.unsplash.com/photo-1486406146926-c627a92ad1ab?q=80&w=2070&auto=format&fit=crop" class="absolute inset-0 w-full h-full object-cover opacity-80 transition-transform duration-700 group-hover:scale-105" alt="Background" />
                 
                 <!-- Floating Card -->
                 <div class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 bg-white/90 backdrop-blur-sm p-4 rounded-xl shadow-xl w-64">
                    <div class="flex items-center gap-3 mb-3">
                        <div class="w-10 h-10 rounded-full bg-gray-300 overflow-hidden">
                             <img src="https://placehold.co/40x40" alt="" />
                        </div>
                        <div>
                            <div class="font-bold text-sm">Aaron Shakaedoff</div>
                            <div class="text-xs text-gray-500">Recruiter • Top 1%</div>
                        </div>
                    </div>
                    <div class="flex justify-between items-center bg-white rounded-lg p-3 shadow-sm">
                        <div class="text-center">
                            <div class="text-xl font-bold">02</div>
                            <div class="text-[10px] text-gray-400 uppercase">Candidates</div>
                        </div>
                         <div class="text-center border-l border-gray-100 pl-3">
                            <div class="bg-green-100 text-green-700 px-2 py-1 rounded text-[10px] font-bold uppercase">Submitted</div>
                        </div>
                    </div>
                 </div>
            </div>

            <!-- Col 3: Testimonial -->
            <div class="bg-[#F6F6F4] p-10 rounded-2xl h-full flex flex-col justify-center min-h-[400px]">
                <div class="mb-8 font-bold text-xl flex items-center gap-2">
                    <span class="w-5 h-5 bg-black rounded-sm flex items-center justify-center text-white text-[10px]">H</span> Hightouch
                </div>
                <blockquote class="text-2xl font-serif leading-relaxed mb-8">
                    “Imagine if agencies actually worked. I've tried countless recruiting tools throughout my entire career and there is nothing quite like Paraform.”
                </blockquote>
                <div class="text-sm font-medium text-gray-900">
                    — Corey Stein, <span class="text-gray-500 font-normal">VP of Engineering</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Dark Recruiter Section -->
    <section class="bg-[#0A0A0A] text-white py-32 overflow-hidden">
        <div class="max-w-[1400px] mx-auto px-6 text-center mb-20">
             <span class="inline-block mb-4 text-xs font-medium tracking-widest text-gray-400 uppercase">• Recruiters</span>
            <h2 class="text-5xl md:text-6xl font-serif mb-6">What recruiter-first really looks like</h2>
            <p class="text-xl text-gray-400 max-w-2xl mx-auto mb-10 font-light">
                We provide you with quality roles, powerful tools, and all the support you need.
            </p>
            <a href="#" class="bg-white text-black px-8 py-3.5 rounded-full text-sm font-medium hover:bg-gray-200 transition-colors">
                For recruiters
            </a>
        </div>

        <!-- Carousel / Cards -->
        <div class="relative w-full max-w-[1600px] mx-auto h-[500px] flex items-center justify-center">
            <!-- Background dimmed cards -->
            <div class="absolute left-[10%] opacity-30 scale-90 blur-[1px] hidden md:block">
                <div class="w-[300px] h-[400px] bg-gray-800 rounded-2xl overflow-hidden relative">
                    <img src="https://images.unsplash.com/photo-1500648767791-00dcc994a43e?q=80&w=1000&auto=format&fit=crop" class="w-full h-full object-cover opacity-50" alt="" />
                </div>
            </div>
            <div class="absolute right-[10%] opacity-30 scale-90 blur-[1px] hidden md:block">
                 <div class="w-[300px] h-[400px] bg-gray-800 rounded-2xl overflow-hidden relative">
                    <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?q=80&w=1000&auto=format&fit=crop" class="w-full h-full object-cover opacity-50" alt="" />
                 </div>
            </div>

            <!-- Main Card -->
            <div class="relative z-10 w-[340px] h-[460px] rounded-2xl overflow-hidden shadow-2xl border border-white/10 group cursor-pointer hover:scale-105 transition-transform duration-300">
                <img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?q=80&w=1528&auto=format&fit=crop" class="absolute inset-0 w-full h-full object-cover" alt="Recruiter" />
                <div class="absolute inset-0 bg-gradient-to-t from-orange-600/90 via-transparent to-transparent"></div>
                
                <div class="absolute top-6 left-6">
                    <span class="bg-white/20 backdrop-blur-md px-3 py-1 rounded-full text-xs font-medium border border-white/20">Olivia</span>
                </div>

                <div class="absolute bottom-0 left-0 right-0 p-8">
                    <div class="text-4xl font-bold mb-1">$80,000</div>
                    <div class="text-sm opacity-80">per month</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Feature Grid Section -->
    <section class="bg-[#0A0A0A] text-white pb-32 px-6">
        <div class="max-w-[1400px] mx-auto grid grid-cols-1 lg:grid-cols-2 gap-6">
            
            <!-- Left Large Card -->
            <div class="bg-[#111] rounded-[2rem] p-10 flex flex-col relative overflow-hidden min-h-[600px] border border-white/5">
                <div class="relative z-10 mb-8">
                    <h3 class="text-2xl font-medium mb-2">Say goodbye to business development</h3>
                    <p class="text-gray-400 max-w-md">
                        We handle the business development, you focus on placing great talent. Paraform connects you to roles from high-growth startups and category leading enterprises.
                    </p>
                </div>
                
                <!-- UI Mockup -->
                <div class="flex-1 relative mt-4 flex items-center justify-center">
                    <div class="bg-white rounded-xl p-6 text-black shadow-2xl w-full max-w-md transform rotate-[-2deg] hover:rotate-0 transition-transform duration-500 border border-gray-200">
                        <div class="flex items-start justify-between mb-6">
                            <div class="flex gap-3">
                                <div class="w-10 h-10 bg-green-100 rounded-lg flex items-center justify-center text-green-600">
                                    <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"/></svg>
                                </div>
                                <div>
                                    <div class="font-bold">Software Engineer, SDK</div>
                                    <div class="text-xs text-gray-500">$150k - $280k • Brooklyn • Hiring 1</div>
                                </div>
                            </div>
                        </div>
                        
                        <div class="space-y-3 mb-6">
                            <div class="flex justify-between text-sm">
                                <span class="text-gray-500">Baseline reward</span>
                                <span class="font-medium">+$12,500 x 1</span>
                            </div>
                            <div class="flex justify-between text-sm">
                                <span class="text-gray-500">Bonus</span>
                                <span class="font-medium">$1,500</span>
                            </div>
                        </div>
                        
                        <div class="border-t border-gray-100 pt-4 mb-4">
                            <div class="text-xs text-gray-500 mb-1">Total bounty</div>
                            <div class="text-3xl font-bold">$283,050</div>
                        </div>
                        
                        <button class="w-full bg-black text-white py-3 rounded-lg font-medium text-sm">Submit candidate</button>
                    </div>
                </div>
            </div>

            <!-- Right Column -->
            <div class="flex flex-col gap-6">
                
                <!-- Card 1: Search -->
                <div class="bg-[#111] rounded-[2rem] p-8 min-h-[280px] relative overflow-hidden border border-white/5 flex flex-col justify-between">
                    <div>
                        <h3 class="text-xl font-medium mb-2">All the tools to make recruiting easy</h3>
                        <p class="text-sm text-gray-400 mb-6">Access an all-in-one toolkit with sourcing, CRM, intake, scheduler and more completely free of charge.</p>
                    </div>
                    
                    <div class="bg-[#1A1A1A] rounded-xl p-4 flex items-center gap-3 border border-white/10">
                         <div class="w-8 h-8 rounded-full bg-gray-700 flex-shrink-0"></div>
                         <div class="flex-1 h-2 bg-gray-700 rounded-full w-20"></div>
                         <div class="w-full max-w-[200px] bg-white rounded-full h-10 flex items-center px-4 text-black text-sm justify-between">
                            <span class="opacity-50 text-xs truncate">Search across 2.7M profiles...</span>
                            <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="11" cy="11" r="8"/><line x1="21" y1="21" x2="16.65" y2="16.65"/></svg>
                         </div>
                    </div>
                </div>

                <!-- Card 2: Chat -->
                <div class="bg-[#111] rounded-[2rem] p-8 min-h-[280px] relative overflow-hidden border border-white/5 flex flex-col justify-between">
                    <div>
                        <h3 class="text-xl font-medium mb-2">Leave the follow-ups to us</h3>
                        <p class="text-sm text-gray-400 mb-6">From client comms to feedback and payments, we manage the manual work so you can stay focused on recruiting.</p>
                    </div>
                    
                    <div class="flex justify-end">
                        <div class="bg-blue-600 text-white p-4 rounded-2xl rounded-tr-sm max-w-[85%] text-sm relative shadow-lg">
                            <div class="flex items-center gap-2 mb-2">
                                <div class="w-6 h-6 rounded-full bg-blue-400 overflow-hidden">
                                     <img src="https://placehold.co/24x24/blue/white" alt="" />
                                </div>
                                <span class="font-bold text-xs">Dominic Anderson</span>
                            </div>
                            Great! Let's move to the Technical Interview. 👍
                        </div>
                    </div>
                </div>

                <!-- Card 3: AI Video -->
                <div class="bg-[#111] rounded-[2rem] p-0 relative overflow-hidden h-[300px] border border-white/5 group">
                     <img src="https://images.unsplash.com/photo-1531427186611-ecfd6d936c79?q=80&w=1000&auto=format&fit=crop" class="w-full h-full object-cover opacity-60 transition-transform duration-700 group-hover:scale-105" alt="AI Video" />
                     <div class="absolute bottom-0 left-0 p-8 bg-gradient-to-t from-black via-black/50 to-transparent w-full z-10">
                        <h3 class="text-xl font-medium mb-1">Let AI do the heavy lifting</h3>
                        <p class="text-sm text-gray-400">AI to supercharge recruiters, not to replace.</p>
                     </div>
                     
                     <div class="absolute bottom-8 right-8 w-24 h-32 bg-gray-800 rounded-lg border border-white/20 overflow-hidden shadow-2xl z-20">
                        <img src="https://images.unsplash.com/photo-1494790108377-be9c29b29330?q=80&w=1000&auto=format&fit=crop" class="w-full h-full object-cover" alt="Caller" />
                     </div>
                     
                     <div class="absolute bottom-12 right-12 w-8 h-8 bg-white/20 backdrop-blur rounded-full flex items-center justify-center z-30">
                        <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 14.5v-9l6 4.5-6 4.5z"/></svg>
                     </div>
                </div>

            </div>
        </div>
    </section>

    <!-- Trusted By Section -->
    <section class="py-32 px-6 bg-[#FBFBF9]">
        <div class="max-w-[1400px] mx-auto">
            <div class="flex justify-between items-end mb-16">
                <h2 class="text-4xl md:text-5xl font-serif">Trusted by high-growth teams</h2>
                <a href="#" class="border border-gray-200 bg-white px-6 py-2 rounded-full text-sm font-medium hover:bg-gray-50 transition-colors">
                    Customer stories
                </a>
            </div>

            <div class="bg-[#F6F6F4] rounded-2xl p-12 mb-4 flex flex-col md:flex-row gap-12 items-center">
                <div class="w-32 h-32 rounded-full overflow-hidden flex-shrink-0 bg-gray-200">
                    <img src="https://images.unsplash.com/photo-1506794778202-cad84cf45f1d?q=80&w=1000&auto=format&fit=crop" class="w-full h-full object-cover grayscale" alt="Michael" />
                </div>
                <div class="flex-1">
                    <div class="flex items-center gap-2 mb-6 font-bold uppercase tracking-wider text-sm">
                        <div class="w-5 h-5 bg-black rounded-sm flex items-center justify-center text-white text-[10px]">D</div> Decagon
                    </div>
                    <blockquote class="text-2xl md:text-3xl font-serif leading-relaxed mb-6">
                        “We hired exceptional engineers and GTM talent through Paraform - the biggest differentiator over other vendors is the quality of candidates.”
                    </blockquote>
                    <div class="text-sm text-gray-500">— Michael Sman, Co-founder of Decagon</div>
                </div>
            </div>

            <!-- List of other companies -->
            <div class="space-y-4">
                <div class="bg-[#F6F6F4] rounded-xl p-6 flex justify-between items-center cursor-pointer hover:bg-gray-100 transition-colors group">
                    <div class="flex items-center gap-4 font-medium">
                        <div class="w-8 h-8 bg-black text-white flex items-center justify-center rounded text-xs">W</div>
                        Windsurf
                    </div>
                    <div class="hidden md:block text-sm text-gray-500">Hired 7 engineers in under two months</div>
                    <div class="text-gray-400 group-hover:text-black transition-colors">+</div>
                </div>
                <div class="bg-[#F6F6F4] rounded-xl p-6 flex justify-between items-center cursor-pointer hover:bg-gray-100 transition-colors group">
                    <div class="flex items-center gap-4 font-medium">
                        <div class="w-8 h-8 bg-black text-white flex items-center justify-center rounded text-xs">T</div>
                        Tecton
                    </div>
                    <div class="hidden md:block text-sm text-gray-500">Hired scientists, PMs, and engineers while reducing time to hire by 3x</div>
                    <div class="text-gray-400 group-hover:text-black transition-colors">+</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer CTA -->
    <section class="relative py-40 flex flex-col items-center justify-center text-center overflow-hidden">
        <!-- Background Image -->
        <div class="absolute inset-0 z-0">
             <img src="https://images.unsplash.com/photo-1519999482648-25049ddd37b1?q=80&w=2626&auto=format&fit=crop" class="w-full h-full object-cover opacity-40 grayscale" alt="Castle" />
             <div class="absolute inset-0 bg-gradient-to-b from-[#FBFBF9] via-white/50 to-[#FBFBF9]"></div>
        </div>
        
        <div class="relative z-10 max-w-4xl mx-auto px-6">
            <h2 class="text-5xl md:text-6xl font-serif mb-6 text-[#111]">Let us be your competitive advantage</h2>
            <p class="text-lg text-gray-600 mb-10 max-w-xl mx-auto">
                Join world-class teams using Paraform to fill their most important roles in record time.
            </p>
            <a href="#" class="bg-black text-white px-8 py-4 rounded-full text-base font-medium hover:bg-gray-800 transition-colors shadow-lg hover:shadow-xl transform hover:-translate-y-0.5 duration-200">
                Get a demo
            </a>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-[#FBFBF9] pt-20 pb-10 px-6 border-t border-gray-200">
        <div class="max-w-[1400px] mx-auto grid grid-cols-1 md:grid-cols-5 gap-12 mb-20">
            <div class="col-span-1 md:col-span-2">
                <div class="flex items-center gap-2 font-medium text-xl tracking-tight mb-8">
                    <div class="w-6 h-6 bg-black text-white rounded-full flex items-center justify-center text-[10px]">
                        <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
                            <path d="M12 2L22 20H2L12 2Z" />
                        </svg>
                    </div>
                    Paraform
                </div>
            </div>
            
            <div>
                <h4 class="font-medium mb-6 text-sm">Product</h4>
                <ul class="space-y-4 text-sm text-gray-500">
                    <li><a href="#" class="hover:text-black">For companies</a></li>
                    <li><a href="#" class="hover:text-black">For recruiters</a></li>
                </ul>
            </div>
            
            <div>
                <h4 class="font-medium mb-6 text-sm">Company</h4>
                <ul class="space-y-4 text-sm text-gray-500">
                    <li><a href="#" class="hover:text-black">Careers</a></li>
                    <li><a href="#" class="hover:text-black">About</a></li>
                    <li><a href="#" class="hover:text-black">Customers</a></li>
                    <li><a href="#" class="hover:text-black">Blog</a></li>
                    <li><a href="#" class="hover:text-black">Help center</a></li>
                </ul>
            </div>
            
            <div>
                <h4 class="font-medium mb-6 text-sm">Use cases</h4>
                <ul class="space-y-4 text-sm text-gray-500">
                    <li><a href="#" class="hover:text-black">Early stage</a></li>
                    <li><a href="#" class="hover:text-black">Growth stage</a></li>
                    <li><a href="#" class="hover:text-black">Enterprise</a></li>
                </ul>
            </div>
        </div>
        
        <div class="max-w-[1400px] mx-auto flex flex-col md:flex-row justify-between items-center text-xs text-gray-400 border-t border-gray-200 pt-8">
            <div>© Paraform, 2023</div>
            <div class="flex gap-6 mt-4 md:mt-0">
                <a href="#" class="hover:text-black">Terms of use</a>
                <a href="#" class="hover:text-black">Privacy policy</a>
            </div>
            <div class="mt-4 md:mt-0 flex items-center gap-2">
                <span class="border border-gray-200 px-2 py-1 rounded bg-white">SOC2 Certified</span>
            </div>
        </div>
    </footer>

</div>

