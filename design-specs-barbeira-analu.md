# Design Specifications — Barbeira Analu
> Documento técnico para execução de brand book, identidade visual, redes sociais e site.
> Design Chief — Design Squad | Versão 1.0 — Abril 2026

---

## Índice

1. [Design Tokens — Sistema Base](#1-design-tokens--sistema-base)
2. [Sistema Tipográfico](#2-sistema-tipográfico)
3. [Grid e Espaçamento](#3-grid-e-espaçamento)
4. [Especificações de Logo](#4-especificações-de-logo)
5. [Sistema de Redes Sociais](#5-sistema-de-redes-sociais)
6. [Direção de Fotografia e Conteúdo](#6-direção-de-fotografia-e-conteúdo)
7. [Aplicações Físicas](#7-aplicações-físicas)
8. [Estrutura do Site](#8-estrutura-do-site)
9. [Estrutura do Brand Book](#9-estrutura-do-brand-book)
10. [Checklist de Qualidade](#10-checklist-de-qualidade)

---

## 1. Design Tokens — Sistema Base

> Tokens são os valores base que alimentam todo o sistema. Todo componente, template e aplicação usa esses valores. Nada é hard-coded fora daqui.

### 1.1 Paleta de Cores

```
/* CORES PRIMÁRIAS */
--color-verde-noite:     #03110D   /* Fundo principal */
--color-verde-floresta:  #16302B   /* Fundo secundário, camadas */
--color-borde-profundo:  #390517   /* Destaque, CTA, contraste */

/* CORES DE ACENTO */
--color-caramelo:        #A38560   /* Detalhe nobre — uso restrito */
--color-prata:           #E0E0E0   /* Tipografia sobre fundo escuro */

/* NEUTROS */
--color-branco:          #FFFFFF   /* Uso limitado — impressão/contraste forçado */
--color-preto-suave:     #0A0A0A   /* Nunca usar #000000 puro */
```

**Regras de uso obrigatórias:**

| Token | Uso permitido | Uso proibido |
|---|---|---|
| Verde Noite | Fundo principal, backgrounds | Tipografia, ícones |
| Verde Floresta | Fundos secundários, cards, sobreposições | Fundo principal |
| Bordô Profundo | CTAs, destaques, molduras, elementos-chave | Fundo de texto corrido |
| Caramelo | Filetes, ornamentos, sublinhados, hot stamp, logo sobre fundo escuro | Blocos, backgrounds, texto corrido |
| Prata | Tipografia sobre fundos escuros, ícones sutis | Fundos, elementos de destaque |

**Proporção de uso por peça:**

```
Fundo escuro (Verde Noite / Bordô):  ████████░░  ~80%
Caramelo:                            █░░░░░░░░░  ~10%
Prata / Texto:                       █░░░░░░░░░  ~10%
```

### 1.2 Opacidades e Variações

```
/* VARIAÇÕES FUNCIONAIS */
--color-overlay-dark:    rgba(3, 17, 13, 0.85)    /* Overlay sobre foto */
--color-overlay-borde:   rgba(57, 5, 23, 0.70)    /* Overlay bordô sobre foto */
--color-caramelo-sutil:  rgba(163, 133, 96, 0.20)  /* Background hint sutil */
--color-borda-sutil:     rgba(163, 133, 96, 0.30)  /* Bordas, divisores */
```

### 1.3 Gradientes

```
/* USO: transições entre seções, overlays em foto */
--gradient-principal:
  linear-gradient(180deg, #03110D 0%, #16302B 100%)

--gradient-dramatico:
  linear-gradient(135deg, #03110D 0%, #390517 100%)

--gradient-foto-overlay:
  linear-gradient(180deg, transparent 0%, rgba(3,17,13,0.95) 100%)
```

---

## 2. Sistema Tipográfico

### 2.1 Famílias Tipográficas

**Família A — Display Serif (Headlines, Logo, Títulos)**

Ordem de preferência (designer escolhe baseado em licença e orçamento):

| Fonte | Acesso | Caractere |
|---|---|---|
| **Cormorant Garamond** | Google Fonts — gratuita | Alto contraste, elegância editorial |
| **Bodoni Moda** | Google Fonts — gratuita | Mais impacto, mais ousada |
| **Canela** | Comercial (Commercial Type) | Premium, moderna com alma clássica |
| **Freight Display** | Comercial (Adobe Fonts) | Peso e presença, muito sofisticada |

> **Recomendação para orçamento zero:** Cormorant Garamond para títulos + DM Sans para texto.
> **Recomendação para orçamento premium:** Canela Display + Neue Haas Grotesk.

**Família B — Sans-serif (Textos, Legendas, Interface)**

| Fonte | Acesso | Caractere |
|---|---|---|
| **DM Sans** | Google Fonts — gratuita | Limpa, moderna, neutro nobre |
| **Jost** | Google Fonts — gratuita | Geométrica, clean |
| **Futura PT** | Comercial (Adobe Fonts) | Clássica do modernismo |
| **Neue Haas Grotesk** | Comercial | Referência máxima de neutralidade |

### 2.2 Escala Tipográfica

Base: **16px**, multiplicador: **1.25 (Major Third)**

```
/* DISPLAY */
--text-display-xl:   80px / line-height: 88px   /* Impacto máximo, hero */
--text-display-lg:   64px / line-height: 72px   /* Headlines de seção */
--text-display-md:   48px / line-height: 56px   /* Títulos principais */

/* HEADINGS */
--text-h1:           40px / line-height: 48px
--text-h2:           32px / line-height: 40px
--text-h3:           24px / line-height: 32px
--text-h4:           20px / line-height: 28px

/* BODY */
--text-body-lg:      18px / line-height: 28px   /* Texto de apoio */
--text-body:         16px / line-height: 26px   /* Corpo padrão */
--text-body-sm:      14px / line-height: 22px   /* Legendas, notas */

/* MICRO */
--text-caption:      12px / line-height: 18px   /* Etiquetas, timestamps */
--text-label:        11px / line-height: 16px   /* Caps pequenas */
```

### 2.3 Regras de Estilo Tipográfico

**Headlines (Serif):**
```
font-family: [Família A]
font-weight: 300 (Light) ou 400 (Regular) — nunca Bold em display
letter-spacing: 0.08em a 0.15em (tracking generoso)
text-transform: UPPERCASE para impact, Title Case para elegância
color: var(--color-prata) sobre fundos escuros
       var(--color-caramelo) para ênfase especial
```

**Textos de apoio (Sans-serif):**
```
font-family: [Família B]
font-weight: 300 (Light) ou 400 (Regular)
letter-spacing: 0.02em a 0.05em
line-height: 1.6 a 1.8
color: var(--color-prata) com 70-80% opacidade para hierarquia
```

**Regras absolutas:**
- Nunca Bold + Uppercase em display — escolhe um
- Nunca duas fontes serif juntas na mesma peça
- Tracking generoso é o sinal visual de luxo — jamais aperte letras
- Títulos em caixa alta com letter-spacing ≥ 0.1em

---

## 3. Grid e Espaçamento

### 3.1 Sistema de Espaçamento (8pt Grid)

```
--space-1:    4px
--space-2:    8px
--space-3:    12px
--space-4:    16px
--space-5:    24px
--space-6:    32px
--space-7:    48px
--space-8:    64px
--space-9:    96px
--space-10:   128px
--space-11:   192px
--space-12:   256px
```

**Princípio:** luxo respira. Margens generosas comunicam que a marca não precisa disputar espaço.

### 3.2 Grid para Digital (Site)

```
Colunas:        12 (desktop) / 4 (mobile)
Gutter:         24px (desktop) / 16px (mobile)
Margem lateral: 80px (desktop) / 20px (mobile)
Max-width:      1200px
```

### 3.3 Grid para Instagram

```
Feed quadrado (1:1):   1080 × 1080px
Feed retrato (4:5):    1080 × 1350px
Stories/Reels:         1080 × 1920px

Safe zone Stories:     Manter conteúdo entre y:150px e y:1750px
                        (evitar UI do Instagram)

Margem interna:        72px (feed) / 80px (stories)
```

---

## 4. Especificações de Logo

> O designer deve desenvolver os três caminhos e apresentar para aprovação. As specs abaixo definem o que cada versão deve entregar.

### 4.1 Caminho A — A Navalha Soberana

**Conceito:**
Símbolo de navalha estilizada (traço essencial, não ilustrativo) + wordmark BARBEIRA ANALU.

**Construção do símbolo:**
- Navalha em posição diagonal (45°) — lâmina aberta
- Traço único, limpo — não mais que 3 elementos visuais
- Proporção: símbolo ocupa 60% da altura do wordmark ao lado
- O cabo da navalha pode ter espessura levemente maior — contraste intencional

**Wordmark:**
- BARBEIRA em Família A, weight light, caixa alta, tracking 0.12em
- ANALU em Família A, weight regular ou medium, caixa alta, tracking 0.15em
- ANALU levemente maior que BARBEIRA (escala 1:1.3)
- Espaço entre as duas palavras: 0.8em

**Lockup:**
- Versão vertical: símbolo acima, wordmark abaixo
- Versão horizontal: símbolo à esquerda, wordmark à direita
- Versão símbolo solo: para bordado, lacre de cera, favicon

**Cores:**
- Principal: Caramelo (`#A38560`) sobre Verde Noite
- Alternativa: Prata sobre Verde Noite
- Alternativa: Bordô sobre fundo claro (uso limitado)
- Monocromático: preto, branco (para situações forçadas)

---

### 4.2 Caminho B — Monograma BA

**Conceito:**
Iniciais B e A entrelacadas como monograma de maison + nome completo como wordmark.

**Construção do monograma:**
- B e A compartilham ao menos um elemento gráfico (haste, curva ou serifas)
- A lâmina de navalha pode ser o traço diagonal do A — duplo sentido visual
- Proporção: o monograma deve ser legível em 16px (para favicon/bordado mínimo)
- Estilo: serif clássico customizado — não fonte padrão, mas derivado de uma
- Teste obrigatório: ler as letras em 2 segundos ou menos

**Wordmark:**
- ANALU em Família A, weight light, caixa alta, tracking 0.20em
- BARBEIRA abaixo, em Família B (sans-serif), weight light, caixa alta, tracking 0.25em, escala menor (70% de ANALU)

**Lockup:**
- Versão completa: monograma + ANALU + BARBEIRA
- Versão reduzida: monograma + ANALU
- Versão símbolo: monograma solo

**Aplicações ideais deste caminho:**
- Bordado em avental / uniforme
- Lacre de cera em embalagens
- Hot stamp em cartão
- Perfil Instagram (foto redonda)
- Tag de produto

---

### 4.3 Caminho C — Wordmark Soberano

**Conceito:**
Só o nome, tratado como peça tipográfica única. Sem símbolo.

**Construção:**
- BARBEIRA em linha superior: Família A, weight light, caixa alta, tracking 0.20em
- ANALU em linha inferior: Família A, weight regular, caixa alta, tracking 0.15em, escala 1.6× maior que BARBEIRA
- ANALU é a âncora visual — o nome próprio domina
- Entre as duas linhas: filete horizontal fino em Caramelo (1px) — assinatura da marca

**Customização tipográfica (obrigatória neste caminho):**
O designer deve fazer ao menos um ajuste manual que torna o wordmark único:
- Opção 1: O A de ANALU tem a barra diagonal removida (remete à navalha)
- Opção 2: A última letra U de ANALU tem serifas levemente estendidas
- Opção 3: Ajuste de kerning entre N-A-L-U que cria ritmo único

**Aplicações ideais:**
- Fachada
- Papel timbrado
- Site (header)
- Stories com fundo escuro

---

### 4.4 Regras Universais para Todos os Caminhos

**Área de proteção:**
```
Mínimo de espaço em branco ao redor do logo:
Horizontal: ½ da altura do logo
Vertical:   ½ da altura do logo
```

**Tamanhos mínimos:**
```
Digital:   120px de largura (lockup completo)
           32px de largura (símbolo/monograma solo)
Impressão: 25mm de largura (lockup completo)
           8mm de largura (símbolo/monograma solo)
```

**Versões obrigatórias a entregar:**
- [ ] Logo principal (cor, fundo escuro)
- [ ] Logo alternativo (fundo claro/branco)
- [ ] Logo monocromático preto
- [ ] Logo monocromático branco
- [ ] Símbolo/monograma solo (todas as versões acima)
- [ ] Favicon (32×32px, 16×16px)

**Formatos de entrega:**
- SVG (vetorial, web)
- PDF (vetorial, impressão)
- PNG 2× e 3× (digital)
- Figma components (para o time usar)

---

## 5. Sistema de Redes Sociais

> Foco principal: Instagram. O sistema é estendível para outras plataformas.

### 5.1 Arquitetura do Perfil Instagram

**Foto de perfil:**
```
Tamanho de entrega:  800 × 800px (exibido em ~110px)
Conteúdo:           Logo/monograma centralizado
Fundo:              Verde Noite (#03110D)
Elemento:           Símbolo/monograma em Caramelo
Teste:              Reconhecível em 110px sem zoom
```

**Bio (140 caracteres):**
```
Linha 1: BARBEIRA ANALU
Linha 2: [Cidade] • [especialidade se houver]
Linha 3: ✦ Agendamento pelo link
(sem emojis excessivos — máximo 1 por linha, e somente se fizer sentido)
```

**Destaques (Highlights):**
```
Covers: 1080 × 1920px (exibido como círculo 160px)
Design: Fundo Verde Noite + ícone simples em Caramelo ou inicial da categoria
Categorias sugeridas:
  - TRABALHO (portfólio de cortes)
  - PROCESSO (behind the scenes)
  - AGENDA (como agendar)
  - SOBRE (quem é Analu)
  - [nome do serviço principal]
```

---

### 5.2 Templates de Feed

**Template 01 — Portfólio de Trabalho (uso mais frequente)**
```
Formato:     1080 × 1350px (4:5) — melhor alcance orgânico
Estrutura:
  - Foto do trabalho ocupa 100% do fundo
  - Overlay gradient na parte inferior (gradient-foto-overlay)
  - Logo/assinatura no canto inferior direito — 100px de margem
  - Fonte do assinatura: Família B, 11px, Prata 60%
Variações:
  - Detalhe extremo (close no cabelo/navalha)
  - Resultado completo
  - Processo (mão + ferramenta)
```

**Template 02 — Frase / Citação**
```
Formato:     1080 × 1080px ou 1080 × 1350px
Estrutura:
  - Fundo sólido: Verde Noite ou Bordô
  - Frase em Família A, display-md, caixa alta, centralizada
  - Tracking: 0.10em
  - Cor do texto: Prata ou Caramelo (para palavras-chave)
  - Filete fino Caramelo separando frase e assinatura
  - Assinatura: BARBEIRA ANALU, Família B, caption, Prata 60%
  - Margens: 80px em todos os lados
```

**Template 03 — Produto/Serviço**
```
Formato:     1080 × 1080px
Estrutura:
  - Fundo: Verde Floresta (#16302B)
  - Nome do serviço: Família A, h2, caixa alta, Prata
  - Subtítulo/descrição: Família B, body, Prata 70%
  - Elemento decorativo: filete Caramelo horizontal ou vertical
  - Logo no canto (versão reduzida)
  - Opcional: preço em Caramelo (se quiser comunicar)
```

**Template 04 — Bastidores (Behind the Scenes)**
```
Formato:     1080 × 1350px
Estrutura:
  - Foto real, autêntica, levemente descontraída (mas ainda curada)
  - Overlay mínimo (só para legibilidade de texto se necessário)
  - Sem texto sobreposto obrigatório — deixa a foto falar
  - Logo discreta no canto
```

**Template 05 — Anúncio / Vaga de Agenda**
```
Formato:     1080 × 1080px
Estrutura:
  - Fundo: Bordô (#390517)
  - Texto principal: "AGENDA ABERTA" ou similar, Família A, display-lg
  - Texto secundário: dia/horário, Família B, body, Prata
  - CTA: "Link na bio" ou "Responda esse post"
  - Filete Caramelo como elemento
  - Sem urgência excessiva — elegante, não ansioso
```

---

### 5.3 Templates de Stories

**Formato base:** 1080 × 1920px
**Safe zone:** conteúdo entre y:150px e y:1750px (respeitar UI do Instagram)
**Margem lateral:** 80px

**Story 01 — Divulgação de trabalho**
```
- Foto de fundo full-bleed (ocupa 100%)
- Overlay gradient-foto-overlay na metade inferior
- Nome do serviço em Família A, h3, Prata, parte inferior
- Logo no canto superior (fora da safe zone? ajustar para dentro)
```

**Story 02 — Texto sobre fundo de marca**
```
- Fundo sólido Verde Noite ou Bordô
- Texto centralizado, Família A, display-md
- Máximo 2-3 palavras por linha
- Filete Caramelo como separador
```

**Story 03 — Agenda / CTA**
```
- Fundo: Verde Noite
- Ícone ou símbolo da marca no topo (centralizado)
- Texto: "HORÁRIOS DISPONÍVEIS" — Família A, h3
- Dias/horários: Família B, body, Prata
- Área de swipe up / botão: Bordô com texto Prata
```

**Story 04 — Repost de cliente (UGC)**
```
- Screenshot/repost com moldura da marca
- Moldura: 12px, Caramelo, bordas arredondadas 0
- Fundo extra: Verde Noite (25px ao redor)
- Logo no canto inferior direito
```

---

### 5.4 Capa de Reels

```
Formato:     1080 × 1920px (mesma specs que story)
Design:      Igual Story 01 ou Story 02
Regra:       TODA reel deve ter capa personalizada da marca
             Nunca deixar frame aleatório do vídeo como capa
```

---

### 5.5 Sistema de Feed — Estratégia Visual

**Regra de sequência (a cada 6 posts):**
```
Post 1: Portfólio (foto de trabalho, fundo escuro natural)
Post 2: Frase/citação (Template 02)
Post 3: Portfólio (detalhe — close em navalha, mão, textura)
Post 4: Produto/serviço ou bastidores
Post 5: Portfólio (resultado completo)
Post 6: Vaga de agenda ou frase curta
```

**Consistência de cor no feed:**
- Nunca dois posts de fundo claro seguidos
- Nunca mais de 3 posts de fundo verde seguidos sem um de fundo bordô
- O feed visto como grid 3×3 deve ter equilíbrio visual entre Verde Noite e Bordô

---

### 5.6 Extensão para Outras Plataformas

| Plataforma | Adaptação |
|---|---|
| TikTok | Mesmo sistema de Reels, mesma capa |
| Pinterest | Formato 2:3 (1000×1500px), mesmo sistema de Templates |
| WhatsApp Business | Foto de perfil = foto de perfil Instagram, status alinhado com bio |
| Google Meu Negócio | Fotos de capa e perfil seguem sistema de feed |

---

## 6. Direção de Fotografia e Conteúdo

> Brief para fotógrafo, videomaker ou para a própria Analu ao fazer conteúdo.

### 6.1 Estilo Fotográfico

**Palavras-chave visuais:**
precisão / textura / sombra rica / luz direcional / detalhe extremo / calma / maestria

**O que fotografar:**
- Mãos em movimento com a navalha — foco no gesto preciso
- Ferramentas em close: navalha, tesoura, pente — sobre superfícies nobres (mármore, couro, madeira escura)
- Resultado de cabelo — contra a luz, com textura visível
- Ambiente: o espaço de trabalho de Analu — mesmo que simples, fotografado com intenção
- Produto: produtos usados no trabalho — embalagens, frascos

**O que NÃO fotografar:**
- Antes e depois com moldura genérica
- Selfie sem intenção de enquadramento
- Flash direto (luz dura, sem sombra)
- Fundo branco sem propósito
- Emojis em fotos

### 6.2 Iluminação

```
Estilo:     Luz direcional (lateral ou diagonal) — Rembrandt lighting
Temperatura: Fria-neutra (5000K–5500K) — não amarelada
Sombras:    Presentes e intencionais — não eliminadas
Referências: Editorial masculino de moda, campanha Rolex, Porsche Magazine
```

### 6.3 Edição e Retoque

```
Estilo:     Matte escuro — levanta as sombras levemente, mantém profundidade
Saturação:  Reduzida (-10 a -20) — menos vibrante, mais sofisticado
Highlights: Contidos — não estourar brancos
Sombras:    Detalhadas — não fechar em preto total
Tom:        Tendência levemente esverdeada nas sombras (coerente com a paleta)
Filtros:    Nunca filtro quente/amarelado — destrói a identidade de cor
```

### 6.4 Vídeo / Reels

```
Proporção:   9:16 (vertical) para Reels/TikTok
             16:9 (horizontal) se for YouTube/conteúdo longo
Edição:      Cortes limpos — sem transições chamativas
Ritmo:       Lento para trabalho de precisão, ágil para resultado
Música:      Jazz instrumental / lo-fi sofisticado / jazz moderno
             Evitar: funk, axé, músicas virais genéricas
Legenda:     Subtítulos quando houver fala — fonte alinhada com identidade
```

---

## 7. Aplicações Físicas

### 7.1 Cartão de Visita

```
Dimensões:    85 × 54mm (padrão) ou 90 × 50mm (elegante slim)
Papel:        Triplex 600g (mínimo) ou Kraft 400g (alternativa orgânica)
Acabamento:   Laminação matte + hot stamp Caramelo (ideal)
              Ou: papelão preto texturizado + relevo seco

FRENTE:
  - Fundo: Verde Noite (#03110D) impresso
  - Logo/monograma centralizado em hot stamp Caramelo
  - Nada mais

VERSO:
  - Fundo: Verde Noite ou Bordô
  - ANALU em Família A, h4, Prata
  - Abaixo: BARBEIRA, Família B, caption, Prata 70%
  - Filete Caramelo horizontal separando nome de contatos
  - Contatos: WhatsApp, Instagram — Família B, body-sm, Prata
  - Cidade — Família B, caption, Prata 60%

MARGEM INTERNA: 8mm em todos os lados
```

### 7.2 Avental / Uniforme

```
Cor base:     Verde Noite (tecido) ou Preto profundo
              Alternativa: Bordô escuro
Material:     Sarja ou gabardine — acabamento fosco
Bordado:      Monograma BA ou logo completo
              Posição: peito esquerdo
              Cor do bordado: Caramelo (#A38560)
              Tamanho: 4cm × 4cm (monograma) ou 8cm × 3cm (logo horizontal)
Acabamento:   Sem estampas, sem patches coloridos
              Máximo 1 elemento de identidade
```

### 7.3 Embalagem (Produtos/Presentes)

```
Caixa/Sacola:
  - Cor: Verde Noite ou Kraft natural escuro
  - Logo em hot stamp Caramelo
  - Papel de seda interno: Preto ou Verde Noite
  - Fita: Caramelo ou Bordô

Tag de produto:
  - Papel: Kraft 300g ou cartão preto
  - Impressão: Logo + nome do produto + Família B, caption
  - Acabamento: fio Caramelo para amarrar

Lacre de cera:
  - Cor da cera: Bordô (#390517) — mistura de ceras vermelha + preta
  - Carimbo: monograma BA
  - Uso: caixas de presente, envelopes, convites de inauguração
```

### 7.4 Fachada / Sinalização

```
Tipografia:   BARBEIRA ANALU em Família A, caixa alta
              Acabamento: corte a laser em aço escovado ou alumínio preto
              Ou: adesivo recortado em espelho ou dourado fosco

Painel:       Fundo escuro (parede pintada Verde Noite #03110D)
              Logo/nome em destaque central ou lateral
              Iluminação: spot direcionado (não néon, não LED colorido)

Porta/vitrine: Adesivo jateado com monograma BA (translúcido/fosco)
```

---

## 8. Estrutura do Site

> UX brief para desenvolvedor e designer. Uma página de alta performance (landing page sofisticada).

### 8.1 Princípio de UX

Cada scroll aumenta o desejo. Não informa — seduz. O usuário deve chegar ao CTA querendo agendar, não apenas entendendo o serviço.

### 8.2 Estrutura de Seções (Single Page)

**Seção 01 — Hero**
```
Layout:      Full viewport (100vh)
Fundo:       Foto de alta qualidade + overlay gradient-foto-overlay
Headline:    "O CORTE QUE TE RECONHECE"
             Família A, display-xl, Prata, tracking 0.12em
Subheadline: 1 linha — quem é Analu em palavras mínimas
             Família B, body-lg, Prata 70%
CTA:         "AGENDE SEU HORÁRIO" — botão Bordô, texto Prata, sem bordas arredondadas
             (cantos retos = força, cantos arredondados = amigável — aqui é força)
Scroll hint: Seta ou filete animado para baixo, Caramelo
```

**Seção 02 — Quem é Analu**
```
Layout:      2 colunas (desktop) / 1 coluna (mobile)
Esquerda:    Foto editorial de Analu — iluminação direcional, pose natural, profissional
Direita:     Texto em 3–4 parágrafos curtos
             Não é currículo. É apresentação de personagem.
             "Analu [sobrenome] é barbeira há X anos..."
             Tom: primeira pessoa ou terceira pessoa — decidir e manter
Elemento:    Filete Caramelo vertical separando as colunas (desktop)
```

**Seção 03 — Serviços**
```
Layout:      Cards em grid 3 colunas (desktop) / 2 (tablet) / 1 (mobile)
Cada card:   Fundo Verde Floresta
             Nome do serviço — Família A, h3, Prata
             Descrição curta — Família B, body-sm, Prata 70%
             Valor opcional — Caramelo
             Sem imagens nos cards (clean)
             Hover: levantar card com sombra sutil
```

**Seção 04 — Portfólio**
```
Layout:      Grid masonry ou grade irregular — 3–4 colunas
             Fotos de trabalho selecionadas (10–16 fotos)
Hover:       Overlay com nome do serviço, Família B, caption
CTA ao final: "VER MAIS NO INSTAGRAM" — link para perfil
```

**Seção 05 — Depoimentos**
```
Layout:      Carrossel ou grid 2 colunas
Cada item:   Texto do depoimento — Família B, body, Prata, itálico
             Nome — Família A, h4, Caramelo
             Sem foto de cliente (privacidade, elegância)
Fundo:       Bordô Profundo (#390517)
```

**Seção 06 — Agendamento**
```
Layout:      Centralizado, espaço generoso
Headline:    "PRONTO PARA O SEU MELHOR CORTE?"
             Família A, display-md, Prata
CTA:         Botão principal "AGENDAR AGORA" — Caramelo, texto Verde Noite
             Botão secundário "FALAR NO WHATSAPP" — outline Prata
Fundo:       Verde Noite — o mais escuro, o mais íntimo
```

**Footer**
```
Informações: Logo + endereço + Instagram + WhatsApp
             Família B, caption, Prata 50%
Direito:     "© 2026 Barbeira Analu — Todos os direitos reservados"
Fundo:       Preto suave (#0A0A0A)
```

### 8.3 Especificações Técnicas

```
Performance: Imagens otimizadas (WebP, max 200kb cada)
Fontes:      Google Fonts se gratuitas, self-hosted se comerciais
Animações:   Fade-in suave ao scroll — nada abrupto
Mobile:      Mobile-first, touch-friendly, botões mínimo 48px de altura
Acessibilidade: Contraste mínimo 4.5:1 para textos (WCAG AA)
CTA:         Fixo no mobile (sticky bottom bar com "Agendar")
```

---

## 9. Estrutura do Brand Book

> O brand book é o documento físico/digital que o time usa como bíblia. Estrutura e conteúdo de cada seção.

### Sumário do Brand Book

```
CAPA
  Logo principal sobre Verde Noite / hot stamp Caramelo (se físico)

CONTRA-CAPA
  Frase de manifesto + filete Caramelo

SEÇÃO 01 — SOBRE A MARCA
  1.1 Nossa história (quem é Analu — narrativa humana)
  1.2 Nossa missão
  1.3 Nossa visão
  1.4 Nossos valores
  1.5 A essência: "O corte que te reconhece"

SEÇÃO 02 — POSICIONAMENTO
  2.1 Quem somos no mercado
  2.2 Para quem somos
  2.3 O que nos diferencia
  2.4 O que nunca somos

SEÇÃO 03 — PERSONALIDADE E VOZ
  3.1 Os 5 atributos da marca
  3.2 Tom de voz — guia prático
  3.3 Como escrevemos (com exemplos certos e errados)
  3.4 Palavras da marca / palavras proibidas

SEÇÃO 04 — LOGO
  4.1 Logo principal e variações
  4.2 Área de proteção
  4.3 Tamanhos mínimos
  4.4 Usos corretos
  4.5 Usos proibidos (contra-exemplos visuais)
  4.6 Versões por aplicação

SEÇÃO 05 — CORES
  5.1 Paleta primária e acento
  5.2 Valores de cor (HEX, RGB, CMYK, Pantone)
  5.3 Hierarquia e proporção de uso
  5.4 Combinações permitidas
  5.5 Combinações proibidas

SEÇÃO 06 — TIPOGRAFIA
  6.1 Família primária (serif) — usos e exemplos
  6.2 Família secundária (sans) — usos e exemplos
  6.3 Escala tipográfica
  6.4 Regras de estilo (tracking, weight, case)
  6.5 Usos proibidos

SEÇÃO 07 — LINGUAGEM VISUAL
  7.1 Estilo fotográfico
  7.2 Iluminação e composição
  7.3 Edição e retoque
  7.4 Exemplos aprovados
  7.5 Exemplos reprovados

SEÇÃO 08 — APLICAÇÕES DIGITAIS
  8.1 Instagram — perfil, feed, stories, reels, highlights
  8.2 Templates — cada template documentado
  8.3 Outras plataformas

SEÇÃO 09 — APLICAÇÕES FÍSICAS
  9.1 Cartão de visita
  9.2 Avental e uniforme
  9.3 Embalagens
  9.4 Fachada e sinalização
  9.5 Papelaria (se necessário)

SEÇÃO 10 — O QUE NÃO SOMOS
  Página de contra-exemplos visuais — o que nunca fazer
  (Esta seção é tão importante quanto as outras)

CONTRACAPA FINAL
  Logo + assinatura
```

---

## 10. Checklist de Qualidade

> Antes de aprovar qualquer entrega, verificar todos os itens.

### Logo
- [ ] Funciona em Verde Noite, Bordô e fundo branco
- [ ] Funciona em monocromático (preto e branco)
- [ ] Legível em tamanho mínimo digital (120px largura)
- [ ] Legível em tamanho mínimo impresso (25mm largura)
- [ ] Símbolo solo funciona em 32px
- [ ] Entregue em SVG, PDF, PNG 2×/3×

### Tipografia
- [ ] Contraste texto/fundo ≥ 4.5:1 (WCAG AA)
- [ ] Tracking generoso em todos os headlines
- [ ] Não há Bold + Uppercase juntos em display
- [ ] Duas famílias tipográficas, não mais

### Cores
- [ ] Nenhum componente usa cor fora da paleta definida
- [ ] Caramelo não aparece como bloco de fundo em nenhuma peça
- [ ] Fundo branco é raro e justificado

### Instagram
- [ ] Foto de perfil legível em 110px
- [ ] Todos os templates testados em iOS e Android
- [ ] Safe zone respeitada em Stories/Reels
- [ ] Toda Reel tem capa personalizada

### Site
- [ ] Contraste WCAG AA em todos os textos
- [ ] CTA visível acima da dobra no mobile
- [ ] Imagens ≤ 200kb (WebP)
- [ ] Sticky CTA no mobile

### Brand Book
- [ ] Cada seção tem exemplos certos E errados
- [ ] Valores de cor incluem HEX, RGB, CMYK, Pantone
- [ ] Fontes documentadas com link de download/compra
- [ ] Seção "O que não somos" incluída

---

*Documento elaborado por Design Chief — Design Squad*
*Para uso exclusivo da Barbeira Analu*
*Versão 1.0 — Abril 2026*
