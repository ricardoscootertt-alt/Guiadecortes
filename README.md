<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Espaço Vanessa Braga - Masterclass de Cortes</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --rose-bg: #fffcfd;
            --rose-light: #fdf2f7;
            --gold-gradient: linear-gradient(45deg, #bf953f, #fcf6ba, #b38728, #fbf5b7, #aa771c);
            --gold-shine: #d4af37;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background-color: var(--rose-bg);
            color: #4a3b3b;
        }

        .gold-text {
            background: var(--gold-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-weight: bold;
        }

        .gold-border {
            border: 2px solid transparent;
            background-image: linear-gradient(white, white), var(--gold-gradient);
            background-origin: border-box;
            background-clip: content-box, border-box;
        }

        .gold-btn {
            background: var(--gold-gradient);
            color: #4a3b3b;
            font-weight: 600;
            box-shadow: 0 4px 15px rgba(179, 135, 40, 0.3);
            transition: all 0.3s ease;
        }

        .gold-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(179, 135, 40, 0.5);
        }

        .video-wrapper {
            position: relative;
            padding-bottom: 56.25%;
            height: 0;
            overflow: hidden;
            border-radius: 24px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
        }

        .video-wrapper iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
        }

        .nav-link {
            position: relative;
            transition: color 0.3s;
        }

        .nav-link.active::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 100%;
            height: 2px;
            background: var(--gold-gradient);
        }

        .custom-scroll::-webkit-scrollbar {
            width: 5px;
        }
        .custom-scroll::-webkit-scrollbar-thumb {
            background: #f8c8dc;
            border-radius: 10px;
        }

        .shine-effect {
            position: relative;
            overflow: hidden;
        }
        .shine-effect::after {
            content: "";
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255,255,255,0.3), transparent);
            transform: rotate(45deg);
            transition: 0.5s;
        }
        .shine-effect:hover::after {
            left: 100%;
        }
    </style>
</head>
<body>

    <!-- Header -->
    <header class="bg-white/80 backdrop-blur-md sticky top-0 z-50 py-4 px-6 border-b border-pink-100">
        <div class="max-w-7xl mx-auto flex flex-col md:flex-row justify-between items-center">
            <div class="text-center md:text-left mb-4 md:mb-0">
                <h1 class="text-3xl font-serif gold-text" style="font-family: 'Playfair Display', serif;">Espaço Vanessa Braga</h1>
                <p class="text-[10px] tracking-widest uppercase text-pink-400 font-bold">Projeção • Ângulos • Visagismo</p>
            </div>
            <nav class="flex space-x-8 text-xs font-semibold uppercase tracking-tighter">
                <button onclick="showPage('videoaulas')" class="nav-link active" id="nav-videoaulas">Masterclass</button>
                <button onclick="showPage('catalogo')" class="nav-link" id="nav-catalogo">Catálogo 50+</button>
                <button onclick="showPage('tecnica')" class="nav-link" id="nav-tecnica">Ângulos</button>
            </nav>
        </div>
    </header>

    <main class="max-w-7xl mx-auto px-6 py-10">

        <!-- SEÇÃO: VIDEOAULAS (YOUTUBE LINKS) -->
        <section id="page-videoaulas" class="block">
            <div class="grid grid-cols-1 lg:grid-cols-3 gap-10">
                <!-- Player Principal -->
                <div class="lg:col-span-2">
                    <div class="video-wrapper gold-border p-1 bg-white">
                        <iframe id="main-iframe" src="https://www.youtube.com/embed/eL0PmFM-C-w" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                    </div>
                    <div class="mt-6">
                        <h2 id="current-video-title" class="text-3xl font-serif gold-text">Long Bob: Técnica de Precisão</h2>
                        <div class="flex gap-4 mt-4">
                            <span id="tag-angulo" class="bg-pink-100 text-pink-600 px-4 py-1 rounded-full text-xs font-bold">ÂNGULO: 0° e 45°</span>
                            <span id="tag-tesoura" class="bg-gold-light border border-gold-shine text-gold-shine px-4 py-1 rounded-full text-xs font-bold">TESOURA: Fio Laser</span>
                        </div>
                        <p id="video-desc" class="mt-4 text-gray-500 text-sm leading-relaxed">
                            Aprenda a projeção correta para o Long Bob, mantendo o peso na base e o bico frontal alongado.
                        </p>
                    </div>
                </div>

                <!-- Playlist de Aulas Envidadas -->
                <div class="bg-white rounded-3xl p-6 shadow-xl border border-pink-50">
                    <h3 class="font-bold text-lg mb-6 flex items-center gap-2">
                        <span class="text-pink-400">●</span> Conteúdo Programático
                    </h3>
                    <div class="space-y-4 max-h-[500px] overflow-y-auto custom-scroll pr-2">
                        
                        <!-- Aula 1 -->
                        <div onclick="changeVideo('eL0PmFM-C-w', 'Long Bob: Técnica de Precisão', '0° e 45°', 'Fio Laser', 'Ideal para quem busca elegância e modernidade com base reta e frente alongada.')" class="flex gap-4 cursor-pointer p-2 hover:bg-pink-50 rounded-xl transition group">
                            <div class="w-24 h-16 rounded-lg overflow-hidden shrink-0 border-2 border-transparent group-hover:border-gold-shine">
                                <img src="https://img.youtube.com/vi/eL0PmFM-C-w/0.jpg" class="w-full h-full object-cover">
                            </div>
                            <div>
                                <h4 class="text-xs font-bold group-hover:text-gold-shine">Long Bob</h4>
                                <p class="text-[10px] text-gray-400">Vanessa Braga Academy</p>
                            </div>
                        </div>

                        <!-- Aula 2 -->
                        <div onclick="changeVideo('KpuAPqHyNKU', 'Corte Pixie: Ousadia e Forma', '90° e Graduação', 'Fio Navalha', 'Corte curto focado em nuca batida e topo volumoso para visagismo moderno.')" class="flex gap-4 cursor-pointer p-2 hover:bg-pink-50 rounded-xl transition group">
                            <div class="w-24 h-16 rounded-lg overflow-hidden shrink-0 border-2 border-transparent group-hover:border-gold-shine">
                                <img src="https://img.youtube.com/vi/KpuAPqHyNKU/0.jpg" class="w-full h-full object-cover">
                            </div>
                            <div>
                                <h4 class="text-xs font-bold group-hover:text-gold-shine">Pixie Cut</h4>
                                <p class="text-[10px] text-gray-400">Técnicas Curtas</p>
                            </div>
                        </div>

                        <!-- Aula 3 -->
                        <div onclick="changeVideo('Fgi-AILh6Es', 'Butterfly Cut: O Corte Borboleta', '180° e 90°', 'Fio Navalha', 'Sucesso nas redes, focado em camadas altíssimas e muito movimento.')" class="flex gap-4 cursor-pointer p-2 hover:bg-pink-50 rounded-xl transition group">
                            <div class="w-24 h-16 rounded-lg overflow-hidden shrink-0 border-2 border-transparent group-hover:border-gold-shine">
                                <img src="https://img.youtube.com/vi/Fgi-AILh6Es/0.jpg" class="w-full h-full object-cover">
                            </div>
                            <div>
                                <h4 class="text-xs font-bold group-hover:text-gold-shine">Butterfly Cut</h4>
                                <p class="text-[10px] text-gray-400">Camadas Extremas</p>
                            </div>
                        </div>

                        <!-- Aula 4 -->
                        <div onclick="changeVideo('nPk5MwGtextured', 'Franja Torcida: O Segredo do Caimento', 'Torção de Ângulo', 'Fio Laser/Navalha', 'Técnica de torção para franjas perfeitas sem marcas.')" class="flex gap-4 cursor-pointer p-2 hover:bg-pink-50 rounded-xl transition group">
                            <div class="w-24 h-16 rounded-lg overflow-hidden shrink-0 border-2 border-transparent group-hover:border-gold-shine">
                                <img src="https://img.youtube.com/vi/nPk5MwGtextured/0.jpg" class="w-full h-full object-cover">
                            </div>
                            <div>
                                <h4 class="text-xs font-bold group-hover:text-gold-shine">Franja Torcida</h4>
                                <p class="text-[10px] text-gray-400">Visagismo Frontal</p>
                            </div>
                        </div>

                        <!-- Aula 5 -->
                        <div onclick="changeVideo('BngQhBm8v9c', 'Corte em Camadas Uniformes', '90° em todo o crânio', 'Fio Navalha', 'Remoção de peso e criação de balanço natural em cabelos médios e longos.')" class="flex gap-4 cursor-pointer p-2 hover:bg-pink-50 rounded-xl transition group">
                            <div class="w-24 h-16 rounded-lg overflow-hidden shrink-0 border-2 border-transparent group-hover:border-gold-shine">
                                <img src="https://img.youtube.com/vi/BngQhBm8v9c/0.jpg" class="w-full h-full object-cover">
                            </div>
                            <div>
                                <h4 class="text-xs font-bold group-hover:text-gold-shine">Corte em Camadas</h4>
                                <p class="text-[10px] text-gray-400">Movimento Total</p>
                            </div>
                        </div>

                        <!-- Aula 6 -->
                        <div onclick="changeVideo('dplHNmCjMbY', 'Corte em V: Ângulo de Encontro', 'Inclinado / Diagonal', 'Fio Laser', 'Como criar o formato V perfeito sem perder o comprimento nas laterais.')" class="flex gap-4 cursor-pointer p-2 hover:bg-pink-50 rounded-xl transition group">
                            <div class="w-24 h-16 rounded-lg overflow-hidden shrink-0 border-2 border-transparent group-hover:border-gold-shine">
                                <img src="https://img.youtube.com/vi/dplHNmCjMbY/0.jpg" class="w-full h-full object-cover">
                            </div>
                            <div>
                                <h4 class="text-xs font-bold group-hover:text-gold-shine">Corte V</h4>
                                <p class="text-[10px] text-gray-400">Geometria Longa</p>
                            </div>
                        </div>

                    </div>
                </div>
            </div>
        </section>

        <!-- SEÇÃO: CATALOGO -->
        <section id="page-catalogo" class="hidden">
            <div class="flex justify-between items-end mb-10">
                <div>
                    <h2 class="text-4xl font-serif gold-text">Inspiração VB</h2>
                    <p class="text-gray-400 text-sm">Explore mais de 50 variações exclusivas</p>
                </div>
                <div class="flex gap-2">
                    <button onclick="filterCuts('todos')" class="bg-white border border-pink-100 px-4 py-1 rounded-full text-[10px] font-bold hover:bg-pink-50">TODOS</button>
                    <button onclick="filterCuts('curto')" class="bg-white border border-pink-100 px-4 py-1 rounded-full text-[10px] font-bold hover:bg-pink-50">CURTOS</button>
                    <button onclick="filterCuts('longo')" class="bg-white border border-pink-100 px-4 py-1 rounded-full text-[10px] font-bold hover:bg-pink-50">LONGOS</button>
                </div>
            </div>
            
            <div id="grid-container" class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-6 gap-6">
                <!-- Dinâmico via JS -->
            </div>
        </section>

        <!-- SEÇÃO: TÉCNICA -->
        <section id="page-tecnica" class="hidden">
            <div class="max-w-4xl mx-auto">
                <div class="bg-white rounded-[40px] p-10 shadow-2xl gold-border relative">
                    <h2 class="text-3xl font-serif text-center mb-10 gold-text">Diagramação Técnica de Ângulos</h2>
                    
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-12">
                        <div class="space-y-8">
                            <div class="border-l-4 border-pink-200 pl-6">
                                <h4 class="text-gold-shine font-bold text-xl">0° - Sólido</h4>
                                <p class="text-sm text-gray-500">Corte na queda natural. Cria linhas de peso e bases retas (Blunt Cut).</p>
                            </div>
                            <div class="border-l-4 border-pink-200 pl-6">
                                <h4 class="text-gold-shine font-bold text-xl">45° - Graduado</h4>
                                <p class="text-sm text-gray-500">Cria volume médio. Essencial para Chanéis e Bobs clássicos.</p>
                            </div>
                            <div class="border-l-4 border-pink-200 pl-6">
                                <h4 class="text-gold-shine font-bold text-xl">90° - Camadas</h4>
                                <p class="text-sm text-gray-500">Remove peso sem perder o comprimento. Camadas uniformes.</p>
                            </div>
                            <div class="border-l-4 border-pink-200 pl-6">
                                <h4 class="text-gold-shine font-bold text-xl">180° - Longas</h4>
                                <p class="text-sm text-gray-500">Projeção para o topo. Camadas ativadas com base pesada.</p>
                            </div>
                        </div>
                        <div class="flex flex-col items-center justify-center">
                            <div class="w-64 h-64 rounded-full border-4 border-dashed border-pink-200 flex items-center justify-center relative bg-pink-50/30">
                                <div class="absolute w-full h-px bg-pink-200"></div>
                                <div class="absolute h-full w-px bg-pink-200"></div>
                                <div class="bg-white p-4 rounded-full shadow-lg z-10 border border-gold-shine">
                                    <span class="text-[10px] font-bold text-center block">FOCO<br>VB</span>
                                </div>
                                <!-- Ângulos em volta -->
                                <div class="absolute -top-6 font-bold gold-text">180°</div>
                                <div class="absolute -right-10 font-bold gold-text">90°</div>
                                <div class="absolute -bottom-6 font-bold gold-text">0°</div>
                                <div class="absolute -left-10 font-bold gold-text">90°</div>
                            </div>
                            <p class="mt-10 text-xs text-gray-400 italic">Cada grau determina o balanço final da fibra capilar.</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer class="mt-20 py-20 bg-white border-t border-pink-50 text-center">
        <div class="gold-text text-4xl font-serif mb-4">VB</div>
        <p class="text-gray-400 text-xs tracking-widest uppercase">Espaço Vanessa Braga • © 2024</p>
    </footer>

    <script>
        // Dados dos Cortes (50+)
        const cortes = [];
        const nomes = ["Butterfly", "Shaggy", "Blunt", "Pixie", "Bob", "Long Bob", "Camadas", "Corte V", "U-Shape", "French Bob"];
        
        for(let i=1; i<=60; i++) {
            const cat = i % 2 === 0 ? "curto" : "longo";
            const nomeBase = nomes[Math.floor(Math.random() * nomes.length)];
            cortes.push({
                id: i,
                nome: `${nomeBase} Estilo ${i}`,
                cat: cat,
                img: `https://images.unsplash.com/photo-1562322140-8baeececf3df?auto=format&fit=crop&w=400&q=80&sig=${i}`
            });
        }

        function showPage(id) {
            document.querySelectorAll('main > section').forEach(s => s.classList.add('hidden'));
            document.getElementById(`page-${id}`).classList.remove('hidden');
            
            document.querySelectorAll('.nav-link').forEach(l => l.classList.remove('active'));
            document.getElementById(`nav-${id}`).classList.add('active');
            window.scrollTo({top: 0, behavior: 'smooth'});
        }

        function changeVideo(id, title, angulo, tesoura, desc) {
            document.getElementById('main-iframe').src = `https://www.youtube.com/embed/${id}?autoplay=1`;
            document.getElementById('current-video-title').innerText = title;
            document.getElementById('tag-angulo').innerText = `ÂNGULO: ${angulo}`;
            document.getElementById('tag-tesoura').innerText = `TESOURA: ${tesoura}`;
            document.getElementById('video-desc').innerText = desc;
            window.scrollTo({top: 0, behavior: 'smooth'});
        }

        function renderCortes(list) {
            const container = document.getElementById('grid-container');
            container.innerHTML = '';
            list.forEach(c => {
                container.innerHTML += `
                    <div class="shine-effect bg-white p-2 rounded-2xl shadow-sm border border-pink-50 cursor-pointer group">
                        <div class="aspect-[3/4] overflow-hidden rounded-xl mb-2">
                            <img src="${c.img}" class="w-full h-full object-cover group-hover:scale-110 transition duration-700">
                        </div>
                        <h5 class="text-[10px] font-bold text-gray-600 truncate px-1">${c.nome}</h5>
                        <div class="flex justify-between items-center px-1 mt-1">
                            <span class="text-[8px] text-pink-300 font-bold uppercase">${c.cat}</span>
                            <span class="text-[8px] text-gold-shine">Ver Detalhes →</span>
                        </div>
                    </div>
                `;
            });
        }

        function filterCuts(cat) {
            if(cat === 'todos') renderCortes(cortes);
            else renderCortes(cortes.filter(c => c.cat === cat));
        }

        // Init
        window.onload = () => {
            renderCortes(cortes);
        };
    </script>
</body>
</html>
