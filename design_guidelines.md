# Design Guidelines - Milk Filter Mobile

## Aplicativo
**Milk Filter** - Processamento Artístico de Imagens para Android

## Arquitetura e Navegação

### Navegação
- **Tab Navigation** (2 abas principais)
  1. **Editor** - Tela principal com upload, filtros e comparação
  2. **Galeria** - Histórico de imagens processadas (opcional fase 2)

### Funcionalidades Core
- Upload de imagem (câmera ou galeria)
- Seleção de filtro artístico (Milk 1 ou Milk 2)
- Toggle Pointillism
- Slider de compressão (0-100)
- Comparação Before/After com slider interativo
- Download/Share da imagem processada
- Reset para novo upload

## Sistema de Design

### Paleta de Cores (baseada no Milk Filter original)
**Cores Primárias:**
- Primary: hsl(340, 82%, 28%) - #890028 (vermelho wine)
- Primary Foreground: hsl(340, 20%, 98%) - #fef5f8
- Primary Hover: hsl(340, 75%, 30%) - #8b0a2f

**Cores Secundárias:**
- Secondary: hsl(340, 4%, 88%) - #e3dcde
- Secondary Dark: hsl(340, 6%, 18%) - #2f2729
- Muted: hsl(340, 3%, 90%) - #e7e3e4
- Muted Foreground: hsl(340, 4%, 25%) - #423a3c

**Background:**
- Light: hsl(0, 0%, 100%) - #ffffff
- Dark: hsl(0, 0%, 7%) - #121212
- Card Light: hsl(0, 0%, 98%) - #fafafa
- Card Dark: hsl(0, 0%, 9%) - #171717

**Bordas e Sombras:**
- Border: hsl(0, 0%, 91%) light / hsl(0, 0%, 16%) dark
- Ring/Focus: hsl(340, 82%, 28%)
- Card Shadow: rgba(137, 0, 40, 0.1)

**Filtros Milk (paletas de cores):**
- Milk 1: #000000, #66001F, #890092
- Milk 2: #000000, #5C243C, #CB2B2B

**Cores de Texto:**
- Foreground Light: hsl(0, 0%, 9%) - #171717
- Foreground Dark: hsl(0, 0%, 96%) - #f5f5f5
- Muted Text Light: hsl(340, 4%, 25%)
- Muted Text Dark: hsl(340, 5%, 75%)

### Tipografia
**Fontes:**
- Poppins Regular (corpo de texto)
- Poppins Medium (subtítulos)
- Poppins SemiBold (títulos)
- Poppins Bold (destaques)
- Roboto Regular (textos secundários)

**Escala Tipográfica:**
- Hero: Poppins Bold, 32-36px
- H1: Poppins SemiBold, 28px
- H2: Poppins SemiBold, 24px
- H3: Poppins Medium, 20px
- Body: Poppins Regular, 16px
- Caption: Roboto Regular, 14px
- Small: Roboto Regular, 12px

### Efeitos Glassmorphism
**Especificações de Vidro:**
- Background: rgba(255, 255, 255, 0.10-0.15)
- Backdrop Filter: blur(20px) - usar react-native-blur
- Border: 1px sólida rgba(255, 255, 255, 0.20)
- Border Radius: 20px (cards), 16px (botões), 12px (inputs)
- Shadow: shadowOffset {width: 0, height: 8}, shadowOpacity: 0.25, shadowRadius: 20

**Camadas de Profundidade:**
- Nível 1 (fundo): opacidade 0.05, blur 10px
- Nível 2 (cards): opacidade 0.10, blur 15px
- Nível 3 (modais): opacidade 0.15, blur 20px
- Nível 4 (floating): opacidade 0.20, blur 25px

### Espaçamento
- xs: 4px
- sm: 8px
- md: 16px
- lg: 24px
- xl: 32px
- xxl: 48px

## Especificações de Telas

### Tela Principal (Home)
**Layout:**
- Header transparente com efeito glassmorphism
- Safe area top: headerHeight + 24px
- Safe area bottom: tabBarHeight + 24px
- Background: Gradiente de fundo principal
- Conteúdo: ScrollView com cards glassmorphism

**Componentes:**
- Cards com efeito vidro, bordas arredondadas (20px), sombras suaves
- Botões flutuantes com glassmorphism e ícones Feather
- Animações de entrada: FadeIn + SlideIn (300ms, ease-out)

### Tab Bar
**Design:**
- Background: rgba(255, 255, 255, 0.10)
- Blur: 20px backdrop filter
- Border superior: rgba(255, 255, 255, 0.15)
- Altura: 70px
- Ícones: Feather icons, tamanho 24px
- Animação de seleção: Scale (1.0 → 1.15) + Color transition

### Botões e Interações
**Botão Primário:**
- Background: Gradiente primário com glassmorphism overlay
- Padding: 16px vertical, 32px horizontal
- Border radius: 16px
- Animação press: Scale (1.0 → 0.95) + opacity (1.0 → 0.85)
- Haptic feedback: light

**Botão Secundário:**
- Background: Glass Secondary
- Border: 1px glass border
- Animação hover: Brightness increase + border glow

**Inputs:**
- Background: rgba(255, 255, 255, 0.08)
- Border: 1px rgba(255, 255, 255, 0.15)
- Border radius: 12px
- Padding: 14px
- Focus: Border glow animation + scale (1.0 → 1.02)

## Animações

### Transições de Tela
- Duração: 350ms
- Tipo: Slide from right (Android padrão aprimorado)
- Easing: cubic-bezier(0.4, 0.0, 0.2, 1)

### Animações de Componentes
- Fade In: 300ms, ease-out, opacity 0 → 1
- Slide In: 400ms, ease-out, translateY 20 → 0
- Scale Press: 150ms, ease-in-out, scale 1.0 → 0.95
- Shimmer Loading: 1500ms loop, gradiente animado

### Micro-interações
- Feedback háptico em todos os toques
- Ripple effect em cards (Material Design adaptado)
- Glow effect em focus de inputs (300ms)
- Bounce animation em confirmações (400ms)

## Assets Críticos

### Ícones e Ilustrações
1. **Ícone do App** - Design glassmorphism com gradiente primário
2. **Splash Screen** - Background gradiente com logo glassmorphism centralizado
3. **Avatares** (3 presets):
   - Avatar 1: Design geométrico com gradiente #667eea → #764ba2
   - Avatar 2: Design abstrato com gradiente #f093fb → #f5576c
   - Avatar 3: Design minimalista com gradiente #4facfe → #00f2fe
4. **Ilustrações decorativas** - Elementos glassmorphism que complementam o conteúdo principal

### Ícones do Sistema
- Usar Feather icons de @expo/vector-icons
- Tamanho padrão: 24px
- Cor: #FFFFFF com opacidade variável

## Responsividade

### Breakpoints
- Small: 320-480px (smartphones compactos)
- Medium: 481-768px (smartphones padrão)
- Large: 769-1024px (tablets)

### Adaptações
- Espaçamento proporcional baseado em dimensões da tela
- Cards: 100% width em small, grid 2 colunas em large
- Tipografia: Scale factor 0.9-1.1 baseado em tamanho de tela
- Tab bar: Adaptável com labels visíveis apenas em large

## Acessibilidade
- Contraste mínimo 4.5:1 para textos
- Áreas de toque mínimas: 48x48px
- Suporte a leitores de tela
- Animações respeitam preferências de movimento reduzido