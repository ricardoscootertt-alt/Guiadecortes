<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Espaço Vanessa Braga - Projeção de Cortes</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --rose-primary: #f8c8dc;
            --rose-dark: #e5a9c0;
            --gold-cintilante: linear-gradient(45deg, #bf953f, #fcf6ba, #b38728, #fbf5b7, #aa771c);
            --gold-text: #b38728;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background-color: #fff5f8;
            color: #4a4a4a;
        }

        .gold-gradient {
            background: var(--gold-cintilante);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .gold-border {
            border: 2px solid transparent;
            background-image: linear-gradient(#fff5f8, #fff5f8), var(--gold-cintilante);
            background-origin: border-box;
            background-clip: content-box, border-box;
        }

        .bg-gold-shine {
            background: var(--gold-cintilante);
        }

        .card-rose {
            background: white;
            border-radius: 15px;
            transition: transform 0.3s ease;
            box-shadow: 0 10px 15px -3px rgba(248, 200, 220, 0.5);
        }

        .card-rose:hover {
            transform: translateY(-5px);
        }

        .nav-link.active {
            border-bottom: 2px solid #b38728;
            font-weight: 600;
        }

        .angle-circle {
            width: 100px;
            height: 100px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            border: 3px solid #b38728;
            margin: 0 auto;
        }
    </style>
</head>
<body>

    <!-- Header -->
    <header class="bg-white shadow-sm sticky top-0 z-50">
        <div class="max-w-7xl mx-auto px-4 py-6 flex flex-col items-center">
            <h1 class="text-4xl font-bold gold-gradient font-serif mb-2" style="font-family: 'Playfair Display', serif;">
                Espaço Vanessa Braga
            </h1>
            <p class="text-xs uppercase tracking-widest text-pink-400">Excelência em Cortes & Visagismo</p>
        </div>
        <nav class="flex justify-center space-x-6 pb-4 text-sm overflow-x-auto px-4">
            <button onclick="showSection('home')" class="nav-link text-gray-600 hover:text-gold-text">Início</button>
            <button onclick="showSection('catalogo')" class="nav-link text-gray-600 hover:text-gold-text">Catálogo (50+)</button>
            <button onclick="showSection('tecnica')" class="nav-link text-gray-600 hover:text-gold-text">Projeção e Ângulos</button>
            <button onclick="showSection('ferramentas')" class="nav-link text-gray-600 hover:text-gold-text">Tesouras</button>
        </nav>
    </header>

    <main class="max-w-7xl mx-auto px-4 py-8">
        
        <!-- SECTION: HOME -->
        <section id="home" class="block animate-fade-in text-center">
            <div class="relative rounded-3xl overflow-hidden mb-8 h-80 flex items-center justify-center">
                <img src="https://images.unsplash.com/photo-1562322140-8baeececf3df?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80" alt="Salão de Luxo" class="absolute w-full h-full object-cover brightness-50">
                <div class="relative z-10 text-white p-6">
                    <h2 class="text-4xl font-bold mb-4">A Arte de Esculpir Fios</h2>
                    <p class="text-lg mb-6">Transforme-se com a técnica perfeita do Espaço Vanessa Braga.</p>
                    <button onclick="showSection('catalogo')" class="bg-gold-shine px-8 py-3 rounded-full text-white font-bold shadow-lg hover:scale-105 transition">Explorar Modelos</button>
                </div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <div class="card-rose p-6 border-t-4 border-pink-200">
                    <h3 class="font-bold text-pink-600 mb-2">Visagismo</h3>
                    <p class="text-sm">Análise facial para encontrar o corte que realça sua essência.</p>
                </div>
                <div class="card-rose p-6 border-t-4 border-pink-200">
                    <h3 class="font-bold text-pink-600 mb-2">Técnica Avançada</h3>
                    <p class="text-sm">Uso preciso de ângulos e projeções para caimento natural.</p>
                </div>
                <div class="card-rose p-6 border-t-4 border-pink-200">
                    <h3 class="font-bold text-pink-600 mb-2">Acabamento Premium</h3>
                    <p class="text-sm">Finalização com produtos de alta performance.</p>
                </div>
            </div>
        </section>

        <!-- SECTION: CATALOGO -->
        <section id="catalogo" class="hidden">
            <div class="flex justify-between items-center mb-8">
                <h2 class="text-3xl font-serif gold-text">Catálogo de Inspiração</h2>
                <div class="flex space-x-2">
                    <button onclick="filterCuts('todos')" class="bg-pink-100 px-3 py-1 rounded text-xs">Todos</button>
                    <button onclick="filterCuts('curto')" class="bg-pink-100 px-3 py-1 rounded text-xs">Curtos</button>
                    <button onclick="filterCuts('medio')" class="bg-pink-100 px-3 py-1 rounded text-xs">Médios</button>
                    <button onclick="filterCuts('longo')" class="bg-pink-100 px-3 py-1 rounded text-xs">Longos</button>
                </div>
            </div>
            
            <div id="grid-cortes" class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-5 gap-4">
                <!-- Gerado por JS -->
            </div>
        </section>

        <!-- SECTION: TECNICA (PROJEÇÃO E ANGULOS) -->
        <section id="tecnica" class="hidden">
            <h2 class="text-3xl font-serif gold-text mb-8 text-center">Projeções e Diagramação</h2>
            
            <div class="grid grid-cols-1 md:grid-cols-2 gap-12">
                <div class="space-y-8">
                    <div class="flex items-start gap-4">
                        <div class="angle-circle shrink-0 bg-white">0°</div>
                        <div>
                            <h4 class="font-bold text-lg">Forma Sólida (Base Reta)</h4>
                            <p class="text-sm text-gray-600">O cabelo é cortado em sua queda natural. Cria peso e linhas horizontais ou inclinadas definidas.</p>
                        </div>
                    </div>
                    <div class="flex items-start gap-4">
                        <div class="angle-circle shrink-0 bg-white">45°</div>
                        <div>
                            <h4 class="font-bold text-lg">Graduação (Chanel/Bob)</h4>
                            <p class="text-sm text-gray-600">Cria expansão de volume e sobreposição controlada. Ideal para nucas batidas e volume médio.</p>
                        </div>
                    </div>
                    <div class="flex items-start gap-4">
                        <div class="angle-circle shrink-0 bg-white">90°</div>
                        <div>
                            <h4 class="font-bold text-lg">Camadas Uniformes</h4>
                            <p class="text-sm text-gray-600">O cabelo é projetado perpendicularmente à cabeça. Remove peso e cria movimento uniforme.</p>
                        </div>
                    </div>
                    <div class="flex items-start gap-4">
                        <div class="angle-circle shrink-0 bg-white">180°</div>
                        <div>
                            <h4 class="font-bold text-lg">Camadas Aumentadas</h4>
                            <p class="text-sm text-gray-600">Projeção totalmente para o topo. Mantém o comprimento na base e cria camadas longas no topo.</p>
                        </div>
                    </div>
                </div>

                <div class="bg-white p-6 rounded-3xl gold-border flex flex-col items-center justify-center text-center">
                    <h3 class="text-xl font-bold mb-4">Esquema Técnico de Visagismo</h3>
                    <div class="w-full max-w-xs aspect-square border-2 border-dashed border-pink-300 rounded-full flex items-center justify-center relative mb-4">
                        <div class="absolute w-full h-px bg-pink-200"></div>
                        <div class="absolute h-full w-px bg-pink-200"></div>
                        <div class="z-10 bg-white p-4 rounded-full border border-gold-text">
                            <span class="text-xs font-bold">PONTO DE<br>EQUILÍBRIO</span>
                        </div>
                        <div class="absolute top-0 -translate-y-6 text-xs text-gold-text font-bold">180° TOP</div>
                        <div class="absolute right-0 translate-x-10 text-xs text-gold-text font-bold">90° LATERAL</div>
                        <div class="absolute bottom-0 translate-y-6 text-xs text-gold-text font-bold">0° QUEDA NATURAL</div>
                    </div>
                    <p class="text-xs italic text-gray-500">A angulação define onde o volume se concentra no rosto da cliente.</p>
                </div>
            </div>
        </section>

        <!-- SECTION: FERRAMENTAS -->
        <section id="ferramentas" class="hidden">
            <h2 class="text-3xl font-serif gold-text mb-8 text-center">O Poder da Ferramenta</h2>
            
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <!-- Tesoura Fio Laser -->
                <div class="card-rose p-8 text-center">
                    <div class="w-16 h-16 mx-auto mb-4 bg-pink-50 rounded-full flex items-center justify-center">
                        <svg viewBox="0 0 24 24" class="w-8 h-8 fill-gold-text"><path d="M19,3L13,9L15,11L21,5L19,3M11,11L3,19L5,21L13,13L11,11Z"/></svg>
                    </div>
                    <h3 class="text-xl font-bold text-gray-800 mb-2">Tesoura Fio Laser</h3>
                    <p class="text-sm text-gray-600 mb-4">Possui micro-serrilhas que "prendem" o cabelo na lâmina.</p>
                    <div class="bg-pink-50 p-3 rounded text-xs text-pink-700 font-bold">
                        USO: Cortes de base reta, cortes masculinos clássicos e finalizações de precisão absoluta.
                    </div>
                </div>

                <!-- Tesoura Fio Navalha -->
                <div class="card-rose p-8 text-center">
                    <div class="w-16 h-16 mx-auto mb-4 bg-pink-50 rounded-full flex items-center justify-center">
                        <svg viewBox="0 0 24 24" class="w-8 h-8 fill-gold-text"><path d="M17,2L14,5L16.5,7.5L19.5,4.5L17,2M10,9L3,16L5,18L12,11L10,9Z"/></svg>
                    </div>
                    <h3 class="text-xl font-bold text-gray-800 mb-2">Tesoura Fio Navalha</h3>
                    <p class="text-sm text-gray-600 mb-4">Lâminas polidas extremamente afiadas como uma navalha.</p>
                    <div class="bg-pink-50 p-3 rounded text-xs text-pink-700 font-bold">
                        USO: Desfiar, repicar, criar leveza, "slice" (deslizar) e tirar volume sem marcar as camadas.
                    </div>
                </div>

                <!-- Tesoura Dentada -->
                <div class="card-rose p-8 text-center">
                    <div class="w-16 h-16 mx-auto mb-4 bg-pink-50 rounded-full flex items-center justify-center">
                        <svg viewBox="0 0 24 24" class="w-8 h-8 fill-gold-text"><path d="M12,2L4,10L12,18L20,10L12,2Z"/></svg>
                    </div>
                    <h3 class="text-xl font-bold text-gray-800 mb-2">Tesoura Dentada/Estatística</h3>
                    <p class="text-sm text-gray-600 mb-4">Possui dentes em uma ou ambas as lâminas.</p>
                    <div class="bg-pink-50 p-3 rounded text-xs text-pink-700 font-bold">
                        USO: Texturização, remover volume em cabelos muito densos e suavizar marcas de transição.
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer class="mt-20 py-12 bg-white border-t border-pink-100 text-center">
        <p class="gold-text font-serif text-xl">Vanessa Braga</p>
        <p class="text-gray-400 text-xs mt-2 italic">A beleza está nos detalhes de cada ângulo.</p>
    </footer>

    <!-- Modal para Detalhes do Corte -->
    <div id="modal-corte" class="fixed inset-0 bg-black/80 hidden z-[100] flex items-center justify-center p-4">
        <div class="bg-white rounded-3xl max-w-lg w-full p-8 relative">
            <button onclick="closeModal()" class="absolute top-4 right-4 text-gray-400 hover:text-pink-500 text-2xl">&times;</button>
            <div id="modal-content"></div>
        </div>
    </div>

    <script>
        const cortes = [
            // CURTOS
            { id: 1, nome: "Pixie Moderno", cat: "curto", angulo: "90°", tesoura: "Fio Navalha", img: "https://images.unsplash.com/photo-1595476108010-b4d1f102b1b1?auto=format&fit=crop&w=400&q=80" },
            { id: 2, nome: "Buzz Cut Feminino", cat: "curto", angulo: "0°", tesoura: "Máquina/Fio Laser", img: "https://images.unsplash.com/photo-1505148230895-d9a7a67386fb?auto=format&fit=crop&w=400&q=80" },
            { id: 3, nome: "Short Bob", cat: "curto", angulo: "45°", tesoura: "Fio Laser", img: "https://images.unsplash.com/photo-1592139932924-633049755152?auto=format&fit=crop&w=400&q=80" },
            { id: 4, nome: "Nuca Batida", cat: "curto", angulo: "45° e 90°", tesoura: "Fio Navalha", img: "https://images.unsplash.com/photo-1552046122-03184de85e08?auto=format&fit=crop&w=400&q=80" },
            { id: 5, nome: "Undercut Artístico", cat: "curto", angulo: "Variado", tesoura: "Máquina", img: "https://images.unsplash.com/photo-1492106087820-71f1a00d2b11?auto=format&fit=crop&w=400&q=80" },
            
            // MÉDIOS
            { id: 6, nome: "Long Bob (Lob)", cat: "medio", angulo: "0° e 45°", tesoura: "Fio Laser", img: "https://images.unsplash.com/photo-1516914943479-89db7d9ae7f2?auto=format&fit=crop&w=400&q=80" },
            { id: 7, nome: "Shaggy Hair", cat: "medio", angulo: "90° e 180°", tesoura: "Fio Navalha", img: "https://images.unsplash.com/photo-1542438823-9993309a62ba?auto=format&fit=crop&w=400&q=80" },
            { id: 8, nome: "Blunt Cut Médio", cat: "medio", angulo: "0°", tesoura: "Fio Laser", img: "https://images.unsplash.com/photo-1580618672591-eb180b1a973f?auto=format&fit=crop&w=400&q=80" },
            { id: 9, nome: "Chanel de Bico", cat: "medio", angulo: "45°", tesoura: "Fio Laser", img: "https://images.unsplash.com/photo-1495385794356-15371f348c31?auto=format&fit=crop&w=400&q=80" },
            { id: 10, nome: "Médio Repicado", cat: "medio", angulo: "90°", tesoura: "Dentada (Finalização)", img: "https://images.unsplash.com/photo-1599351431202-1e0f0137899a?auto=format&fit=crop&w=400&q=80" },

            // LONGOS
            { id: 11, nome: "U-Shape Cut", cat: "longo", angulo: "0°", tesoura: "Fio Laser", img: "https://images.unsplash.com/photo-1560869713-7d0a29430863?auto=format&fit=crop&w=400&q=80" },
            { id: 12, nome: "V-Shape Cut", cat: "longo", angulo: "0°", tesoura: "Fio Laser", img: "https://images.unsplash.com/photo-1519699047748-de8e457a634e?auto=format&fit=crop&w=400&q=80" },
            { id: 13, nome: "Camadas Butterfly", cat: "longo", angulo: "180°", tesoura: "Fio Navalha", img: "https://images.unsplash.com/photo-1492106087820-71f1a00d2b11?auto=format&fit=crop&w=400&q=80" },
            { id: 14, nome: "Longo Reto", cat: "longo", angulo: "0°", tesoura: "Fio Laser", img: "https://images.unsplash.com/photo-1521590832167-7bcbfaa6381f?auto=format&fit=crop&w=400&q=80" },
            { id: 15, nome: "Longo com Franja", cat: "longo", angulo: "Variado", tesoura: "Fio Navalha", img: "https://images.unsplash.com/photo-1582095133179-bfd08e2fc6b3?auto=format&fit=crop&w=400&q=80" }
        ];

        // Adicionando mocks para chegar a 50 itens de forma dinâmica para demonstração
        for(let i=16; i<=55; i++) {
            const types = ["curto", "medio", "longo"];
            const type = types[Math.floor(Math.random()*3)];
            cortes.push({
                id: i,
                nome: `Variação de Corte ${i}`,
                cat: type,
                angulo: i % 2 === 0 ? "90°" : "180°",
                tesoura: i % 3 === 0 ? "Fio Navalha" : "Fio Laser",
                img: `https://images.unsplash.com/photo-1560869713-7d0a29430863?auto=format&fit=crop&w=400&q=80&sig=${i}`
            });
        }

        function showSection(id) {
            document.querySelectorAll('main > section').forEach(s => s.classList.add('hidden'));
            document.getElementById(id).classList.remove('hidden');
            
            // Update nav styles
            document.querySelectorAll('.nav-link').forEach(l => l.classList.remove('active'));
            event?.target?.classList?.add('active');
        }

        function renderCortes(list) {
            const grid = document.getElementById('grid-cortes');
            grid.innerHTML = '';
            list.forEach(corte => {
                const div = document.createElement('div');
                div.className = "card-rose p-2 cursor-pointer group";
                div.onclick = () => openModal(corte);
                div.innerHTML = `
                    <div class="relative aspect-square rounded-xl overflow-hidden mb-2">
                        <img src="${corte.img}" class="w-full h-full object-cover group-hover:scale-110 transition duration-500">
                        <div class="absolute bottom-0 left-0 right-0 bg-gradient-to-t from-pink-500/80 to-transparent p-2">
                            <span class="text-[10px] text-white font-bold uppercase">${corte.cat}</span>
                        </div>
                    </div>
                    <h4 class="text-xs font-bold text-gray-700 truncate">${corte.nome}</h4>
                `;
                grid.appendChild(div);
            });
        }

        function filterCuts(cat) {
            if(cat === 'todos') {
                renderCortes(cortes);
            } else {
                const filtered = cortes.filter(c => c.cat === cat);
                renderCortes(filtered);
            }
        }

        function openModal(corte) {
            const modal = document.getElementById('modal-corte');
            const content = document.getElementById('modal-content');
            content.innerHTML = `
                <div class="text-center">
                    <img src="${corte.img}" class="w-48 h-48 mx-auto rounded-full object-cover border-4 border-pink-100 mb-6">
                    <h3 class="text-2xl font-serif gold-text mb-4">${corte.nome}</h3>
                    
                    <div class="grid grid-cols-2 gap-4 mb-6">
                        <div class="bg-pink-50 p-4 rounded-2xl">
                            <p class="text-[10px] text-pink-400 uppercase font-bold">Ângulo de Corte</p>
                            <p class="text-lg font-bold text-gray-700">${corte.angulo}</p>
                        </div>
                        <div class="bg-pink-50 p-4 rounded-2xl">
                            <p class="text-[10px] text-pink-400 uppercase font-bold">Instrumento</p>
                            <p class="text-lg font-bold text-gray-700">${corte.tesoura}</p>
                        </div>
                    </div>

                    <div class="text-left space-y-3">
                        <h4 class="font-bold text-pink-600">Prescrição Técnica:</h4>
                        <p class="text-sm text-gray-600">Para o <strong>${corte.nome}</strong>, iniciamos com a diagramação em quadrantes. A projeção a ${corte.angulo} garante o caimento ideal para o tipo de rosto oval ou triangular.</p>
                        <p class="text-sm text-gray-600">A finalização com <strong>${corte.tesoura}</strong> permite que as pontas tenham ${corte.tesoura.includes('Navalha') ? 'desfiação e leveza' : 'selagem e precisão'}.</p>
                    </div>

                    <button onclick="closeModal()" class="mt-8 bg-gold-shine text-white px-10 py-2 rounded-full font-bold">Fechar Detalhes</button>
                </div>
            `;
            modal.classList.remove('hidden');
        }

        function closeModal() {
            document.getElementById('modal-corte').classList.add('hidden');
        }

        // Initialize
        window.onload = () => {
            renderCortes(cortes);
        };
    </script>
</body>
</html>
