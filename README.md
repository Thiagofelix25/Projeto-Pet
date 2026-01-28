# 📘 Pet Care - Documentação Técnica do Projeto

## 🎯 Visão Geral

**Pet Care** é uma plataforma integrada para tutores de cães e gatos que combina:

- Gerenciamento de saúde pet
- Rede comunitária para recuperação de animais perdidos
- E-commerce contextual de produtos pet
- Sistema de identificação biométrica (PetID)
- Monitoramento via coleira inteligente

---

## 🏗️ Arquitetura Atual

### **Stack Tecnológico**

`Frontend: React 18 + TypeScript Estilização: Tailwind CSS Animações: Framer Motion + Lottie Ícones: Lucide React Estado Global: Context API (CartManager, WishlistManager, OrderManager) Persistência: localStorage (temporário - migrar para backend) Build: Vite Tipo de App: PWA (Progressive Web App)`

### **Estrutura de Pastas**

`src/ ├── components/          # Componentes reutilizáveis │   ├── PetCard.tsx │   ├── ProductCard.tsx │   ├── Toast.tsx │   └── TestingChecklist.tsx │ ├── screens/             # Telas principais │   ├── HomeScreen.tsx │   ├── HealthScreen.tsx │   ├── NetworkScreen.tsx │   ├── ProfileScreen.tsx │   ├── ShopScreen.tsx │   ├── CartScreen.tsx │   ├── WishlistView.tsx │   ├── OrdersView.tsx │   ├── OrderDetailView.tsx │   ├── ProductDetailScreen.tsx │   ├── PetProfileScreen.tsx │   ├── PetRegistrationFlow.tsx │   ├── OnboardingFlow.tsx │   └── onboarding/ │       ├── WelcomeScreen.tsx │       ├── RegisterPetScreen.tsx │       ├── PetIDScreen.tsx │       └── CommunityScreen.tsx │ ├── lib/                 # Utilitários e gerenciadores │   ├── cartStore.ts     # Gerenciamento de carrinho │   ├── wishlistStore.ts # Gerenciamento de favoritos │   ├── orderStore.ts    # Gerenciamento de pedidos │   ├── products.ts      # Mock de produtos │   ├── recommendationEngine.ts # Sistema de recomendação │   ├── onboardingStorage.ts │   ├── haptics.ts       # Feedback tátil │   └── supabase.ts      # Config backend (não utilizado ainda) │ ├── types.ts             # TypeScript interfaces ├── App.tsx              # Componente raiz └── main.tsx             # Entry point`

---

## 🎨 Design System

### **Paleta de Cores**

`Primary Orange: #FF6B35 Secondary Orange: #FF8C5E Brown Dark: #5C2E1F Brown Medium: #8B4513 Green Success: #7CB342 Blue Info: #007AFF Red Alert: #E53935 Yellow Warning: #FFB300  Semantic Colors (adaptam a light/dark mode): - label (texto primário) - secondaryLabel (texto secundário) - systemBackground - secondarySystemBackground`

### **Tipografia (Dynamic Type)**


`Large Title: 34pt - Títulos de seção Title 1: 28pt - Cabeçalhos principais Title 2: 22pt - Subtítulos Title 3: 20pt - Cards destacados Headline: 17pt - Títulos de card Body: 17pt - Texto corrido Callout: 16pt - Metadados importantes Footnote: 13pt - Informações secundárias Caption: 12pt - Timestamps Caption 2: 11pt - Labels pequenos`

### **Espaçamento (Scale)**


`2pt, 4pt, 8pt, 12pt, 16pt, 20pt, 24pt, 32pt, 40pt, 48pt`

### **Componentes Principais**

- **ProductCard**: Card de produto com foto, nome, preço, botão de adicionar
- **PetCard**: Card de pet com foto, status de saúde, alertas
- **ContextualShopSection**: Seção de produtos recomendados
- **ToastView**: Notificação temporária (sucesso/erro)
- **ProductDetailScreen**: Tela completa do produto com carousel

---

## ✅ Funcionalidades Implementadas

### **1. Navegação (4 Tabs)**

- ✅ Home
- ✅ Saúde
- ✅ Rede
- ✅ Perfil

### **2. Onboarding Interativo**

- ✅ 4 telas com animações (Framer Motion)
- ✅ Swipe navigation
- ✅ Progress indicators
- ✅ Skip functionality
- ✅ Persistência (não mostra novamente após completar)

### **3. Gerenciamento de Pets**

- ✅ Cadastro de pets (nome, foto, idade, raça)
- ✅ PetID (status de ativação)
- ✅ Lembretes de vacinas
- ✅ Monitoramento de saúde (BPM, bateria da coleira)
- ✅ Perfil completo do pet
- ✅ Foto de perfil do usuário

### **4. E-commerce Completo**

- ✅ Loja com busca e filtros
- ✅ Categorias (Coleiras, Ração, Brinquedos, Higiene, Acessórios)
- ✅ Carrinho de compras (persistência em localStorage)
- ✅ Wishlist/Favoritos
- ✅ Detalhes do produto (carousel de imagens, reviews)
- ✅ Histórico de pedidos
- ✅ Tracking de pedidos (timeline visual)
- ✅ Checkout simplificado
- ✅ Produtos relacionados

### **5. Sistema de Recomendação**

- ✅ Seções contextuais na Home
- ✅ Baseado em:
    - Pets sem coleira
    - Vacinas próximas
    - PetID não cadastrado
    - Sazonalidade

### **6. Rede Comunitária (Estrutura)**

- ✅ Tela de rede com mapa
- ✅ Sistema de avistamentos
- ⚠️ Alerta "Perdi meu Pet" (parcialmente implementado)

### **7. UX/UI Polish**

- ✅ Animações suaves (Framer Motion)
- ✅ Haptic feedback
- ✅ Toast notifications
- ✅ Loading states
- ✅ Pull-to-refresh (estrutura)
- ✅ Dark mode (suporte de cores semânticas)

---

## ⚠️ Limitações Atuais

### **Tecnológicas**

- **Sem backend**: Dados apenas em localStorage (não sincroniza entre dispositivos)
- **Sem autenticação**: Usuário mock fixo
- **Sem API**: Produtos e pedidos são mocks
- **PWA apenas**: Não é app nativo (sem widget, sem push notifications completas)
- **Sem integração de pagamento**: Checkout é simulado
- **Sem coleira real**: Dados de BPM/bateria são mocks

### **Funcionais**

- **PetID**: Não há algoritmo real de reconhecimento facial
- **Matching de pets perdidos**: Sistema de comparação não implementado
- **Geolocalização**: Não utiliza GPS real para avistamentos
- **Parceiros**: Lista estática sem integração real
- **Tracking de pedidos**: Códigos de rastreio não funcionais

---

## 🚀 Oportunidades de Melhoria Pendentes

### **ALTA PRIORIDADE (Impacto Imediato)**

#### **1. Modo "Pet Perdido" Extremo** 🚨

**Status**: Não implementado  
**Esforço**: Médio (3-5 dias)  
**Impacto**: Crítico (core value proposition)

**Descrição**:

- Interface adaptativa quando pet marcado como perdido
- Tab Bar muda para: [🚨 ALERTA] [📍 Mapa Ao Vivo] [💬 Mensagens] [⚙️ Config]
- Dashboard de busca em tempo real:
    - Contadores (pessoas ajudando, avistamentos, matches)
    - Mapa ao vivo com pins de avistamentos
    - Ações rápidas (ampliar área, ligar abrigos, compartilhar)
- Remove distrações (esconde loja, conteúdo educativo)
- Design vermelho urgente

**Arquivos a criar**:

`screens/LostPetMode.tsx components/LostPetDashboard.tsx components/LiveMap.tsx`

---

#### **2. Smart Notifications** 🔔

**Status**: Não implementado  
**Esforço**: Médio (2-3 dias)  
**Impacto**: Alto (reengajamento)

**Descrição**:

- Web Push Notifications (funciona em PWA)
- Notificações ricas com imagem e ações
- Timing inteligente:
    - Manhã (8h): Lembretes do dia
    - Urgente: Match de pet perdido (95%+)
    - Promoções: Contextual (ex: vacina próxima → kit em oferta)
- Deep links para partes específicas do app

**Exemplo de payload**:

`{   "title": "🐕 Milly avistada!",   "body": "95% de similaridade • 800m de você",   "icon": "/pet-icon.png",   "image": "https://...",   "actions": [     {"action": "view", "title": "👁️ Ver no Mapa"},     {"action": "dismiss", "title": "Não é ela"}   ],   "data": {"url": "/network?alert=123"} }`

**Arquivos a criar**:


`lib/notifications.ts public/service-worker.js components/NotificationPermissionPrompt.tsx`

---

#### **3. Empty States Narrativos** 📖

**Status**: Parcialmente implementado  
**Esforço**: Baixo (1-2 dias)  
**Impacto**: Médio (reduz frustração)

**Descrição**:

- Substituir mensagens genéricas por narrativas com personalidade
- Incluir sugestões acionáveis
- Usar emojis e tom de voz do app

**Exemplos**:

|Tela|Antes|Depois|
|---|---|---|
|**Shop (busca vazia)**|"Nenhum produto encontrado"|"🐾 Ops! Nem o Thor encontrou isso...<br>Que tal: [coleira GPS] [ração premium]<br>[🛒 Ver Destaques]"|
|**Rede (sem avistamentos)**|"Nenhum avistamento"|"🌟 Boa notícia!<br>Nenhum pet perdido por perto hoje"|
|**Favoritos (vazio)**|"Nenhum favorito"|"❤️ Seu coração ainda está vazio...<br>Toque no ❤️ dos produtos que você gosta<br>[Ir para Loja]"|
|**Sem pets cadastrados**|"Adicione um pet"|"👋 Cadê seu melhor amigo?<br>Vamos apresentá-lo!<br>[+ Cadastrar Primeiro Pet]"|
|**Pedidos (vazio)**|"Nenhum pedido"|"📦 Sua primeira compra será especial!<br>[Explorar Produtos]"|

**Arquivos a modificar**:


`screens/ShopScreen.tsx (linha ~180) screens/WishlistView.tsx (linha ~35) screens/OrdersView.tsx (linha ~50) screens/NetworkScreen.tsx`

---

### **MÉDIA PRIORIDADE (Melhora Experiência)**

#### **4. Micro-interações & Celebrações** ✨

**Status**: Não implementado  
**Esforço**: Médio (3-4 dias)  
**Impacto**: Médio (delight)

**Descrição**:

- Animações especiais para momentos importantes
- Confete, pulsos, transições elaboradas

**Momentos a celebrar**:

**A. Primeiro pet cadastrado**:


`// Confete animation import confetti from 'canvas-confetti';  confetti({   particleCount: 100,   spread: 70,   origin: { y: 0.6 } });  // + Badge desbloqueado <Badge text="Tutor Responsável" icon="🏆" />`

**B. PetID ativado**:

`// Scan facial animado (já existe parcialmente) // + Gráfico comparativo <ComparisonChart    before={30} // 30% chance sem PetID   after={98}  // 98% com PetID   label="Chance de recuperação" />`

**C. Pet encontrado**:

`// Coração reunindo animação <HeartReunionAnimation />  // + Reconhecimento público <ThankYouCard    helper="João Silva"   message="Obrigado por ajudar Thor a voltar para casa!" />`

**D. Milestone de pedidos**:

`// 10º pedido <MilestoneModal   title="Cliente VIP!"   description="Você completou 10 pedidos"   reward="Cupom 15% OFF: VIP15" />`

**Arquivos a criar**:

`components/celebrations/ConfettiEffect.tsx components/celebrations/HeartReunion.tsx components/celebrations/MilestoneModal.tsx components/charts/ComparisonChart.tsx lib/achievements.ts`

---

#### **5. Social Proof Estratégico** 👥

**Status**: Não implementado  
**Esforço**: Baixo (1-2 dias)  
**Impacto**: Médio (trust building)

**Descrição**:

- Mostrar dados reais da comunidade
- Stats pessoais do usuário
- Transparência com números

**Onde adicionar**:

**A. Home Screen - Nova seção**:
`<section className="px-6 py-6 bg-blue-50 rounded-2xl mb-6">   <h3 className="text-[18px] font-bold text-[#5C2E1F] mb-4">     📊 Impacto da Comunidade   </h3>   <div className="space-y-2 text-[14px]">     <div className="flex justify-between">       <span className="text-gray-600">Esta semana em São Paulo:</span>     </div>     <div className="flex items-center gap-2">       <Heart size={16} className="text-green-500" />       <span><strong>23 pets</strong> reunidos com tutores</span>     </div>     <div className="flex items-center gap-2">       <Clock size={16} className="text-blue-500" />       <span>Tempo médio: <strong>4 horas</strong></span>     </div>     <div className="flex items-center gap-2">       <TrendingUp size={16} className="text-green-500" />       <span>Taxa de sucesso: <strong>94%</strong></span>     </div>   </div>   <button className="w-full mt-4 py-2 bg-blue-500 text-white rounded-xl">     Ver Histórias de Sucesso →   </button> </section>`

**B. Network Screen - Badge no mapa**:

`<div className="absolute top-4 left-4 bg-white/90 backdrop-blur px-4 py-2 rounded-full shadow-lg">   <div className="text-[12px] font-bold text-green-600">     💚 234 tutores ativos agora   </div> </div>`

**C. Profile Screen - Stats pessoais**:

`<section>   <h3>Seu Impacto</h3>   <div className="grid grid-cols-3 gap-3">     <StatCard icon="👁️" value="12" label="Avistamentos" />     <StatCard icon="🏆" value="3" label="Pets ajudados" />     <StatCard icon="⭐" value="#247" label="Rank (top 5%)" />   </div> </section>`

**Arquivos a modificar/criar**:

`screens/HomeScreen.tsx (adicionar seção) screens/NetworkScreen.tsx (badge no mapa) screens/ProfileScreen.tsx (stats section) components/StatCard.tsx (novo) lib/communityStats.ts (mock data)`

---

#### **6. Busca Inteligente com NLP** 🔍

**Status**: Busca básica implementada  
**Esforço**: Médio (2-3 dias)  
**Impacto**: Médio (conveniência)

**Descrição**:

- Entender queries em linguagem natural
- Sinônimos e contexto
- Filtros inteligentes extraídos da query

**Exemplos**:

`Query: "ração para golden retriever filhote" Parsing: - categoria: food - raça: golden retriever - idade: filhote  Resultados: Rações para raças grandes, linha puppy`

`Query: "coleira que avisa se fugir" Parsing: - categoria: collar - feature: geofencing, GPS  Resultados: Coleiras GPS com alertas de zona`

`Query: "brinquedo resistente para pitbull" Parsing: - categoria: toy - raça: pitbull (mordida forte) - característica: resistente  Resultados: Brinquedos indestrutíveis, linha heavy duty`

**Implementação**:

`// lib/smartSearch.ts export class SmartSearch {   static parse(query: string): SearchFilters {     const keywords = {       breeds: ['golden', 'pitbull', 'poodle', 'bulldog'],       ages: ['filhote', 'adulto', 'idoso', 'puppy', 'senior'],       features: ['GPS', 'geofencing', 'resistente', 'indestrutível'],       categories: ['ração', 'coleira', 'brinquedo']     };      // Extract filters from query     const filters: SearchFilters = {       category: this.extractCategory(query, keywords.categories),       breed: this.extractBreed(query, keywords.breeds),       age: this.extractAge(query, keywords.ages),       features: this.extractFeatures(query, keywords.features)     };      return filters;   } }`

**Arquivos a criar/modificar**:

`lib/smartSearch.ts (novo) screens/ShopScreen.tsx (integrar parser)`

---

#### **7. Animações Intencionais (Choreography)** 🎬

**Status**: Animações básicas implementadas  
**Esforço**: Médio (3-4 dias)  
**Impacto**: Baixo-Médio (polish)

**Descrição**:

- Sequências de animação elaboradas para momentos-chave
- Mostra relação entre elementos
- Feedback visual rico

**Sequências a implementar**:

**A. Adicionar ao carrinho**:

`const addToCartSequence = async () => {   // 1. Produto escala   await animate(productRef, { scale: [1, 1.2, 0.8] }, { duration: 0.2 });      // 2. Ícone do produto "voa" até carrinho   await animate(iconRef, {     x: cartPosition.x,     y: cartPosition.y,     scale: 0.3   }, { duration: 0.4, ease: "easeOut" });      // 3. Badge do carrinho pulsa   await animate(badgeRef, { scale: [1, 1.3, 1] }, { duration: 0.3 });      // 4. Toast aparece   showToast("Produto adicionado!"); };`

**B. PetID Scan Success**:

`// Já existe parcialmente em PetIDScreen.tsx // Melhorar com: - Pontos faciais aparecem sequencialmente (olhos → nariz → boca) - Linha de scan com trail effect - Checkmark cresce do centro com spring animation - Haptic pattern (light → medium → success)`

**C. Pet Encontrado**:

`// Animação de "reunião" const reunionSequence = () => {   // 1. Duas fotos aparecem (perdida vs encontrada)   // 2. Aproximam-se uma da outra   // 3. "Fundem" com efeito de brilho   // 4. Porcentagem de match conta 0% → 95%   // 5. Se >90%: confete sutil   // 6. Botão "É meu pet!" pulsa };`

**Arquivos a criar/modificar**:
`lib/animations.ts (choreography helpers) components/ProductCard.tsx (add to cart sequence) screens/NetworkScreen.tsx (pet found animation)`

---

### **BAIXA PRIORIDADE (Nice-to-Have)**

#### **8. Acessibilidade Profunda** ♿

**Status**: Parcialmente implementado (cores semânticas)  
**Esforço**: Alto (1 semana)  
**Impacto**: Médio (inclusão, compliance)

**Melhorias necessárias**:

**A. Alto Contraste**:
`// Settings toggle const [highContrast, setHighContrast] = useState(false);  // Apply theme const theme = highContrast ? {   background: '#000000',   text: '#FFFFFF',   accent: '#FF5500', // saturado   borders: '3px', // mais grossas   shadows: 'none' // removidas } : defaultTheme;`

**B. Navegação por Teclado**:
`// Todos botões/links com focus states <button className="... focus:ring-4 focus:ring-[#FF6B35]/50">  // Skip to content <a href="#main-content" className="sr-only focus:not-sr-only">   Pular para conteúdo </a>`

**C. ARIA Labels**:

`// Ícones sempre com label <button aria-label="Adicionar ao carrinho">   <ShoppingCart /> </button>  // Status dinâmicos <div role="status" aria-live="polite">   {cartCount} itens no carrinho </div>`

**D. VoiceOver/Screen Reader**:
`// Agrupamento lógico <div role="group" aria-labelledby="pet-info">   <h3 id="pet-info">Informações do Pet</h3>   ... </div>  // Anúncios importantes <div role="alert" aria-atomic="true">   Pet encontrado! </div>`

**Arquivos a modificar**:
`Todos os components/ (adicionar ARIA) App.tsx (tema de alto contraste) components/AccessibilitySettings.tsx (novo)`

---

#### **9. PWA Install Prompt** 📲

**Status**: Não implementado  
**Esforço**: Baixo (meio dia)  
**Impacto**: Médio (retention)

**Descrição**:

- Prompt nativo iOS/Android para "instalar" PWA
- Aumenta engagement em 3x (usuários com ícone na home)

**Implementação**:
`// components/InstallPrompt.tsx const InstallPrompt = () => {   const [showPrompt, setShowPrompt] = useState(false);   const [deferredPrompt, setDeferredPrompt] = useState<any>(null);    useEffect(() => {     // Android/Chrome     window.addEventListener('beforeinstallprompt', (e) => {       e.preventDefault();       setDeferredPrompt(e);       setTimeout(() => setShowPrompt(true), 5000); // após 5s     });      // iOS (manual)     const isIOS = /iPad|iPhone|iPod/.test(navigator.userAgent);     const isInstalled = window.matchMedia('(display-mode: standalone)').matches;     if (isIOS && !isInstalled) {       setTimeout(() => setShowPrompt(true), 5000);     }   }, []);    const handleInstall = async () => {     if (deferredPrompt) {       deferredPrompt.prompt();       const { outcome } = await deferredPrompt.userChoice;       if (outcome === 'accepted') {         setShowPrompt(false);       }     }   };    if (!showPrompt) return null;    return (     <motion.div       initial={{ y: 100 }}       animate={{ y: 0 }}       className="fixed bottom-20 left-4 right-4 bg-white rounded-2xl shadow-2xl p-5 z-[300]"     >       <button onClick={() => setShowPrompt(false)} className="absolute top-3 right-3">         <X size={20} />       </button>              <div className="flex gap-4">         <div className="text-4xl">📱</div>         <div>           <h3 className="font-bold mb-1">Adicionar à Tela Inicial</h3>           <p className="text-sm text-gray-600 mb-3">             Acesse o Pet Care com 1 toque           </p>           {deferredPrompt ? (             <button onClick={handleInstall} className="btn-primary">               Instalar             </button>           ) : (             <div className="text-xs text-gray-500">               Toque em <Share size={14} /> e "Adicionar à Tela de Início"             </div>           )}         </div>       </div>     </motion.div>   ); };`

---

#### **10. Testing Checklist (Debug)** ✅

**Status**: Implementado  
**Melhoria**: Adicionar testes automatizados

**Próximos passos**:

- Integrar com Playwright/Cypress para E2E
- Unit tests com Vitest
- Visual regression tests

---

## 🔮 Roadmap de Longo Prazo

### **Fase 1: Backend & Infraestrutura** (4-6 semanas)

- [ ]  Setup Supabase/Firebase
- [ ]  API REST para CRUD de pets
- [ ]  Autenticação (email/Google/Apple)
- [ ]  Storage de imagens (S3/Cloud Storage)
- [ ]  WebSockets para tempo real (avistamentos)
- [ ]  Banco de dados relacional (pets, users, sightings, orders)

### **Fase 2: App Nativo** (8-12 semanas)

- [ ]  Migração para React Native
- [ ]  Publicação App Store (iOS)
- [ ]  Publicação Play Store (Android)
- [ ]  Push notifications nativas
- [ ]  Deep linking
- [ ]  Biometria (Face ID / Touch ID)

### **Fase 3: Hardware Integration** (12-16 semanas)

- [ ]  API da coleira inteligente (Bluetooth Low Energy)
- [ ]  Algoritmo PetID real (Computer Vision + ML)
- [ ]  GPS tracking em tempo real
- [ ]  Sensores de saúde (BPM, temperatura)

### **Fase 4: Advanced Features** (16+ semanas)

- [ ]  Widget iOS/Android
- [ ]  Live Activities (iOS 16+)
- [ ]  Apple Watch app
- [ ]  AR para "preview" de produtos
- [ ]  Social features (feed, stories)
- [ ]  Inteligência artificial para diagnóstico preventivo

---

## 📦 Dependências Atuais

`{   "dependencies": {     "react": "^18.2.0",     "react-dom": "^18.2.0",     "framer-motion": "^10.16.0",     "lottie-react": "^2.4.0",     "lucide-react": "^0.294.0",     "@supabase/supabase-js": "^2.38.0"    },   "devDependencies": {     "@types/react": "^18.2.0",     "@types/react-dom": "^18.2.0",     "@vitejs/plugin-react": "^4.2.0",     "typescript": "^5.3.0",     "vite": "^5.0.0",     "tailwindcss": "^3.4.0"   } }`

---

## 🐛 Bugs Conhecidos

1. **Empty State (ShopScreen)**: Prompt de implementação não funcionou corretamente - requer debugging
2. **Carousel dots (ProductDetail)**: Indicadores de página não aparecem em algumas telas
3. **Toast overflow**: Toasts podem sobrepor header em telas pequenas
4. **localStorage limits**: Pode estourar limite de 5MB com muitas imagens em base64

---

## 🚦 Como Contribuir

### **Setup do Projeto**

`# Clone git clone https://github.com/seu-usuario/pet-care.git cd pet-care  # Install npm install  # Dev server npm run dev  # Build npm run build  # Preview production build npm run preview`

### **Convenções de Código**

- **Components**: PascalCase (ex: `ProductCard.tsx`)
- **Utilities**: camelCase (ex: `cartStore.ts`)
- **Constants**: UPPER_SNAKE_CASE (ex: `SAMPLE_PRODUCTS`)
- **CSS**: Tailwind classes apenas (evitar CSS custom)
- **Commits**: Conventional Commits (ex: `feat: add empty states`, `fix: cart badge overflow`)

### **Pull Request Template**
`## Descrição [Descrição clara do que foi implementado/corrigido]  ## Tipo de mudança - [ ] Bug fix - [ ] Nova feature - [ ] Breaking change - [ ] Documentação  ## Checklist - [ ] Testado em Chrome/Safari - [ ] Testado em mobile (responsivo) - [ ] Sem erros no console - [ ] Código segue convenções do projeto - [ ] Adicionei comentários em lógica complexa - [ ] Atualizei documentação (se necessário)  ## Screenshots [Se aplicável, adicione prints antes/depois]`

---

**Última atualização**: 28/01/2026  
**Versão do app**: 1.0.0 (MVP)  
