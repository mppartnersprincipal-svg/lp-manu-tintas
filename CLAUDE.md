# CLAUDE.md — Manu Tintas & Ferragista

> Documento vivo do projeto. Atualizar sempre que houver mudanças de design, copy, estrutura ou decisões técnicas.

---

## Sobre o Projeto

**Cliente:** Manu Tintas & Ferragista
**Objetivo:** Landing page de alta conversão, mobile-first, para destino de anúncios no Meta Ads
**Meta de faturamento:** R$50k–R$70k/mês
**Budget de tráfego pago:** R$400/mês
**Canal de conversão principal:** WhatsApp
**Agência responsável:** M|P Assessoria

---

## Contatos e Redes Sociais

| Canal | Dado |
|---|---|
| WhatsApp / Telefone | (62) 99813-6715 |
| Instagram | @ManuTintas |
| Link wa.me | `https://wa.me/5562998136715` |
| Endereço | Av. Contorno, 2975 - Qd 08 - Res. Maringa, Goiânia - GO, 74473-838 |

---

## Identidade Visual

### Paleta de Cores (extraída da logo oficial)

```css
--navy-primary: #1B2D6B;   /* Azul marinho — cor institucional (header, fundos, footer) */
--navy-dark:    #122050;   /* Navy escuro — hover, footer mais profundo */
--red-accent:   #CC1B1B;   /* Vermelho — ação, CTAs, badges, "E FERRAGISTA" */
--red-dark:     #A01515;   /* Vermelho escuro — hover de botões vermelhos */
--yellow-hl:    #F5C518;   /* Amarelo — badges pontuais, detalhes da fachada */
--gray-light:   #F7F7F7;   /* Cinza claro — fundos alternados de seção */
--gray-text:    #444444;   /* Texto corrido */
--white:        #FFFFFF;   /* Texto sobre fundos escuros */
--wa-green:     #25D366;   /* WhatsApp — exclusivo para botões de WA */
--wa-dark:      #128C7E;   /* WhatsApp hover */
```

### Tipografia

```
Google Fonts:
- Barlow Condensed (700, 800) → Headlines, títulos de seção, nome da marca
- Inter (400, 500, 600)       → Corpo de texto, labels, botões, subtítulos
```

### Logo

- **Arquivo:** `assets/logo.pdf` (logo original PDF fornecida pelo cliente)
- **Composição:** Casa em azul marinho + roda dentada vermelha + ferramentas (martelo, chave, rolo de pintura, pincel) + texto "MANU TINTAS" (navy) + "E FERRAGISTA" (vermelho)
- **Uso:** Header sticky (altura 44px) + Footer (centralizada)
- **Implementação:** Usar `<img src="assets/logo.pdf">` para browsers modernos. Se houver problemas de compatibilidade, converter para PNG.

---

## Produtos e Público

### Produtos Principais
1. Tinta imobiliária — Diamante, Collor, NewColor
2. Material elétrico
3. Material hidráulico
4. Chuveiros e filtros
5. Esmalte sintético e verniz
6. Tinta automotiva
7. Produtos de ferragista em geral

### Público-Alvo
- **Perfil:** Prestadores de serviço (pintores, eletricistas, encanadores), consumidor final, lojistas
- **Localização:** Perto do Friboi, aeródromo, aeroporto
- **Faixa etária:** 25+
- **O que valoriza:** Atendimento de qualidade e indicação

### Concorrentes
- Ferragista Machado (Av. do Contorno)
- Maranata Ferragista
- Premissas Tintas
- Central das Tintas

---

## Estrutura de Arquivos

```
LP - Manu Tintas/
├── CLAUDE.md                        ← Este arquivo
├── index.html                       ← Landing page (HTML + CSS + JS embutidos)
├── Briefing.pdf                     ← Kick-off original com o cliente
├── Logo loja.pdf (1).pdf            ← Logo original do cliente
└── assets/
    ├── logo.pdf                     ← Cópia da logo para uso na página
    └── imgs/
        ├── fachada.jpeg             ← Foto da fachada externa da loja
        ├── interior-estoque.jpeg    ← Corredor interno com estoque variado
        ├── interior-tintas.jpeg     ← Interior com latas Collor/Diamante
        └── interior-esmaltes.jpeg  ← Depósito com esmaltes e vernizes
```

---

## Estrutura da Landing Page (11 Seções)

| # | Seção | Objetivo | CTA |
|---|---|---|---|
| 1 | Header sticky | Navegação + acesso rápido | Botão WA verde |
| 2 | Hero | Capturar atenção, proposta de valor | Botão WA vermelho grande + tel |
| 3 | Barra de benefícios | Reforçar confiança (3 pilares) | — |
| 4 | Grid de categorias (6) | Mostrar amplitude do catálogo | Cada card abre WA contextual |
| 5 | Marcas parceiras | Prova social de qualidade | — |
| 6 | Para profissionais | Segmentar pintores/eletricistas/encanadores | Botão WA "condições especiais" |
| 7 | Por que a Manu Tintas | Diferenciar da concorrência | — |
| 8 | Localização + horário | Reduzir fricção para visita física | Botão "Traçar rota" |
| 9 | CTA final | Última chance de conversão | Botão WA grande + tel |
| 10 | Footer | Informações institucionais | — |
| 11 | Botão WA flutuante | Conversão a qualquer momento | Sempre visível |

---

## Mensagens WhatsApp Pré-preenchidas

| Contexto | Mensagem |
|---|---|
| Hero / Flutuante | `Olá! Vim pelo site da Manu Tintas e gostaria de um atendimento` |
| Card Tintas | `Olá! Preciso de tintas imobiliárias. Podem me ajudar com preço e disponibilidade?` |
| Card Elétrico | `Olá! Preciso de material elétrico. Têm disponível?` |
| Card Hidráulico | `Olá! Preciso de material hidráulico. Podem me ajudar?` |
| Card Chuveiros | `Olá! Tenho interesse em chuveiros e filtros. O que vocês têm?` |
| Card Esmalte/Verniz | `Olá! Preciso de esmalte sintético ou verniz. Quais marcas e preços?` |
| Card Automotiva | `Olá! Preciso de tinta automotiva. Podem me ajudar?` |
| Profissionais | `Olá! Sou profissional e gostaria de condições especiais para compras frequentes` |
| CTA Final | `Olá! Quero resolver tudo com vocês. Podem me atender?` |

---

## Decisões Técnicas

| Decisão | Escolha | Motivo |
|---|---|---|
| Stack | HTML + CSS + JS (sem framework) | Zero dependência, deploy simples em qualquer hospedagem |
| CSS | Custom properties + Flexbox/Grid | Controle total, sem peso de Tailwind CDN |
| Fontes | Google Fonts (Barlow Condensed + Inter) | Gratuito, identidade visual coerente com a marca |
| JS | Embutido, < 5KB | Scroll do header, botão flutuante, lazy maps |
| Mapa | Google Maps iframe com lazy load | Não penaliza carregamento inicial no mobile |
| Imagens | JPEGs locais da loja | Autenticidade e confiança do visitante |
| Logo | PDF → `<img>` ou PNG | Máxima qualidade em telas retina |
| Responsivo | Mobile-first: base = mobile, `min-width` para tablet/desktop | Sem `max-width` overrides — garante performance e legibilidade em celulares |

### Breakpoints (Mobile-First)

| Breakpoint | Largura | Comportamento |
|---|---|---|
| Base (mobile) | < 640px | 1 coluna, padding 48px, hero CTAs empilhados, texto curto no header |
| Tablet | ≥ 640px | 2 colunas, padding restaurado (72–80px), hero CTAs lado a lado |
| Desktop | ≥ 900px | 3–4 colunas, fontes maiores, tooltip do botão flutuante visível |

### Touch UX
- `-webkit-tap-highlight-color: transparent` + `touch-action: manipulation` em `.btn`, `.produto-card`, `.header-cta`
- `min-height: 44px` no `.header-cta` (Apple HIG tap target)
- Botão flutuante WA: 60px × 60px (tap target adequado)
- Tooltip do float: `display: none` no mobile (sem hover em touch); reaparece no desktop (≥ 900px)

---

## Informações Pendentes (confirmar com cliente)

- [x] Endereço completo da loja — Av. Contorno, 2975 - Qd 08 - Res. Maringa, Goiânia - GO, 74473-838
- [x] Número de WhatsApp validado — (62) 99813-6715
- [ ] Horário de funcionamento (dias e horas exatos)
- [ ] Confirmar se aceita pedidos/orçamentos só pelo WA ou também por e-mail

---

## Histórico de Alterações

| Data | Alteração |
|---|---|
| 2026-04-14 | Criação inicial do projeto — CLAUDE.md + estrutura de arquivos |
| 2026-04-14 | Paleta atualizada para navy + vermelho (logo oficial) |
| 2026-04-14 | Otimização Mobile-First completa — CSS reestruturado para `min-width` only, paddings reduzidos no mobile, touch UX, `.show-xs`/`.hide-xs` corrigidos, `@media (max-width)` eliminado |
