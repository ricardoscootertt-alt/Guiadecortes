
<!DOCTYPE html>
<html lang="pt-PT">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Espaço Vanessa Braga - Cinema Mode</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --rose-lux: #fffbfc;
            --gold-gradient: linear-gradient(135deg, #bf953f 0%, #fcf6ba 45%, #b38728 70%, #fbf5b7 100%);
            --gold-solid: #b38728;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background-color: var(--rose-lux);
            margin: 0;
            overflow-x: hidden;
        }

        .gold-text {
            background: var(--gold-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-family: 'Playfair Display', serif;
        }

        /* Player Expansivo */
        .hero-video-section {
            width: 100%;
            background: #000;
            position: relative;
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
        }

        .video-wrapper {
            position: relative;
            padding-bottom: 56.25%; /* 16:9 */
            height: 0;
        }

        .video-wrapper iframe {
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
            border: none;
        }

        .info-panel {
            background: white;
            border-radius: 32px 32px 0 0;
            margin-top: -30px;
            position: relative;
            z-index: 20;
            padding: 30px 20px;
            border-top: 2px solid rgba(179, 135, 40, 0.2);
        }

        .tech-tag {
            background: var(--gold-gradient);
            color: #fff;
            font-weight: 800;
            padding: 6px 16px;
            border-radius: 50px;
            font-size: 10px;
            letter-spacing: 1px;
            box-shadow: 0 4px 10px rgba(179, 135, 40, 0.2);
        }

        .playlist-card {
            background: #fff;
            border: 1px solid #fceef3;
            border-radius: 20px;
            transition: all 0.3s ease;
        }

        .playlist-card.active {
            border: 1px solid var(--gold-solid);
            background: #fff9fb;
        }

        .custom-scroll::-webkit-scrollbar { height: 4px; }
        .custom-scroll::-webkit-scrollbar-thumb { background: var(--gold-solid); border-radius: 10px; }
        
        .cintilante-btn {
            background: var(--gold-gradient);
            transition: 0.3s;
        }
        .cintilante-btn:hover { filter: brightness(1.1); transform: scale(1.02); }
    </style>
</head>
<body>

    <!-- Header Compacto -->
    <header class="bg-white/95 backdrop-blur-md py-4 px-6 sticky top-0 z-50 flex justify-between items-center border-b border-pink-50">
        <div>
            <h1 class="text-xl md:text-2xl gold-text">Espaço Vanessa Braga</h1>
            <p class="text-[8px] tracking-[0.3em] uppercase text-pink-400 font-bold">Expert Academy</p>
        </div>
        <button onclick="window.scrollTo({top: document.body.scrollHeight, behavior: 'smooth'})" class="text-[10px] font-bold text-gold-solid border border-gold-solid px-3 py-1 rounded-full uppercase">Catálogo</button>
    </header>

    <!-- ÁREA DE VÍDEO GIGANTE -->
    <section class="hero-video-section">
        <div class="video-wrapper">
            <iframe id="mainPlayer" src="https://www.youtube.com/embed/eL0PmFM-C-w?rel=0&showinfo=0&autoplay=0" allowfullscreen></iframe>
        </div>
    </section>

    <!-- PAINEL DE INFORMAÇÕES TÉCNICAS -->
    <main class="info-panel">
        <div class="max-w-6xl mx-auto">
            
            <div class="flex flex-col lg:flex-row gap-10">
                
                <!-- Detalhes do Corte Atual -->
                <div class="lg:w-2/3">
                    <div class="flex flex-wrap gap-3 mb-6">
                        <span id="labelAngulo" class="tech-tag uppercase">ÂNGULO: 0° A 45°</span>
                        <span id="labelTesoura" class="bg-pink-100 text-pink-500 font-black text-[10px] px-4 py-1.5 rounded-full border border-pink-200 uppercase">TESOURA: FIO LASER</span>
                    </div>
                    
                    <h2 id="videoTitle" class="text-3xl font-serif text-gray-800 mb-4">Long Bob: Precisão e Caimento</h2>
                    <p id="videoDesc" class="text-gray-500 text-sm leading-relaxed mb-8">
                        Domine a técnica do corte médio mais desejado. Aprenda a controlar a tensão da mecha e a projeção correta para um bico frontal impecável sem marcas.
                    </p>
                    
                    <div class="grid grid-cols-1 sm:grid-cols-3 gap-4 mb-10">
                        <div class="p-4 bg-pink-50/50 rounded-2xl border border-pink-100">
                            <p class="text-[9px] font-bold text-gray-400 uppercase">Projeção</p>
                            <p class="text-xs font-bold text-gold-solid">Base Baixa</p>
                        </div>
                        <div class="p-4 bg-pink-50/50 rounded-2xl border border-pink-100">
                            <p class="text-[9px] font-bold text-gray-400 uppercase">Visagismo</p>
                            <p class="text-xs font-bold text-gold-solid">Rostos Ovais/Redondos</p>
                        </div>
                        <div class="p-4 bg-pink-50/50 rounded-2xl border border-pink-100">
                            <p class="text-[9px] font-bold text-gray-400 uppercase">Dificuldade</p>
                            <p class="text-xs font-bold text-gold-solid">Intermediário</p>
                        </div>
                    </div>
                </div>

                <!-- PLAYLIST VERTICAL INTEGRADA -->
                <div class="lg:w-1/3">
                    <h3 class="font-serif text-xl mb-6 flex items-center gap-2">
                        <span class="w-2 h-6 bg-gold-solid rounded-full"></span>
                        Próximas Aulas
                    </h3>
                    
                    <div class="space-y-3 max-h-[500px] overflow-y-auto pr-2 custom-scroll">
                        
                        <!-- Aula 1 -->
                        <div onclick="play('eL0PmFM-C-w', 'Long Bob: Precisão e Caimento', '0° A 45°', 'FIO LASER', 'Domine a técnica do corte médio mais desejado. Foco em tensão e bico frontal.', this)" class="playlist-card active p-3 flex gap-4 cursor-pointer">
                            <div class="w-20 h-14 rounded-lg overflow-hidden shrink-0">
                                <img src="https://img.youtube.com/vi/eL0PmFM-C-w/mqdefault.jpg" class="w-full h-full object-cover">
                            </div>
                            <div class="flex flex-col justify-center">
                                <h4 class="text-[11px] font-bold text-gray-800 uppercase">1. Long Bob</h4>
                                <span class="text-[9px] text-pink-400 font-bold italic">Técnica de Base</span>
                            </div>
                        </div>

                        <!-- Aula 2 -->
                        <div onclick="play('KpuAPqHyNKU', 'Pixie: Curto e Despojado', '90° GRADUADO', 'FIO NAVALHA', 'Corte curto com foco em nuca batida e textura superior.', this)" class="playlist-card p-3 flex gap-4 cursor-pointer">
                            <div class="w-20 h-14 rounded-lg overflow-hidden shrink-0">
                                <img src="https://img.youtube.com/vi/KpuAPqHyNKU/mqdefault.jpg" class="w-full h-full object-cover">
                            </div>
                            <div class="flex flex-col justify-center">
                                <h4 class="text-[11px] font-bold text-gray-800 uppercase">2. Pixie Cut</h4>
                                <span class="text-[9px] text-pink-400 font-bold italic">Texturização</span>
                            </div>
                        </div>

                        <!-- Aula 3 -->
                        <div onclick="play('Fgi-AILh6Es', 'Butterfly Cut: Movimento', '180° ELEVADO', 'FIO NAVALHA', 'Camadas altíssimas para volume e balanço extremo.', this)" class="playlist-card p-3 flex gap-4 cursor-pointer">
                            <div class="w-20 h-14 rounded-lg overflow-hidden shrink-0">
                                <img src="https://img.youtube.com/vi/Fgi-AILh6Es/mqdefault.jpg" class="w-full h-full object-cover">
                            </div>
                            <div class="flex flex-col justify-center">
                                <h4 class="text-[11px] font-bold text-gray-800 uppercase">3. Butterfly</h4>
                                <span class="text-[9px] text-pink-400 font-bold italic">Camadas Altas</span>
                            </div>
                        </div>

                        <!-- Aula 4 -->
                        <div onclick="play('nPk5MwGktu8', 'Franja Torcida: Sem Marcas', 'TORÇÃO GEOMÉTRICA', 'FIO LASER', 'Técnica de torção para franjas perfeitas com caimento natural.', this)" class="playlist-card p-3 flex gap-4 cursor-pointer">
                            <div class="w-20 h-14 rounded-lg overflow-hidden shrink-0">
                                <img src="https://img.youtube.com/vi/nPk5MwGktu8/mqdefault.jpg" class="w-full h-full object-cover">
                            </div>
                            <div class="flex flex-col justify-center">
                                <h4 class="text-[11px] font-bold text-gray-800 uppercase">4. Franja Luxo</h4>
                                <span class="text-[9px] text-pink-400 font-bold italic">Acabamento Frontal</span>
                            </div>
                        </div>

                    </div>
                </div>
            </div>

            <!-- SEÇÃO DE CATÁLOGO (ABAIXO) -->
            <div class="mt-20 pt-10 border-t border-pink-100">
                <h3 class="text-3xl font-serif text-center gold-text mb-10 italic">Inspirações para o seu Salão</h3>
                <div id="gridCatalogo" class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-6 gap-6">
                    <!-- Gerado via JS -->
                </div>
            </div>

        </div>
    </main>

    <footer class="bg-white py-12 text-center">
        <div class="gold-text text-3xl font-serif">VB</div>
        <p class="text-[9px] uppercase tracking-widest text-gray-400 mt-2">© 2026 Espaço Vanessa Braga</p>
    </footer>

    <script>
        function play(id, title, angulo, tesoura, desc, el) {
            // Atualiza Player
            document.getElementById('mainPlayer').src = `https://www.youtube.com/embed/${id}?autoplay=1&rel=0`;
            
            // Atualiza Textos
            document.getElementById('videoTitle').innerText = title;
            document.getElementById('videoDesc').innerText = desc;
            document.getElementById('labelAngulo').innerText = `ÂNGULO: ${angulo}`;
            document.getElementById('labelTesoura').innerText = `TESOURA: ${tesoura}`;
            
            // UI Active
            document.querySelectorAll('.playlist-card').forEach(card => card.classList.remove('active'));
            el.classList.add('active');
            
            // Scroll para o vídeo no mobile
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // Gerar 50+ cortes para o catálogo
        const grid = document.getElementById('gridCatalogo');
        const cortes = ["Shaggy", "French Bob", "Wolf Cut", "Blunt Cut", "Tapered", "U-Shape", "A-Line", "Bixie", "Mixie", "Curtain Bangs"];
        
        for(let i=1; i<=54; i++) {
            const nome = cortes[i % cortes.length];
            grid.innerHTML += `
                <div class="group cursor-pointer">
                    <div class="aspect-[3/4] rounded-2xl overflow-hidden shadow-sm border border-pink-50 relative">
                        <img src="https://images.unsplash.com/photo-1562322140-8baeececf3df?auto=format&fit=crop&w=300&q=80&sig=${i}" class="w-full h-full object-cover group-hover:scale-110 transition duration-700">
                        <div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent opacity-0 group-hover:opacity-100 transition-opacity flex items-end p-3">
                            <span class="text-[10px] text-white font-bold uppercase">${nome} Style</span>
                        </div>
                    </div>
                </div>
            `;
        }
    </script>
</body>
</html>
