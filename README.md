<!DOCTYPE html>
<html lang="pt-PT">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Espaço Vanessa Braga - Academy</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Poppins:wght@300;400;500;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --rose-lux: #fff5f8;
            --gold-gradient: linear-gradient(135deg, #bf953f 0%, #fcf6ba 45%, #b38728 70%, #fbf5b7 100%);
            --gold-solid: #b38728;
            --pink-soft: #fce4ec;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background-color: var(--rose-lux);
            color: #443333;
        }

        .font-serif { font-family: 'Playfair Display', serif; }

        .gold-text {
            background: var(--gold-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .gold-shine {
            background: var(--gold-gradient);
            position: relative;
            overflow: hidden;
        }

        .gold-shine::after {
            content: '';
            position: absolute;
            top: -50%; left: -50%;
            width: 200%; height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255,255,255,0.3), transparent);
            transform: rotate(45deg);
            animation: shine 3s infinite;
        }

        @keyframes shine {
            0% { left: -100%; }
            100% { left: 100%; }
        }

        .video-viewport {
            width: 100%;
            background: #000;
            position: relative;
            box-shadow: 0 20px 50px rgba(0,0,0,0.2);
        }

        .video-aspect {
            position: relative;
            padding-bottom: 56.25%; /* 16:9 */
            height: 0;
        }

        .video-aspect iframe {
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
        }

        .card-lux {
            background: white;
            border-radius: 30px;
            border: 1px solid rgba(179, 135, 40, 0.1);
            box-shadow: 0 10px 30px rgba(248, 200, 220, 0.2);
        }

        .tag-tech {
            background: var(--gold-gradient);
            color: white;
            padding: 4px 12px;
            border-radius: 50px;
            font-size: 10px;
            font-weight: 700;
            text-transform: uppercase;
        }

        .custom-scroll::-webkit-scrollbar { width: 5px; }
        .custom-scroll::-webkit-scrollbar-thumb { background: var(--gold-solid); border-radius: 10px; }

        .btn-whatsapp {
            background: #25d366;
            color: white;
            transition: all 0.3s;
        }

        .btn-whatsapp:hover { transform: translateY(-3px); box-shadow: 0 5px 15px rgba(37, 211, 102, 0.4); }
    </style>
</head>
<body class="pb-10">

    <!-- Header Elegante -->
    <header class="bg-white/90 backdrop-blur-md py-6 px-8 sticky top-0 z-50 border-b border-pink-100 flex flex-col md:flex-row justify-between items-center gap-4">
        <div class="text-center md:text-left">
            <h1 class="text-2xl md:text-3xl font-serif gold-text tracking-tight">Espaço Vanessa Braga</h1>
            <p class="text-[10px] uppercase tracking-[0.4em] font-bold text-pink-400">Academy & High Performance</p>
        </div>
        <div class="flex gap-4 overflow-x-auto w-full md:w-auto pb-2 md:pb-0">
            <button onclick="showSection('masterclass')" class="text-xs font-bold uppercase gold-text whitespace-nowrap px-4 border-b-2 border-gold-solid pb-1">Masterclass</button>
            <button onclick="showSection('tecnica')" class="text-xs font-bold uppercase text-gray-400 whitespace-nowrap px-4 pb-1 hover:text-gold-solid transition">Geometria</button>
            <button onclick="showSection('catalogo')" class="text-xs font-bold uppercase text-gray-400 whitespace-nowrap px-4 pb-1 hover:text-gold-solid transition">Cortes 50+</button>
        </div>
    </header>

    <!-- SECTION 1: MASTERCLASS -->
    <section id="section-masterclass" class="section-content animate-fade-in">
        <div class="video-viewport">
            <div class="video-aspect">
                <iframe id="mainPlayer" src="https://www.youtube.com/embed/eL0PmFM-C-w" allowfullscreen></iframe>
            </div>
        </div>

        <div class="max-w-7xl mx-auto px-4 mt-8 grid grid-cols-1 lg:grid-cols-12 gap-8">
            <!-- Detalhes Técnicos -->
            <div class="lg:col-span-8 card-lux p-8">
                <div class="flex flex-wrap gap-3 mb-6">
                    <span id="labelAngulo" class="tag-tech">ÂNGULO: 0° A 45°</span>
                    <span id="labelTesoura" class="bg-pink-100 text-pink-500 text-[10px] font-bold px-4 py-1.5 rounded-full uppercase border border-pink-200">TESOURA: FIO LASER</span>
                </div>
                
                <h2 id="videoTitle" class="text-3xl font-serif mb-4">Long Bob: Precisão Geométrica</h2>
                <p id="videoDesc" class="text-gray-500 text-sm leading-relaxed mb-8">
                    Aprenda a construir a base perfeita. O segredo deste corte está na projeção das mechas laterais e no controle do ângulo de elevação para evitar marcas na nuca.
                </p>

                <!-- Área de Anotações -->
                <div class="mt-8 p-6 bg-pink-50/50 rounded-2xl border border-pink-100">
                    <h4 class="font-bold text-sm mb-4 flex items-center gap-2">📝 Minhas Anotações Técnicas</h4>
                    <textarea id="userNotes" class="w-full bg-white border border-pink-100 rounded-xl p-4 text-sm focus:ring-2 focus:ring-gold-solid outline-none h-32" placeholder="Ex: Cliente com cabelo denso, usar menos tensão na nuca..."></textarea>
                    <button onclick="sendToWhatsApp()" class="mt-4 w-full btn-whatsapp py-3 rounded-xl font-bold flex items-center justify-center gap-2 text-sm">
                        ENVIAR PARA MEU WHATSAPP
                    </button>
                </div>
            </div>

            <!-- Playlist de Aulas -->
            <div class="lg:col-span-4 card-lux p-6">
                <h3 class="font-serif text-xl mb-6 gold-text">Módulos do Curso</h3>
                <div class="space-y-4 max-h-[500px] overflow-y-auto pr-2 custom-scroll">
                    <!-- Aula 1 -->
                    <div onclick="play('eL0PmFM-C-w', 'Long Bob Clássico', '0° A 45°', 'Fio Laser', 'Base reta com projeção frontal. Ideal para rostos ovais.')" class="flex gap-4 cursor-pointer p-2 hover:bg-pink-50 rounded-xl transition border border-transparent hover:border-pink-100">
                        <img src="https://img.youtube.com/vi/eL0PmFM-C-w/mqdefault.jpg" class="w-20 h-14 object-cover rounded-lg shadow-sm">
                        <div><h5 class="text-[11px] font-bold">Long Bob</h5><span class="text-[9px] text-gold-solid">Base & Projeção</span></div>
                    </div>
                    <!-- Aula 2 -->
                    <div onclick="play('KpuAPqHyNKU', 'Pixie: Curto Moderno', '90° GRADUADO', 'Fio Navalha', 'Nuca batida e topo com movimento desfiado.')" class="flex gap-4 cursor-pointer p-2 hover:bg-pink-50 rounded-xl transition border border-transparent hover:border-pink-100">
                        <img src="https://img.youtube.com/vi/KpuAPqHyNKU/mqdefault.jpg" class="w-20 h-14 object-cover rounded-lg shadow-sm">
                        <div><h5 class="text-[11px] font-bold">Pixie Cut</h5><span class="text-[9px] text-gold-solid">Graduação 90°</span></div>
                    </div>
                    <!-- Aula 3 -->
                    <div onclick="play('Fgi-AILh6Es', 'Butterfly Cut', '180° ELEVADO', 'Fio Navalha', 'Camadas borboleta com volume e balanço extremo.')" class="flex gap-4 cursor-pointer p-2 hover:bg-pink-50 rounded-xl transition border border-transparent hover:border-pink-100">
                        <img src="https://img.youtube.com/vi/Fgi-AILh6Es/mqdefault.jpg" class="w-20 h-14 object-cover rounded-lg shadow-sm">
                        <div><h5 class="text-[11px] font-bold">Butterfly</h5><span class="text-[9px] text-gold-solid">Camadas Altas</span></div>
                    </div>
                    <!-- Aula 4 -->
                    <div onclick="play('nPk5MwGktu8', 'Franja Torcida', 'TORÇÃO GEOMÉTRICA', 'Fio Laser', 'Técnica de torção para franjas sem degraus.')" class="flex gap-4 cursor-pointer p-2 hover:bg-pink-50 rounded-xl transition border border-transparent hover:border-pink-100">
                        <img src="https://img.youtube.com/vi/nPk5MwGktu8/mqdefault.jpg" class="w-20 h-14 object-cover rounded-lg shadow-sm">
                        <div><h5 class="text-[11px] font-bold">Franja de Luxo</h5><span class="text-[9px] text-gold-solid">Acabamento</span></div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- SECTION 2: GEOMETRIA E TÉCNICA -->
    <section id="section-tecnica" class="section-content hidden max-w-7xl mx-auto px-4 mt-10">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-10 items-center bg-white p-10 rounded-[40px] shadow-sm">
            <div>
                <h2 class="text-4xl font-serif gold-text mb-6">Guia de Projeção</h2>
                <p class="text-gray-500 text-sm mb-8">A precisão do corte feminino depende do domínio dos ângulos do crânio. Cada grau altera o volume e o caimento final.</p>
                
                <div class="space-y-6">
                    <div class="flex items-center gap-6 p-4 rounded-2xl hover:bg-pink-50 transition border border-transparent hover:border-pink-100">
                        <div class="w-12 h-12 rounded-full bg-gold-gradient text-white flex items-center justify-center font-bold">0°</div>
                        <div><h4 class="font-bold text-sm">Linha de Peso</h4><p class="text-xs text-gray-400">Cria bases sólidas. Tesoura ideal: <b>Fio Laser</b>.</p></div>
                    </div>
                    <div class="flex items-center gap-6 p-4 rounded-2xl hover:bg-pink-50 transition border border-transparent hover:border-pink-100">
                        <div class="w-12 h-12 rounded-full bg-gold-gradient text-white flex items-center justify-center font-bold">45°</div>
                        <div><h4 class="font-bold text-sm">Graduação</h4><p class="text-xs text-gray-400">Cria empilhamento. Tesoura ideal: <b>Fio Laser / Navalha</b>.</p></div>
                    </div>
                    <div class="flex items-center gap-6 p-4 rounded-2xl hover:bg-pink-50 transition border border-transparent hover:border-pink-100">
                        <div class="w-12 h-12 rounded-full bg-gold-gradient text-white flex items-center justify-center font-bold">90°</div>
                        <div><h4 class="font-bold text-sm">Camadas Uniformes</h4><p class="text-xs text-gray-400">Remove volume. Tesoura ideal: <b>Dentada / Navalha</b>.</p></div>
                    </div>
                    <div class="flex items-center gap-6 p-4 rounded-2xl hover:bg-pink-50 transition border border-transparent hover:border-pink-100">
                        <div class="w-12 h-12 rounded-full bg-gold-gradient text-white flex items-center justify-center font-bold">180°</div>
                        <div><h4 class="font-bold text-sm">Camadas Altas</h4><p class="text-xs text-gray-400">Movimento extremo. Tesoura ideal: <b>Fio Navalha</b>.</p></div>
                    </div>
                </div>
            </div>
            <div class="relative flex justify-center">
                <!-- Diagrama de Ângulo (SVG) -->
                <svg viewBox="0 0 200 200" class="w-80 h-80 drop-shadow-xl">
                    <circle cx="100" cy="100" r="80" fill="none" stroke="#f8c8dc" stroke-width="1" stroke-dasharray="4"/>
                    <!-- Linhas de Ângulo -->
                    <line x1="100" y1="100" x2="180" y2="100" stroke="#b38728" stroke-width="2" /> <!-- 0 -->
                    <line x1="100" y1="100" x2="156" y2="156" stroke="#b38728" stroke-width="2" /> <!-- 45 -->
                    <line x1="100" y1="100" x2="100" y2="180" stroke="#b38728" stroke-width="2" /> <!-- 90 -->
                    <circle cx="100" cy="100" r="5" fill="#b38728" />
                    <text x="110" y="95" class="text-[8px] fill-gray-400 font-bold">PROJEÇÃO TÉCNICA VB</text>
                </svg>
            </div>
        </div>
    </section>

    <!-- SECTION 3: CATÁLOGO 50+ CORTES -->
    <section id="section-catalogo" class="section-content hidden max-w-7xl mx-auto px-4 mt-10">
        <div class="text-center mb-12">
            <h2 class="text-4xl font-serif gold-text mb-2">Catálogo de Inspiração 2026</h2>
            <p class="text-xs text-gray-400 uppercase tracking-widest font-bold">Explore mais de 50 tendências exclusivas</p>
        </div>

        <div id="grid-catalogo" class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-6 gap-6">
            <!-- Gerado via JavaScript -->
        </div>
    </section>

    <!-- Footer -->
    <footer class="mt-20 py-10 text-center border-t border-pink-100">
        <div class="gold-text text-3xl font-serif mb-2">VB</div>
        <p class="text-[9px] uppercase tracking-widest text-gray-400">© 2026 Espaço Vanessa Braga. Desenvolvido para Experts.</p>
    </footer>

    <script>
        // Sistema de Troca de Seções
        function showSection(id) {
            document.querySelectorAll('.section-content').forEach(s => s.classList.add('hidden'));
            document.getElementById(`section-${id}`).classList.remove('hidden');
            
            // UI Update
            document.querySelectorAll('header button').forEach(b => {
                b.classList.remove('gold-text', 'border-gold-solid', 'border-b-2');
                b.classList.add('text-gray-400');
            });
            event.target.classList.add('gold-text', 'border-gold-solid', 'border-b-2');
            event.target.classList.remove('text-gray-400');
        }

        // Sistema de Player
        function play(id, title, angulo, tesoura, desc) {
            document.getElementById('mainPlayer').src = `https://www.youtube.com/embed/${id}?autoplay=1`;
            document.getElementById('videoTitle').innerText = title;
            document.getElementById('videoDesc').innerText = desc;
            document.getElementById('labelAngulo').innerText = `ÂNGULO: ${angulo}`;
            document.getElementById('labelTesoura').innerText = `TESOURA: ${tesoura}`;
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // WhatsApp Sender
        function sendToWhatsApp() {
            const notes = document.getElementById('userNotes').value;
            const title = document.getElementById('videoTitle').innerText;
            const phone = "5584991514922"; // Formato internacional
            
            if (!notes) {
                alert("Por favor, escreva alguma anotação antes de enviar.");
                return;
            }

            const message = encodeURIComponent(`*ANOTAÇÃO TÉCNICA - ESPAÇO VANESSA BRAGA*\n\n*Aula:* ${title}\n*Nota:* ${notes}`);
            window.open(`https://wa.me/${phone}?text=${message}`, '_blank');
        }

        // Gerador de Catálogo (54 itens)
        const grid = document.getElementById('grid-catalogo');
        const cortesData = [
            { n: "Pixie Cut", t: "Fio Navalha", a: "90°" },
            { n: "Long Bob", t: "Fio Laser", a: "45°" },
            { n: "Butterfly", t: "Fio Navalha", a: "180°" },
            { n: "French Bob", t: "Fio Laser", a: "0°" },
            { n: "Shaggy Hair", t: "Navalha", a: "90°" },
            { n: "Blunt Cut", t: "Fio Laser", a: "0°" },
            { n: "Camadas V", t: "Fio Laser", a: "Diagonal" },
            { n: "Wolf Cut", t: "Navalha", a: "90°" }
        ];

        for(let i=1; i<=54; i++) {
            const data = cortesData[i % cortesData.length];
            const card = document.createElement('div');
            card.className = "group cursor-pointer";
            card.innerHTML = `
                <div class="relative aspect-[3/4] rounded-2xl overflow-hidden shadow-sm border border-pink-50 mb-3">
                    <img src="https://images.unsplash.com/photo-1595476108010-b4d1fbee0201?auto=format&fit=crop&w=300&q=80&sig=${i}" class="w-full h-full object-cover group-hover:scale-110 transition duration-700">
                    <div class="absolute inset-0 bg-gradient-to-t from-black/70 via-transparent to-transparent opacity-0 group-hover:opacity-100 transition-opacity flex flex-col justify-end p-4">
                        <p class="text-white text-[8px] font-bold uppercase tracking-widest mb-1">Tesoura: ${data.t}</p>
                        <p class="text-white text-[8px] font-bold uppercase tracking-widest">Ângulo: ${data.a}</p>
                    </div>
                </div>
                <h5 class="text-[10px] font-bold text-center uppercase tracking-tighter">${data.n} VB-${i}</h5>
            `;
            grid.appendChild(card);
        }
    </script>
</body>
</html>
