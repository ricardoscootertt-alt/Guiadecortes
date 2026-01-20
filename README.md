<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Espaço Vanessa Braga - App de Cortes</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Montserrat:wght@300;400;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --gold-gradient: linear-gradient(45deg, #d4af37, #f7d794, #d4af37);
            --pink-soft: #fff5f7;
            --pink-accent: #db2777;
        }

        body {
            font-family: 'Montserrat', sans-serif;
            background-color: var(--pink-soft);
            color: #333;
            overflow-x: hidden;
        }

        .font-serif { font-family: 'Playfair Display', serif; }

        .gold-bg { background: var(--gold-gradient); }
        .gold-text {
            background: var(--gold-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .tab-content { display: none; }
        .tab-content.active { display: block; }

        .active-tab {
            color: var(--pink-accent);
            border-bottom: 3px solid var(--pink-accent);
        }

        /* Animação do Simulador */
        .head-svg {
            filter: drop-shadow(0 4px 6px rgba(0,0,0,0.1));
        }

        .projection-line {
            transform-origin: left center;
            transition: transform 0.3s ease-out;
        }

        .cintilante {
            background-size: 200% auto;
            animation: shine 3s linear infinite;
        }

        @keyframes shine {
            to { background-position: 200% center; }
        }

        input[type=range] {
            accent-color: var(--pink-accent);
        }

        .modal {
            display: none;
            background: rgba(0,0,0,0.7);
            backdrop-filter: blur(4px);
        }
        .modal.active { display: flex; }
    </style>
</head>
<body class="pb-24">

    <!-- Header -->
    <header class="gold-bg p-6 shadow-xl text-center sticky top-0 z-50">
        <h1 class="text-2xl font-serif font-bold text-white tracking-[0.2em] drop-shadow-lg uppercase">
            Espaço Vanessa Braga
        </h1>
        <p class="text-white/90 text-[10px] mt-1 uppercase tracking-widest font-semibold">Técnicas de Projeção e Visagismo</p>
    </header>

    <!-- Navigation -->
    <nav class="flex justify-around bg-white border-b border-pink-100 sticky top-[76px] z-40 shadow-sm">
        <button onclick="switchTab('catalog')" id="tab-catalog" class="py-4 px-4 flex flex-col items-center gap-1 active-tab">
            <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6.253v13m0-13C10.832 5.477 9.246 5 7.5 5S4.168 5.477 3 6.253v13C4.168 18.477 5.754 18 7.5 18s3.332.477 4.5 1.253m0-13C13.168 5.477 14.754 5 16.5 5c1.747 0 3.332.477 4.5 1.253v13C19.832 18.477 18.247 18 16.5 18c-1.746 0-3.332.477-4.5 1.253" /></svg>
            <span class="text-[9px] font-bold uppercase tracking-tighter">Catálogo</span>
        </button>
        <button onclick="switchTab('projection')" id="tab-projection" class="py-4 px-4 flex flex-col items-center gap-1 text-gray-400">
            <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 8V4m0 0h4M4 4l5 5m11-1V4m0 0h-4m4 0l-5 5M4 16v4m0 0h4m-4 0l5-5m11 5l-5-5m5 5v-4m0 4h-4" /></svg>
            <span class="text-[9px] font-bold uppercase tracking-tighter">Projeção</span>
        </button>
        <button onclick="switchTab('notes')" id="tab-notes" class="py-4 px-4 flex flex-col items-center gap-1 text-gray-400">
            <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2m-3 7h3m-3 4h3m-6-4h.01M9 16h.01" /></svg>
            <span class="text-[9px] font-bold uppercase tracking-tighter">Anotações</span>
        </button>
    </nav>

    <main class="p-5 max-w-md mx-auto">
        
        <!-- Tab: Catalog -->
        <section id="content-catalog" class="tab-content active space-y-4">
            <div class="relative mb-6">
                <input type="text" id="searchInput" onkeyup="filterCortes()" placeholder="Buscar entre +50 modelos..." class="w-full pl-12 pr-4 py-4 rounded-2xl border-2 border-pink-100 focus:border-pink-300 outline-none shadow-sm transition-all">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 absolute left-4 top-1/2 -translate-y-1/2 text-pink-300" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" /></svg>
            </div>
            
            <div id="cortesList" class="grid gap-3">
                <!-- Injetado via JS -->
            </div>
        </section>

        <!-- Tab: Projection -->
        <section id="content-projection" class="tab-content space-y-6">
            <div class="bg-white p-8 rounded-[2rem] shadow-xl border border-pink-50 flex flex-col items-center">
                <h3 class="gold-text font-serif text-xl font-bold mb-8">Simulador de Ângulos</h3>
                
                <div class="relative w-64 h-64 flex items-center justify-center bg-pink-50/50 rounded-full border-2 border-dashed border-pink-100">
                    <!-- Cabeça Humana Simplificada -->
                    <svg viewBox="0 0 100 100" class="w-48 h-48 head-svg text-pink-200 fill-current">
                        <circle cx="50" cy="45" r="28" />
                        <path d="M50 73 Q50 95 50 95" stroke="currentColor" stroke-width="2" fill="none"/>
                    </svg>
                    
                    <!-- Linha de Projeção -->
                    <div id="projLine" class="projection-line absolute w-32 h-1 bg-gradient-to-r from-pink-600 to-transparent left-1/2 top-[45%]" style="transform: rotate(-45deg);">
                        <div class="absolute -right-2 -top-2 w-5 h-5 bg-pink-600 rounded-full border-4 border-white shadow-md"></div>
                    </div>
                    
                    <div id="angleBadge" class="absolute top-4 right-4 bg-pink-600 text-white text-xs font-bold px-3 py-1 rounded-full shadow-lg">45°</div>
                </div>

                <input type="range" min="0" max="180" value="45" class="w-full mt-10" id="angleSlider" oninput="updateProjection(this.value)">
                
                <div class="flex justify-between w-full mt-4 text-[10px] font-bold text-gray-400 uppercase tracking-widest">
                    <span>Peso (0°)</span>
                    <span>Camadas (90°)</span>
                    <span>Elevação (180°)</span>
                </div>
            </div>

            <div id="angleInfo" class="bg-gradient-to-br from-pink-600 to-rose-700 p-6 rounded-3xl text-white shadow-lg">
                <h4 class="font-bold flex items-center gap-2 mb-2">
                    <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"/></svg>
                    Dica Técnica
                </h4>
                <p id="angleDescription" class="text-sm text-pink-100 leading-relaxed">Ângulo de 45 graus: Cria graduação média, removendo peso das pontas mas mantendo a estrutura da base.</p>
            </div>
        </section>

        <!-- Tab: Notes -->
        <section id="content-notes" class="tab-content">
            <div class="bg-white p-6 rounded-3xl shadow-xl border border-pink-100">
                <h3 class="text-xl font-bold text-gray-800 mb-4 flex items-center gap-2">
                    <span class="p-2 bg-pink-100 rounded-lg text-pink-600">
                        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M11 5H6a2 2 0 00-2 2v11a2 2 0 002 2h11a2 2 0 002-2v-5m-1.414-9.414a2 2 0 112.828 2.828L11.828 15H9v-2.828l8.586-8.586z"/></svg>
                    </span>
                    Ficha da Cliente
                </h3>
                <textarea id="clientNote" class="w-full h-64 p-5 rounded-2xl bg-pink-50/30 border border-pink-100 focus:ring-2 focus:ring-pink-300 outline-none text-gray-700 mb-4" placeholder="Nome:
Corte:
Ângulos:
Observações Técnicas..."></textarea>
                
                <button onclick="sendToWhatsApp()" class="w-full bg-[#25D366] hover:bg-[#128C7E] text-white font-bold py-5 rounded-2xl shadow-lg flex items-center justify-center gap-3 transition-all active:scale-95">
                    <svg class="w-6 h-6 fill-current" viewBox="0 0 24 24"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg>
                    ENVIAR AO WHATSAPP
                </button>
            </div>
        </section>
    </main>

    <!-- Modal de Detalhes -->
    <div id="corteModal" class="modal fixed inset-0 z-[60] p-4 items-end justify-center sm:items-center">
        <div class="bg-white w-full max-w-md rounded-t-[3rem] sm:rounded-[3rem] overflow-hidden shadow-2xl animate-in slide-in-from-bottom duration-300">
            <div class="h-1.5 w-12 bg-gray-200 mx-auto mt-4 rounded-full"></div>
            <div class="p-8">
                <div id="modalHeader" class="mb-6">
                    <!-- Injetado via JS -->
                </div>
                <div class="space-y-6" id="modalBody">
                    <!-- Injetado via JS -->
                </div>
                <button onclick="closeModal()" class="w-full mt-8 py-4 text-gray-400 font-bold text-[10px] uppercase tracking-[0.3em] border-t border-gray-100">
                    Fechar Painel
                </button>
            </div>
        </div>
    </div>

    <script>
        const WHATSAPP_NUMBER = "5584991514922";
        
        const categorias = {
            "Curtos": ["Pixie", "Buzz Cut", "Mixie", "Bixie", "Micro Bob", "French Bob", "Short Bob", "Garçonne", "Undercut Feminino", "Asimétrico Curto"],
            "Médios": ["Long Bob", "Shaggy Hair", "Clavicle Cut", "Wolf Cut", "Blunt Cut", "Curtain Bangs", "Chanel de Bico", "Hime Cut", "U-Cut", "Camadas Médias"],
            "Longos": ["Butterfly Cut", "V-Cut", "Corte em U Longo", "Camadas Longas", "Point Cutting", "Fio Reto", "Repicado Diagonal", "Double Long Bob", "Boho Chic", "Sereia"],
            "Franjas": ["Franja Torcida", "Baby Bangs", "Franja Lateral", "Bottleneck Bangs", "Franja Desfiada", "Sidecut", "Hair Contour", "Franja Cortina", "Wispy Bangs", "Bardot Bangs"]
        };

        const tecnicasExtras = [
            "Shullet", "Wolf Cut Curto", "Bowl Cut", "Pixie Repicado", "Long Bob Assimétrico", 
            "Camadas em Cascata", "Corte em V Desfiado", "Chanel Clássico", "Curtain Bangs Longo", "Micro Franja"
        ];

        const baseDetalhes = {
            "Long Bob": { scissors: "Fio Navalha (leveza) ou Laser (precisão)", angle: "0° base, 45° laterais", video: "https://youtu.be/eL0PmFM-C-w?si=Rp6p54MGCKFJFCsj" },
            "Pixie": { scissors: "Fio Laser e Desbaste", angle: "90° topo, 0° nuca", video: "https://youtu.be/H1yCl7E4u8g?si=ZtA6Dao29S4qcWMP" },
            "Butterfly Cut": { scissors: "Fio Navalha", angle: "135° a 180° (elevação alta)", video: "https://youtu.be/Bw7LEmx7eoQ?si=0H1IQbVyG1zisyrl" },
            "Franja Torcida": { scissors: "Fio Laser", angle: "0° com torção técnica", video: "https://youtube.com/shorts/MYKoEfkDKZs?si=pr5sLRbQlRgTZsMm" },
            "Corte em Camada": { scissors: "Fio Navalha ou Dentada", angle: "90° a 180°", video: "https://youtu.be/BngQhBm8v9c?si=CJVKufG1DtUzncmw" },
            "Corte V": { scissors: "Fio Laser", angle: "45° direção ao centro", video: "https://youtu.be/dxh5F4cpfVU?si=F44f4nZzVBw61vpd" }
        };

        let allCortes = [];

        // Inicializar dados
        function initData() {
            Object.entries(categorias).forEach(([cat, names]) => {
                names.forEach(name => {
                    allCortes.push({
                        name,
                        category: cat,
                        ...(baseDetalhes[name] || {
                            scissors: "Fio Laser para estrutura, Fio Navalha para acabamento",
                            angle: "Variação dinâmica conforme visagismo",
                            video: "#"
                        })
                    });
                });
            });
            // Adiciona extras para passar de 50
            tecnicasExtras.forEach(name => {
                allCortes.push({
                    name,
                    category: "Especial",
                    scissors: "Mix de Fio Laser e Navalha",
                    angle: "Multidimensional",
                    video: "#"
                });
            });
            renderList(allCortes);
        }

        function renderList(list) {
            const container = document.getElementById('cortesList');
            container.innerHTML = list.map(corte => `
                <div onclick="openModal('${corte.name}')" class="bg-white p-5 rounded-2xl shadow-sm border border-pink-50 flex items-center justify-between group active:scale-[0.98] transition-all cursor-pointer">
                    <div>
                        <h3 class="font-bold text-gray-700">${corte.name}</h3>
                        <span class="text-[10px] text-pink-500 font-extrabold uppercase tracking-widest">${corte.category}</span>
                    </div>
                    <div class="p-2 bg-pink-50 rounded-full text-pink-300 group-hover:text-pink-500 transition-colors">
                        <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"/></svg>
                    </div>
                </div>
            `).join('');
        }

        function filterCortes() {
            const query = document.getElementById('searchInput').value.toLowerCase();
            const filtered = allCortes.filter(c => c.name.toLowerCase().includes(query));
            renderList(filtered);
        }

        function switchTab(tabId) {
            document.querySelectorAll('.tab-content').forEach(c => c.classList.remove('active'));
            document.querySelectorAll('nav button').forEach(b => b.classList.remove('active-tab', 'text-pink-accent'));
            document.querySelectorAll('nav button').forEach(b => b.classList.add('text-gray-400'));
            
            document.getElementById(`content-${tabId}`).classList.add('active');
            document.getElementById(`tab-${tabId}`).classList.add('active-tab', 'text-pink-accent');
            document.getElementById(`tab-${tabId}`).classList.remove('text-gray-400');
        }

        function updateProjection(val) {
            document.getElementById('projLine').style.transform = `rotate(-${val}deg)`;
            document.getElementById('angleBadge').innerText = `${val}°`;
            
            let desc = "";
            if(val == 0) desc = "Ângulo de 0 graus: Cria linha de peso máxima. Ideal para bases retas e cortes sólidos.";
            else if(val <= 45) desc = "Ângulo de 45 graus: Cria graduação. Remove peso mantendo volume na base. Perfeito para Bobs.";
            else if(val <= 90) desc = "Ângulo de 90 graus: Camadas uniformes. Cria movimento e distribui o volume igualmente.";
            else desc = "Ângulo de 135-180 graus: Camadas altas e repicados intensos. Máxima leveza e redução de volume nas pontas.";
            
            document.getElementById('angleDescription').innerText = desc;
        }

        function openModal(name) {
            const corte = allCortes.find(c => c.name === name);
            if(!corte) return;

            document.getElementById('modalHeader').innerHTML = `
                <h2 class="text-3xl font-serif font-bold text-gray-800">${corte.name}</h2>
                <p class="text-pink-500 font-bold text-xs tracking-[0.2em] uppercase">${corte.category}</p>
            `;

            document.getElementById('modalBody').innerHTML = `
                <div class="flex gap-5 items-center p-4 bg-amber-50 rounded-2xl">
                    <div class="text-amber-600">
                        <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14.121 14.121L19 19m-7-7l7-7m-7 7l-2.879 2.879M12 12L9.121 9.121m0 5.758a3 3 0 11-4.243-4.243 3 3 0 014.243 4.243z"/></svg>
                    </div>
                    <div>
                        <h4 class="text-xs font-bold text-amber-800 uppercase">Tesoura Ideal</h4>
                        <p class="text-sm text-amber-900/70">${corte.scissors}</p>
                    </div>
                </div>

                <div class="flex gap-5 items-center p-4 bg-pink-50 rounded-2xl">
                    <div class="text-pink-600">
                        <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 7v10c0 2.21 3.582 4 8 4s8-1.79 8-4V7M4 7c0 2.21 3.582 4 8 4s8-1.79 8-4M4 7c0-2.21 3.582-4 8-4s8 1.79 8 4m0 5c0 2.21-3.582 4-8 4s-8-1.79-8-4"/></svg>
                    </div>
                    <div>
                        <h4 class="text-xs font-bold text-pink-800 uppercase">Projeção Base</h4>
                        <p class="text-sm text-pink-900/70">${corte.angle}</p>
                    </div>
                </div>

                <a href="${corte.video}" target="_blank" class="flex items-center justify-between p-5 bg-gradient-to-r from-pink-600 to-rose-600 text-white rounded-2xl font-bold shadow-lg transform transition-transform active:scale-95">
                    <span class="flex items-center gap-3">
                        <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg>
                        ASSISTIR TÉCNICA
                    </span>
                    <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7-7 7"/></svg>
                </a>
            `;

            document.getElementById('corteModal').classList.add('active');
        }

        function closeModal() {
            document.getElementById('corteModal').classList.remove('active');
        }

        function sendToWhatsApp() {
            const note = document.getElementById('clientNote').value;
            if(!note) {
                alert("Por favor, digite alguma anotação.");
                return;
            }
            const text = encodeURIComponent(`*Anotação Técnica - Espaço Vanessa Braga*\n\n${note}`);
            window.open(`https://wa.me/${WHATSAPP_NUMBER}?text=${text}`, '_blank');
        }

        // Fechar modal ao clicar fora
        window.onclick = function(event) {
            const modal = document.getElementById('corteModal');
            if (event.target == modal) closeModal();
        }

        initData();
    </script>
</body>
</html>
