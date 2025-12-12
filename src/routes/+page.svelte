<script lang="ts">
	import { onMount } from 'svelte';

	// Icons
	const ArrowRight = `<svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M6 12L10 8L6 4" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/></svg>`;
	const LogoIcon = `<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" clip-rule="evenodd" d="M6.99251 12.196C6.85314 12.5757 6.62925 12.9208 6.33682 13.2067H6.33835C6.00191 13.5351 5.58566 13.7756 5.12816 13.9059C4.67065 14.0362 4.18671 14.0522 3.72118 13.9523C3.25564 13.8524 2.82357 13.64 2.46501 13.3345C2.10645 13.0291 1.83299 12.6406 1.66998 12.2051C1.50697 11.7696 1.45969 11.3012 1.5325 10.8432C1.60532 10.3852 1.79587 9.95244 2.08653 9.58516C2.37718 9.21781 2.75852 8.9277 3.1952 8.74177C3.63188 8.55585 4.10979 8.48002 4.58462 8.52142L4.57074 8.50792C5.0567 8.54782 5.54575 8.48407 6.00378 8.32124C6.4618 8.15846 6.87776 7.90043 7.2226 7.56521C7.56746 7.22998 7.83285 6.82564 8.00036 6.38041C8.16786 5.93517 8.23344 5.45976 8.1924 4.98737L8.20628 5.00087C8.15181 4.43594 8.27796 3.86844 8.56753 3.37575C8.85701 2.88307 9.29579 2.48919 9.82407 2.24782C10.3523 2.00645 10.9443 1.92933 11.5192 2.02701C12.0942 2.12467 12.6243 2.39237 13.037 2.79358C13.4497 3.19479 13.7251 3.70999 13.8256 4.26892C13.926 4.82785 13.8467 5.4033 13.5984 5.9168C13.3501 6.4303 12.9449 6.85685 12.4381 7.13828C11.9313 7.41971 11.3474 7.54233 10.7663 7.4894L10.781 7.5029C10.2949 7.46279 9.80563 7.52632 9.34741 7.68904C8.88919 7.85176 8.47309 8.10975 8.12805 8.44499C7.78301 8.78025 7.51742 9.18466 7.34983 9.63001C7.18224 10.0754 7.11669 10.551 7.15774 11.0235L7.14309 11.01C7.1833 11.4112 7.13189 11.8162 6.99251 12.196ZM11.5077 14.7121L11.493 14.6986C11.9061 14.739 12.3232 14.6897 12.7143 14.5543C13.1053 14.4188 13.4605 14.2007 13.7542 13.9154C14.0477 13.6302 14.2726 13.285 14.4121 12.905C14.5518 12.525 14.6028 12.1196 14.5615 11.718L14.5762 11.7315C14.5351 11.2591 14.6007 10.7838 14.7681 10.3385C14.9356 9.89327 15.2011 9.48893 15.5459 9.15368C15.8908 8.8185 16.3068 8.56042 16.7648 8.39767C17.2228 8.23481 17.7118 8.17111 18.1978 8.21099L18.1832 8.19749C18.7645 8.25059 19.3485 8.12801 19.8556 7.84656C20.3627 7.56511 20.7681 7.13845 21.0165 6.62479C21.265 6.11114 21.3444 5.53548 21.2439 4.97634C21.1435 4.4172 20.868 3.9018 20.4551 3.50044C20.0422 3.09909 19.512 2.8313 18.9368 2.73364C18.3616 2.63596 17.7695 2.71315 17.241 2.95467C16.7126 3.19618 16.2737 3.59027 15.9842 4.08319C15.6946 4.57609 15.5685 5.14383 15.6232 5.70895L15.6093 5.6947C15.6504 6.16712 15.585 6.64259 15.4175 7.08788C15.2501 7.53318 14.9846 7.93758 14.6398 8.27287C14.2949 8.60805 13.8789 8.86612 13.4208 9.02888C12.9627 9.19163 12.4736 9.25523 11.9876 9.21526L12.0015 9.22951C11.5885 9.18908 11.1713 9.23836 10.7803 9.37381C10.3893 9.50919 10.034 9.72744 9.74039 10.0127C9.44674 10.2979 9.22199 10.6431 9.08234 11.0231C8.94276 11.4031 8.89176 11.8085 8.93304 12.2101L8.91915 12.1966C8.96005 12.6689 8.89439 13.1443 8.72688 13.5895C8.5593 14.0346 8.29389 14.4389 7.94908 14.7741C7.60425 15.1093 7.18835 15.3673 6.73039 15.5302C6.27242 15.693 5.78342 15.7569 5.29749 15.7171L5.31138 15.7306C4.73003 15.6775 4.14599 15.8001 3.63892 16.0815C3.13186 16.363 2.72644 16.7896 2.478 17.3033C2.22954 17.817 2.15013 18.3926 2.25061 18.9518C2.35109 19.5109 2.62657 20.0263 3.03945 20.4276C3.45234 20.829 3.98253 21.0968 4.55773 21.1944C5.13293 21.2921 5.72512 21.2149 6.25353 20.9734C6.78193 20.7319 7.22085 20.3379 7.51038 19.8449C7.79994 19.352 7.92601 18.7843 7.87139 18.2191L7.88605 18.2326C7.845 17.7602 7.91058 17.2849 8.07809 16.8396C8.24551 16.3944 8.511 15.99 8.85581 15.6548C9.20069 15.3196 9.61664 15.0615 10.0746 14.8988C10.5327 14.7359 11.0217 14.6722 11.5077 14.7121ZM17.1996 10.7633C16.9071 11.0493 16.6832 11.3944 16.5437 11.7741C16.4042 12.1538 16.3526 12.5587 16.3925 12.9601L16.3786 12.9466C16.4197 13.419 16.3541 13.8944 16.1866 14.3396C16.0191 14.7849 15.7537 15.1892 15.4089 15.5244C15.064 15.8596 14.648 16.1177 14.19 16.2804C13.732 16.4433 13.2429 16.507 12.757 16.4671L12.7708 16.4806C12.1896 16.4281 11.6057 16.551 11.0989 16.8328C10.5921 17.1145 10.1871 17.5414 9.93902 18.0551C9.69097 18.5689 9.61188 19.1444 9.71265 19.7035C9.81349 20.2625 10.0892 20.7777 10.5022 21.1788C10.9152 21.5799 11.4454 21.8474 12.0205 21.9448C12.5957 22.0423 13.1877 21.9649 13.716 21.7234C14.2443 21.4817 14.683 21.0877 14.9724 20.5947C15.2618 20.1018 15.3878 19.5342 15.3332 18.9692L15.3478 18.9827C15.3068 18.5103 15.3723 18.0349 15.5398 17.5896C15.7073 17.1444 15.9728 16.7401 16.3176 16.4048C16.6625 16.0696 17.0784 15.8115 17.5364 15.6488C17.9945 15.486 18.4835 15.4222 18.9695 15.4621L18.9548 15.4486C19.4296 15.4901 19.9076 15.4144 20.3444 15.2286C20.7811 15.0427 21.1625 14.7527 21.4533 14.3854C21.744 14.0181 21.9347 13.5854 22.0075 13.1274C22.0805 12.6694 22.0332 12.2009 21.8703 11.7653C21.7073 11.3298 21.4339 10.9413 21.0754 10.6358C20.7168 10.3303 20.2848 10.1178 19.8192 10.0179C19.3536 9.91795 18.8697 9.93385 18.4121 10.0641C17.9546 10.1945 17.5383 10.4349 17.2019 10.7633H17.1996Z" fill="currentColor"/></svg>`;
    const CheckIcon = `<svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"></polyline></svg>`;

    // Data
    const companies = ["OpenAI", "Anthropic", "Cohere", "Mistral", "Perplexity", "Hugging Face", "Runway"];
</script>

<div class="min-h-screen flex flex-col font-sans text-[#111]">
	<!-- Navbar -->
	<nav class="sticky top-0 z-50 bg-[#FBFBF9]/80 backdrop-blur-md border-b border-transparent transition-all duration-300">
		<div class="max-w-[1400px] mx-auto px-6 h-20 flex items-center justify-between">
			<div class="flex items-center gap-2 font-medium text-xl tracking-tight">
				<div class="w-6 h-6 text-black flex items-center justify-center">
                    <!-- OpenTrain AI Logo -->
                    {@html LogoIcon}
                </div>
				OpenTrain AI
			</div>

			<div class="hidden md:flex items-center gap-8 text-sm font-medium text-gray-600">
				<a href="#" class="hover:text-black transition-colors">For AI companies</a>
				<a href="#" class="hover:text-black transition-colors">For labelers</a>
				<a href="#" class="hover:text-black transition-colors">Customers</a>
				<a href="#" class="hover:text-black transition-colors">Pricing</a>
				<a href="#" class="hover:text-black transition-colors">Careers</a>
			</div>

			<div class="flex items-center gap-4 text-sm font-medium">
				<a href="#" class="hidden md:block hover:text-gray-600 transition-colors">Sign in</a>
				<a href="#" class="bg-black text-white px-5 py-2.5 rounded-full hover:bg-gray-800 transition-colors">Get started</a>
			</div>
		</div>
	</nav>

	<!-- Hero Section -->
	<section class="pt-16 pb-24 px-6 flex flex-col items-center text-center">
		<a href="#" class="inline-flex items-center gap-2 bg-white border border-gray-200 rounded-full pl-1 pr-3 py-1 text-xs font-medium text-gray-600 hover:border-gray-300 transition-colors mb-8 shadow-sm">
			<div class="w-5 h-5 rounded-full overflow-hidden bg-gray-100 flex-shrink-0 flex items-center justify-center">
                <div class="w-3 h-3 text-black">{@html LogoIcon}</div>
            </div>
			OpenTrain AI launches tool-agnostic data labeling marketplace
			<span class="text-gray-400">{@html ArrowRight}</span>
		</a>

		<h1 class="text-5xl md:text-7xl lg:text-[5.5rem] leading-[1.1] tracking-tight max-w-5xl mx-auto mb-6 font-serif">
			Quality labeled data from vetted experts
		</h1>

		<p class="text-lg md:text-xl text-gray-500 max-w-2xl mx-auto mb-10 font-light">
			Connect with specialized data labelers through our tool-agnostic marketplace with secure escrow payments.
		</p>

		<a href="#" class="bg-black text-white px-8 py-4 rounded-full text-base font-medium hover:bg-gray-800 transition-colors shadow-lg hover:shadow-xl transform hover:-translate-y-0.5 duration-200">
			Get started
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
                    <img src="/generated/image-person-working-at-computer-annotating-im-1765515992045-0.webp" alt="Data labeling work" class="w-full h-full object-cover opacity-60 mix-blend-overlay" />
                </div>
                
                <div class="relative z-20 p-10 flex flex-col h-full justify-between">
                    <h3 class="text-2xl font-medium">Quality data, faster</h3>
                    
                    <div class="flex items-end justify-between">
                        <p class="text-2xl font-serif max-w-md leading-snug">
                            Match with vetted data labelers and get high-quality training data in record time.
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
                    <h3 class="text-2xl font-medium mb-2">Tool-agnostic marketplace</h3>
                </div>
                
                <!-- UI Mockup -->
                <div class="flex-1 relative mt-8 px-10 overflow-hidden">
                    <div class="bg-white rounded-t-xl shadow-[0_0_40px_rgba(0,0,0,0.05)] border border-gray-100 p-6 w-full h-full transform translate-y-4">
                        <div class="flex justify-between items-center mb-6">
                            <span class="text-xs font-semibold text-gray-400 uppercase tracking-wider">Labeler</span>
                            <span class="text-xs font-semibold text-gray-400 uppercase tracking-wider">Specialty</span>
                        </div>
                        <div class="space-y-4">
                            {#each [['Sarah Chen', 'Computer Vision'], ['Marcus Liu', 'NLP & Text'], ['Aisha Patel', 'Audio/Video'], ['James Kim', 'Medical Imaging'], ['Elena Rodriguez', 'Autonomous Driving']] as [name, specialty], i}
                                <div class="flex items-center justify-between py-2 border-b border-gray-50 last:border-0">
                                    <div class="flex items-center gap-3">
                                        <div class="w-8 h-8 rounded bg-gray-100 flex items-center justify-center text-xs font-bold">{name[0]}</div>
                                        <span class="font-medium">{name}</span>
                                    </div>
                                    <span class="text-gray-400 text-sm">{specialty}</span>
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
        <span class="inline-block mb-4 text-xs font-medium tracking-widest text-gray-500 uppercase">• AI Companies</span>
        <h2 class="text-5xl md:text-6xl font-serif mb-6">Built for models that<br/>demand precision</h2>
        <p class="text-xl text-gray-500 mb-10 font-light">A data labeling partner as rigorous as your training pipeline.</p>
        <a href="#" class="bg-black text-white px-8 py-3.5 rounded-full text-sm font-medium hover:bg-gray-800 transition-colors">
            For AI companies
        </a>
    </section>

    <!-- 3-Column Grid -->
    <section class="px-6 pb-32">
        <div class="max-w-[1400px] mx-auto grid grid-cols-1 md:grid-cols-3 gap-8 items-center">
            <!-- Col 1 -->
            <div class="pr-8">
                <h3 class="text-2xl font-medium mb-4">Access specialized labeler networks</h3>
                <p class="text-gray-500 mb-8 leading-relaxed">
                    Work with vetted data labelers who have proven expertise in your specific domain and annotation needs.
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
                    <div class="text-5xl font-serif mb-1">40K+</div>
                    <div class="text-sm text-gray-500">Vetted labelers</div>
                </div>
            </div>

            <!-- Col 2: Image -->
            <div class="relative h-[400px] bg-gray-100 rounded-2xl overflow-hidden shadow-lg group">
                 <!-- Background Image -->
                 <img src="/generated/image-diverse-team-collaborating-on-ai-trainin-1765515999226-2.webp" class="absolute inset-0 w-full h-full object-cover opacity-80 transition-transform duration-700 group-hover:scale-105" alt="Background" />
                 
                 <!-- Floating Card -->
                 <div class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 bg-white/90 backdrop-blur-sm p-4 rounded-xl shadow-xl w-64">
                    <div class="flex items-center gap-3 mb-3">
                        <div class="w-10 h-10 rounded-full bg-gray-300 overflow-hidden">
                             <img src="https://placehold.co/40x40" alt="" />
                        </div>
                        <div>
                            <div class="font-bold text-sm">Maya Rodriguez</div>
                            <div class="text-xs text-gray-500">Labeler • Computer Vision</div>
                        </div>
                    </div>
                    <div class="flex justify-between items-center bg-white rounded-lg p-3 shadow-sm">
                        <div class="text-center">
                            <div class="text-xl font-bold">2.4K</div>
                            <div class="text-[10px] text-gray-400 uppercase">Images</div>
                        </div>
                         <div class="text-center border-l border-gray-100 pl-3">
                            <div class="bg-green-100 text-green-700 px-2 py-1 rounded text-[10px] font-bold uppercase">Completed</div>
                        </div>
                    </div>
                 </div>
            </div>

            <!-- Col 3: Testimonial -->
            <div class="bg-[#F6F6F4] p-10 rounded-2xl h-full flex flex-col justify-center min-h-[400px]">
                <div class="mb-8 font-bold text-xl flex items-center gap-2">
                    <span class="w-5 h-5 bg-black rounded-sm flex items-center justify-center text-white text-[10px]">A</span> Anthropic
                </div>
                <blockquote class="text-2xl font-serif leading-relaxed mb-8">
                    “OpenTrain AI solved our biggest challenge: finding specialized labelers without vendor lock-in. The quality is exceptional.”
                </blockquote>
                <div class="text-sm font-medium text-gray-900">
                    — Sarah Chen, <span class="text-gray-500 font-normal">ML Engineering Lead</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Dark Labeler Section -->
    <section class="bg-[#0A0A0A] text-white py-32 overflow-hidden">
        <div class="max-w-[1400px] mx-auto px-6 text-center mb-20">
             <span class="inline-block mb-4 text-xs font-medium tracking-widest text-gray-400 uppercase">• Data Labelers</span>
            <h2 class="text-5xl md:text-6xl font-serif mb-6">What labeler-first really looks like</h2>
            <p class="text-xl text-gray-400 max-w-2xl mx-auto mb-10 font-light">
                We provide you with quality projects, fair compensation, and flexible tools you already know.
            </p>
            <a href="#" class="bg-white text-black px-8 py-3.5 rounded-full text-sm font-medium hover:bg-gray-200 transition-colors">
                For labelers
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
                <img src="/generated/image-young-professional-man-smiling-in-tech-s-1765516006941-5.webp" class="absolute inset-0 w-full h-full object-cover" alt="Data Labeler" />
                <div class="absolute inset-0 bg-gradient-to-t from-cyan-600/90 via-transparent to-transparent"></div>
                
                <div class="absolute top-6 left-6">
                    <span class="bg-white/20 backdrop-blur-md px-3 py-1 rounded-full text-xs font-medium border border-white/20">Alex</span>
                </div>

                <div class="absolute bottom-0 left-0 right-0 p-8">
                    <div class="text-4xl font-bold mb-1">$6,500</div>
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
                    <h3 class="text-2xl font-medium mb-2">Say goodbye to client hunting</h3>
                    <p class="text-gray-400 max-w-md">
                        We handle client acquisition, you focus on quality labeling. OpenTrain AI connects you to projects from leading AI labs and innovative startups.
                    </p>
                </div>
                
                <!-- UI Mockup -->
                <div class="flex-1 relative mt-4 flex items-center justify-center">
                    <div class="bg-white rounded-xl p-6 text-black shadow-2xl w-full max-w-md transform rotate-[-2deg] hover:rotate-0 transition-transform duration-500 border border-gray-200">
                        <div class="flex items-start justify-between mb-6">
                            <div class="flex gap-3">
                                <div class="w-10 h-10 bg-blue-100 rounded-lg flex items-center justify-center text-blue-600">
                                    <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="3" y="3" width="18" height="18" rx="2"/><path d="M9 3v18M15 3v18M3 9h18M3 15h18"/></svg>
                                </div>
                                <div>
                                    <div class="font-bold">Image Segmentation</div>
                                    <div class="text-xs text-gray-500">Computer Vision • 10K images • Urgent</div>
                                </div>
                            </div>
                        </div>
                        
                        <div class="space-y-3 mb-6">
                            <div class="flex justify-between text-sm">
                                <span class="text-gray-500">Base rate</span>
                                <span class="font-medium">$0.45 per image</span>
                            </div>
                            <div class="flex justify-between text-sm">
                                <span class="text-gray-500">Quality bonus</span>
                                <span class="font-medium">+$500</span>
                            </div>
                        </div>
                        
                        <div class="border-t border-gray-100 pt-4 mb-4">
                            <div class="text-xs text-gray-500 mb-1">Total project value</div>
                            <div class="text-3xl font-bold">$5,000</div>
                        </div>
                        
                        <button class="w-full bg-black text-white py-3 rounded-lg font-medium text-sm">Apply to project</button>
                    </div>
                </div>
            </div>

            <!-- Right Column -->
            <div class="flex flex-col gap-6">
                
                <!-- Card 1: Tool Agnostic -->
                <div class="bg-[#111] rounded-[2rem] p-8 min-h-[280px] relative overflow-hidden border border-white/5 flex flex-col justify-between">
                    <div>
                        <h3 class="text-xl font-medium mb-2">Use your preferred tools</h3>
                        <p class="text-sm text-gray-400 mb-6">Work with any annotation tool you're comfortable with. No vendor lock-in, no forced software changes.</p>
                    </div>
                    
                    <div class="bg-[#1A1A1A] rounded-xl p-4 flex items-center gap-3 border border-white/10">
                         <div class="w-8 h-8 rounded bg-gray-700 flex-shrink-0 flex items-center justify-center text-xs text-white">L</div>
                         <div class="w-8 h-8 rounded bg-gray-700 flex-shrink-0 flex items-center justify-center text-xs text-white">C</div>
                         <div class="w-8 h-8 rounded bg-gray-700 flex-shrink-0 flex items-center justify-center text-xs text-white">V</div>
                         <div class="flex-1 flex items-center justify-end">
                            <span class="text-xs text-gray-400">+ 20 more tools</span>
                         </div>
                    </div>
                </div>

                <!-- Card 2: Escrow -->
                <div class="bg-[#111] rounded-[2rem] p-8 min-h-[280px] relative overflow-hidden border border-white/5 flex flex-col justify-between">
                    <div>
                        <h3 class="text-xl font-medium mb-2">Secure escrow payments</h3>
                        <p class="text-sm text-gray-400 mb-6">Get paid on time, every time. Our escrow system protects both labelers and clients with guaranteed payments.</p>
                    </div>
                    
                    <div class="flex justify-end">
                        <div class="bg-green-600 text-white p-4 rounded-2xl rounded-tr-sm max-w-[85%] text-sm relative shadow-lg">
                            <div class="flex items-center gap-2 mb-2">
                                <div class="w-6 h-6 rounded-full bg-green-400 overflow-hidden flex items-center justify-center">
                                     <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M9 16.17L4.83 12l-1.42 1.41L9 19 21 7l-1.41-1.41L9 16.17z"/></svg>
                                </div>
                                <span class="font-bold text-xs">Payment Released</span>
                            </div>
                            Your payment of $5,000 has been released 💰
                        </div>
                    </div>
                </div>

                <!-- Card 3: Quality Control -->
                <div class="bg-[#111] rounded-[2rem] p-0 relative overflow-hidden h-[300px] border border-white/5 group">
                     <img src="/generated/image-professional-data-labeler-at-modern-work-1765515996105-1.webp" class="w-full h-full object-cover opacity-60 transition-transform duration-700 group-hover:scale-105" alt="Quality Control" />
                     <div class="absolute bottom-0 left-0 p-8 bg-gradient-to-t from-black via-black/50 to-transparent w-full z-10">
                        <h3 class="text-xl font-medium mb-1">Quality-first approach</h3>
                        <p class="text-sm text-gray-400">Built-in quality checks and feedback loops ensure exceptional results.</p>
                     </div>
                     
                     <div class="absolute top-8 right-8 bg-white/90 backdrop-blur-sm rounded-lg p-3 shadow-2xl z-20">
                        <div class="text-2xl font-bold text-black">98.5%</div>
                        <div class="text-xs text-gray-500">Accuracy</div>
                     </div>
                </div>

            </div>
        </div>
    </section>

    <!-- Trusted By Section -->
    <section class="py-32 px-6 bg-[#FBFBF9]">
        <div class="max-w-[1400px] mx-auto">
            <div class="flex justify-between items-end mb-16">
                <h2 class="text-4xl md:text-5xl font-serif">Trusted by leading AI teams</h2>
                <a href="#" class="border border-gray-200 bg-white px-6 py-2 rounded-full text-sm font-medium hover:bg-gray-50 transition-colors">
                    Customer stories
                </a>
            </div>

            <div class="bg-[#F6F6F4] rounded-2xl p-12 mb-4 flex flex-col md:flex-row gap-12 items-center">
                <div class="w-32 h-32 rounded-full overflow-hidden flex-shrink-0 bg-gray-200">
                    <img src="/generated/image-confident-professional-woman-with-laptop-1765516004226-4.webp" class="w-full h-full object-cover" alt="Customer" />
                </div>
                <div class="flex-1">
                    <div class="flex items-center gap-2 mb-6 font-bold uppercase tracking-wider text-sm">
                        <div class="w-5 h-5 bg-black rounded-sm flex items-center justify-center text-white text-[10px]">C</div> Cohere
                    </div>
                    <blockquote class="text-2xl md:text-3xl font-serif leading-relaxed mb-6">
                        “OpenTrain AI gave us access to specialized labelers we couldn't find elsewhere. The quality and turnaround time exceeded our expectations.”
                    </blockquote>
                    <div class="text-sm text-gray-500">— Emily Zhang, Head of Data</div>
                </div>
            </div>

            <!-- List of other companies -->
            <div class="space-y-4">
                <div class="bg-[#F6F6F4] rounded-xl p-6 flex justify-between items-center cursor-pointer hover:bg-gray-100 transition-colors group">
                    <div class="flex items-center gap-4 font-medium">
                        <div class="w-8 h-8 bg-black text-white flex items-center justify-center rounded text-xs">M</div>
                        Mistral AI
                    </div>
                    <div class="hidden md:block text-sm text-gray-500">Labeled 500K samples with 99% accuracy in 3 weeks</div>
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

