
<html lang="pt-BR" class="dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SAMS | Cidades À Prova de Catástrofes & Fundações Inteligentes</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        sci: {
                            950: '#020617',
                            900: '#090d16',
                            800: '#111827',
                            700: '#1f2937',
                            cyan: '#06b6d4',
                            emerald: '#10b981',
                            amber: '#f59e0b',
                            rose: '#f43f5e',
                            purple: '#8b5cf6'
                        }
                    }
                }
            }
        }
    </script>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;500;700&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; }
        .font-mono { font-family: 'JetBrains Mono', monospace; }
        .glass-panel {
            background: rgba(15, 23, 42, 0.75);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(6, 182, 212, 0.2);
        }
        .glow-cyan {
            box-shadow: 0 0 25px rgba(6, 182, 212, 0.25);
        }
        .glow-rose {
            box-shadow: 0 0 25px rgba(244, 63, 94, 0.3);
        }
        ::-webkit-scrollbar {
            width: 6px;
            height: 6px;
        }
        ::-webkit-scrollbar-track {
            background: #020617;
        }
        ::-webkit-scrollbar-thumb {
            background: #1e293b;
            border-radius: 3px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #06b6d4;
        }
    </style>
</head>
<body class="bg-sci-950 text-slate-100 min-h-screen flex flex-col overflow-x-hidden">

    <!-- Header / Navbar -->
    <header class="glass-panel border-b border-cyan-500/20 px-6 py-4 flex flex-wrap items-center justify-between gap-4 sticky top-0 z-50">
        <div class="flex items-center space-x-3">
            <div class="relative flex items-center justify-center w-10 h-10 rounded-xl bg-cyan-950 border border-cyan-500/50 glow-cyan">
                <svg class="w-6 h-6 text-cyan-400 animate-pulse" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 21V5a2 2 0 00-2-2H7a2 2 0 00-2 2v16m14 0h2m-2 0h-5m-9 0H3m2 0h5M9 7h1m-1 4h1m4-4h1m-1 4h1m-5 10v-5a1 1 0 011-1h2a1 1 0 011 1v5m-4 0h4"/>
                </svg>
            </div>
            <div>
                <h1 class="text-lg font-bold tracking-wider text-transparent bg-clip-text bg-gradient-to-r from-cyan-400 to-emerald-400">SAMS URBAN SHIELD</h1>
                <p class="text-xs text-slate-400 font-mono">Fundações de Fluido Magnetorreológico & Cidades Indestrutíveis</p>
            </div>
        </div>

        <!-- System Status Pills -->
        <div class="flex items-center gap-3 text-xs font-mono flex-wrap">
            <div class="flex items-center gap-2 px-3 py-1.5 rounded-full bg-slate-900 border border-slate-700">
                <span id="sams-status-dot" class="w-2.5 h-2.5 rounded-full bg-emerald-500 animate-ping"></span>
                <span>SAMS Defesa Sísmica: <strong id="sams-status-text" class="text-emerald-400">ATIVO (0.4 ms)</strong></span>
            </div>
            <div class="flex items-center gap-2 px-3 py-1.5 rounded-full bg-slate-900 border border-slate-700">
                <span class="w-2.5 h-2.5 rounded-full bg-cyan-500"></span>
                <span>Fundações MR: <strong id="foundation-state-badge" class="text-cyan-400">VISCOSO / ADAPTATIVO</strong></span>
            </div>
            <div class="flex items-center gap-2 px-3 py-1.5 rounded-full bg-slate-900 border border-slate-700">
                <span class="w-2.5 h-2.5 rounded-full bg-purple-500"></span>
                <span>Dissipação de Energia: <strong class="text-purple-400">100%</strong></span>
            </div>
        </div>
    </header>

    <!-- Main Workspace -->
    <main class="flex-1 grid grid-cols-1 lg:grid-cols-12 gap-6 p-6 max-w-[1700px] mx-auto w-full">
        
        <!-- Left Sidebar: Disaster Scenarios & SAMS Controls -->
        <section class="lg:col-span-3 flex flex-col gap-6">
            
            <!-- Disaster Type Selection -->
            <div class="glass-panel rounded-2xl p-5 shadow-xl">
                <h2 class="text-sm font-semibold tracking-wide text-cyan-400 uppercase mb-4 flex items-center gap-2">
                    <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3.055 11H5a2 2 0 012 2v1a2 2 0 002 2 2 2 0 012 2v2.945M8 3.935V5.5A2.5 2.5 0 0010.5 8h.5a2 2 0 012 2 2 2 0 104 0 2 2 0 012-2h1.064M15 20.488V18a2 2 0 012-2h3.064M21 12a9 9 0 11-18 0 9 9 0 0118 0z"/></svg>
                    Cenários de Catástrofe
                </h2>
                <div class="space-y-3">
                    <button onclick="setDisaster('earthquake')" id="dis-earthquake" class="w-full text-left p-3 rounded-xl border border-cyan-500/40 bg-cyan-500/10 transition-all hover:bg-cyan-500/20 flex items-center justify-between group">
                        <div>
                            <div class="font-semibold text-sm text-cyan-300">Terremoto Magnitude 9.5</div>
                            <div class="text-xs text-slate-400">Ondas de choque tectônicas verticais/horizontais</div>
                        </div>
                        <span class="w-2 h-2 rounded-full bg-cyan-400"></span>
                    </button>
                    <button onclick="setDisaster('tsunami')" id="dis-tsunami" class="w-full text-left p-3 rounded-xl border border-slate-700 bg-slate-900/60 transition-all hover:border-cyan-500/40 flex items-center justify-between group">
                        <div>
                            <div class="font-semibold text-sm text-slate-200 group-hover:text-cyan-300">Tsunami de Mega-Impacto</div>
                            <div class="text-xs text-slate-400">Parede d'água de 40 metros nas fundações</div>
                        </div>
                        <span class="w-2 h-2 rounded-full bg-slate-600" id="dot-tsunami"></span>
                    </button>
                    <button onclick="setDisaster('hurricane')" id="dis-hurricane" class="w-full text-left p-3 rounded-xl border border-slate-700 bg-slate-900/60 transition-all hover:border-amber-500/40 flex items-center justify-between group">
                        <div>
                            <div class="font-semibold text-sm text-slate-200 group-hover:text-amber-300">Furacão Categoria 5+</div>
                            <div class="text-xs text-slate-400">Ventos de 320 km/h e cisalhamento estrutural</div>
                        </div>
                        <span class="w-2 h-2 rounded-full bg-slate-600" id="dot-hurricane"></span>
                    </button>
                </div>
            </div>

            <!-- SAMS Control Unit -->
            <div class="glass-panel rounded-2xl p-5 shadow-xl border-cyan-500/30">
                <div class="flex items-center justify-between mb-4">
                    <h2 class="text-sm font-semibold tracking-wide text-cyan-400 uppercase flex items-center gap-2">
                        <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z"/></svg>
                        Mecanismo SAMS
                    </h2>
                    <span id="sams-badge" class="px-2.5 py-0.5 rounded text-xs font-mono font-bold bg-cyan-500/20 text-cyan-300 border border-cyan-500/40">ATIVO</span>
                </div>
                
                <div class="space-y-4">
                    <div class="flex items-center justify-between bg-slate-900/80 p-3 rounded-xl border border-slate-800">
                        <div>
                            <div class="text-xs font-medium text-slate-300">Mudança de Estado MR (Fluido -> Sólido)</div>
                            <div class="text-[10px] text-slate-400 font-mono">Rigidez superior ao diamante</div>
                        </div>
                        <label class="relative inline-flex items-center cursor-pointer">
                            <input type="checkbox" id="samsToggle" checked onchange="toggleSAMS()" class="sr-only peer">
                            <div class="w-11 h-6 bg-slate-700 peer-focus:outline-none rounded-full peer peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all peer-checked:bg-cyan-500"></div>
                        </label>
                    </div>

                    <div>
                        <div class="flex justify-between text-xs mb-1 font-mono">
                            <span class="text-slate-400">Intensidade do Desastre</span>
                            <span id="intensity-val" class="text-amber-400">85%</span>
                        </div>
                        <input type="range" id="disasterIntensity" min="20" max="100" value="85" oninput="updateIntensity(this.value)" class="w-full h-2 bg-slate-800 rounded-lg appearance-none cursor-pointer accent-cyan-400">
                    </div>

                    <div>
                        <div class="flex justify-between text-xs mb-1 font-mono">
                            <span class="text-slate-400">Campo Eletromagnético de Bloqueio</span>
                            <span class="text-emerald-400">12.8 Tesla</span>
                        </div>
                        <input type="range" min="1" max="10" value="9" class="w-full h-2 bg-slate-800 rounded-lg appearance-none cursor-pointer accent-emerald-400">
                    </div>
                </div>
            </div>

            <!-- Action Triggers -->
            <div class="glass-panel rounded-2xl p-5 shadow-xl flex flex-col gap-3">
                <h2 class="text-sm font-semibold tracking-wide text-cyan-400 uppercase mb-1">Simulações de Impacto</h2>
                <button onclick="triggerShockwave()" class="w-full py-3 px-4 rounded-xl bg-gradient-to-r from-cyan-600 to-emerald-600 hover:from-cyan-500 hover:to-emerald-500 text-white font-semibold text-sm shadow-lg shadow-cyan-900/30 transition-all flex items-center justify-center gap-2">
                    <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 9v2m0 4h.01m-6.938 4h13.856c1.54 0 2.502-1.667 1.732-3L13.732 4c-.77-1.333-2.694-1.333-3.464 0L3.34 16c-.77 1.333.192 3 1.732 3z"/></svg>
                    Liberar Onda de Choque Extrema
                </button>
                <button onclick="recalibrateCity()" class="w-full py-2.5 px-4 rounded-xl bg-slate-900 hover:bg-slate-800 border border-slate-700 text-slate-300 font-medium text-xs transition-all flex items-center justify-center gap-2">
                    <svg class="w-4 h-4 text-cyan-400" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 4v5h.582m15.356 2A8.001 8.001 0 004.582 9m0 0H9m11 11v-5h-.581m0 0a8.003 8.003 0 01-15.357-2m15.357 2H15"/></svg>
                    Recalibrar Fundações MR
                </button>
            </div>

        </section>

        <!-- Center: Canvas 2D Simulation Viewport -->
        <section class="lg:col-span-6 flex flex-col gap-6">
            <div class="glass-panel rounded-2xl p-4 shadow-2xl relative flex flex-col overflow-hidden border-cyan-500/30">
                
                <!-- Viewport Header HUD -->
                <div class="flex items-center justify-between pb-3 mb-3 border-b border-slate-800 text-xs font-mono">
                    <div class="flex items-center gap-2">
                        <span class="w-2 h-2 rounded-full bg-emerald-400 animate-pulse"></span>
                        <span class="text-slate-300">CORTE TRANSVERSAL - ARRANHA-CÉU E FUNDAÇÕES MR</span>
                    </div>
                    <div class="flex items-center gap-4 text-slate-400">
                        <span>Tempo de Reação: <strong id="hud-reaction" class="text-emerald-400">0.4 ms</strong></span>
                        <span>Força Sísmica: <strong id="hud-force" class="text-cyan-400">9.5 Richter</strong></span>
                    </div>
                </div>

                <!-- Canvas Container -->
                <div class="relative w-full aspect-[4/3] bg-slate-950 rounded-xl overflow-hidden border border-slate-800 shadow-inner">
                    <canvas id="simCanvas" class="w-full h-full block"></canvas>
                    
                    <!-- HUD Instructions / Legend -->
                    <div class="absolute bottom-4 left-4 pointer-events-none bg-slate-900/80 backdrop-blur-md px-3 py-2 rounded-lg border border-cyan-500/30 text-[11px] font-mono text-cyan-300 space-y-1">
                        <div>🏢 Prédio inteligente com amortecedores de fluido MR subterrâneos</div>
                        <div>⚡ Transição de líquido para sólido rígido em milissegundos</div>
                    </div>

                    <!-- Disaster Alert Banner -->
                    <div id="disaster-banner" class="absolute top-4 inset-x-4 pointer-events-none hidden transition-all duration-300">
                        <div class="bg-cyan-950/90 border border-cyan-400 text-cyan-200 px-4 py-2 rounded-xl text-xs font-mono font-bold flex items-center justify-center gap-2 animate-bounce">
                            <svg class="w-4 h-4 text-cyan-400" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z"/></svg>
                            ONDA TECTÔNICA DETECTADA! FUNDAÇÕES MR ENDURECERAM ALÉM DO DIAMANTE! ENERGIA DISSIPADA!
                        </div>
                    </div>
                </div>

                <!-- Quick Metrics Bar -->
                <div class="grid grid-cols-3 gap-3 mt-4 text-center font-mono">
                    <div class="bg-slate-900/60 p-2.5 rounded-xl border border-slate-800">
                        <div class="text-[10px] text-slate-400">Integridade Estrutural</div>
                        <div id="metric-integrity" class="text-sm font-bold text-cyan-400">100.0%</div>
                    </div>
                    <div class="bg-slate-900/60 p-2.5 rounded-xl border border-slate-800">
                        <div class="text-[10px] text-slate-400">Rigidez da Fundação MR</div>
                        <div id="metric-rigidity" class="text-sm font-bold text-emerald-400">Sólido Extremo (Diamantino)</div>
                    </div>
                    <div class="bg-slate-900/60 p-2.5 rounded-xl border border-slate-800">
                        <div class="text-[10px] text-slate-400">Absorção de Choque</div>
                        <div id="metric-absorption" class="text-sm font-bold text-purple-400">100% (Zero Oscilação)</div>
                    </div>
                </div>

            </div>
        </section>

        <!-- Right Sidebar: Telemetry & SAMS Urban Intelligence Console -->
        <section class="lg:col-span-3 flex flex-col gap-6">
            
            <!-- Urban Metrics -->
            <div class="glass-panel rounded-2xl p-5 shadow-xl">
                <h2 class="text-sm font-semibold tracking-wide text-cyan-400 uppercase mb-4 flex items-center gap-2">
                    <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z"/></svg>
                    Métricas Urbanas SAMS
                </h2>
                <div class="space-y-3 font-mono text-xs">
                    <div class="flex justify-between items-center bg-slate-900/80 p-2.5 rounded-xl border border-slate-800">
                        <span class="text-slate-400">Edifícios Protegidos</span>
                        <span class="text-emerald-400 font-bold">1,420 Torres</span>
                    </div>
                    <div class="flex justify-between items-center bg-slate-900/80 p-2.5 rounded-xl border border-slate-800">
                        <span class="text-slate-400">População Segura</span>
                        <span class="text-cyan-400 font-bold">8.4 Milhões</span>
                    </div>
                    <div class="flex justify-between items-center bg-slate-900/80 p-2.5 rounded-xl border border-slate-800">
                        <span class="text-slate-400">Viscosidade Base MR</span>
                        <span class="text-purple-400 font-bold">Variável (0 a 500k Pa·s)</span>
                    </div>
                    <div class="flex justify-between items-center bg-slate-900/80 p-2.5 rounded-xl border border-slate-800">
                        <span class="text-slate-400">Alimentação Magnética</span>
                        <span class="text-amber-400 font-bold">Reator Fissão / Fusion</span>
                    </div>
                </div>
            </div>

            <!-- SAMS AI Urban Intelligence Console -->
            <div class="glass-panel rounded-2xl p-5 shadow-xl flex flex-col flex-1 min-h-[260px]">
                <h2 class="text-sm font-semibold tracking-wide text-cyan-400 uppercase mb-3 flex items-center gap-2">
                    <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 9l3 3-3 3m5 0h3M5 20h14a2 2 0 002-2V6a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z"/></svg>
                    Console SAMS Urban AI
                </h2>
                <div id="ai-console" class="flex-1 bg-slate-950/80 rounded-xl p-3 border border-slate-900 font-mono text-[11px] text-slate-300 space-y-1.5 overflow-y-auto max-h-[220px]">
                    <div class="text-slate-500">[00:00:01] SAMS Urban Shield v7.4 inicializado.</div>
                    <div class="text-cyan-400">[00:00:03] Sensores piezoelétricos na crosta terrestre ativos.</div>
                    <div class="text-emerald-400">[00:00:05] Fundações MR em prontidão molecular diamantina.</div>
                </div>
            </div>

        </section>

    </main>

    <!-- Footer -->
    <footer class="text-center py-4 text-xs text-slate-500 border-t border-slate-900 font-mono">
        SAMS (Smart Active Micro-Vibration Suppression) &bull; Cidades À Prova de Catástrofes v4.0
    </footer>

    <!-- JavaScript Simulation Engine -->
    <script>
        // --- Simulation State ---
        let state = {
            disaster: 'earthquake', // 'earthquake', 'tsunami', 'hurricane'
            samsActive: true,
            disasterIntensity: 85,
            time: 0,
            shockActive: false,
            shockTimer: 0
        };

        // DOM Elements
        const canvas = document.getElementById('simCanvas');
        const ctx = canvas.getContext('2d');
        const samsToggleEl = document.getElementById('samsToggle');
        const samsBadgeEl = document.getElementById('sams-badge');
        const samsStatusTextEl = document.getElementById('sams-status-text');
        const foundationStateBadgeEl = document.getElementById('foundation-state-badge');
        const disasterBannerEl = document.getElementById('disaster-banner');
        const hudReactionEl = document.getElementById('hud-reaction');
        const metricIntegrityEl = document.getElementById('metric-integrity');
        const metricRigidityEl = document.getElementById('metric-rigidity');
        const metricAbsorptionEl = document.getElementById('metric-absorption');
        const aiConsole = document.getElementById('ai-console');

        // Audio Helper
        let audioCtx = null;
        function initAudio() {
            if (!audioCtx) audioCtx = new (window.AudioContext || window.webkitAudioContext)();
        }

        function playBeep(freq = 440, type = 'sine', duration = 0.1) {
            try {
                initAudio();
                if (!audioCtx) return;
                const osc = audioCtx.createOscillator();
                const gain = audioCtx.createGain();
                osc.type = type;
                osc.frequency.value = freq;
                gain.gain.setValueAtTime(0.04, audioCtx.currentTime);
                gain.gain.exponentialRampToValueAtTime(0.0001, audioCtx.currentTime + duration);
                osc.connect(gain);
                gain.connect(audioCtx.destination);
                osc.start();
                osc.stop(audioCtx.currentTime + duration);
            } catch (e) {}
        }

        // Resize Canvas
        function resizeCanvas() {
            const rect = canvas.getBoundingClientRect();
            canvas.width = rect.width * window.devicePixelRatio;
            canvas.height = rect.height * window.devicePixelRatio;
            ctx.setTransform(window.devicePixelRatio, 0, 0, window.devicePixelRatio, 0, 0);
        }

        window.addEventListener('resize', resizeCanvas);

        // Control Handlers
        function setDisaster(dis) {
            state.disaster = dis;
            ['earthquake', 'tsunami', 'hurricane'].forEach(d => {
                const btn = document.getElementById(`dis-${d}`);
                if (d === dis) {
                    btn.className = "w-full text-left p-3 rounded-xl border border-cyan-500/40 bg-cyan-500/10 transition-all flex items-center justify-between group";
                } else {
                    btn.className = "w-full text-left p-3 rounded-xl border border-slate-700 bg-slate-900/60 transition-all hover:border-slate-500 flex items-center justify-between group";
                }
            });

            if (dis === 'earthquake') {
                logAI("Cenário selecionado: Terremoto 9.5 Richter. Sensores monitorando ondas P e S.");
                playBeep(400, 'triangle', 0.15);
            } else if (dis === 'tsunami') {
                logAI("Cenário selecionado: Tsunami de Mega-Impacto. Paredes d'água oceânicas em aproximação.");
                playBeep(350, 'sawtooth', 0.15);
            } else {
                logAI("Cenário selecionado: Furacão Cat 5+. Ventos de cisalhamento e pressão atmosférica extrema.");
                playBeep(500, 'sine', 0.15);
            }
        }

        function toggleSAMS() {
            state.samsActive = samsToggleEl.checked;
            if (state.samsActive) {
                samsBadgeEl.textContent = "ATIVO";
                samsBadgeEl.className = "px-2.5 py-0.5 rounded text-xs font-mono font-bold bg-cyan-500/20 text-cyan-300 border border-cyan-500/40";
                samsStatusTextEl.textContent = "ATIVO (0.4 ms)";
                foundationStateBadgeEl.textContent = "VISCOSO / ADAPTATIVO";
                logAI("SAMS reativado: Fundações MR preparadas para endurecimento molecular instantâneo.");
                playBeep(880, 'sine', 0.2);
            } else {
                samsBadgeEl.textContent = "DESLIGADO";
                samsBadgeEl.className = "px-2.5 py-0.5 rounded text-xs font-mono font-bold bg-rose-500/20 text-rose-300 border border-rose-500/40";
                samsStatusTextEl.textContent = "VULNERÁVEL";
                foundationStateBadgeEl.textContent = "CONCRETO TRADICIONAL";
                logAI("ALERTA: SAMS desativado! Risco de colapso estrutural sob impacto catastrófico.");
                playBeep(180, 'sawtooth', 0.3);
            }
        }

        function updateIntensity(val) {
            state.disasterIntensity = parseInt(val);
            document.getElementById('intensity-val').textContent = val + '%';
        }

        function triggerShockwave() {
            state.shockActive = true;
            state.shockTimer = 80;
            disasterBannerEl.classList.remove('hidden');

            if (state.samsActive) {
                logAI("⚡ ONDA DE CHOQUE EXTREMA DETECTADA! Fluido MR mudou para estado sólido diamantino em 0.4ms. Energia 100% dissipada.");
                playBeep(1200, 'square', 0.3);
            } else {
                logAI("💥 CATÁSTROFE! Sem SAMS, o arranha-céu sofre torção severa, fraturas no concreto e oscilação extrema!");
                playBeep(110, 'sawtooth', 0.5);
            }

            setTimeout(() => {
                disasterBannerEl.classList.add('hidden');
                state.shockActive = false;
            }, 3000);
        }

        function recalibrateCity() {
            logAI("🔄 Calibração da rede eletromagnética subterrânea concluída. Alinhamento perfeito.");
            playBeep(750, 'sine', 0.2);
        }

        function logAI(message) {
            const timeStr = new Date().toTimeString().split(' ')[0];
            const div = document.createElement('div');
            div.className = "text-slate-300";
            div.innerHTML = `<span class="text-slate-500">[${timeStr}]</span> ${message}`;
            aiConsole.appendChild(div);
            aiConsole.scrollTop = aiConsole.scrollHeight;
        }

        // --- Main Animation & Simulation Loop ---
        function updateSimulation() {
            state.time += 0.04;
            drawCanvas();
            requestAnimationFrame(updateSimulation);
        }

        function drawCanvas() {
            const width = canvas.clientWidth;
            const height = canvas.clientHeight;
            
            ctx.clearRect(0, 0, width, height);

            // Draw sky / atmosphere
            ctx.fillStyle = '#020617';
            ctx.fillRect(0, 0, width, height);

            // Draw ground level line
            const groundY = height * 0.65;
            ctx.fillStyle = '#090d16';
            ctx.fillRect(0, groundY, width, height - groundY);

            ctx.strokeStyle = '#06b6d4';
            ctx.lineWidth = 2;
            ctx.beginPath();
            ctx.moveTo(0, groundY);
            ctx.lineTo(width, groundY);
            ctx.stroke();

            // Draw underground foundation chamber (Magnetorheological Fluid Dampers)
            const towerWidth = 140;
            const towerHeight = 240;
            const towerX = (width - towerWidth) / 2;
            const towerY = groundY - towerHeight;

            // Underground foundation vault
            ctx.fillStyle = 'rgba(15, 23, 42, 0.9)';
            ctx.strokeStyle = state.samsActive ? '#06b6d4' : '#f43f5e';
            ctx.lineWidth = 3;
            ctx.fillRect(towerX - 20, groundY, towerWidth + 40, 110);
            ctx.strokeRect(towerX - 20, groundY, towerWidth + 40, 110);

            // Underground MR Fluid Chamber glowing nodes
            for (let i = 0; i < 3; i++) {
                const cx = towerX + 35 + (i * 35);
                const cy = groundY + 55;
                ctx.fillStyle = state.samsActive && (state.shockActive || state.disasterIntensity > 50) ? '#10b981' : '#06b6d4';
                ctx.beginPath();
                ctx.arc(cx, cy, 12, 0, Math.PI * 2);
                ctx.fill();

                // Magnetic field rings
                ctx.strokeStyle = state.samsActive ? 'rgba(6, 182, 212, 0.6)' : 'rgba(244, 63, 94, 0.4)';
                ctx.lineWidth = 2;
                ctx.beginPath();
                ctx.arc(cx, cy, 18 + Math.sin(state.time * 6 + i) * 4, 0, Math.PI * 2);
                ctx.stroke();
            }

            // Seismic wave or tsunami wave animation
            let waveOffset = 0;
            if (state.shockActive || state.disaster === 'earthquake') {
                waveOffset = Math.sin(state.time * 25) * (state.disasterIntensity / 4);
                if (!state.samsActive) {
                    waveOffset *= 2.5;
                }
            }

            // Draw Skyscraper building with sway calculation
            ctx.save();
            let sway = 0;
            if (state.shockActive) {
                if (state.samsActive) {
                    sway = Math.sin(state.time * 30) * 1.5; // Almost zero sway thanks to diamond rigidity
                } else {
                    sway = Math.sin(state.time * 15) * 22; // Severe swaying and potential structural failure
                }
            } else if (state.disaster === 'hurricane') {
                sway = Math.sin(state.time * 4) * (state.samsActive ? 3 : 14);
            }

            ctx.translate(towerX + towerWidth / 2 + waveOffset, groundY);
            ctx.rotate(sway * 0.008);
            ctx.translate(-(towerX + towerWidth / 2), -groundY);

            // Building Structure
            ctx.fillStyle = '#0f172a';
            ctx.strokeStyle = state.samsActive ? '#06b6d4' : (state.shockActive ? '#f43f5e' : '#334155');
            ctx.lineWidth = 4;
            ctx.fillRect(towerX, towerY, towerWidth, towerHeight);
            ctx.strokeRect(towerX, towerY, towerWidth, towerHeight);

            // Building Windows Grid
            ctx.fillStyle = 'rgba(6, 182, 212, 0.3)';
            for (let wy = towerY + 20; wy < groundY - 20; wy += 30) {
                for (let wx = towerX + 15; wx < towerX + towerWidth - 15; wx += 35) {
                    ctx.fillRect(wx, wy, 20, 16);
                }
            }

            // Tsunami wave overlay if disaster is tsunami
            if (state.disaster === 'tsunami') {
                ctx.fillStyle = 'rgba(6, 182, 212, 0.35)';
                ctx.beginPath();
                const tsunamiHeight = groundY - 80 + Math.sin(state.time * 8) * 20;
                ctx.moveTo(0, groundY);
                ctx.bezierCurveTo(width * 0.3, tsunamiHeight, width * 0.5, tsunamiHeight - 30, width * 0.6, groundY);
                ctx.fill();
            }

            ctx.restore();

            // Update UI telemetry badges dynamically
            if (state.samsActive) {
                metricRigidity.textContent = state.shockActive ? "SÓLIDO DIAMANTINO (MÁX)" : "Adaptativo Inteligente";
                metricRigidity.className = "text-sm font-bold text-emerald-400";
                metricIntegrity.textContent = "100.0% (Indestrutível)";
                metricAbsorption.textContent = "100% (Dissipado)";
                foundationStateBadgeEl.textContent = "SÓLIDO RÍGIDO (DIAMANTE)";
                hudReactionEl.textContent = "0.4 ms";
            } else {
                metricRigidity.textContent = "Vulnerável (Fluido Livre)";
                metricRigidity.className = "text-sm font-bold text-rose-400";
                metricIntegrity.textContent = state.shockActive ? "64.2% (Danos Críticos!)" : "98.5%";
                metricAbsorption.textContent = "12% (Oscilação Severa)";
                foundationStateBadgeEl.textContent = "VULNERÁVEL / LÍQUIDO";
                hudReactionEl.textContent = "OFF";
            }
        }

        // Initialize on load
        window.onload = function() {
            resizeCanvas();
            updateSimulation();
        };
    </script>
</body>
</html>
