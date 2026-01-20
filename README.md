<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Espaço Vanessa Braga - Academy</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --rose-lux: #fff5f8;
            --gold-gradient: linear-gradient(135deg, #bf953f 0%, #fcf6ba 45%, #b38728 70%, #fbf5b7 100%);
            --gold-shine: #d4af37;
            --pink-accent: #f8c8dc;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background-color: var(--rose-lux);
            color: #4a3b3b;
        }

        .font-serif { font-family: 'Playfair Display', serif; }

        .gold-border {
            border: 2px solid transparent;
            background-image: linear-gradient(white, white), var(--gold-gradient);
            background-origin: border-box;
            background-clip: content-box, border-box;
        }

        .gold-text {
            background: var(--gold-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-weight: bold;
        }

        .nav-active {
            color: #b38728;
            border-bottom: 2px solid #b38728;
        }

        /* Animação de brilho cintilante */
        .cintilante {
            position: relative;
            overflow: hidden;
        }
        .cintilante::after {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255,255,255,0.4), transparent);
            transform: rotate(45deg);
            transition: 0.6s;
        }
        .cintilante:hover::after {
            left: 100%;
        }

        .video-container {
            position: relative;
            padding-bottom: 56.25%;
            height: 0;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 20px 50px rgba(0,0,0,0.1);
        }

        .video-container iframe {
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
        }

        .custom-scroll::-webkit-scrollbar { width: 4px; }
        .custom-scroll::-webkit-scrollbar-thumb { background: var(--gold-shine); border-radius: 10px; }
    </style>
</head>
<body>

    <!-- Header -->
    <header class="bg-white/90 backdrop-blur-md sticky top-0 z-50 border-b border-pink-100 py-4 px-6">
        <div class="max-w-7xl mx-auto flex flex-col md:flex-row justify-between items-center">
            <div class="text-center md:text-left">
                <h1 class="text-3xl font-serif gold-text tracking-tighter">Espaço Vanessa Braga</h1>
                <p class="text-[10px] uppercase tracking-[0.5em] text-pink-400 font-bold">Visagismo & Alta Performance</p>
            </div>
            <nav class="flex gap-6 mt-4 md:mt-0">
                <button onclick="switchTab('aulas')" id="tab-aulas" class="nav-active text-xs font-bold uppercase py-2">Masterclass</button>
                <button onclick="switchTab('catalogo')" id="tab-catalogo" class="text-gray-400 text-xs font-bold uppercase py-2">Catálogo 50+</button>
                <button onclick="switchTab('tecnica')" id="tab-tecnica" class="text-gray-400 text-xs font-bold uppercase py-2">Guia de Ângulos</button>
            </nav>
        </div>
    </header>

    <main class="max-w-7xl mx-auto px-4 py-8">

        <!-- ABA 1: MASTERCLASS E VÍDEOS -->
        <section id="section-aulas" class="block">
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-8">
                <!-- Player -->
                <div class="lg:col-span-8">
                    <div class="video-container gold-border p-1 bg-white">
                        <iframe id="mainPlayer" src="https://www.youtube.com/embed/eL0PmFM-C-w" frameborder="0" allowfullscreen></iframe>
                    </div>
                    <div class="mt-8 bg-white p-8 rounded-[32px] shadow-sm border border-pink-50">
                        <div class="flex flex-wrap gap-3 mb-4">
                            <span id="badgeAngulo" class="bg-gold-gradient text-white px-4 py-1 rounded-full text-[10px] font-bold">ÂNGULO: 0° A 45°</span>
                            <span id="badgeTesoura" class="bg-pink-100 text-pink-500 px-4 py-1 rounded-full text-[10px] font-bold">TESOURA: FIO LASER</span>
                        </div>
                        <h2 id="mainTitle" class="text-3xl font-serif mb-4">Long Bob Clássico</h2>
                        <p id="mainDesc" class="text-gray-500 text-sm leading-relaxed">Técnica fundamental para cortes médios, focando na base reta e projeção frontal para criar o bico alongado.</p>
                        
                        <div class="grid grid-cols-2 md:grid-cols-4 gap-4 mt-8 pt-8 border-t border-pink-50">
                            <div class="text-center">
                                <p class="text-[9px] uppercase text-gray-400 font-bold">Ponto de Partida</p>
                                <p class="text-xs font-bold">Nuca Baixa</p>
                            </div>
                            <div class="text-center">
                                <p class="text-[9px] uppercase text-gray-400 font-bold">Divisões</p>
                                <p class="text-xs font-bold">Ferradura</p>
                            </div>
                            <div class="text-center">
                                <p class="text-[9px] uppercase text-gray-400 font-bold">Densidade</p>
                                <p class="text-xs font-bold">Média a Alta</p>
                            </div>
                            <div class="text-center">
                                <p class="text-[9px] uppercase text-gray-400 font-bold">Finalização</p>
                                <p class="text-xs font-bold">Brush Out</p>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Lista de Aulas -->
                <div class="lg:col-span-4 space-y-4">
                    <h3 class="font-serif text-xl mb-4 gold-text">Aulas Disponíveis</h3>
                    <div class="space-y-3 max-h-[700px] overflow-y-auto pr-2 custom-scroll">
                        
                        <!-- Cards das Aulas -->
                        <div onclick="updateVideo('eL0PmFM-C-w', 'Long Bob Clássico', '0° A 45°', 'FIO LASER', 'Base reta com projeção frontal para alongamento.')" class="bg-white p-3 rounded-2xl flex gap-4 cursor-pointer hover:shadow-md transition border border-pink-50">
                            <img src="https://img.youtube.com/vi/eL0PmFM-C-w/mqdefault.jpg" class="w-24 h-16 rounded-lg object-cover">
                            <div>
                                <h4 class="text-xs font-bold">Long Bob</h4>
                                <p class="text-[10px] text-gray-400">Ângulo: 45°</p>
                            </div>
                        </div>

                        <div onclick="updateVideo('KpuAPqHyNKU', 'Pixie Moderno', '90° GRADUADO', 'FIO NAVALHA', 'Corte curto com foco em nuca batida e topo desfiado.')" class="bg-white p-3 rounded-2xl flex gap-4 cursor-pointer hover:shadow-md transition border border-pink-50">
                            <img src="https://img.youtube.com/vi/KpuAPqHyNKU/mqdefault.jpg" class="w-24 h-16 rounded-lg object-cover">
                            <div>
                                <h4 class="text-xs font-bold">Pixie Cut</h4>
                                <p class="text-[10px] text-gray-400">Ângulo: 90°</p>
                            </div>
                        </div>

                        <div onclick="updateVideo('Fgi-AILh6Es', 'Butterfly Cut (Borboleta)', '180° ELEVADO', 'FIO NAVALHA', 'Camadas altíssimas para volume e movimento extremo.')" class="bg-white p-3 rounded-2xl flex gap-4 cursor-pointer hover:shadow-md transition border border-pink-50">
                            <img src="https://img.youtube.com/vi/Fgi-AILh6Es/mqdefault.jpg" class="w-24 h-16 rounded-lg object-cover">
                            <div>
                                <h4 class="text-xs font-bold">Butterfly Cut</h4>
                                <p class="text-[10px] text-gray-400">Ângulo: 180°</p>
                            </div>
                        </div>

                        <div onclick="updateVideo('nPk5MwGktu8', 'Franja Torcida', 'TORÇÃO GEOMÉTRICA', 'FIO LASER', 'Técnica de torção para franjas sem marcações.')" class="bg-white p-3 rounded-2xl flex gap-4 cursor-pointer hover:shadow-md transition border border-pink-50">
                            <img src="https://img.youtube.com/vi/nPk5MwGktu8/mqdefault.jpg" class="w-24 h-16 rounded-lg object-cover">
                            <div>
                                <h4 class="text-xs font-bold">Franja Torcida</h4>
                                <p class="text-[10px] text-gray-400">Ângulo: Torção</p>
                            </div>
                        </div>

                        <div onclick="updateVideo('BngQhBm8v9c', 'Corte em Camadas Uniformes', '90° PERPENDICULAR', 'DENTADA', 'Distribuição de volume uniforme em todo o crânio.')" class="bg-white p-3 rounded-2xl flex gap-4 cursor-pointer hover:shadow-md transition border border-pink-50">
                            <img src="https://img.youtube.com/vi/BngQhBm8v9c/mqdefault.jpg" class="w-24 h-16 rounded-lg object-cover">
                            <div>
                                <h4 class="text-xs font-bold">Em Camadas</h4>
                                <p class="text-[10px] text-gray-400">Ângulo: 90°</p>
                            </div>
                        </div>

                        <div onclick="updateVideo('dplHNmCjMbY', 'Corte em V', 'DIAGONAL POSTERIOR', 'FIO LASER', 'Geometria longa com finalização pontiaguda.')" class="bg-white p-3 rounded-2xl flex gap-4 cursor-pointer hover:shadow-md transition border border-pink-50">
                            <img src="https://img.youtube.com/vi/dplHNmCjMbY/mqdefault.jpg" class="w-24 h-16 rounded-lg object-cover">
                            <div>
                                <h4 class="text-xs font-bold">Corte em V</h4>
                                <p class="text-[10px] text-gray-400">Ângulo: Diagonal</p>
                            </div>
                        </div>

                    </div>
                </div>
            </div>
        </section>

        <!-- ABA 2: CATALOGO 50+ -->
        <section id="section-catalogo" class="hidden">
            <div class="mb-10 flex justify-between items-end">
                <div>
                    <h2 class="text-4xl font-serif gold-text">Catálogo de Tendências</h2>
                    <p class="text-gray-400 text-sm">Mais de 50 referências para sua cliente</p>
                </div>
                <div class="flex gap-2">
                    <button class="bg-white border border-pink-200 px-4 py-1 rounded-full text-[10px] font-bold">CURTOS</button>
                    <button class="bg-white border border-pink-200 px-4 py-1 rounded-full text-[10px] font-bold">MÉDIOS</button>
                    <button class="bg-white border border-pink-200 px-4 py-1 rounded-full text-[10px] font-bold">LONGOS</button>
                </div>
            </div>

            <div id="grid-catalogo" class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-6 gap-4">
                <!-- Gerado por JS -->
            </div>
        </section>

        <!-- ABA 3: TÉCNICA E ÂNGULOS -->
        <section id="section-tecnica" class="hidden">
            <div class="grid grid-cols-1 md:grid-cols-2 gap-10 items-center">
                <div class="bg-white p-10 rounded-[40px] border-2 border-dashed border-pink-200">
                    <h3 class="text-3xl font-serif mb-6 gold-text">Diagrama de Projeção</h3>
                    <div class="space-y-6">
                        <div class="flex items-start gap-4">
                            <div class="w-12 h-12 rounded-full bg-gold-gradient text-white flex items-center justify-center font-bold shrink-0">0°</div>
                            <div>
                                <h4 class="font-bold text-sm">Linha de Peso (Massa)</h4>
                                <p class="text-xs text-gray-500">Queda natural. Cria bases sólidas e fios inteiros.</p>
                            </div>
                        </div>
                        <div class="flex items-start gap-4">
                            <div class="w-12 h-12 rounded-full bg-gold-gradient text-white flex items-center justify-center font-bold shrink-0">45°</div>
                            <div>
                                <h4 class="font-bold text-sm">Graduação (Volume Inferior)</h4>
                                <p class="text-xs text-gray-500">Cria empilhamento de fios. Ideal para Chanel e Bobs.</p>
                            </div>
                        </div>
                        <div class="flex items-start gap-4">
                            <div class="w-12 h-12 rounded-full bg-gold-gradient text-white flex items-center justify-center font-bold shrink-0">90°</div>
                            <div>
                                <h4 class="font-bold text-sm">Camadas Uniformes</h4>
                                <p class="text-xs text-gray-500">Remove peso. O fio é cortado perpendicularmente ao crânio.</p>
                            </div>
                        </div>
                        <div class="flex items-start gap-4">
                            <div class="w-12 h-12 rounded-full bg-gold-gradient text-white flex items-center justify-center font-bold shrink-0">180°</div>
                            <div>
                                <h4 class="font-bold text-sm">Camadas Altas</h4>
                                <p class="text-xs text-gray-500">Projeção total para o topo. Cria movimento extremo em fios longos.</p>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="relative flex justify-center">
                    <!-- Desenho Esquemático -->
                    <div class="w-80 h-80 rounded-full border-4 border-pink-100 flex items-center justify-center bg-white shadow-inner relative">
                        <div class="absolute inset-0 flex items-center justify-center opacity-10">
                            <img src="https://www.svgrepo.com/show/491500/woman-head.svg" class="w-60">
                        </div>
                        <div class="z-10 text-center">
                            <p class="gold-text font-serif text-2xl">Geometria VB</p>
                            <p class="text-[10px] uppercase font-bold text-gray-400">O Segredo do Caimento</p>
                        </div>
                        <!-- Linhas de Ângulo -->
                        <div class="absolute w-full h-px bg-gold-shine/30 rotate-0"></div>
                        <div class="absolute w-full h-px bg-gold-shine/30 rotate-45"></div>
                        <div class="absolute w-full h-px bg-gold-shine/30 rotate-90"></div>
                        <div class="absolute w-full h-px bg-gold-shine/30 -rotate-45"></div>
                    </div>
                </div>
            </div>

            <!-- Seção de Tesouras -->
            <div class="mt-20">
                <h3 class="text-center font-serif text-3xl mb-12 gold-text">Arsenal de Ferramentas</h3>
                <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                    <div class="bg-white p-6 rounded-3xl text-center border border-pink-50 shadow-sm">
                        <h4 class="font-bold text-gold-shine mb-2">Fio Laser</h4>
                        <p class="text-xs text-gray-500 italic">Precisão Absoluta</p>
                        <p class="mt-4 text-[11px] leading-relaxed">Ideal para bases retas e cortes geométricos onde o fio não pode "correr". Uso obrigatório em Long Bobs e Franjas retas.</p>
                    </div>
                    <div class="bg-white p-6 rounded-3xl text-center border border-pink-50 shadow-sm">
                        <h4 class="font-bold text-gold-shine mb-2">Fio Navalha</h4>
                        <p class="text-xs text-gray-500 italic">Movimento e Leveza</p>
                        <p class="mt-4 text-[11px] leading-relaxed">Permite desfiar e criar texturas suaves. Perfeita para Butterfly Cuts e Pixies que pedem pontas desconectadas.</p>
                    </div>
                    <div class="bg-white p-6 rounded-3xl text-center border border-pink-50 shadow-sm">
                        <h4 class="font-bold text-gold-shine mb-2">Tesoura Dentada</h4>
                        <p class="text-xs text-gray-500 italic">Controle de Volume</p>
                        <p class="mt-4 text-[11px] leading-relaxed">Utilizada para remover o "excesso" de massa capilar sem tirar o comprimento. Essencial para finalização de camadas.</p>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <footer class="py-20 text-center">
        <div class="gold-text text-4xl font-serif mb-2">VB</div>
        <p class="text-xs text-gray-400 uppercase tracking-widest">© 2026 Espaço Vanessa Braga Academy</p>
    </footer>

    <script>
        // Gerador de Catálogo 50+
        const grid = document.getElementById('grid-catalogo');
        const cortesNomes = ["Shaggy", "French Bob", "Wolf Cut", "Blunt Cut", "Tapered", "Mullet Lux", "U-Shape", "A-Line", "Bixie", "Mixie", "Curtain Bangs", "Frame Layer"];
        
        for(let i=1; i<=60; i++) {
            const nomeCorte = cortesNomes[Math.floor(Math.random() * cortesNomes.length)];
            const card = document.createElement('div');
            card.className = "cintilante bg-white p-2 rounded-2xl border border-pink-50 shadow-sm hover:scale-105 transition-all duration-500";
            card.innerHTML = `
                <div class="aspect-[3/4] rounded-xl overflow-hidden mb-2">
                    <img src="https://images.unsplash.com/photo-1595476108010-b4d1fbee0201?auto=format&fit=crop&w=300&q=80&sig=${i}" class="w-full h-full object-cover">
                </div>
                <h5 class="text-[10px] font-bold text-gray-700 truncate">${nomeCorte} VB-${i}</h5>
                <p class="text-[8px] text-gold-shine font-bold">PREMIUM STYLE</p>
            `;
            grid.appendChild(card);
        }

        function switchTab(tab) {
            document.querySelectorAll('main > section').forEach(s => s.classList.add('hidden'));
            document.getElementById(`section-${tab}`).classList.remove('hidden');
            
            document.querySelectorAll('nav button').forEach(b => b.classList.remove('nav-active', 'text-gold-shine'));
            document.querySelectorAll('nav button').forEach(b => b.classList.add('text-gray-400'));
            
            document.getElementById(`tab-${tab}`).classList.add('nav-active');
            document.getElementById(`tab-${tab}`).classList.remove('text-gray-400');
        }

        function updateVideo(id, title, angulo, tesoura, desc) {
            document.getElementById('mainPlayer').src = `https://www.youtube.com/embed/${id}?autoplay=1`;
            document.getElementById('mainTitle').innerText = title;
            document.getElementById('badgeAngulo').innerText = `ÂNGULO: ${angulo}`;
            document.getElementById('badgeTesoura').innerText = `TESOURA: ${tesoura}`;
            document.getElementById('mainDesc').innerText = desc;
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }
    </script>
</body>
</html>
                 
