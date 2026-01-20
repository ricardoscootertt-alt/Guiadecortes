import React, { useState, useMemo } from 'react';
import { 
  Scissors, 
  ChevronRight, 
  MessageCircle, 
  Layers, 
  Maximize2, 
  BookOpen, 
  PlayCircle,
  ClipboardList,
  Search,
  Info
} from 'lucide-react';

const App = () => {
  const [activeTab, setActiveTab] = useState('catalog');
  const [selectedCorte, setSelectedCorte] = useState(null);
  const [searchQuery, setSearchQuery] = useState('');
  const [note, setNote] = useState('');
  const [projectionAngle, setProjectionAngle] = useState(45);

  const WHATSAPP_NUMBER = "5584991514922";

  const categorias = {
    "Curtos": ["Pixie", "Buzz Cut", "Mixie", "Bixie", "Micro Bob", "French Bob", "Short Bob", "Garçonne", "Undercut Feminino", "Asimétrico Curto"],
    "Médios": ["Long Bob", "Shaggy Hair", "Clavicle Cut", "Wolf Cut", "Blunt Cut", "Curtain Bangs c/ Médio", "Chanel de Bico", "Hime Cut", "U-Cut", "Camadas Médias"],
    "Longos": ["Butterfly Cut", "V-Cut", "Corte em U Longo", "Camadas Longas", "Point Cutting Longo", "Fio Reto", "Repicado Diagonal", "Double Long Bob", "Boho Chic", "Sereia"],
    "Franjas & Detalhes": ["Franja Torcida", "Baby Bangs", "Franja Lateral", "Bottleneck Bangs", "Franja Desfiada", "Sidecut", "Hair Contour", "Franja Cortina", "Wispy Bangs", "Bardot Bangs"]
  };

  const detalhesTecnicos = {
    "Long Bob": { scissors: "Fio Navalha (para leveza) ou Laser (precisão na base)", angle: "0° na base, 45° nas laterais", video: "https://youtu.be/eL0PmFM-C-w" },
    "Pixie": { scissors: "Fio Laser e Tesoura de Desbaste", angle: "90° no topo, 0° na nuca", video: "https://youtu.be/KpuAPqHuNKU" },
    "Butterfly Cut": { scissors: "Fio Navalha para camadas fluidas", angle: "135° e 180° (elevação alta)", video: "https://youtu.be/Fgi-AILh6Es" },
    "Franja torcida": { scissors: "Fio Laser para corte seco e preciso", angle: "0° com torção técnica", video: "https://youtu.be/nPk5MwGhtm8" },
    "Corte em camada": { scissors: "Fio Navalha ou Dentada (pontas)", angle: "90° a 180° dependendo do volume", video: "https://youtu.be/BngQhBm8v9c" },
    "Corte V": { scissors: "Fio Laser (para definir o desenho)", angle: "45° em direção ao centro", video: "https://youtu.be/dplHNmCjMbY" }
  };

  // Gerador de lista mock para chegar a +50
  const allCortes = useMemo(() => {
    let list = [];
    Object.entries(categorias).forEach(([cat, names]) => {
      names.forEach(name => {
        list.push({
          name,
          category: cat,
          ...detalhesTecnicos[name] || { 
            scissors: "Fio Laser para estrutura, Fio Navalha para acabamento", 
            angle: "Variação entre 45° e 90°",
            video: "#"
          }
        });
      });
    });
    return list;
  }, []);

  const filteredCortes = allCortes.filter(c => 
    c.name.toLowerCase().includes(searchQuery.toLowerCase())
  );

  const sendWhatsApp = () => {
    const text = encodeURIComponent(`*Anotação Técnica - Espaço Vanessa Braga*\n\n${note}`);
    window.open(`https://wa.me/${WHATSAPP_NUMBER}?text=${text}`, '_blank');
  };

  const AngleVisualizer = () => (
    <div className="flex flex-col items-center justify-center p-6 bg-white rounded-2xl border-2 border-amber-100 shadow-inner">
      <div className="relative w-48 h-48 flex items-center justify-center">
        {/* Simulação de Cabeça (SVG) */}
        <svg viewBox="0 0 100 100" className="w-full h-full text-pink-200 fill-current">
          <circle cx="50" cy="40" r="25" />
          <path d="M50 65 Q50 90 50 90" stroke="currentColor" strokeWidth="2" />
        </svg>
        {/* Linha de Projeção */}
        <div 
          className="absolute w-32 h-1 bg-gradient-to-r from-amber-500 to-transparent origin-left transition-all duration-500"
          style={{ 
            transform: `rotate(${-projectionAngle}deg)`,
            left: '50%',
            top: '40%'
          }}
        />
        <div className="absolute top-0 right-0 bg-amber-500 text-white px-3 py-1 rounded-full text-xs font-bold">
          {projectionAngle}°
        </div>
      </div>
      <input 
        type="range" 
        min="0" 
        max="180" 
        value={projectionAngle} 
        onChange={(e) => setProjectionAngle(e.target.value)}
        className="w-full mt-8 accent-pink-500"
      />
      <div className="flex justify-between w-full mt-2 text-[10px] text-gray-400 font-bold">
        <span>0° (PESO)</span>
        <span>90° (CAMADAS)</span>
        <span>180° (REPICADO)</span>
      </div>
    </div>
  );

  return (
    <div className="min-h-screen bg-[#fff5f7] text-gray-800 font-sans pb-20">
      {/* Header */}
      <header className="bg-gradient-to-r from-[#d4af37] via-[#f7d794] to-[#d4af37] p-6 shadow-lg text-center">
        <h1 className="text-2xl font-serif font-bold text-white tracking-widest drop-shadow-md">
          ESPAÇO VANESSA BRAGA
        </h1>
        <p className="text-white/90 text-xs mt-1 uppercase tracking-tighter italic">Expert em Visagismo e Ângulos de Corte</p>
      </header>

      {/* Tabs */}
      <nav className="flex justify-around bg-white border-b border-pink-100 sticky top-0 z-10">
        <button 
          onClick={() => setActiveTab('catalog')}
          className={`py-4 px-2 flex flex-col items-center gap-1 transition-all ${activeTab === 'catalog' ? 'text-pink-600 border-b-2 border-pink-600' : 'text-gray-400'}`}
        >
          <BookOpen size={20} />
          <span className="text-[10px] font-bold uppercase">Catálogo</span>
        </button>
        <button 
          onClick={() => setActiveTab('tools')}
          className={`py-4 px-2 flex flex-col items-center gap-1 transition-all ${activeTab === 'tools' ? 'text-pink-600 border-b-2 border-pink-600' : 'text-gray-400'}`}
        >
          <Maximize2 size={20} />
          <span className="text-[10px] font-bold uppercase">Projeção</span>
        </button>
        <button 
          onClick={() => setActiveTab('notes')}
          className={`py-4 px-2 flex flex-col items-center gap-1 transition-all ${activeTab === 'notes' ? 'text-pink-600 border-b-2 border-pink-600' : 'text-gray-400'}`}
        >
          <ClipboardList size={20} />
          <span className="text-[10px] font-bold uppercase">Notas</span>
        </button>
      </nav>

      <main className="p-4 max-w-md mx-auto">
        {activeTab === 'catalog' && (
          <div className="space-y-6">
            <div className="relative">
              <Search className="absolute left-3 top-1/2 -translate-y-1/2 text-gray-400" size={18} />
              <input 
                type="text"
                placeholder="Buscar entre +50 modelos..."
                className="w-full pl-10 pr-4 py-3 rounded-xl border-2 border-pink-100 focus:outline-none focus:border-pink-300 bg-white"
                value={searchQuery}
                onChange={(e) => setSearchQuery(e.target.value)}
              />
            </div>

            {filteredCortes.length > 0 ? (
              <div className="grid grid-cols-1 gap-3">
                {filteredCortes.map((corte, idx) => (
                  <div 
                    key={idx}
                    onClick={() => setSelectedCorte(corte)}
                    className="bg-white p-4 rounded-xl shadow-sm border border-pink-50 flex items-center justify-between group active:scale-95 transition-all cursor-pointer"
                  >
                    <div>
                      <h3 className="font-bold text-gray-700">{corte.name}</h3>
                      <span className="text-[10px] text-pink-500 font-bold uppercase tracking-wider">{corte.category}</span>
                    </div>
                    <ChevronRight className="text-pink-200 group-hover:text-pink-500" size={20} />
                  </div>
                ))}
              </div>
            ) : (
              <div className="text-center py-10 text-gray-400 italic">Nenhum corte encontrado.</div>
            )}
          </div>
        )}

        {activeTab === 'tools' && (
          <div className="space-y-6">
            <div className="bg-gradient-to-br from-pink-500 to-rose-600 p-6 rounded-3xl text-white">
              <h2 className="text-xl font-bold flex items-center gap-2">
                <Maximize2 size={24} /> Simulador de Ângulo
              </h2>
              <p className="text-pink-100 text-sm mt-1">Ajuste a projeção para definir o efeito do corte.</p>
            </div>
            
            <AngleVisualizer />

            <div className="grid grid-cols-2 gap-4">
              <div className="bg-white p-4 rounded-2xl shadow-sm border border-pink-100">
                <span className="text-[10px] font-bold text-pink-400 uppercase">Efeito</span>
                <p className="text-sm font-medium mt-1">
                  {projectionAngle < 45 ? "Peso e Linha Sólida" : projectionAngle < 90 ? "Camadas Leves" : "Volume e Movimento"}
                </p>
              </div>
              <div className="bg-white p-4 rounded-2xl shadow-sm border border-pink-100">
                <span className="text-[10px] font-bold text-pink-400 uppercase">Sugestão</span>
                <p className="text-sm font-medium mt-1">
                  {projectionAngle == 0 ? "Fio Laser" : "Fio Navalha"}
                </p>
              </div>
            </div>
          </div>
        )}

        {activeTab === 'notes' && (
          <div className="space-y-4">
             <div className="bg-white p-6 rounded-3xl shadow-sm border-2 border-pink-100">
              <h2 className="text-xl font-bold text-gray-700 flex items-center gap-2 mb-4">
                <ClipboardList className="text-pink-500" /> Ficha Técnica
              </h2>
              <textarea 
                className="w-full h-48 p-4 rounded-xl bg-pink-50/30 border border-pink-100 focus:outline-none focus:ring-2 ring-pink-200 resize-none text-gray-700"
                placeholder="Ex: Cliente Maria, Corte Long Bob, Base 0°, Camadas 45°, Tesoura Fio Navalha..."
                value={note}
                onChange={(e) => setNote(e.target.value)}
              />
              <button 
                onClick={sendWhatsApp}
                className="w-full mt-4 bg-green-500 hover:bg-green-600 text-white font-bold py-4 rounded-xl flex items-center justify-center gap-2 transition-all shadow-lg active:scale-95"
              >
                <MessageCircle size={20} />
                ENVIAR PARA WHATSAPP
              </button>
            </div>
          </div>
        )}
      </main>

      {/* Modal de Detalhes do Corte */}
      {selectedCorte && (
        <div className="fixed inset-0 bg-black/60 backdrop-blur-sm z-50 flex items-end sm:items-center justify-center p-4">
          <div className="bg-white w-full max-w-md rounded-t-[3rem] sm:rounded-[3rem] overflow-hidden shadow-2xl animate-in slide-in-from-bottom duration-300">
            <div className="h-2 w-12 bg-gray-200 mx-auto mt-4 rounded-full mb-2" />
            <div className="p-8">
              <div className="flex justify-between items-start mb-6">
                <div>
                  <h2 className="text-3xl font-serif font-bold text-gray-800">{selectedCorte.name}</h2>
                  <p className="text-pink-500 font-bold text-sm tracking-widest uppercase">{selectedCorte.category}</p>
                </div>
                <button onClick={() => setSelectedCorte(null)} className="p-2 bg-pink-50 rounded-full text-pink-400">
                  <Scissors size={20} />
                </button>
              </div>

              <div className="space-y-6">
                <div className="flex gap-4 items-start">
                  <div className="p-3 bg-amber-50 rounded-2xl text-amber-600">
                    <Scissors size={24} />
                  </div>
                  <div>
                    <h4 className="font-bold text-gray-700">Tesoura Recomendada</h4>
                    <p className="text-sm text-gray-500">{selectedCorte.scissors}</p>
                  </div>
                </div>

                <div className="flex gap-4 items-start">
                  <div className="p-3 bg-pink-50 rounded-2xl text-pink-600">
                    <Layers size={24} />
                  </div>
                  <div>
                    <h4 className="font-bold text-gray-700">Projeção Técnica</h4>
                    <p className="text-sm text-gray-500">{selectedCorte.angle}</p>
                  </div>
                </div>

                <a 
                  href={selectedCorte.video} 
                  target="_blank" 
                  className="flex items-center justify-between p-4 bg-gradient-to-r from-pink-500 to-rose-500 text-white rounded-2xl font-bold shadow-md hover:shadow-pink-200 transition-all active:scale-95"
                >
                  <div className="flex items-center gap-3">
                    <PlayCircle size={24} />
                    ASSISTIR PASSO A PASSO
                  </div>
                  <ChevronRight size={20} />
                </a>
              </div>
              
              <button 
                onClick={() => setSelectedCorte(null)}
                className="w-full mt-8 py-4 text-gray-400 font-bold text-xs uppercase tracking-widest border-t border-gray-100"
              >
                Fechar Detalhes
              </button>
            </div>
          </div>
        </div>
      )}

      {/* Decorative floating elements */}
      <div className="fixed -bottom-10 -right-10 w-40 h-40 bg-amber-200/20 rounded-full blur-3xl pointer-events-none" />
      <div className="fixed -top-10 -left-10 w-40 h-40 bg-pink-300/20 rounded-full blur-3xl pointer-events-none" />
    </div>
  );
};

export default App;
