# 🔍 Re-auditoria SEO Completa — Engeplena Engenharia (Fase 4→5)

**URL auditada:** https://www.engeplena.com.br
**Data da auditoria:** 2026-08-13
**Negócio:** Engenharia civil e consultoria ambiental · Itabirito/MG · Serviço local (híbrido: escritório físico + área de atuação)
**Plataforma:** Site estático em HTML no GitHub Pages (este repositório é a fonte do site em produção)
**Escopo:** Re-auditoria **completa** (10 sub-agentes) após Fase 2 em produção, Fase 3 (performance) e Fase 4 (SEO local externo). Medida ao vivo contra as 9 URLs públicas.

---

## 📊 SEO Health Score: **≈79 / 100** (era ≈74)

| Categoria | Peso | Baseline | Pós-Fase 2 | **Pós-Fase 4** | Evidência |
|---|---|---|---|---|---|
| SEO Técnico | 22% | 72 | 82 | **87** | 9/9 URLs 200; `app/index.html` noindex confirmado; canonical por página; robots/sitemap corretos |
| Qualidade de Conteúdo | 23% | 44 | 62 | **72** | 6 páginas de serviço ~800 palavras cada; seção de parceiros comprovadamente comentada (não renderiza) |
| SEO On-Page | 20% | 55 | 70 | **75** (derivada) | title/meta/OG por página; termo "laudo estrutural" ainda canibalizado pela home (A2) |
| Schema / Dados Estruturados | 10% | 75 | 88 | **88** | 8/9 páginas com JSON-LD válido (0 erros, 7 avisos de provider cross-document); NAP 100% consistente |
| Performance (CWV) | 10% | 92 | 92 | **85** | Home Lighthouse 91/100 (CLS 0.0046, LCP 3.4s simulado / 0.58s real, TBT 51ms); página de serviço 100/100; **regressão: CLS 0.28 no hub (FOUT)** |
| Prontidão para Busca com IA | 10% | 54 | 72 | **75** | Texto citável por página de serviço; FAQ estruturada; extratores retêm conteúdo relevante |
| Imagens | 5% | 55 | 60 | **68** (derivada) | 8 JPEGs→WebP; 32 JPEGs órfãos removidos; `og:image` com dimensões |
| **Ponderado** | | **62** | **≈74** | **≈79** | |

> **Nota de honestidade:** Backlinks, SEO Local e dados de campo CrUX **não** foram re-medidos com APIs/GSC — as notas refletem o que foi verificado com evidência direta. A **indexação** de `/servicos/*` (falsificação de 8–12 semanas) ainda não é verificável.

**Diagnóstico em uma frase:** o site deixou de ser "uma página única sem arquitetura" e agora é um site de 9 páginas tecnicamente sólido, rápido e com NAP 100% consistente — mas ainda **sem prova social exibida**, sem política de privacidade (LGPD) e com uma regressão de CLS no hub, enquanto as vitórias externas (avaliações, citações, Search Console) dependem de ações manuais nos painéis.

---

## 🔍 Síntese (PERCEBE → ANALISA → VALIDA → AGE)

- **PERCEBE:** Nove URLs ao vivo, todas 200. Home com CLS 0.0046 (antes 0.314). Seis páginas de serviço de ~800 palavras com schema Service+FAQ+Breadcrumb. Fichas externas com NAP do cluster "Pio XII 109" não aparecem mais nas buscas Google por "Engeplena". Porém: o hub `/servicos/` **regecometeu CLS 0.28** por FOUT, a home ainda **não linka o hub**, o termo "laudo estrutural" segue sem página dona, e não há política de privacidade.
- **ANALISA:** As duas regressões restantes são de **implementação**, não de arquitetura: (1) as páginas de serviço pré-carregam o CSS das Google Fonts (`preload as="style"`) mas **não** os arquivos woff2 (`as="font"`) como a home faz → o texto troca de Roboto fallback→Roboto depois do paint e empurra o layout; (2) a home trata "Serviços" só como âncora `#s-services` e nunca como o hub `/servicos/`. O canibalismo de "laudo estrutural" é intencional não-resolvido: a homepage ocupa o termo sem página dedicada.
- **VALIDA:** O que é *real e funciona*: NAP idêntico em todas as fichas (zero "Pio XII/306"), schema sem erros, CWV da home verdes, link de avaliação `g.page` funcionando, seção de parceiros **comprovadamente inerte** (o sub-agente de conteúdo a reportou como High — **refutado** ao parsear o comentário HTML: a seção `#s-partners` está 100% dentro de `<!-- -->`). O que *dói agora*: prova social zero no site, e-mail pessoal no rodapé, política LGPD ausente.
- **AGE:** Corrigir primeiro as regressões baratas e os bloqueadores de confiança (Fase 5A — ver abaixo), depois atacar a dimensão mais fraca de SEO local: **programa de avaliações** (60–90 dias para ranquear no pack).

---

## ✅ Validado como NÃO-problema (correções de achados)

| Achado | Veredito | Evidência |
|---|---|---|
| **High: seção "Nossos Clientes" vaza equity / prova social falsa** (sub-agente de conteúdo) | ❌ **Refutado** | `#s-partners` (linhas ~899–955 da home) está **inteiramente dentro de um comentário HTML bem-formado** — não renderiza, não vaza equity, não aparece no DOM. Parceiros placeholder eram remanescentes do template, já desativados na Fase 1 |
| 19 imagens com `alt=""` (sub-agente de imagens) | ❌ Não-issue | Todos são SVGs decorativas (setas, ícones) — `alt=""` é o comportamento correto |
| `/app/` (Flutter) indexável | ✅ Já resolvido | `noindex` confirmado; fora do sitemap |

---

## 🔴 Crítico (correção imediata)

**Nenhum Critical on-site.** As 9 URLs retornam 200, schema válido, CWV da home dentro dos limiares. Os itens mais urgentes são High (regressões) e a ausência de política de privacidade.

---

## 🟠 Alto (Fase 5A — aplicadas em 2026-08-14, ver rodapé)

| # | Descoberta | Evidência |
|---|---|---|
| A1 | **CLS 0.28 no hub `/servicos/` (0.115 mobile)** por FOUT — as 7 páginas de serviço pré-carregam o CSS das Google Fonts como `as="style"` mas **não** os woff2 como `as="font"`; a home pré-carrega as 4 fontes (CLS 0.004) | Lighthouse hub 2026-08-13; comparação head da home vs. `servicos/*.html` |
| A2 | **Title/H1 de `laudos-e-pericias` não contém "laudo estrutural"** — a homepage canibaliza o termo (card "Laudos e Orçamentos" rankeia no lugar) | Busca por "laudo estrutural itabirito"; title atual "Laudos Técnicos, Perícias e Regularização" |
| A3 | **A homepage não linka o hub `/servicos/`** — só as 6 subpáginas (2× cada: cards + rodapé); o hub fica órfão de links internos da home | grep: `servicos/` vs `#s-services` na home |
| A4 | **CEP 35450-078 só no JSON-LD da home** — ausente do rodapé visível (Google cruza NAP visível com schema) | `index.html` rodapé vs JSON-LD |
| A5 | **E-mail pessoal `murilofch@gmail.com` exposto no rodapé** ("Powered by Aquarius Systems") — dado pessoal de terceiro sem relação com o negócio | `index.html` linha ~1138 |
| A6 | **Erro de crase "coloca a disposição"** (deveria ser "coloca à disposição") na seção "Sobre a Engeplena" | `index.html` linha ~461 |
| A7 | **Sem política de privacidade (LGPD)** — `/privacidade.html` 404; formulário de contato coleta nome/tel/e-mail sem aviso; GA4 (`G-LKRNWZQ6QW`) roda sem documento | GET `/politica-de-privacidade.html` → 404 |
| A8 | **Texto colado "levantamentoReunimos"** em `projetos-estruturais` — além disso, o **mesmo bug existe em todas as 6 páginas**: etiquetas `<strong>` coladas à descrição ("Entrega com ARTVocê recebe…") | `servicos/*/index.html` passos do processo |

## 🟡 Médio (Fase 5B — conteúdo/prova social)

- **Prova social zero exibida** — nenhum depoimento, caso de cliente com métricas ou contagem de avaliações no site. Recomendado: 1–2 depoimentos + 1 caso com métricas por página de serviço.
- **Programa de avaliações do GBP** — dimensão mais fraca do SEO local (0 avaliações públicas comprováveis). Meta: 10 avaliações em 60–90 dias. ⚠️ Regra do Google: **admin/gestor do GBP NÃO pode avaliar o próprio perfil** — quem avalia devem ser clientes reais em contas pessoais. Mensagens → `https://www.engeplena.com.br/avaliacoes.html`.
- **Search Console ainda não montado** — sem dados de indexação/cobertura; bloqueia acelerar o recrawl do favicon PNG e das páginas de serviço.
- **Statísticas sem case studies** — "+150.000 m²", "R$ 140 Mi" sem respaldo em projetos publicados.
- **Citações Tier-2** — diretórios além do GuiaMais (Apontador, TeleListas, etc.) ainda por fazer.

## 🟢 Baixo (backlog)

- Headers de segurança (HSTS, XFO, nosniff) exigem Cloudflare na frente do GitHub Pages.
- `404.html` personalizado em português.
- `IndexNow` — chave + submissão.
- Touch targets mobile < 48px (botões de serviço 19px, CTA do banner 39px).
- Loop de `requestAnimationFrame` do cubo 3D (custo de main-thread no mobile).

---

## 🌐 Externos (fora do código — ações nos painéis)

| Item | Status | Próximo passo |
|---|---|---|
| **Cylex** | ⚠️ Constava "✅ corrigido", mas o **snippet público ainda exibe "Rua Pio XII 109, 35450-000"** (2026-08-13). Página direta 403; verificar via snippet de busca | Reabrir ficha, conferir se a edição foi publicada ou se é cache do índice |
| **GuiaMais** | Ficha de Itabirito **ainda não publicada**; a homônima RJ ("ENGEPLENA ENGENHARIA LTDA", Pedras/Cerâmica, R. Senador Dantas 75) **domina o nome exato em 3 buscas** | Aguardar contato do representante (via WhatsApp do cliente); garantir login em e-mail controlado pelo usuário. Fallback: ficha correta de Itabirito vence a resolução do Google por conta própria |
| **Bing Places** | Importado + Webmaster Tools verificado, mas **sem ficha surfacing** nas buscas Bing | Revisitar painel; conferir se o perfil foi publicado/aprovado |
| **Bing Webmaster Tools** | ✅ Verificado (metatag `msvalidate.01` na `main`) | Usar para submeter sitemap + recrawls |
| **GBP** | Acesso de admin obtido; perfil configurado; **0 avaliações públicas comprováveis** | Disparar programa de avaliações (Fase 5B) |
| **Apple Business Connect** | ⚠️ **Pulado** por decisão do usuário (B2B engenharia em MG, sem relevância) | — |

---

## 🛠️ Plano de Ação — Fase 5

### Fase 5A — Regressões baratas (2026-08-14, executadas)

1. **A1** — Replicar os preloads `as="font"` dos woff2 nas 7 páginas de serviço (5 fontes: Poppins 400/500/600/700 + Roboto 400, esta cobre 400+500). *Falsificação:* Lighthouse no hub CLS < 0.1.
2. **A2** — Adicionar "Laudo Estrutural" ao title/H1/og:title de `laudos-e-pericias` **com amparo no conteúdo** (1 item na lista "O que você recebe"), para não virar keyword-stuffing.
3. **A3** — Linkar o hub na home: item "Todos os serviços" na coluna do rodapé + CTA "Ver todos os serviços" ao final do grid da seção `#s-services`.
4. **A4** — Adicionar ", CEP 35450-078" ao endereço visível do rodapé.
5. **A5** — Remover o `mailto:murilofch@gmail.com` do "Powered by Aquarius Systems" (mantém texto, sem link).
6. **A6** — Corrigir a crase para "coloca à disposição".
7. **A7** — Criar `politica-de-privacidade.html` (LGPD, com dados oficiais e GA4 descrito) + link no rodapé + sitemap.
8. **A8** — Corrigir o texto colado "levantamentoReunimos" **e o mesmo bug sistêmico nas 6 páginas** (32 ocorrências de `</strong>` colado).

### Fase 5B — Conteúdo e prova social (próximas 2–4 semanas)

9. **Depoimentos + 1 caso de cliente com métricas** por página de serviço (E-E-A-T: confiabilidade é o pilar mais fraco).
10. **Programa de avaliações** — disparar via WhatsApp para clientes reais (meta: 10 em 60–90 dias); nunca o admin avaliar o próprio perfil.
11. **Montar o Search Console** — verificar o domínio, submeter sitemap, acelerar recrawl do favicon PNG e de `/servicos/*`.

### Fase 5C — Citações e técnico (contínuo)

12. Resolver Cylex (reedição/publicação do NAP correto) e aguardar GuiaMais (ficha de Itabirito).
13. Citações Tier-2 (Apontador, TeleListas, etc.).
14. Cloudflare na frente do GitHub Pages (headers de segurança) — opcional.
15. Backlog menor (404.html, touch targets, IndexNow).

---

## 📈 Detalhamento por Sub-Análise

### 1. SEO Técnico — **87/100**

- 9/9 URLs ao vivo retornam 200 (home, avaliacoes, hub, 6 serviços); `app/index.html` **noindex confirmado**
- Canonical por página (todas as 8 + avaliacoes.html); robots.txt com Sitemap; sitemap com 9 locs
- Redirects www/https limpos; HTTPS válido
- Faltam headers de segurança (HSTS, XFO, nosniff) — GitHub Pages não permite configurar

### 2. Qualidade de Conteúdo & E-E-A-T — **72/100**

- 6 páginas de serviço de ~800 palavras únicas; FAQ e processos bem estruturados
- Credenciais reais exibidas (CREA-MG, CNPJ, formação UFOP/INBEC)
- Seção de parceiros placeholder **comprovadamente desativada** (comentário HTML bem-formado)
- **Gaps restantes:** zero depoimentos/casos com métricas; estatísticas sem respaldo; 1 erro de crase (A6) e 1 texto colado (A8) na home/projetos

### 3. Schema / Dados Estruturados — **88/100**

- 8/9 páginas com JSON-LD válido; 0 erros, 7 avisos (provider `@id` cross-document, esperado)
- NAP do schema **100% consistente** com rodapé e fichas (zero "Pio XII", zero "Sala 306")
- Service + FAQPage + BreadcrumbList por página de serviço

### 4. Performance / CWV — **85/100**

| Página | Lighthouse | LCP | CLS | TBT |
|---|---|---|---|---|
| Home (mobile) | 91/100 | 3.4s simulado / 0.58s real | **0.0046** | 51ms |
| Página de serviço | 100/100 | — | — | — |
| **Hub `/servicos/`** | ⚠️ | — | **0.28 desktop / 0.115 mobile (FOUT)** | — |

- Home: CLS resolvido (0.314→0.0046) via remoção do `autoHeight` + preload das fontes
- Hub: **regressão de Fase 5A** — falta preload `as="font"` (corrigido em 2026-08-14)
- Peso otimizado: 4 fontes woff2 pré-carregadas, ícones SVG inline, WebP no hero e portfólio

### 5. GEO / Prontidão para IA — **75/100**

- Texto citável por página de serviço (~800 palavras cada) + FAQ estruturada
- `og:image` com dimensões; `og:locale` pt_BR; `lang="pt-BR"`
- **Gap:** sem `llms.txt`; sem `datePublished`/`dateModified`; presença off-domain fraca

### 6. SXO (Experiência de Busca) — parcial

- Arquitetura hub-and-spoke agora **alinhada** com as intenções de serviço (página dedicada por intenção)
- **"laudo estrutural"** ainda sem página dona (A2) — home canibaliza
- Persona mais fraca: proprietário de imóvel precisando de regularização (sem prova social)

### 7. SEO Local — externo

| Dimensão | Status |
|---|---|
| Sinais GBP | Acesso de admin; perfil configurado; site → `/servicos/` |
| Avaliações & Reputação | **0 públicas comprováveis** — dimensão mais fraca |
| NAP & Citações | NAP 100% consistente on-site; Cylex ainda exibe Pio XII (snippet); GuiaMais aguardando ficha; Bing Places sem surfacing |
| Schema Local | 88 — sólido |
| Links & Autoridade Local | Sem citações Tier-2 (Apontador, TeleListas) |

---

## ⚠️ Limitações Metodológicas

- **Sem Google API keys:** CWV são laboratoriais (sem CrUX de campo), sem status de indexação no GSC, sem tráfego GA4.
- **Backlinks/SEO Local:** dependem de APIs (Moz/Bing/DataForSEO) e acesso aos painéis — não re-medidos.
- **SERP via proxy:** WebSearch não reflete o SERP geofenced do Google no Brasil.
- **Cylex:** snippet público observado 2026-08-13 pode ser cache do índice, não o estado real da ficha.
- **Fase 5A** foi executada em 2026-08-14; a validação de CLS do hub (pós-correção) depende de novo Lighthouse após deploy.

---

## 📁 Arquivos relevantes (repositório local)

| Arquivo | Relevância |
|---|---|
| `index.html` | Home (CRLF). Rodapé: NAP (linha ~1090), "Powered by Aquarius Systems" (linha ~1138), coluna de serviços, review link. Seção `#s-services` com 6 cards → subpáginas |
| `servicos/index.html` | Hub `/servicos/` — tinha CLS 0.28 por FOUT (A1); schema Breadcrumb+ItemList |
| `servicos/*/index.html` | 6 páginas de serviço (LF). Laudos: title/H1 sem "laudo estrutural" (A2). Passos com `</strong>` colado (A8) |
| `css/style.css` | Regras `.services-cta` e `.footer-privacy` adicionadas na Fase 5A |
| `politica-de-privacidade.html` | **Criada na Fase 5A** (LGPD, dados oficiais, GA4 descrito) |
| `sitemap.xml` | 10 URLs (adicionada a política de privacidade) |
| `images/favicon-green.png` | Favicon PNG (Google não suporta SVG) — aguardando recrawl |
| `auditoria-seo-2026-08-13.md` | Auditoria anterior (baseline, Fase 1–3) |

---

*Re-auditoria completa gerada pela auditoria SEO claude-seo em 2026-08-13 (10 sub-agentes). Fase 5A aplicada em 2026-08-14. Recomenda-se revalidar o hub (CLS) e a indexação de `/servicos/*` após o recrawl do Google.*
