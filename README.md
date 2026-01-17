<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Espaço Vanessa Braga - Masterclass</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --rose-bg: #fffafc;
            --gold-gradient: linear-gradient(135deg, #bf953f 0%, #fcf6ba 45%, #b38728 70%, #fbf5b7 100%);
            --gold-soft: #c5a059;
            --pink-accent: #f8c8dc;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background-color: var(--rose-bg);
            color: #3d3434;
        }

        .gold-title {
            background: var(--gold-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-family: 'Playfair Display', serif;
        }

        .video-card {
            background: white;
            border-radius: 24px;
            overflow: hidden;
            box-shadow: 0 15px 35px rgba(248, 200, 220, 0.3);
            border: 1px solid rgba(197, 160, 89, 0.2);
        }

        .player-wrapper {
            position: relative;
            padding-bottom: 56.25%;
            height: 0;
            background: #000;
        }

        .player-wrapper iframe {
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
        }

        .playlist-item {
            transition: all 0.3s ease;
            border-left: 4px solid transparent;
        }

        .playlist-item.active {
            background: #fff0f5;
            border-left-color: #b38728;
        }

        .gold-glow {
            box-shadow: 0 0 15px rgba(179, 135, 40, 0.2);
        }

        .btn-gold {
            background: var(--gold-gradient);
            color: #4a3b1d;
            font-weight: 700;
            letter-spacing: 1px;
            transition: 0.3s;
        }

        .btn-gold:hover {
            filter: brightness(1.1);
            transform: translateY(-2px);
        }
    </style>
</head>
<body class="pb-10">

    <!-- Navegação Superior -->
    <header class="bg-white/80 backdrop-blur-md sticky top-0 z-50 py-4 px-6 border-b border-pink-100">
        <div class="max-w-7xl mx-auto flex justify-between items-center">
            <div>
                <h1 class="text-2xl md:text-3xl gold-title">Espaço Vanessa Braga</h1>
                <p class="text-[9px] uppercase tracking-[0.3em] text-pink-400 font-bold">Expert Education</p>
            </div>
            <div class="hidden md:flex space-x-8 text-[11px] font-bold uppercase text-gray-400">
                <a href="#" class="text-gold-soft border-b-2 border-gold-soft pb-1">Masterclass</a>
                <a href="#" class="hover:text-pink-400 transition">Catálogo</a>
                <a href="#" class="hover:text-pink-400 transition">Técnicas</a>
            </div>
        </div>
    </header>

    <main class="max-w-7xl mx-auto px-4 md:px-6 mt-8">
        
        <div class="grid grid-cols-1 lg:grid-cols-12 gap-8">
            
            <!-- ÁREA DO VÍDEO (LADO ESQUERDO) -->
            <div class="lg:col-span-8">
                <div class="video-card gold-glow">
                    <div class="player-wrapper">
                        <iframe id="mainPlayer" src="https://www.youtube.com/embed/eL0PmFM-C-w" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
                    </div>
                    <div class="p-6 md:p-8">
                        <div class="flex flex-wrap gap-2 mb-4">
                            <span id="labelAngulo" class="bg-pink-50 text-pink-500 text-[10px] font-black px-3 py-1 rounded-full border border-pink-100 italic">ÂNGULO: 0° A 45°</span>
                            <span id="labelTesoura" class="bg-yellow-50 text-gold-soft text-[10px] font-black px-3 py-1 rounded-full border border-yellow-100">TESOURA: FIO LASER</span>
                        </div>
                        <h2 id="videoTitle" class="text-2xl md:text-3xl font-serif mb-4">Long Bob: Base e Projeção</h2>
                        <p id="videoDesc" class="text-gray-500 text-sm leading-relaxed max-w-2xl">
                            O Long Bob é um clássico atemporal. Nesta aula, Vanessa Braga demonstra como manter a simetria lateral enquanto cria o bico frontal característico usando projeção de base.
                        </p>
                        
                        <div class="mt-8 pt-6 border-t border-pink-50 flex items-center justify-between">
                            <div class="flex items-center gap-3">
                                <div class="w-10 h-10 rounded-full bg-gold-gradient p-0.5">
                                    <div class="w-full h-full rounded-full bg-white flex items-center justify-center font-serif font-bold text-gold-soft">VB</div>
                                </div>
                                <div>
                                    <p class="text-xs font-bold">Vanessa Braga</p>
                                    <p class="text-[10px] text-gray-400">Master Stylist</p>
                                </div>
                            </div>
                            <button class="btn-gold px-6 py-2 rounded-full text-[10px] uppercase">Anotações</button>
                        </div>
                    </div>
                </div>
            </div>

            <!-- PLAYLIST (LADO DIREITO) -->
            <div class="lg:col-span-4">
                <div class="bg-white rounded-[32px] p-6 shadow-xl border border-pink-50 h-full">
                    <h3 class="font-serif text-xl mb-6 text-gray-700">Módulos do Curso</h3>
                    
                    <div class="space-y-3 custom-scroll">
                        
                        <!-- Aula 1 -->
                        <div onclick="play('eL0PmFM-C-w', 'Long Bob: Base e Projeção', '0° A 45°', 'FIO LASER', 'O Long Bob é um clássico atemporal. Demonstração de simetria lateral e bico frontal.', this)" class="playlist-item active flex gap-4 p-3 rounded-2xl cursor-pointer hover:bg-pink-50">
                            <div class="w-20 h-14 bg-gray-100 rounded-lg overflow-hidden shrink-0">
                                <img src="https://img.youtube.com/vi/eL0PmFM-C-w/mqdefault.jpg" class="w-full h-full object-cover">
                            </div>
                            <div>
                                <h4 class="text-xs font-bold">1. Long Bob</h4>
                                <p class="text-[10px] text-gray-400 mt-1">12:45 min</p>
                            </div>
                        </div>

                        <!-- Aula 2 -->
                        <div onclick="play('KpuAPqHyNKU', 'Pixie Cut: Visagismo Curto', '90° GRADUADO', 'FIO NAVALHA', 'Aprenda a criar a nuca perfeita e o topo com movimento para rostos ovais e triangulares.', this)" class="playlist-item flex gap-4 p-3 rounded-2xl cursor-pointer hover:bg-pink-50">
                            <div class="w-20 h-14 bg-gray-100 rounded-lg overflow-hidden shrink-0">
                                <img src="https://img.youtube.com/vi/KpuAPqHyNKU/mqdefault.jpg" class="w-full h-full object-cover">
                            </div>
                            <div>
                                <h4 class="text-xs font-bold">2. Pixie Cut</h4>
                                <p class="text-[10px] text-gray-400 mt-1">15:20 min</p>
                            </div>
                        </div>

                        <!-- Aula 3 -->
                        <div onclick="play('Fgi-AILh6Es', 'Butterfly Cut: Camadas Borboleta', '180° ELEVADO', 'FIO NAVALHA', 'Técnica de camadas altas para máximo volume e balanço.', this)" class="playlist-item flex gap-4 p-3 rounded-2xl cursor-pointer hover:bg-pink-50">
                            <div class="w-20 h-14 bg-gray-100 rounded-lg overflow-hidden shrink-0">
                                <img src="https://img.youtube.com/vi/Fgi-AILh6Es/mqdefault.jpg" class="w-full h-full object-cover">
                            </div>
                            <div>
                                <h4 class="text-xs font-bold">3. Butterfly Cut</h4>
                                <p class="text-[10px] text-gray-400 mt-1">18:10 min</p>
                            </div>
                        </div>

                        <!-- Aula 4 -->
                        <div onclick="play('nPk5MwGktu8', 'Franja Torcida: O Pulo do Gato', 'TORÇÃO GEOMÉTRICA', 'FIO LASER', 'Como cortar a franja sem deixar marcas e com caimento natural para ambos os lados.', this)" class="playlist-item flex gap-4 p-3 rounded-2xl cursor-pointer hover:bg-pink-50">
                            <div class="w-20 h-14 bg-gray-100 rounded-lg overflow-hidden shrink-0">
                                <img src="https://img.youtube.com/vi/nPk5MwGktu8/mqdefault.jpg" class="w-full h-full object-cover">
                            </div>
                            <div>
                                <h4 class="text-xs font-bold">4. Franja Torcida</h4>
                                <p class="text-[10px] text-gray-400 mt-1">08:30 min</p>
                            </div>
                        </div>

                        <!-- Aula 5 -->
                        <div onclick="play('BngQhBm8v9c', 'Camadas Uniformes: Movimento', '90° PERPENDICULAR', 'DENTADA', 'Técnica para tirar o aspecto pesado do cabelo sem alterar o comprimento.', this)" class="playlist-item flex gap-4 p-3 rounded-2xl cursor-pointer hover:bg-pink-50">
                            <div class="w-20 h-14 bg-gray-100 rounded-lg overflow-hidden shrink-0">
                                <img src="https://img.youtube.com/vi/BngQhBm8v9c/mqdefault.jpg" class="w-full h-full object-cover">
                            </div>
                            <div>
                                <h4 class="text-xs font-bold">5. Corte em Camada</h4>
                                <p class="text-[10px] text-gray-400 mt-1">20:00 min</p>
                            </div>
                        </div>

                        <!-- Aula 6 -->
                        <div onclick="play('dplHNmCjMbY', 'Corte em V: Geometria Longa', 'DIAGONAL POSTERIOR', 'FIO LASER', 'A base em V clássica. Como evitar falhas nas laterais e manter a ponta centralizada.', this)" class="playlist-item flex gap-4 p-3 rounded-2xl cursor-pointer hover:bg-pink-50">
                            <div class="w-20 h-14 bg-gray-100 rounded-lg overflow-hidden shrink-0">
                                <img src="https://img.youtube.com/vi/dplHNmCjMbY/mqdefault.jpg" class="w-full h-full object-cover">
                            </div>
                            <div>
                                <h4 class="text-xs font-bold">6. Corte em V</h4>
                                <p class="text-[10px] text-gray-400 mt-1">14:15 min</p>
                            </div>
                        </div>

                    </div>
                    
                    <div class="mt-8 p-4 bg-gold-gradient rounded-2xl text-center">
                        <p class="text-[10px] font-bold text-white uppercase mb-1">Certificado VB</p>
                        <p class="text-[8px] text-white/80">Conclua todos os módulos para liberar seu certificado.</p>
                    </div>
                </div>
            </div>
        </div>
    </main>

    <script>
        function play(id, title, angulo, tesoura, desc, el) {
            // Atualiza Player
            document.getElementById('mainPlayer').src = `https://www.youtube.com/embed/${id}?autoplay=1`;
            
            // Atualiza Textos
            document.getElementById('videoTitle').innerText = title;
            document.getElementById('videoDesc').innerText = desc;
            document.getElementById('labelAngulo').innerText = `ÂNGULO: ${angulo}`;
            document.getElementById('labelTesoura').innerText = `TESOURA: ${tesoura}`;
            
            // Atualiza Playlist UI
            document.querySelectorAll('.playlist-item').forEach(item => item.classList.remove('active'));
            el.classList.add('active');
            
            // Scroll para o topo no mobile
            if(window.innerWidth < 1024) {
                window.scrollTo({ top: 0, behavior: 'smooth' });
            }
        }
    </script>
</body>
</html>
