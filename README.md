<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="AmirMohammad Ghasemzadeh - Algorithm Researcher & HPC Architect. Specializing in Rust, C++, and Computational Complexity.">
    <title>AmirMohammad | Kernel Shell Portfolio</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    
    <!-- Chosen Palette: Midnight Obsidian & Cyan Neon (BG: #020617, Primary: #22d3ee, Accent: #f43f5e) -->
    <!-- Application Structure Plan: 
        1. Neural Matrix (Canvas): A high-performance particle system that mimics synaptical firing and distributed logic paths.
        2. Hero Module: Immediate identification as a Systems Architect with a dynamic terminal-style typing engine.
        3. Logic Core (About): Deconstructing the ENTP-A personality into technical philosophy using pseudo-code blocks.
        4. Tactical Arsenal: A data-driven skill visualization using a Radar Chart to show the balance between system engineering and algorithmic research.
        5. Research Lab (Projects): High-impact cards highlighting low-level development and optimization.
        6. The Live Kernel (Advanced Terminal): The centerpiece. A functional shell supporting Tab-completion, history (Arrow keys), and custom system calls like neofetch and hack.
    -->
    <!-- Visualization & Content Choices:
        - Chart.js Radar: Perfect for multi-dimensional skill sets.
        - Terminal API: Custom implementation for persistent command history and fuzzy-tab completion.
        - CSS Grid & Flex: Responsive layout ensures zero horizontal scroll.
        - CONFIRMATION: NO SVG graphics used. NO Mermaid JS used.
    -->

    <style>
        @import url('https://fonts.googleapis.com/css2?family=Fira+Code:wght@300;400;500;700&family=Inter:wght@300;400;700;900&display=swap');
        
        :root {
            --primary: #22d3ee;
            --bg: #020617;
            --surface: #0f172a;
            --accent: #f43f5e;
        }

        body {
            background-color: var(--bg);
            color: #cbd5e1;
            font-family: 'Inter', sans-serif;
            scroll-behavior: smooth;
            overflow-x: hidden;
        }

        .fira { font-family: 'Fira Code', monospace; }

        canvas#neural-bg {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            z-index: -1;
            opacity: 0.35;
        }

        .cyber-card {
            background: rgba(15, 23, 42, 0.6);
            backdrop-filter: blur(16px);
            border: 1px solid rgba(34, 211, 238, 0.1);
            transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .cyber-card:hover {
            border-color: var(--primary);
            box-shadow: 0 0 30px rgba(34, 211, 238, 0.15);
            transform: translateY(-5px);
        }

        .glow-text {
            text-shadow: 0 0 15px rgba(34, 211, 238, 0.5);
        }

        .chart-container {
            position: relative;
            width: 100%;
            max-width: 550px;
            margin: auto;
            height: 380px;
            max-height: 400px;
        }

        /* Screen Shake for Hack command */
        @keyframes shake {
            0% { transform: translate(1px, 1px) rotate(0deg); }
            10% { transform: translate(-1px, -2px) rotate(-1deg); }
            20% { transform: translate(-3px, 0px) rotate(1deg); }
            30% { transform: translate(3px, 2px) rotate(0deg); }
            40% { transform: translate(1px, -1px) rotate(1deg); }
            50% { transform: translate(-1px, 2px) rotate(-1deg); }
            60% { transform: translate(-3px, 1px) rotate(0deg); }
            70% { transform: translate(3px, 1px) rotate(-1deg); }
            80% { transform: translate(-1px, -1px) rotate(1deg); }
            90% { transform: translate(1px, 2px) rotate(0deg); }
            100% { transform: translate(1px, -2px) rotate(-1deg); }
        }
        .shake { animation: shake 0.3s; }

        .terminal-scroll::-webkit-scrollbar { width: 4px; }
        .terminal-scroll::-webkit-scrollbar-thumb { background: var(--primary); border-radius: 10px; }

        @keyframes blink { 50% { opacity: 0; } }
        .cursor { animation: blink 1s step-end infinite; }
    </style>
</head>
<body class="antialiased">

    <canvas id="neural-bg"></canvas>

    <!-- Navigation -->
    <nav class="fixed top-0 w-full z-50 bg-bg/80 backdrop-blur-xl border-b border-white/5">
        <div class="max-w-7xl mx-auto px-8 py-5 flex justify-between items-center">
            <div class="fira text-primary font-bold text-xl glow-text tracking-tighter">
                AMIRGH.sys
            </div>
            <div class="hidden md:flex space-x-10 text-[10px] uppercase font-black tracking-widest">
                <a href="#home" class="hover:text-primary transition-colors">01_Initial</a>
                <a href="#arsenal" class="hover:text-primary transition-colors">02_Arsenal</a>
                <a href="#lab" class="hover:text-primary transition-colors">03_Lab</a>
                <a href="#terminal" class="hover:text-primary transition-colors">04_Kernel</a>
            </div>
            <a href="mailto:amirgh.devtech@gmail.com" class="fira px-4 py-2 border border-primary/30 text-primary text-[10px] uppercase font-bold hover:bg-primary hover:text-bg transition-all">
                Connect.init()
            </a>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="min-h-screen flex flex-col justify-center px-8">
        <div class="max-w-7xl mx-auto w-full pt-20">
            <div class="inline-block px-4 py-1 mb-8 border border-primary/20 text-primary text-[10px] uppercase tracking-[0.4em] bg-primary/5 font-bold">
                Status: Architecting High-Performance Systems
            </div>
            <h1 class="text-6xl md:text-9xl font-black mb-8 glow-text tracking-tighter leading-none uppercase">
                Systems<br><span class="text-white/20">Architect.</span>
            </h1>
            <div class="h-12 fira text-xl md:text-3xl text-gray-400" id="typing-text"></div>
            
            <p class="mt-10 max-w-2xl text-gray-400 leading-relaxed text-lg font-light">
                I optimize for the nanosecond. My work focuses on the intersection of <span class="text-white font-bold">algorithmic complexity</span> and <span class="text-white font-bold">bare-metal performance</span>, ensuring deterministic execution in high-throughput environments.
            </p>

            <div class="mt-14 flex flex-wrap gap-8">
                <a href="#lab" class="px-10 py-5 bg-primary text-bg font-black text-xs uppercase tracking-widest hover:scale-105 transition-all shadow-lg shadow-primary/20">
                    Explore Research
                </a>
                <a href="#terminal" class="fira flex items-center gap-4 text-primary text-xs font-bold hover:gap-6 transition-all uppercase">
                    Connect to Shell <span>&#8594;</span>
                </a>
            </div>
        </div>
    </section>

    <!-- Logic Core Section -->
    <section class="max-w-7xl mx-auto px-8 py-40 grid md:grid-cols-2 gap-24 items-center">
        <div class="space-y-8">
            <h2 class="text-4xl font-black tracking-tight border-l-4 border-primary pl-6 uppercase">The Logic Core</h2>
            <p class="text-gray-400 text-lg leading-relaxed">
                As an <span class="text-white font-bold">ENTP-A Algorithm Researcher</span>, my methodology is built on aggressive deconstruction. I don't just solve problems; I dismantle the legacy logic that creates them.
            </p>
            <p class="text-gray-400 text-lg leading-relaxed">
                Specializing in <span class="text-primary fira">Rust</span> and <span class="text-primary fira">C++</span>, I bridge the gap between abstract mathematics and hardware-level instruction sets.
            </p>
            <div class="grid grid-cols-2 gap-6 pt-6">
                <div class="p-6 bg-surface border border-white/5 cyber-card">
                    <div class="text-primary font-black text-3xl fira">17+</div>
                    <div class="text-[10px] text-gray-500 uppercase tracking-widest mt-2 font-bold">Optimized Repos</div>
                </div>
                <div class="p-6 bg-surface border border-white/5 cyber-card">
                    <div class="text-primary font-black text-3xl fira">0.0ns</div>
                    <div class="text-[10px] text-gray-500 uppercase tracking-widest mt-2 font-bold">Target Overhead</div>
                </div>
            </div>
        </div>
        <div class="relative">
            <div class="cyber-card rounded-lg overflow-hidden border border-white/10">
                <div class="bg-primary/10 p-4 border-b border-white/10 flex justify-between items-center">
                    <span class="fira text-[10px] text-gray-500 uppercase font-bold tracking-widest">kernel_optimization.rs</span>
                    <div class="flex space-x-2">
                        <div class="w-2 h-2 rounded-full bg-red-500/30"></div>
                        <div class="w-2 h-2 rounded-full bg-yellow-500/30"></div>
                        <div class="w-2 h-2 rounded-full bg-green-500/30"></div>
                    </div>
                </div>
                <div class="p-8 bg-surface fira text-sm leading-loose">
                    <p class="text-gray-500">// Evaluating Core Philosophy</p>
                    <p class="text-cyan-400"><span class="text-primary">fn</span> execute_optimization() {</p>
                    <p class="pl-4">let goal = <span class="text-accent">"Stanford_Candidate";</span></p>
                    <p class="pl-4">let strategy = <span class="text-accent">"Zero_Cost_Abstractions";</span></p>
                    <p class="pl-4 mt-4 text-gray-500">loop {</p>
                    <p class="pl-8 text-white">profile_memory();</p>
                    <p class="pl-8 text-white">reduce_complexity();</p>
                    <p class="pl-8 text-primary">if latency == 0.0 { break; }</p>
                    <p class="pl-4 text-gray-500">}</p>
                    <p class="text-cyan-400">}</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Tactical Arsenal (Skill Visualization) -->
    <section id="arsenal" class="bg-surface/30 py-40 border-y border-white/5">
        <div class="max-w-7xl mx-auto px-8">
            <div class="text-center mb-20">
                <h2 class="text-5xl font-black mb-4 uppercase tracking-tighter">Tactical Arsenal</h2>
                <p class="text-gray-500 fira text-sm">A quantified matrix of architectural mastery.</p>
            </div>
            <div class="grid md:grid-cols-2 gap-24 items-center">
                <div class="chart-container">
                    <canvas id="skillRadar"></canvas>
                </div>
                <div class="space-y-10">
                    <div class="p-8 bg-surface border border-white/5 rounded-xl">
                        <h4 class="text-xs font-bold text-primary uppercase tracking-[0.4em] mb-6">Execution Parameters</h4>
                        <div class="space-y-6">
                            <div class="flex justify-between items-center">
                                <span class="text-sm font-bold">Systems (Rust/C++)</span>
                                <span class="fira text-primary">98%</span>
                            </div>
                            <div class="w-full bg-white/5 h-1">
                                <div class="bg-primary h-full" style="width: 98%"></div>
                            </div>
                            <div class="flex justify-between items-center">
                                <span class="text-sm font-bold">Mathematical Logic</span>
                                <span class="fira text-primary">95%</span>
                            </div>
                            <div class="w-full bg-white/5 h-1">
                                <div class="bg-primary h-full" style="width: 95%"></div>
                            </div>
                            <div class="flex justify-between items-center">
                                <span class="text-sm font-bold">HPC & Concurrency</span>
                                <span class="fira text-primary">92%</span>
                            </div>
                            <div class="w-full bg-white/5 h-1">
                                <div class="bg-primary h-full" style="width: 92%"></div>
                            </div>
                        </div>
                    </div>
                    <div class="flex gap-4">
                        <button onclick="toggleSet('sys')" id="set-sys" class="flex-1 py-4 bg-primary/20 border border-primary text-primary text-[10px] font-black uppercase tracking-widest transition-all">Primary Stack</button>
                        <button onclick="toggleSet('research')" id="set-res" class="flex-1 py-4 bg-transparent border border-white/10 text-gray-500 text-[10px] font-black uppercase tracking-widest hover:border-primary transition-all">Research Logic</button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Lab Showcase -->
    <section id="lab" class="max-w-7xl mx-auto px-8 py-40">
        <div class="flex flex-col md:flex-row justify-between items-end mb-24 gap-8">
            <div>
                <h3 class="text-xs uppercase tracking-[0.6em] text-primary font-bold mb-4">Current Directives</h3>
                <h2 class="text-6xl font-black uppercase tracking-tighter leading-none">Disruption<br>Lab.</h2>
            </div>
            <div class="fira text-primary text-[10px] bg-primary/5 px-4 py-2 border border-primary/20">
                ACTIVE_THREADS: 0x11
            </div>
        </div>

        <div class="grid md:grid-cols-3 gap-8">
            <div class="cyber-card p-10 group cursor-crosshair">
                <div class="text-primary/20 text-6xl font-black mb-8 group-hover:text-primary transition-colors fira">01</div>
                <h3 class="text-2xl font-bold mb-4 text-white">QuantumX Engine</h3>
                <p class="text-gray-400 text-sm leading-relaxed mb-8">Ultra-low latency data pipeline written in Rust. Focused on lock-free synchronization and cache-line alignment.</p>
                <div class="flex gap-2"><span class="text-[9px] font-bold px-2 py-1 border border-primary/20">RUST</span><span class="text-[9px] font-bold px-2 py-1 border border-primary/20">SIMD</span></div>
            </div>
            <div class="cyber-card p-10 group cursor-crosshair">
                <div class="text-primary/20 text-6xl font-black mb-8 group-hover:text-primary transition-colors fira">02</div>
                <h3 class="text-2xl font-bold mb-4 text-white">Lattice Crypt</h3>
                <p class="text-gray-400 text-sm leading-relaxed mb-8">Implementation of post-quantum cryptographic primitives optimized for AVX-512 instruction sets.</p>
                <div class="flex gap-2"><span class="text-[9px] font-bold px-2 py-1 border border-primary/20">MATH</span><span class="text-[9px] font-bold px-2 py-1 border border-primary/20">C++</span></div>
            </div>
            <div class="cyber-card p-10 group cursor-crosshair">
                <div class="text-primary/20 text-6xl font-black mb-8 group-hover:text-primary transition-colors fira">03</div>
                <h3 class="text-2xl font-bold mb-4 text-white">Mesh-Flow</h3>
                <p class="text-gray-400 text-sm leading-relaxed mb-8">Distributed consensus algorithm framework designed for minimal network overhead and high-availability logic.</p>
                <div class="flex gap-2"><span class="text-[9px] font-bold px-2 py-1 border border-primary/20">GO</span><span class="text-[9px] font-bold px-2 py-1 border border-primary/20">DISTRIBUTED</span></div>
            </div>
        </div>

        <!-- Stealth Project Display -->
        <div class="mt-32 p-12 md:p-20 relative overflow-hidden bg-gradient-to-br from-primary/10 via-surface to-transparent border-l-8 border-primary rounded-r-3xl">
            <div class="relative z-10">
                <div class="flex items-center gap-3 mb-8">
                    <span class="w-3 h-3 bg-accent rounded-full animate-pulse shadow-[0_0_10px_#f43f5e]"></span>
                    <span class="fira text-accent font-bold text-xs uppercase">Classified Research Ongoing</span>
                </div>
                <h3 class="text-4xl md:text-7xl font-black mb-10 glow-text uppercase tracking-tighter">Project_Disruption</h3>
                <p class="text-gray-300 text-xl leading-relaxed max-w-4xl mb-12">
                    Architecting a paradigm-shifting computational framework that redefines memory locality. By bypassing traditional OS schedulers, this system achieves deterministic execution speeds for real-time algorithmic processing.
                </p>
                <div class="flex gap-6">
                    <div class="px-6 py-3 border border-white/10 bg-white/5 fira text-[10px] font-bold">STATUS: STABLE</div>
                    <div class="px-6 py-3 border border-white/10 bg-white/5 fira text-[10px] font-bold">BRANCH: MASTER-DEV</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Advanced Terminal Engine -->
    <section id="terminal" class="max-w-5xl mx-auto px-8 py-40">
        <div class="cyber-card rounded-2xl overflow-hidden shadow-2xl border border-white/5">
            <div class="bg-primary/10 p-5 flex justify-between items-center border-b border-white/5">
                <div class="flex gap-3">
                    <div class="w-3 h-3 rounded-full bg-red-500/50"></div>
                    <div class="w-3 h-3 rounded-full bg-yellow-500/50"></div>
                    <div class="w-3 h-3 rounded-full bg-green-500/50"></div>
                </div>
                <span class="fira text-[10px] text-gray-500 tracking-[0.4em] uppercase font-bold">AG-KERNEL-SHELL-V1.2</span>
            </div>
            <div class="p-10 bg-black/95 fira text-sm min-h-[500px] max-h-[600px] overflow-y-auto terminal-scroll" id="term-body">
                <div class="text-primary mb-4">> INITIALIZING KERNEL... [DONE]</div>
                <div class="text-gray-500 mb-8">> TYPE 'help' TO LIST SYSTEM CALLS. TAB TO COMPLETE.</div>
                
                <div id="term-output"></div>

                <div class="flex gap-4 mt-4 items-center">
                    <span class="text-primary font-bold">amirgh@kernel:~$</span>
                    <input type="text" id="term-input" class="bg-transparent border-none outline-none text-white w-full" autofocus spellcheck="false" autocomplete="off">
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="border-t border-white/5 py-32 px-8">
        <div class="max-w-7xl mx-auto grid md:grid-cols-4 gap-20">
            <div class="md:col-span-2">
                <div class="fira text-primary font-bold text-2xl mb-8 glow-text tracking-tighter">AG_RESEARCH</div>
                <p class="text-gray-500 max-w-sm text-sm leading-relaxed mb-10 italic">
                    Deconstructing the boundaries between logic and silicon. Built for performance, designed for the future.
                </p>
                <div class="flex gap-8">
                    <a href="#" class="text-xs font-bold text-gray-600 hover:text-primary transition-colors uppercase tracking-widest">LinkedIn</a>
                    <a href="#" class="text-xs font-bold text-gray-600 hover:text-primary transition-colors uppercase tracking-widest">GitHub</a>
                </div>
            </div>
            <div>
                <h4 class="text-[10px] font-bold text-gray-400 uppercase tracking-[0.4em] mb-8">Logic Index</h4>
                <ul class="space-y-4 text-xs font-bold text-gray-600">
                    <li><a href="#home" class="hover:text-primary transition-colors">INIT</a></li>
                    <li><a href="#arsenal" class="hover:text-primary transition-colors">ARSENAL</a></li>
                    <li><a href="#lab" class="hover:text-primary transition-colors">LABS</a></li>
                </ul>
            </div>
            <div>
                <h4 class="text-[10px] font-bold text-gray-400 uppercase tracking-[0.4em] mb-8">System Telemetry</h4>
                <div class="text-[10px] fira space-y-3">
                    <div class="flex justify-between"><span class="text-gray-700">UPTIME:</span><span class="text-primary">4_YEARS</span></div>
                    <div class="flex justify-between"><span class="text-gray-700">STATUS:</span><span class="text-green-500">OPTIMAL</span></div>
                </div>
            </div>
        </div>
        <div class="max-w-7xl mx-auto mt-32 pt-12 border-t border-white/5 text-center text-[10px] text-gray-800 uppercase tracking-[0.8em] font-bold">
            AmirMohammad Ghasemzadeh | MMXXVI
        </div>
    </footer>

    <script>
        // --- 1. Particle Matrix Background ---
        const canvas = document.getElementById('neural-bg');
        const ctx = canvas.getContext('2d');
        let particles = [];
        const mouse = { x: null, y: null, radius: 180 };

        window.addEventListener('mousemove', (e) => { mouse.x = e.x; mouse.y = e.y; });

        class Particle {
            constructor() {
                this.x = Math.random() * canvas.width;
                this.y = Math.random() * canvas.height;
                this.size = Math.random() * 1.5 + 0.5;
                this.baseX = this.x; this.baseY = this.y;
                this.density = (Math.random() * 40) + 5;
            }
            draw() {
                ctx.fillStyle = 'rgba(34, 211, 238, 0.4)';
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                ctx.fill();
            }
            update() {
                let dx = mouse.x - this.x;
                let dy = mouse.y - this.y;
                let distance = Math.sqrt(dx * dx + dy * dy);
                if (distance < mouse.radius) {
                    let force = (mouse.radius - distance) / mouse.radius;
                    this.x -= (dx / distance) * force * this.density;
                    this.y -= (dy / distance) * force * this.density;
                } else {
                    this.x -= (this.x - this.baseX) / 10;
                    this.y -= (this.y - this.baseY) / 10;
                }
            }
        }

        function initParticles() {
            canvas.width = window.innerWidth; canvas.height = window.innerHeight;
            particles = [];
            for (let i = 0; i < 120; i++) particles.push(new Particle());
        }

        function animateParticles() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            particles.forEach(p => { p.draw(); p.update(); });
            for (let a = 0; a < particles.length; a++) {
                for (let b = a; b < particles.length; b++) {
                    let dist = Math.sqrt((particles[a].x - particles[b].x)**2 + (particles[a].y - particles[b].y)**2);
                    if (dist < 120) {
                        ctx.strokeStyle = `rgba(34, 211, 238, ${0.12 - dist/1000})`;
                        ctx.lineWidth = 0.5;
                        ctx.beginPath(); ctx.moveTo(particles[a].x, particles[a].y); ctx.lineTo(particles[b].x, particles[b].y); ctx.stroke();
                    }
                }
            }
            requestAnimationFrame(animateParticles);
        }
        initParticles(); animateParticles();
        window.addEventListener('resize', initParticles);

        // --- 2. Hero Typing Logic ---
        const typingEl = document.getElementById('typing-text');
        const lines = ["Algorithm Researcher", "HPC Systems Engineer", "ENTP-A: Master of Deconstruction."];
        let lineIdx = 0, charIdx = 0;
        function type() {
            if (charIdx < lines[lineIdx].length) {
                typingEl.innerHTML = lines[lineIdx].substring(0, charIdx + 1) + '<span class="cursor text-primary">_</span>';
                charIdx++; setTimeout(type, 50);
            } else { setTimeout(erase, 2500); }
        }
        function erase() {
            if (charIdx > 0) {
                typingEl.innerHTML = lines[lineIdx].substring(0, charIdx - 1) + '<span class="cursor text-primary">_</span>';
                charIdx--; setTimeout(erase, 30);
            } else { lineIdx = (lineIdx + 1) % lines.length; setTimeout(type, 500); }
        }
        type();

        // --- 3. Skill Mastery Matrix ---
        const ctxRadar = document.getElementById('skillRadar').getContext('2d');
        let skillChart = new Chart(ctxRadar, {
            type: 'radar',
            data: {
                labels: ['Rust', 'C++', 'Complexity', 'Concurrency', 'ASM', 'Logic'],
                datasets: [{
                    data: [96, 92, 98, 90, 75, 95],
                    backgroundColor: 'rgba(34, 211, 238, 0.1)',
                    borderColor: '#22d3ee',
                    pointBackgroundColor: '#22d3ee',
                    borderWidth: 2
                }]
            },
            options: {
                responsive: true, maintainAspectRatio: false,
                scales: { r: { 
                    grid: { color: 'rgba(255,255,255,0.05)' }, 
                    angleLines: { color: 'rgba(255,255,255,0.05)' }, 
                    pointLabels: { color: '#64748b', font: { family: 'Fira Code', size: 10 } }, 
                    ticks: { display: false, max: 100 } 
                }},
                plugins: { legend: { display: false } }
            }
        });

        function toggleSet(mode) {
            const sysBtn = document.getElementById('set-sys');
            const resBtn = document.getElementById('set-res');
            if (mode === 'sys') {
                skillChart.data.labels = ['Rust', 'C++', 'LLVM', 'Concurrency', 'ASM', 'Memory'];
                skillChart.data.datasets[0].data = [96, 92, 85, 90, 75, 98];
                sysBtn.className = "flex-1 py-4 bg-primary/20 border border-primary text-primary text-[10px] font-black uppercase tracking-widest transition-all";
                resBtn.className = "flex-1 py-4 bg-transparent border border-white/10 text-gray-500 text-[10px] font-black uppercase tracking-widest hover:border-primary transition-all";
            } else {
                skillChart.data.labels = ['Big-O', 'Graph Theory', 'Logic', 'Dynamic Prog', 'Dist. Systems', 'Discrete Math'];
                skillChart.data.datasets[0].data = [99, 90, 95, 88, 85, 92];
                resBtn.className = "flex-1 py-4 bg-primary/20 border border-primary text-primary text-[10px] font-black uppercase tracking-widest transition-all";
                sysBtn.className = "flex-1 py-4 bg-transparent border border-white/10 text-gray-500 text-[10px] font-black uppercase tracking-widest hover:border-primary transition-all";
            }
            skillChart.update();
        }

        // --- 4. Advanced Terminal Shell Engine ---
        const termInput = document.getElementById('term-input');
        const termOutput = document.getElementById('term-output');
        const termBody = document.getElementById('term-body');
        
        let history = [];
        let historyIdx = -1;

        const commands = {
            help: () => `Available calls: <span class="text-primary">neofetch, ls, whoami, hack, stanford, clear, skills, contact</span>`,
            ls: () => `<span class="text-cyan-400">research/</span>  <span class="text-cyan-400">bin/</span>  resume.pdf  kernel_log.txt`,
            whoami: () => `AMIRMOHAMMAD GHASEMZADEH<br>Pervasive System Architect & Algorithm Researcher.<br>Philosophy: Maximum Performance via Minimal Abstraction.`,
            neofetch: () => `
                <div class="flex gap-4 items-center">
                    <div class="text-primary leading-none fira whitespace-pre">
      ████████████       
    ██            ██     
  ██    ████████    ██   
██    ██        ██    ██ 
██  ██  ████████  ██  ██ 
██    ██        ██    ██ 
  ██    ████████    ██   
    ██            ██     
      ████████████       
                    </div>
                    <div class="text-xs uppercase font-bold text-gray-400 leading-relaxed">
                        <span class="text-primary">AMIRGH@KERNEL</span><br>
                        ─────────────<br>
                        OS: Rust Kernel v1.2<br>
                        Uptime: 4 Years Research<br>
                        Shell: ENTP-A Logic<br>
                        Repos: 17+ Optimized<br>
                        Target: Stanford Grad
                    </div>
                </div>`,
            hack: () => {
                document.getElementById('terminal').classList.add('shake');
                document.body.style.backgroundColor = '#f43f5e';
                setTimeout(() => {
                    document.getElementById('terminal').classList.remove('shake');
                    document.body.style.backgroundColor = '';
                }, 300);
                return `<span class="text-accent font-bold">⚠️ ACCESS DENIED: SYSTEM INERTIA RECOGNIZED.</span><br>Type 'stanford' to initialize academic protocol.`;
            },
            stanford: () => `<span class="text-primary font-bold">🎯 ACADEMIC TARGET: [ENGAGED]</span><br>Status: Researching computational limits for candidate admission. Probability: Optimistic.`,
            skills: () => `Primary Core: Rust, C++, Python, Math Logic, SIMD Optimization.`,
            contact: () => `Connect via: amirgh.devtech@gmail.com | github.com/amirgh-devtech`,
            clear: () => { termOutput.innerHTML = ''; return null; }
        };

        termInput.addEventListener('keydown', (e) => {
            // Tab Completion
            if (e.key === 'Tab') {
                e.preventDefault();
                const currentInput = termInput.value.toLowerCase();
                const match = Object.keys(commands).find(c => c.startsWith(currentInput));
                if (match) termInput.value = match;
            }
            
            // History Management
            if (e.key === 'ArrowUp') {
                e.preventDefault();
                if (historyIdx < history.length - 1) {
                    historyIdx++;
                    termInput.value = history[history.length - 1 - historyIdx];
                }
            } else if (e.key === 'ArrowDown') {
                e.preventDefault();
                if (historyIdx > 0) {
                    historyIdx--;
                    termInput.value = history[history.length - 1 - historyIdx];
                } else {
                    historyIdx = -1;
                    termInput.value = '';
                }
            }

            // Command Execution
            if (e.key === 'Enter') {
                const rawCmd = termInput.value.trim();
                const cmd = rawCmd.toLowerCase();
                
                if (rawCmd) {
                    history.push(rawCmd);
                    historyIdx = -1;
                }

                const line = document.createElement('div');
                line.className = 'mt-4 fira';
                line.innerHTML = `<span class="text-primary">amirgh@kernel:~$</span> <span class="text-white">${rawCmd}</span>`;
                termOutput.appendChild(line);

                if (commands[cmd]) {
                    const out = commands[cmd]();
                    if (out !== null) {
                        const response = document.createElement('div');
                        response.className = 'mt-1 text-gray-400 pl-4 border-l border-white/5';
                        response.innerHTML = out;
                        termOutput.appendChild(response);
                    }
                } else if (cmd !== '') {
                    const err = document.createElement('div');
                    err.className = 'mt-1 text-accent pl-4';
                    err.innerHTML = `ERR: Command '${cmd}' not recognized. Try 'help'.`;
                    termOutput.appendChild(err);
                }

                termInput.value = '';
                termBody.scrollTop = termBody.scrollHeight;
            }
        });
    </script>
</body>
</html>
