# 🔍 Auditoria SEO Completa — Engeplena Engenharia

**URL auditada:** https://www.engeplena.com.br
**Data da auditoria:** 2026-08-13
**Negócio:** Engenharia civil e consultoria ambiental · Itabirito/MG · Serviço local (híbrido: escritório físico + área de atuação)
**Plataforma:** Site estático em HTML no GitHub Pages (este repositório é a fonte do site em produção)

---

## ✅ Dados Oficiais Confirmados (2026-08-13) — CONFEA + CNPJ

Consulta realizada hoje no CONFEA (sistema de registro profissional) e em registro de CNPJ. Estes dados **resolvem lacunas das seções C3, H9 e do schema (Seção 7)**: agora há números reais de registro e um endereço canônico verificado.

### Registros CREA (fonte: CONFEA)

| Engenheiro(a) | Registro Nacional | Data de Registro | CREA | Situação | Título | Atribuições |
|---|---|---|---|---|---|---|
| **ANTONIO CARLOS CUNHA JUNIOR** | 1402661576 | 09/04/2003 | CREA-MG | Ativo | Engenheiro Civil | Art. 7º Res. 218/73 CONFEA |
| **JUNAIA DE PAULA LACERDA** | 1402661533 | 28/06/2004 | CREA-MG | Ativo | Engenheira Civil | Art. 7º Res. 218/73 CONFEA |

**Notas:**
- Nenhum visto em outros CREAs para ambos.
- O CONFEA **não registra os cursos de pós-graduação** (os dados de UFOP/INBEC/IETEC/IPOG divulgados no site vêm dos currículos da equipe, não do registro profissional — não são contraditórios, apenas fontes distintas).
- "Registro Nacional" é o identificador oficial no sistema CONFEA → usar como número de registro na exibição e no schema.

### CNPJ (fonte: Receita Federal / registro público)

| Campo | Valor |
|---|---|
| Razão Social | **ENGEPLENA ENGENHARIA LTDA - ME** |
| CNPJ | **07.936.059/0001-35** |
| Fundação | **05/04/2006** (20 anos, 4 meses e 8 dias) |
| Situação | **Ativa** |
| Natureza Jurídica | 206 — Sociedade Empresária Limitada |
| Matriz/Filial | Matriz |
| Endereço | **Rua Carlos Michel, 66 — Centro, Itabirito/MG, CEP 35450-078** |
| Atividade Principal | 7112-0/00 — Serviços de engenharia |
| Atividades Secundárias | 1813-0/99 (plotagem), 4321-5/00 (elétrica), 4322-3/01 (hidráulica), 4330-4/99 (acabamento), 4399-1/03 (alvenaria), 7119-7/99 (atividades técnicas) |

**Impacto na auditoria:**
- **Resolve a discrepância de endereço (H9):** o registro oficial confirma **Rua Carlos Michel, 66, CEP 35450-078** (não Pio XII 109). O CNPJ **não registra sala/complemento** → **remover "Sala 306" do schema** (a sala pertencia ao endereço Pio XII 109, de registros agregadores desatualizados).
- **`foundingDate` confirmado:** 2006-04-05.
- **`taxID` confirmado:** 07.936.059/0001-35.
- **Homônima do RJ** (CNPJ 00.562.202/0001-27) é empresa diferente — não usar seus dados em nenhuma citação da Engeplena de Itabirito.
- A exibição na página pode usar o nome fantasia "Engeplena Engenharia" + CNPJ; a razão social com "- ME" fica registrada no `legalName` do schema.

---

## 📊 SEO Health Score: **62 / 100**

| Categoria | Peso | Nota | Fonte |
|---|---|---|---|
| SEO Técnico | 22% | 72 | seo-technical |
| Qualidade de Conteúdo | 23% | 44 | seo-content (E-E-A-T 47) |
| SEO On-Page | 20% | 55 | derivada (title/meta bons; `lang="en"`, keyword local comentada no H1) |
| Schema / Dados Estruturados | 10% | 75 | seo-schema |
| Performance (CWV) | 10% | 92 | seo-performance (mobile 100 / desktop 84) |
| Prontidão para Busca com IA | 10% | 54 | seo-geo |
| Imagens | 5% | 55 | derivada (alts bons, webp no hero; fonte de ícones 312 KB, JPEGs pesados) |

**Sub-notas:** Sitemap 77 · Visual/Mobile 72 · SXO 51 · SEO Local 54 · GEO 54 · Backlinks 18 (estimativa — sem dados ao vivo).

> **Diagnóstico em uma frase:** um site estático limpo e rápido, cuja arquitetura de página única e a ausência de sinais de credibilidade/imposto o impedem de ranquear para as buscas de serviço que realmente trazem clientes de engenharia. O site é tecnicamente sólido, mas *subdimensionado* para sua categoria — e um dos botões de conversão centrais está quebrado no mobile.

---

## 🔍 Síntese (PERCEBE → ANALISA → VALIDA → AGE)

- **PERCEBE:** A homepage é uma página única bem construída e rápida. Porém, todos os itens do menu são âncoras `#` — `/servicos`, `/contato`, `/portifolio` retornam 404. Os seis serviços que geram receita existem como cards de ~25 palavras. A seção "Clientes" publica placeholders de template (`site-do-parceiro.com`). As credenciais reais da equipe (UFOP, INBEC, M.Sc.) estão expostas, mas CREA/CNPJ/ART aparecem **zero** vezes.
- **ANALISA:** A tensão central é arquitetura vs. intenção. As evidências de SERP (via proxy) mostram que "projeto estrutural mg" e "consultoria ambiental itabirito" premiam *páginas de serviço dedicadas e landing pages locais* — estruturas que o site literalmente não consegue produzir. Toda fraqueza a jusante (sem backlinks profundos, sem schema de serviço, citações finas, colapso de extração para IA) remonta a essa única decisão.
- **VALIDA:** O que é *real e funciona*: CWV mobile totalmente verdes, engenharia de LCP excelente (webp preload, srcset), JSON-LD LocalBusiness rico e válido, redirects www/https limpos, sócios reais nomeados, NAP real. O que *dói agora*: logos de clientes fabricados em produção, botão WhatsApp do mobile quebrado, e uma página que extratores de IA leem como ~5% do conteúdo.
- **AGE:** Corrigir confiança + fundamentos primeiro (barato, reversível), depois construir a arquitetura que destrava o ranqueamento. Cada recomendação abaixo carrega uma verificação de falsificabilidade.

---

## 🔴 Crítico (correção imediata)

| # | Descoberta | Evidência |
|---|---|---|
| C1 | **Sem páginas de serviço dedicadas** — 6 serviços de receita comprimidos em ~25 palavras cada em uma única homepage; impossível ranquear para "projeto estrutural mg", "consultoria ambiental itabirito", "laudo técnico regularização". | Proxy de SERP: concorrentes vencem com páginas dedicadas `/projeto-estrutural-*` e landing pages por cidade; todas as URLs internas retornam 404 |
| C2 | **Logos de clientes fabricados em produção** — 4 links-follow para `site-do-parceiro.com` / `site-parceiro-c.com`, "Empresa Parceira 1–3", nomes genéricos "Construtora Rocha"/"Imobiliária Silva". Parece prova social falsa; vaza equity para domínios mortos. | `index.html` `#s-partners` (~linhas 776–818); confirmado no HTML ao vivo |
| C3 | **Zero credenciais profissionais** — sem CREA, sem ART, sem CNPJ, sem "Responsável Técnico". O CNPJ (07.936.059/0001-35) é público, mas nunca exibido. Para uma empresa que vende entregáveis assinados por ART, isso é uma lacuna fatal de E-E-A-T. | grep: 0 ocorrências de CREA/CNPJ/ART no HTML |
| C4 | **CLS desktop 0.314 (ruim)** — única falha de CWV. `autoHeight:true` no Swiper do banner + troca de fonte Poppins/Roboto após o primeiro paint empurra a seção "sobre" ~290px para baixo. | Lighthouse desktop; `js/script.js` `bannerSwiper` |

## 🟠 Alto (1 semana)

| # | Descoberta | Evidência |
|---|---|---|
| H1 | **`<html lang="en">` em site 100% pt-BR** (enquanto `og:locale` diz `pt_BR`) — enfraquece a segmentação de idioma e pode suprimir a página para buscas em português | `index.html` linha 2 (também `og:locale`) |
| H2 | **Ícone de WhatsApp do cabeçalho mobile aponta para o Facebook** — o principal canal de conversão abre o site errado | `index.html` linhas 229–231: ícone de WhatsApp + `aria-label="Facebook"` + `href="facebook.com/engeplena"` |
| H3 | **Sem CTA de WhatsApp/telefone acima da dobra no mobile** — o float está `display:none` no CSS mobile; redes sociais do cabeçalho dentro da drawer fechada; botões de card de serviço com 19px | captura de viewport mobile; `css/style.css` media query mobile |
| H4 | **Shell Flutter `/app/` indexável** — título padrão "gestor_obras", descrição "A new Flutter project.", 4,5 MB, zero texto rastreável, órfão (sem links internos, fora do sitemap) | `app/index.html`; render ao vivo extrai 0 palavras |
| H5 | **Números-chave renderizam como "0" sem JS** — contadores animam `0` → alvo ao rolar; crawlers/IA leem "0+ anos", "R$ 0 Mi+" | `<span class="num-js" data-count="20">0</span>` + `animateCounter()` |
| H6 | **Sem cabeçalhos de segurança** (HSTS, X-Frame-Options, nosniff, CSP) + `Access-Control-Allow-Origin: *` — GitHub Pages não permite configurar headers; precisa de Cloudflare na frente | headers de resposta ao vivo |
| H7 | **Perfil de backlinks quase zero** — domínio ausente do Common Crawl em 2024–2026 (~10 crawls); sem citações de CREA/prefeitura/contratações | consultas ao CC web graph + CDX |
| H8 | **Sem programa de avaliações / sinais de confiança no GBP** — avaliações 2,5/10; sem solicitação de reviews, sem depoimentos, sem `aggregateRating` | ausência on-page; sinais públicos de GBP |
| H9 | **Inconsistências de NAP** — "Sala 306" no schema mas não no rodapé; `addressRegion: "Minas Gerais"` vs `MG`; geo do schema ~13 m do pin do GBP; **endereço registrado no CNPJ é Rua Pio XII, 109** enquanto site/GBP mostram R. Carlos Michel, 66 | schema vs rodapé vs agregadores de CNPJ (Casa dos Dados) |
| H10 | **Colapso de extração para IA** — extratores de boilerplate (trafilatura) retêm ~33 de 673 palavras (~5%); passagens com 11–35 palavras vs. a faixa ideal de 134–167 | teste de extração trafilatura |
| H11 | **Fonte de ícones Material Symbols de 312 KB** = 34% do peso mobile para ~10 glifos | auditoria de recursos Lighthouse |

## 🟡 Médio (1 mês)

- `lastmod` do sitemap desatualizado (2025-12-27 vs. 2026-03-25) + tag `priority` obsoleta
- `/index.html` duplicado retorna 200 (não 301)
- Keyword local do H1 "em Itabirito e Região" está **comentada** (artefato de comentário quebrado `..--›`)
- Erros de português: "**Portifólio**" (menu, ×2), "aprimoramento **continuo**", "**todas os serviços**", "nos segmentos **que atuamos**"
- Sem `tel:` click-to-call (telefone embrulhado em `wa.me`)
- Formulário de contato só via WhatsApp, sem backend, sem confirmação, sem aviso de privacidade/LGPD
- Presença no GuiaMais **ocupada por homônima do Rio de Janeiro** (CNPJ 00.562.202/0001-27, categoria errada); Bing Places provavelmente ausente
- Estatísticas não verificáveis (+150.000 m², R$ 140 Mi+) sem respaldo em case studies
- Sem `llms.txt`; sem diretivas explícitas de crawlers de IA (aberto apenas por padrão)
- Cache TTL de 10 min (`max-age=600`) → ~1,8 MiB desperdiçados em visitas de retorno no desktop
- Sem Brotli; 1 stylesheet bloqueante (~150 ms); ~92 KB de JS não utilizado
- Loop infinito de `requestAnimationFrame` do cubo 3D (custo de main-thread/bateria no mobile)
- JPEGs pesados de portfólio abaixo da dobra (até 504 KB) sem WebP; `why-bg.jpg` sem dimensões
- Alvos de toque de conversão mobile < 48px (botões de serviço 19px, links do rodapé 25px, CTA do banner 39px); texto do CTA do banner mobile com 12px
- CLS mobile 0.052 (shift de 0.037 de uma seção animada por wow)
- Sem frescor: sem conteúdo datado, copyright 2025, lastmod do sitemap desatualizado
- Inconsistência de rótulo no menu: desktop "Equipe" vs. mobile "História" → ambos para `#s-team`

## 🟢 Baixo (backlog)

- JSON-LD colocado **antes do `<head>`** (linha 3, sem elemento `<html>`) — mover para o head
- Lacunas de schema: sem `logo`, `email`, `@id`, `foundingDate`, `taxID`, `hasCredential`, `Person` para os dois engenheiros
- `telephone` como array (schema.org tipa como `Text`); `url` sem barra final
- `favicon.ico` 404 (o site usa corretamente um SVG); links mortos `href="#"` no rodapé
- ~4–5 MiB de imagens não utilizadas no repo (`client-*.jpg`, `gallery-4/7/10/11/12.jpg`, `team-*.jpg`, etc.)
- JPEGs da equipe 150×150 declarados como 400×400 (upscale borrado); `height="auto"` inválido no logo do rodapé
- IndexNow não configurado (baixo valor — site estático, só importa se páginas de serviço/blog forem adicionadas)
- `meta name="keywords"` (obsoleto); hrefs de WhatsApp com acentos não codificados

---

## 🛠️ Plano de Ação Priorizado

### Fase 1 — Confiança e fundamentos (dias 1–7) — mais barato, maior impacto em confiança

1. **Corrigir H1** (`lang="en"` → `lang="pt-BR"`) — *Falsificação:* após o deploy, `grep lang` mostra pt-BR; o teste de rastreamento mostra idioma português.
2. **Remover ou substituir logos de clientes placeholder (C2)** — substituir por clientes reais autorizados ou excluir a seção.
3. **Corrigir o botão WhatsApp→Facebook do mobile (H2)** — apontar para `https://wa.me/5531987950463`; deduplicar os dois links do Facebook.
4. **Adicionar CREA/CNPJ no rodapé + seção Equipe (C3)** — exibir CNPJ 07.936.059/0001-35, números CREA-MG, "Responsável Técnico". *Indicador antecedente:* melhor correspondência de entidade no Knowledge Panel.
5. **Noindex do `/app/` (H4)** — `Disallow: /app/` no robots.txt + `<meta name="robots" content="noindex">` em `app/index.html`; corrigir seus metadados padrão.
6. **Restaurar keyword local no H1 + corrigir erros de português** — descomentar "em Itabirito e Região"; corrigir "Portfólio", "contínuo", "todos os serviços", "em que atuamos".

### Fase 2 — O destravamento do ranking (semanas 2–6) — construir a arquitetura

7. **Criar 6 páginas de serviço dedicadas (C1)** — `/servicos/projetos-estruturais/`, `/servicos/consultoria-ambiental/`, `/servicos/laudos-e-pericias/`, `/servicos/gestao-de-obras/`, `/servicos/execucao-de-obras/`, `/servicos/plotagem/`. Cada uma com ~800 palavras: processo, entregáveis, regulamentações (NBR 13752, licenciamento LP/LI/LO), para quem, cronograma, FAQ. Adicionar schema `Service` por página + atualizar o sitemap. *Falsificação:* em 8–12 semanas, páginas aparecem no índice do Google (`site:engeplena.com.br/servicos`).
8. **Tornar as estatísticas rastreáveis (H5)** — renderizar valores reais como texto estático, animar como aprimoramento.
9. **Adotar o JSON-LD pronto do agente de schema** — corrige NAP/Sala 306, região→MG, alinhamento do geo, adiciona logo/email/@id (`index.html` linhas 3–115).
10. **Adicionar `tel:` click-to-call** junto aos CTAs de WhatsApp.

### Fase 3 — Performance (semanas 3–8)

11. **Corrigir CLS desktop (C4)** — preload dos woff2 de Poppins/Roboto, remover `autoHeight:true`, corrigir CSS `.slide-bg` → desktop 84 → ~99. *Indicador antecedente:* CrUX CLS desktop < 0,1.
12. **Substituir a fonte de ícones por SVG inline (H11)** → cortar ~300 KB nos dois formatos.
13. **Re-encodar JPEGs de portfólio + `why-bg` para WebP com dimensões** (~60–75% menores).

### Fase 4 — Autoridade e local (contínuo)

14. **GBP: verificar categoria primária** ("Engenheiro civil"/"Serviços de engenharia"), lançar programa de avaliações (meta de 10+ reviews, depois ≥1 a cada 18 dias), adicionar fotos/posts.
15. **Resolver a discrepância de endereço do CNPJ** (Pio XII vs. Carlos Michel) — confirmar com a Receita Federal; limpar o GuiaMais (criar ficha em Itabirito, sinalizar a homônima do RJ).
16. **Construção de citações** — CREA-MG, Prefeitura de Itabirito, PNCP/ComprasNet, SINDUSCON-MG, Bing Places, Apple Business Connect, imprensa local. (Nota de backlinks 18 → meta de 40+ em um ano.)

*Nota de dependência:* a Fase 2 (páginas de serviço) é pré-requisito para a maior parte da construção de links (links profundos precisam de páginas para apontar) e para as vitórias de citação IA e pacote local. As Fases 1 e 3 são independentes e podem rodar em paralelo.

---

## 📈 Detalhamento por Sub-Análise

### 1. SEO Técnico — **72/100**

| Categoria | Nota | Status |
|---|---|---|
| Rastreabilidade | 85 | Passa (com ressalvas) |
| Indexabilidade | 65 | Falha parcial |
| Segurança | 55 | Falha |
| Estrutura de URL | 85 | Passa (duplicata menor) |
| Mobile | 80 | Passa (menor) |
| Core Web Vitals | 70 | Parcial (laboratório) |
| Dados Estruturados | 85 | Passa |
| Renderização JavaScript | 70 | Passa para `/` / Falha para `/app/` |
| IndexNow | 40 | Não configurado |

- robots.txt válido com referência ao sitemap; 404 correto (mas sem `404.html` personalizado em português)
- Canonical auto-consistente, H1 único, title único (61 chars), meta description ~158 chars
- Redirects 301 limpos: `http://www` → `https://www`, `http://` → `https://www`, sem-www → www, `/app` → `/app/`
- Faltam headers de segurança (HSTS, X-Frame-Options, nosniff, CSP); `ACAO: *` presente

### 2. Qualidade de Conteúdo & E-E-A-T — **44/100** (E-E-A-T composto 47)

| Pilar | Nota |
|---|---|
| Experiência (20%) | 55 |
| Expertise (25%) | 55 |
| Autoridade (25%) | 30 |
| Confiabilidade (30%) | 50 |
| **Prontidão para citação por IA** | 62 |

- Total de texto visível: ~534 palavras (acima do piso de 500 da homepage, mas por pouco)
- Seção "Sobre" 67 palavras (benchmark 400); cada serviço ~25 palavras (benchmark 800 cada)
- Equipe com credenciais reais (UFOP, INBEC, IETEC, IPOG) — ativo mais forte da página
- Sem CREA/CNPJ/ART; seção de clientes com placeholders; portfólio somente com títulos
- Erros de gramática portuguesa que prejudicam o sinal de profissionalismo
- Marcadores de conteúdo de baixa qualidade do QRG de set/2025 presentes (estrutura repetitiva de cards)

### 3. Schema / Dados Estruturados — **75/100**

- 1 bloco JSON-LD válido: `HomeAndConstructionBusiness` com NAP, geo, horários, 6 `Service` offers, `sameAs`
- Sem tipos obsoletos (HowTo, FAQPage); FAQPage foi aposentado pelo Google em 07/05/2026 — não recomendar
- Inconsistências: "Sala 306" no schema mas não no rodapé; `addressRegion: "Minas Gerais"` vs `MG`; geo ~13 m do pin do GBP
- Bloco colocado antes do `<head>` (HTML malformado)
- JSON-LD recomendado (pronto para colar) foi fornecido pelo agente de schema

### 4. Sitemap & Estrutura — **77/100**

- `/sitemap.xml` existe, válido, referenciado no robots.txt; contém **1 URL** (a homepage)
- `lastmod` desatualizado (2025-12-27 vs. 2026-03-25); tag `priority` obsoleta
- `/index.html` duplicado retorna 200 (não 301)
- `/app/` indexável e fino (shell Flutter); não no sitemap
- Links de rodapé mortos (`href="#"`); links de parceiros placeholder (`site-do-parceiro.com`)

### 5. Performance / CWV — **92/100** (mobile 100 / desktop 84)

| Métrica | Mobile | Desktop | Limiar (Bom) | Veredito |
|---|---|---|---|---|
| **LCP** | 1,9 s | 0,5 s | ≤ 2,5 s | Passa |
| **CLS** | 0,003 | **0,314** | ≤ 0,1 | Mobile passa / **Desktop FALHA** |
| **INP** | est. < 200 ms | est. < 200 ms | ≤ 200 ms | Provavelmente passa |

- Peso da página: 919 KiB mobile / 2.582 KiB desktop (fonte de ícones 312 KB + JPEGs de portfólio pesados)
- Cache TTL 10 min; apenas gzip, sem Brotli; 1 stylesheet bloqueante; ~92 KB JS não utilizado
- Loop infinito de `requestAnimationFrame` do cubo 3D
- Engenharia de LCP excelente (webp preload, `fetchpriority`, `srcset`)

### 6. Visual / Mobile — **72/100**

- Renderização limpa: 0 imagens quebradas, 0 erros de console, sem scroll horizontal
- **Bug funcional:** ícone de WhatsApp do cabeçalho mobile aponta para o Facebook (`index.html:229–231`)
- **Sem CTA de WhatsApp/telefone acima da dobra no mobile** (float `display:none`)
- Alvos de toque abaixo de 48px: botões de serviço **19px**, links do rodapé 25px, CTA do banner 39px
- Texto do CTA do banner mobile com **12px**; CLS mobile 0.052
- CLS desktop excelente (0.002); imagens pesadas abaixo da dobra (gallery-8 516 KB, gallery-9 316 KB)

### 7. GEO / Prontidão para IA — **54/100**

| Plataforma | Nota |
|---|---|
| Google AI Overviews | 45 |
| ChatGPT web search | 35 |
| Perplexity | 50 |
| Bing Copilot | 50 |

- **Crítico:** extratores de boilerplate retêm ~5% do conteúdo (33 de 673 palavras); passagens 11–35 palavras vs. ideal 134–167
- **Alto:** estatísticas JS-animadas leem "0+" sem JS; `lang="en"` em conteúdo português
- Acessibilidade de crawlers de IA: passa (aberto por padrão); sem `llms.txt` (404)
- Presença off-domain fraca (sem Wikipedia, YouTube, Reddit, LinkedIn); `sameAs` só Instagram/Facebook
- Sem `datePublished`/`dateModified`

### 8. SXO (Experiência de Busca) — **51/100**

| Intenção | Tipo de página vencedora | Tipo da Engeplena | Gravidade |
|---|---|---|---|
| engenheiro civil itabirito | Listas de vagas (LinkedIn, Catho…) | Homepage local | MÉDIO (keyword errada) |
| projeto estrutural mg | Página de serviço dedicada | Card na homepage | ALTO |
| consultoria ambiental itabirito | Landing page local / Gov | Card na homepage | ALTO |
| empresa de engenharia itabirito | Homepage local | Homepage local | **ALINHADO** |
| laudo técnico regularização | Blog post + Página de serviço | Card na homepage | ALTO |

- Persona mais fraca: proprietário de imóvel precisando de regularização/laudo (41/100)
- Confiança é a dimensão mais fraca (sem CREA/CNPJ/ART, clientes placeholder, sem depoimentos)
- WhatsApp com mensagens pré-preenchidas por serviço é melhor prática genuína
- Sem `tel:` click-to-call; formulário de contato não captura o serviço desejado

### 9. SEO Local — **54/100**

| Dimensão | Peso | Nota | Ponderado |
|---|---|---|---|
| Sinais GBP | 25% | 7,5/10 | 18,8 |
| Avaliações & Reputação | 20% | 2,5/10 | 5,0 |
| SEO Local On-Page | 20% | 5,5/10 | 11,0 |
| NAP & Citações | 15% | 5,0/10 | 7,5 |
| Schema Local | 10% | 8,5/10 | 8,5 |
| Links & Autoridade Local | 10% | 3,5/10 | 3,5 |
| **Total** | | | **54,3** |

- Tipo de negócio: **HÍBRIDO** (SAB + escritório físico) — classificação correta; manter endereço visível no GBP (serviço de plotagem walk-in)
- **CNPJ endereço registrado: Rua Pio XII, 109, Sala 306** vs. site/GBP: R. Carlos Michel, 66 → risco de consistência de entidade
- Homônima no RJ (CNPJ 00.562.202/0001-27) ocupa o GuiaMais → perigo de resolução de entidade no Knowledge Graph
- GBP confirmado (place ID `0x3cf05f87311d2d10`); sem avaliações visíveis; sem programa de reviews
- Categoria primária do GBP não verificável sem acesso ao painel (#1 fator do pacote local)
- Vantagem de proximidade em Itabirito (Quadrilátero Ferrífero, demanda de mineração)

### 10. Backlinks — **18/100** (estimativa — sem dados ao vivo)

- **Sem dados ao vivo:** domínio ausente do Common Crawl (web graph + índice CDX) em ~10 crawls de 2024–2026; Moz/Bing/DataForSEO não configurados
- Domínio registrado em 2012-10-03; site atual é um rebuild recente (2026-03-25) de um domínio antigo mas com pouco peso
- Único órfão real: `/app/` (Flutter, indexável, sem links internos)
- Links de parceiros placeholder com `rel` follow passam equity para domínios mortos
- Estratégia de citações de alta prioridade: GBP → CREA-MG → Prefeitura de Itabirito → PNCP/ComprasNet → ABNT → SINDUSCON-MG → imprensa local → clientes reais → diretórios (GuiaMais, Apontador, Bing Places)

---

## ⚠️ Limitações Metodológicas

- **Sem Google API keys:** sem dados de campo CrUX (Core Web Vitals são laboratoriais), sem status de indexação no GSC, sem tráfego GA4
- **Backlinks:** sem Moz/Bing/DataForSEO — o score de 18 é uma estimativa qualitativa, não medida
- **SERP via proxy:** WebSearch não reflete o SERP localizado/geofenced do Google no Brasil (sem local pack, PAA, AI Overview)
- **GBP:** contagem/classificação de avaliações, categorias e posts não verificáveis sem acesso ao painel
- **SXO:** o padrão "engenheiro civil itabirito" (intenção de emprego) é baseado em proxy não geolocalizado
- **Construtoras concorrentes:** dados de estrutura inferidos de snippets de SERP

---

## 📁 Arquivos relevantes (repositório local)

| Arquivo | Relevância |
|---|---|
| `index.html` | Página única; `lang="en"` (linha 2), JSON-LD (linhas 3–115), NAP do rodapé (linhas 942–982), WhatsApp mobile (linhas 229–231), clientes placeholder (linhas 776–818) |
| `js/script.js` | `autoHeight:true` no bannerSwiper, `animateCounter()` (linhas 52–97), formulário→WhatsApp (linhas 173–200), loop rAF do cubo 3D |
| `css/style.css` | Regras `.slide-bg` conflitantes, `.social-sidebar{display:none}` no mobile |
| `robots.txt` | Precisa de `Disallow: /app/` |
| `sitemap.xml` | `lastmod` desatualizado; 1 URL |
| `app/index.html` | Shell Flutter "gestor_obras" — metadados padrão, precisa de noindex |
| `images/` | ~4–5 MiB de imagens não utilizadas; JPEGs de portfólio pesados |

---

*Relatório gerado automaticamente pela auditoria SEO completa claude-seo em 2026-08-13. Recomenda-se reauditar após a implementação da Fase 1 para medir o impacto.*
