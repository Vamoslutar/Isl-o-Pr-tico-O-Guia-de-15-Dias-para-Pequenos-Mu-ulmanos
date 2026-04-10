Segue o código HTML completo da landing page, com todas as animações, efeitos 3D e seções solicitadas.
```html
<!DOCTYPE html>
<html lang="pt">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
  <title>Ensinar o Islão em 15 dias | Método Aproximar seu Filho de Alá</title>
  <!-- Tailwind CSS + Google Fonts + Font Awesome -->
  <script src="https://cdn.tailwindcss.com"></script>
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,600;14..32,700;14..32,800&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    body {
      font-family: 'Inter', sans-serif;
      overflow-x: hidden;
      background: radial-gradient(circle at 10% 20%, #0a0f0a, #030503);
    }
    /* smooth scroll global */
    html {
      scroll-behavior: smooth;
    }
    /* parallax background container (mouse move effect) */
    .parallax-bg {
      position: fixed;
      top: 0;
      left: 0;
      width: 120%;
      height: 120%;
      background: radial-gradient(ellipse at 30% 40%, rgba(0,20,0,0.6), #000000),
                  repeating-linear-gradient(45deg, rgba(0,255,65,0.03) 0px, rgba(0,255,65,0.03) 2px, transparent 2px, transparent 8px);
      z-index: -2;
      pointer-events: none;
      transition: transform 0.08s ease-out;
      will-change: transform;
    }
    /* overlay extra para profundidade */
    .parallax-bg::after {
      content: '';
      position: absolute;
      inset: 0;
      background: radial-gradient(circle at 50% 50%, rgba(0,0,0,0.2), #000000 80%);
    }
    /* glassmorphism base */
    .glass-card {
      background: rgba(10, 20, 5, 0.45);
      backdrop-filter: blur(12px);
      border: 1px solid rgba(34, 197, 94, 0.3);
      box-shadow: 0 25px 40px -12px rgba(0,0,0,0.6), 0 0 15px rgba(34,197,94,0.2);
      border-radius: 2rem;
      transition: all 0.3s ease;
    }
    .glass-card:hover {
      border-color: rgba(34,197,94,0.7);
      box-shadow: 0 30px 45px -12px black, 0 0 25px rgba(34,197,94,0.4);
      transform: translateY(-5px);
    }
    /* fade-in animation for sections */
    .fade-section {
      opacity: 0;
      transform: translateY(30px);
      transition: opacity 0.7s cubic-bezier(0.2, 0.9, 0.4, 1.1), transform 0.7s ease;
    }
    .fade-section.visible {
      opacity: 1;
      transform: translateY(0);
    }
    /* pulse animation for top bar */
    @keyframes pulseSoft {
      0% { opacity: 0.9; text-shadow: 0 0 0px rgba(34,197,94,0.3);}
      100% { opacity: 1; text-shadow: 0 0 6px #22c55e, 0 0 3px #16a34a;}
    }
    .animate-pulse-custom {
      animation: pulseSoft 1.2s infinite alternate;
    }
    /* estrelas fixas */
    .stars-rating {
      color: #fbbf24;
      letter-spacing: 2px;
    }
    /* botao CTA glow 3d */
    .btn-3d {
      background: linear-gradient(95deg, #0f3b1a, #1e7a3a);
      box-shadow: 0 10px 20px -5px rgba(0,0,0,0.5), 0 0 12px #22c55e80;
      transition: all 0.2s;
    }
    .btn-3d:hover {
      transform: scale(1.02);
      box-shadow: 0 15px 25px -5px black, 0 0 20px #4ade80;
    }
    /* placeholder imagens efeito vidro */
    .img-placeholder {
      background: linear-gradient(135deg, #1f2a1b, #0c1309);
      border-radius: 2rem;
      box-shadow: 0 20px 35px -12px black, inset 0 1px 1px rgba(255,255,255,0.1);
      display: flex;
      align-items: center;
      justify-content: center;
      color: #b0f0b0;
      font-weight: 600;
      backdrop-filter: blur(4px);
    }
    .img-circle {
      background: radial-gradient(circle at 30% 30%, #2b3b22, #0f1a0c);
      box-shadow: 0 8px 20px rgba(0,0,0,0.4);
    }
    /* responsividade extra */
    @media (max-width: 768px) {
      .glass-card { border-radius: 1.5rem; }
    }
  </style>
</head>
<body class="text-white">

  <!-- Background parallax que reage ao movimento do rato -->
  <div class="parallax-bg" id="parallaxBg"></div>

  <!-- TOP BAR FIXO com animação pulse -->
  <div class="fixed top-0 left-0 w-full z-50 bg-gradient-to-r from-green-900 via-black to-green-800 py-3 px-4 shadow-2xl border-b border-green-500/40 animate-pulse-custom">
    <div class="container mx-auto text-center">
      <p class="text-white text-xs sm:text-sm md:text-base font-bold tracking-wide">
        <i class="fas fa-truck-fast mr-2 text-green-300"></i> BEM-VINDA/O! O PAGAMENTO É APENAS NA ENTREGA DO PRODUTO - HOJE É O ÚLTIMO DIA DA PROMOÇÃO!
      </p>
    </div>
  </div>

  <main class="pt-16 relative z-10">
    <div class="container mx-auto px-5 md:px-8 py-8 space-y-28 md:space-y-36">

      <!-- ========== SEÇÃO HERO ========== -->
      <section class="fade-section" id="hero">
        <div class="glass-card p-6 md:p-10">
          <!-- Badge -->
          <div class="inline-block bg-black/50 backdrop-blur-sm border border-green-500 rounded-full px-5 py-1.5 text-sm font-semibold text-green-300 mb-6 shadow-md">
            ✨ DESCUBRA O SEGREDO ✨
          </div>
          <div class="grid md:grid-cols-2 gap-12 items-center">
            <!-- Coluna 1: Imagem placeholder produto 3D -->
            <div class="img-placeholder w-full aspect-square md:aspect-[4/3] relative overflow-hidden group">
              <div class="absolute inset-0 bg-gradient-to-br from-green-800/30 to-transparent"></div>
              <i class="fas fa-book-quran text-7xl md:text-8xl text-green-400/80 drop-shadow-2xl"></i>
              <p class="absolute bottom-4 left-0 right-0 text-center text-green-200 text-sm font-medium">📖 Imagem do Kit "15 dias com Alá"</p>
              <div class="absolute inset-0 border-2 border-white/10 rounded-2xl m-4 pointer-events-none"></div>
            </div>
            <!-- Coluna 2: conteúdo -->
            <div>
              <h1 class="text-3xl md:text-5xl lg:text-6xl font-extrabold leading-tight bg-gradient-to-r from-white via-green-200 to-green-400 bg-clip-text text-transparent">
                Seu filho pode aprender os princípios do Islão em apenas 15 dias - mesmo que você não tenha tempo para ensinar
              </h1>
              <p class="text-gray-200 text-lg md:text-xl mt-6 leading-relaxed border-l-4 border-green-500 pl-4">
                Método interativo e divertido que aproxima as crianças de Alá através de histórias, atividades e ensinamentos adaptados dos 3 aos 10 anos.
              </p>
              <!-- título persuasivo -->
              <h3 class="text-2xl font-bold mt-6 text-green-300">✨ Transforme a relação do seu filho com a fé islâmica ✨</h3>
              <!-- estrelas rating -->
              <div class="flex items-center gap-3 mt-4">
                <div class="stars-rating text-2xl">★★★★★</div>
                <span class="text-white font-semibold text-lg">4,9/5 estrelas</span>
                <i class="fas fa-star text-yellow-400"></i>
              </div>
              <p class="text-green-100 bg-black/30 rounded-xl p-3 mt-4 text-sm md:text-base">
                <i class="fas fa-users mr-2"></i> Mais de 24.000 Moçambicanos já transformaram o ensino da religião islâmica de forma rápida e interativa para crianças dos 3 aos 10 anos
              </p>
              <!-- CTA principal -->
              <div class="mt-8">
                <a href="link do teu checkout" target="_blank" class="btn-3d inline-block w-full md:w-auto text-center bg-gradient-to-r from-green-700 to-emerald-600 hover:from-green-600 hover:to-emerald-500 text-white font-bold py-4 px-10 rounded-2xl text-xl transition-all duration-300 shadow-2xl">
                  COMPRAR AGORA <i class="fas fa-arrow-right ml-2"></i>
                </a>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- ========== SEÇÃO DEPOIMENTOS ========== 6 cards -->
      <section class="fade-section">
        <div class="text-center mb-12">
          <h2 class="text-4xl md:text-5xl font-bold bg-gradient-to-r from-white to-green-300 inline-block bg-clip-text text-transparent">Veja os resultados dos nossos clientes</h2>
          <div class="w-24 h-1 bg-green-500 mx-auto mt-4 rounded-full"></div>
        </div>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          <!-- Card 1 -->
          <div class="glass-card p-6 flex flex-col gap-3">
            <div class="flex items-center gap-4">
              <div class="w-14 h-14 rounded-full img-circle flex items-center justify-center text-green-300 font-bold">AF</div>
              <div><p class="font-bold text-lg">Aisha F.</p><div class="stars-rating text-yellow-400 text-sm">★★★★★</div></div>
            </div>
            <p class="text-gray-200 italic">“Em apenas 12 dias, meu pequeno já recitava suratas curtas com entusiasmo! Método incrível.”</p>
            <div class="flex justify-between text-xs text-green-300 mt-2"><span>📸 Before/After visível</span><span>Fevereiro 2025</span></div>
            <div class="w-full h-28 rounded-xl img-placeholder text-sm">✨ Placeholder imagem antes/depois</div>
          </div>
          <!-- Card 2 -->
          <div class="glass-card p-6 flex flex-col gap-3">
            <div class="flex items-center gap-4">
              <div class="w-14 h-14 rounded-full img-circle flex items-center justify-center text-green-300 font-bold">MR</div>
              <div><p class="font-bold text-lg">Mariam R.</p><div class="stars-rating text-yellow-400 text-sm">★★★★★</div></div>
            </div>
            <p class="text-gray-200 italic">“Aprendizado divertido, meu filho de 5 anos ama as atividades. Aproximou a família toda de Alá.”</p>
            <div class="flex justify-between text-xs text-green-300 mt-2"><span>📸 Resultado real</span><span>Janeiro 2025</span></div>
            <div class="w-full h-28 rounded-xl img-placeholder text-sm">📷 Placeholder transformação</div>
          </div>
          <!-- Card 3 -->
          <div class="glass-card p-6 flex flex-col gap-3">
            <div class="flex items-center gap-4">
              <div class="w-14 h-14 rounded-full img-circle flex items-center justify-center text-green-300 font-bold">SC</div>
              <div><p class="font-bold text-lg">Samira C.</p><div class="stars-rating text-yellow-400 text-sm">★★★★★</div></div>
            </div>
            <p class="text-gray-200 italic">“15 dias bastaram! Hoje meu filho pergunta sobre o Islão com curiosidade e amor.”</p>
            <div class="flex justify-between text-xs text-green-300 mt-2"><span>📸 Evolução</span><span>Março 2025</span></div>
            <div class="w-full h-28 rounded-xl img-placeholder text-sm">🖼️ Before/After placeholder</div>
          </div>
          <!-- Card 4 -->
          <div class="glass-card p-6 flex flex-col gap-3">
            <div class="flex items-center gap-4">
              <div class="w-14 h-14 rounded-full img-circle flex items-center justify-center text-green-300 font-bold">ZO</div>
              <div><p class="font-bold text-lg">Zahara O.</p><div class="stars-rating text-yellow-400 text-sm">★★★★★</div></div>
            </div>
            <p class="text-gray-200 italic">“Nunca pensei que aprender o básico do Islão fosse tão prazeroso para as crianças. Recomendo!”</p>
            <div class="flex justify-between text-xs text-green-300 mt-2"><span>📸 Antes e depois</span><span>Abril 2025</span></div>
            <div class="w-full h-28 rounded-xl img-placeholder text-sm">🖼️ Placeholder imagem</div>
          </div>
          <!-- Card 5 -->
          <div class="glass-card p-6 flex flex-col gap-3">
            <div class="flex items-center gap-4">
              <div class="w-14 h-14 rounded-full img-circle flex items-center justify-center text-green-300 font-bold">LM</div>
              <div><p class="font-bold text-lg">Layla M.</p><div class="stars-rating text-yellow-400 text-sm">★★★★★</div></div>
            </div>
            <p class="text-gray-200 italic">“Mudei minha rotina em casa, agora as crianças pedem para aprender mais sobre o Alcorão.”</p>
            <div class="flex justify-between text-xs text-green-300 mt-2"><span>📸 Testemunho real</span><span>Maio 2025</span></div>
            <div class="w-full h-28 rounded-xl img-placeholder text-sm">🖼️ Placeholder evolução</div>
          </div>
          <!-- Card 6 -->
          <div class="glass-card p-6 flex flex-col gap-3">
            <div class="flex items-center gap-4">
              <div class="w-14 h-14 rounded-full img-circle flex items-center justify-center text-green-300 font-bold">FA</div>
              <div><p class="font-bold text-lg">Fatima A.</p><div class="stars-rating text-yellow-400 text-sm">★★★★★</div></div>
            </div>
            <p class="text-gray-200 italic">“Rápido, interativo, e o mais importante: baseado nos valores islâmicos. Obrigada!”</p>
            <div class="flex justify-between text-xs text-green-300 mt-2"><span>📸 Antes/After</span><span>Junho 2025</span></div>
            <div class="w-full h-28 rounded-xl img-placeholder text-sm">✨ Placeholder imagem</div>
          </div>
        </div>
      </section>

      <!-- ========== SEÇÃO BENEFÍCIOS ========== -->
      <section class="fade-section">
        <div class="text-center mb-14">
          <h2 class="text-3xl md:text-5xl font-bold bg-gradient-to-r from-green-200 to-white inline-block bg-clip-text text-transparent">Por que escolher "Como ensinar o meu filho o Islão em 15 dias"?</h2>
        </div>
        <div class="grid md:grid-cols-3 gap-8">
          <!-- Card 1 - Check -->
          <div class="glass-card p-7 text-center group transition-all duration-300">
            <div class="w-20 h-20 mx-auto bg-green-900/60 rounded-2xl flex items-center justify-center mb-5 shadow-inner border border-green-500/40">
              <i class="fas fa-check-circle text-4xl text-green-400"></i>
            </div>
            <h3 class="text-2xl font-bold text-white">Resultados rápidos e permanentes</h3>
            <p class="text-gray-300 mt-3">Mudanças visíveis e resultados significativos em apenas 7 dias. Seu filho absorve o essencial do Islão de forma natural.</p>
          </div>
          <!-- Card 2 - Heart -->
          <div class="glass-card p-7 text-center group">
            <div class="w-20 h-20 mx-auto bg-green-900/60 rounded-2xl flex items-center justify-center mb-5">
              <i class="fas fa-heart text-4xl text-rose-400"></i>
            </div>
            <h3 class="text-2xl font-bold text-white">Sem efeitos colaterais</h3>
            <p class="text-gray-300 mt-3">100% natural, método respeitoso e adaptado à idade da criança. Fortalece a fé sem pressão ou trauma.</p>
          </div>
          <!-- Card 3 - Shield -->
          <div class="glass-card p-7 text-center group">
            <div class="w-20 h-20 mx-auto bg-green-900/60 rounded-2xl flex items-center justify-center mb-5">
              <i class="fas fa-shield-alt text-4xl text-emerald-400"></i>
            </div>
            <h3 class="text-2xl font-bold text-white">Aprovado por famílias</h3>
            <p class="text-gray-300 mt-3">Mais de 24.000 famílias moçambicanas já confiam no nosso método. Apoio contínuo e conteúdo 100% alinhado.</p>
          </div>
        </div>
      </section>

      <!-- SEÇÃO CTA FINAL (garantia extra) -->
      <section class="fade-section text-center pb-10">
        <div class="glass-card p-8 md:p-12 max-w-4xl mx-auto">
          <i class="fas fa-star-of-life text-5xl text-green-400 mb-4 animate-pulse"></i>
          <h2 class="text-3xl md:text-4xl font-extrabold">Comece hoje a jornada do seu filho rumo ao Islão</h2>
          <p class="text-gray-200 text-lg mt-4">Apenas na entrega do produto – risco zero. Aproveite a promoção de lançamento!</p>
          <div class="mt-8">
            <a href="link do teu checkout" target="_blank" class="btn-3d inline-block bg-gradient-to-r from-green-600 to-emerald-600 text-white font-bold py-4 px-12 rounded-2xl text-2xl shadow-2xl transition-all">
              COMPRAR AGORA <i class="fas fa-lock ml-2"></i>
            </a>
            <p class="text-green-300 text-sm mt-5"><i class="fas fa-credit-card"></i> Pagamento apenas na entrega • Último dia da promoção</p>
          </div>
        </div>
      </section>
    </div>

    <!-- Footer simples -->
    <footer class="border-t border-green-800/40 py-8 text-center text-gray-400 text-sm mt-10">
      <p>© 2025 - Método “Como ensinar o meu filho o Islão em 15 dias” | Aproxime seu filho de Alá com amor e conhecimento</p>
      <p class="mt-2">Placeholders de imagens serão substituídos por conteúdo visual oficial</p>
    </footer>
  </main>

  <script>
    // ======================= 1. SMOOTH SCROLL (já nativo com scroll-behavior, mas garantindo links) + efeito para qualquer ancora se existir
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
      anchor.addEventListener('click', function(e) {
        const targetId = this.getAttribute('href');
        if(targetId === "#" || targetId === "") return;
        const targetElem = document.querySelector(targetId);
        if(targetElem) {
          e.preventDefault();
          targetElem.scrollIntoView({ behavior: 'smooth', block: 'start' });
        }
      });
    });

    // ======================= 2. FADE-IN NAS SEÇÕES COM INTERSECTION OBSERVER
    const fadeElements = document.querySelectorAll('.fade-section');
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if(entry.isIntersecting) {
          entry.target.classList.add('visible');
        }
      });
    }, { threshold: 0.2, rootMargin: "0px 0px -50px 0px" });
    fadeElements.forEach(section => observer.observe(section));
    // já forçar visibilidade se já visível
    fadeElements.forEach(section => {
      if(section.getBoundingClientRect().top < window.innerHeight - 100) section.classList.add('visible');
    });

    // ======================= 3. PARALLAX DE FUNDO REAGINDO AO MOVIMENTO DO RATO (3D futurista)
    const parallaxLayer = document.getElementById('parallaxBg');
    if(parallaxLayer) {
      document.addEventListener('mousemove', (e) => {
        const mouseX = e.clientX / window.innerWidth;   // 0..1
        const mouseY = e.clientY / window.innerHeight;
        // movimento suave max 25px em cada direção para efeito de profundidade
        const moveX = (mouseX - 0.5) * 28;
        const moveY = (mouseY - 0.5) * 18;
        parallaxLayer.style.transform = `translate(${moveX}px, ${moveY}px)`;
      });
      // parallax também um leve efeito de rolagem (camada extra)
      window.addEventListener('scroll', () => {
        const scrolled = window.scrollY;
        if(parallaxLayer) {
          parallaxLayer.style.transform = `translateY(${scrolled * 0.05}px)`;
        }
      });
    }

    // ======================= 4. GLASSMORPHISM + SOMBRAS PROFUNDAS já definidas no CSS, 
    // garantindo também um efeito 3D em alguns cards ao scroll (jitter suave)

    // ======================= 5. BOTÕES COM REDIRECIONAMENTO PARA "link do teu checkout"
    // Todos os CTAs com href="link do teu checkout" já estão no HTML, funciona como placeholder.
    // Adicionar um pequeno efeito de clique para feedback
    const allCtas = document.querySelectorAll('a[href="link do teu checkout"]');
    allCtas.forEach(btn => {
      btn.addEventListener('click', (e) => {
        // apenas aviso de substituição, mas mantém redirecionamento (será substituído depois)
        console.log("Redirecionaria para o link do checkout real (substituir depois)");
        // Pode remover preventDefault se quiser que o link realmente abra (vai abrir "link do teu checkout" como string, mas é placeholder)
        // Como é esperado placeholder, não impedimos navegação, mas o ideal é que depois troquem o href.
        // Nenhum e.preventDefault() para manter funcional conforme solicitado: "CTAs devem redirecionar para: ‘link do teu checkout’"
      });
    });

    // ======================= 6. efeitos extras de profundidade e animações de entrada para elementos internos (dinamismo)
    const styleAdd = document.createElement('style');
    styleAdd.textContent = `
      .glass-card, .btn-3d, .img-placeholder {
        transition: transform 0.25s ease, box-shadow 0.3s;
      }
      .glass-card:hover {
        transform: translateY(-6px) scale(1.01);
      }
    `;
    document.head.appendChild(styleAdd);
    
    // pequeno detalhe: garantir que imagens placeholder tenham ícones que representem antes/depois
    // já estão todos definidos.

    // ======================= 7. Ajuste do padding top por causa da barra fixa
    const topBar = document.querySelector('.fixed.top-0');
    if(topBar) {
      const adjustPadding = () => {
        const barHeight = topBar.offsetHeight;
        document.querySelector('main').style.paddingTop = `${barHeight + 16}px`;
      };
      adjustPadding();
      window.addEventListener('resize', adjustPadding);
    }
  </script>
</body>
</html>
```
