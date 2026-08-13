# 📍 Plano de Execução — SEO Local Externo (Engeplena Engenharia)

**Objetivo:** executar a Fase 4 da auditoria — ações **externas** (painéis, diretórios, citações) que só podem ser feitas por um humano com acesso às contas. Este plano tem os dados prontos para copiar/colar em cada plataforma.

**Data:** 2026-08-13 · **Branch:** `feat/seo-optimize` · **Fonte:** `auditoria-seo-local-2026-08-13.md` (score atual 45/100)

> ⚠️ **Tudo o que era código já está feito** (Fase 1): `lang="pt-BR"`, H1 com "em Itabirito e Região", `tel:` click-to-call, JSON-LD com NAP correto/CNPJ/CREA, credenciais no rodapé. **Nada aqui toca o site.**

---

## 0. NAP Canônico — copie byte-idêntico em TODAS as plataformas

Este é o único endereço verdadeiro (confirmado pelo CNPJ da Receita Federal em 2026-08-13).

| Campo | Valor |
|---|---|
| **Nome** | Engeplena Engenharia Ltda. |
| **Endereço** | R. Carlos Michel, 66 — Centro, Itabirito/MG, CEP 35450-078 |
| **Telefone** | (31) 3561-3966 |
| **WhatsApp** | (31) 98795-0463 |
| **Site** | https://www.engeplena.com.br/ |
| **E-mail** | contato@engeplena.com.br |
| **CNPJ** | 07.936.059/0001-35 |
| **Horário** | Seg–Qui 08:00–17:00 · Sex 08:00–16:30 · Sáb/Dom fechado |
| **Geo (pin)** | -20.2529953, -43.8041709 |
| **Place ID (Google)** | `0x3cf05f87311d2d10` |

**Regras rígidas:**
- NUNCA use "Rua Pio XII, 109" ou "Sala 306" — são de um cluster de agregadores desatualizado e contradizem o registro legal.
- NUNCA use CEP 35450-000 (errado); o correto é **35450-078**.
- Estado sempre `MG`, nunca por extenso.
- Se um campo limitar caracteres/maiúsculas, use `ENGEPLENA ENGENHARIA LTDA`.

---

## 1. Ordem de execução sugerida

| # | Ação | Onde | Tempo | Impacto |
|---|---|---|---|---|
| 1 | Verificar painel + categoria + fotos | Google Business Profile | 1h | Alto (categoria = fator #1) |
| 2 | Programa de avaliações | WhatsApp + Google | 1h setup | Alto (dimensão mais fraca) |
| 3 | Reivindicar ficha | Bing Places | 30min | Alto (alimenta ChatGPT/Copilot/Alexa) |
| 4 | Reivindicar ficha | Apple Business Connect | 30min | Médio |
| 5 | Criar ficha Itabirito + sinalizar homônima RJ | GuiaMais | 1h | Médio (limpa identidade) |
| 6 | Corrigir endereço/horários/texto | Cylex, Bendito Guia | 2h | Médio |
| 7 | Citações Tier-2 | CREA-MG, Prefeitura, SINDUSCON, Apontador… | contínuo | Médio |

---

## 2. Google Business Profile (item mais importante)

Painel: https://business.google.com (login com o e-mail que controla a ficha).

1. **Verificação da ficha** — se não estiver verificada, solicitar verificação (vídeo ou cartão postal). Badge verificado é sinal forte.
2. **Categoria primária** (fator #1 do pacote local): `Serviços de engenharia`. Se não existir essa opção: `Engenheiro civil`.
3. **Categorias secundárias** (adicionar):
   - `Empreiteiro`
   - `Serviços de consultoria ambiental`
   - (opcionais) `Projetista de estruturas`, `Engenheiro estrutural`
4. **Horário** — conferir que bate exatamente com o site: Seg–Qui 08:00–17:00, Sex 08:00–16:30, fechado Sáb/Dom. (A ficha do Bendito Guia hoje diz 09–18h/Sáb 09–13h — está errada.)
5. **Endereço** — R. Carlos Michel, 66, Itabirito/MG, 35450-078. Sem "Sala".
6. **Fotos (15–30)** — prioridade: fachada do escritório (R. Carlos Michel 66), a equipe (fotos do site: `team-1`, `team-2`), obras do portfólio (usar as `gallery-*.webp` do site). Negócios com fotos recebem ~45% mais pedidos de direção.
7. **Posts (2–4/mês)** — obra concluída, equipe, dica de engenharia, serviço. Reaproveite o Instagram.
8. **Q&A** — responder 5–10 perguntas comuns ("Quais serviços oferecem?", "Atendem quais cidades?", "Trabalham com laudo técnico?").
9. **Campo "site"** — hoje ok apontando para a homepage. **Quando as páginas de serviço existirem, aponte para `/servicos/`** (não a homepage) para não suprimir o orgânico (Sterling Sky Diversity Update).

---

## 3. Programa de avaliações (dimensão mais fraca — prioridade alta)

### Link direto de avaliação — ✅ ATUALIZADO (2026-08-13)
O antigo `https://search.google.com/local/writereview?placeid=...` foi **descontinuado (404)**. Novo link gerado no painel do GBP (Resenhas → Obter mais avaliações) e já aplicado em `avaliacoes.html` (botão "Avaliar no Google"):
```
https://g.page/r/CRAtHTGHX_A8EAI/review
```
Coloque este link no WhatsApp dos clientes e no e-mail de pós-projeto. (Mensagens devem apontar para `https://www.engeplena.com.br/avaliacoes.html` — curto e de marca.)

### Página "Avalie-nos" (já pronta no site)
```
https://www.engeplena.com.br/avaliacoes.html
```
Página dedicada com o botão de avaliação, os 3 passos e um link alternativo de WhatsApp. Use este endereço **no template do WhatsApp abaixo** (mais amigável que o link longo) e no rodapé do site.

### Template de WhatsApp (copiar e enviar ao cliente)
> Olá, {Nome}! Aqui é a Engeplena Engenharia. Foi um prazer concluir {serviço} com você. Se puder dedicar 1 minuto, uma avaliação no Google ajuda muito nossa empresa na região. É rapidinho, é só acessar: https://www.engeplena.com.br/avaliacoes.html — muito obrigado!

### Regras de conformidade (não pule — proibido por Google + FTC)
- Peça a **todos** os clientes, não só aos que parecem satisfeitos. Medir satisfação antes de pedir = filtrar = proibido (multa FTC US$ 53.088/violação nos EUA; Google penaliza).
- Meta: **10 avaliações em 60–90 dias** (limiar "Magic-10"), depois **≥1 a cada 18 dias** (regra dos 18 dias).
- **Responda TODAS as avaliações em <48h**, mesmo críticas (88% dos consumidores preferem empresa que responde).
- Nunca ofereça brinde/desconto em troca de avaliação (também proibido).

---

## 4. Bing Places (ausente hoje — alimenta ChatGPT/Copilot/Alexa)

1. Crie uma conta Microsoft em https://www.bingplaces.com.
2. Cadastre o negócio com o **NAP canônico** (Seção 0) — nome, endereço, telefone, site, categoria `Serviços de engenharia`.
3. Verifique por telefone ou vídeo.
4. Adicione fotos e horários (os mesmos do site).
5. **Verificação depois:** o Bing Maps retorna a ficha com NAP correto; uma pergunta no Copilot/ChatGPT sobre "engenheiros em Itabirito" a cita.

---

## 5. Apple Business Connect — **PULADO** (decisão do usuário, 2026-08-13)

~~1. https://businessconnect.apple.com (conta Apple ID).~~
~~2. Reivindique a ficha da Engeplena com o NAP canônico.~~
~~3. Adicione fotos (fachada + equipe), horários, categoria.~~
~~4. Apple Maps = ~14–27% dos consumidores; é a maior lacuna de presença multi-plataforma.~~

Justificativa: negócio B2B (engenharia civil) em MG, sem relevância de público no Apple Maps. Se algum dia aparecer pedido recorrente de iPhone/Apple Maps, reavaliar.

---

## 6. GuiaMais — limpar o footprint (homônima do RJ)

Problema comprovado: o nome exato "ENGEPLENA ENGENHARIA LTDA" está ocupado no GuiaMais pela empresa homônima do **Rio de Janeiro** (CNPJ 00.562.202/0001-27, categoria errada "Pedras/Artefatos de Cimento", endereço R. Senador Dantas 75, 0 avaliações).

1. **Crie a ficha da Engeplena de Itabirito** em https://www.guiamais.com.br — categoria **`Engenharia civil` / `Serviços de engenharia`**, NAP canônico, site, telefone.
2. **Sinalize a ficha do RJ** como duplicada/incorreta (link "Sugerir correção" / "Reivindicar" na ficha): informe que o nome correto para aquele CNPJ é outro ou que é entidade distinta. O objetivo é o Google parar de resolver o nome da Engeplena para a empresa do Rio.
3. **Verificação:** `site:guiamais.com.br "Engeplena"` mostra o resultado de Itabirito com endereço/telefone corretos acima do RJ em até 60 dias.

**Status 2026-08-13:**
- ✅ Cadastro da ficha de Itabirito **enviado** — formulário inicial só pediu nome + WhatsApp (colocado o (31) 98795-0463, WhatsApp oficial da Engeplena — correto). Resposta do site: *"Agora é com a gente. Em breve um representante entrará em contato com você."* → ficha em **fila de moderação**.
- ⏳ **AGUARDANDO:** contato do representante (via WhatsApp do cliente) para aprovar a ficha. No momento em que aprovar, completar o NAP completo: endereço `R. Carlos Michel, 66 — Centro, Itabirito/MG, CEP 35450-078` (cuidado: GuiaMais autocompleta -000), descrição da Seção 7, horários Seg–Qui 08–17 / Sex 08–16:30.
- ⚠️ **Garantia ao aprovar:** o login/gestão da ficha deve ficar em e-mail controlado pelo usuário (ex.: `contato@engeplena.com.br`) — se ficar preso ao WhatsApp do cliente, perde-se a gestão.
- 🚧 **Homônima RJ** (CNPJ 00.562.202/0001-27): sem botão "sugerir correção" na ficha; o único botão "essa empresa é minha" redireciona à home **sem login**. **Criar conta no GuiaMais não é possível antes do contato do representante** (confirmado 2026-08-13) — a sinalização do RJ fica **BLOQUEADA até a aprovação da ficha**. Ao aprovar, logado, tentar denunciar/corrigir; se nada, acionar o suporte pedindo correção/remoção da homônima. **NÃO reivindicar a ficha do RJ** (CNPJ não é do cliente — barra na verificação e é apropriação indevida).
- **Fallback:** se não der para sinalizar, a ficha correta de Itabirito vence a resolução de identidade do Google por conta própria (CNPJ real + endereço real + site).

---

## 7. Corrigir fichas existentes com dados errados

| Diretório | Erro atual | Correção (copiar da Seção 0) |
|---|---|---|
| **Cylex** (cylex.com.br) | "Rua Pio XII, 109" | → R. Carlos Michel, 66 — Centro, Itabirito/MG, CEP 35450-078 |
| **Bendito Guia** (benditoguia.com.br) | Endereço Pio XII 109-306 + horários 09–18h/Sáb 09–13h + texto template de Atibaia + nota contraditória ("4.3" / "0 avaliações") | → NAP canônico + horários corretos + reescrever descrição com texto de Itabirito; remover a nota inventada |
| **todosnegocios** | Já mostra telefone/Itabirito | Revisar e confirmar NAP completo |

**Status 2026-08-13:**
- **Bendito Guia: RESIDUAL ACEITO (baixa prioridade).** CORREÇÃO DA CHECAGEM ANTERIOR: a ficha **existe e continua com dados errados** — `https://www.benditoguia.com.br/empresa/engeplena-engenharia-ltda-itabirito-mg` mostra "R. Pio XII, 109-306, CEP 35450-000" + texto template de Atibaia + nota inventada "4,3 / 0 avaliações". Não está no sitemap nem indexada no DDG (por isso a checagem anterior falhou), mas o Google a tem. **Sem caminho de edição/reivindicação exposto** (edição só via login JS; sem e-mail/página de contato no site). **Decisão: não perseguir agora** — diretório Tier-2 raspado, e a busca Google por "Engeplena" já resolve para a entidade correta de Itabirito sem o cluster Pio XII. Opção futura: registrar no site e tentar reivindicar após login.
- **Cylex: CONCLUÍDO** (2026-08-13) — reivindicado via e-mail, NAP corrigido (Carlos Michel 66 / CEP 35450-078), palavras-chave preenchidas. ✅
- **todosnegocios**: revisar NAP completo (pendente, mostra telefone/Itabirito já).

**Descrição pronta para copiar (Bendito Guia / diretórios):**

> A Engeplena Engenharia Ltda. atende Itabirito e a Região Central de Minas Gerais com projetos estruturais (concreto armado e metálicas), consultoria ambiental, plotagem e impressão de projetos, gestão de obras, laudos técnicos e execução de obras residenciais e comerciais. Sócios: Eng.ª Junaia de Paula Lacerda (CREA-MG 1402661533) e Eng.º Antônio Carlos Cunha Júnior (CREA-MG 1402661576). CNPJ 07.936.059/0001-35.

---

## 8. Citações Tier-2 brasileiras (consistência + autoridade)

Cadastrar a Engeplena (NAP canônico) em:
- **CREA-MG** — cadastro/credenciamento de empresa + perfil dos engenheiros (autoridade profissional).
- **Prefeitura de Itabirito** — cadastro de fornecedores da prefeitura (sinal local forte).
- **SINDUSCON-MG** — associação da indústria da construção (muitas PMEs de engenharia são membros).
- **Apontador** (apontador.com.br)
- **MaisEmpresas** (maisempresas.com.br)
- **TeleListas** (telelistas.net)
- **Solutudo** (solutudo.com.br)

**Verificação de consistência:** quando terminar, todos os diretórios devem retornar NAP idêntico (score BrightLocal/Whitespark ≥ 90%).

---

## 9. Checklist de verificação (falsificabilidade)

Rode estes checagens depois de cada ação:

- [ ] `site:guiamais.com.br "Engeplena"` → resultado de **Itabirito** correto acima do RJ (até 60 dias)
- [x] Bing Maps → ficha da Engeplena Itabirito com NAP correto (2026-08-13, Webmaster Tools verificado)
- [ ] Busca Google por "Engeplena" → resolve para a empresa certa, sem cluster "Pio XII"
- [ ] Contagem de avaliações do GBP → **≥ 10** (meta 60–90 dias)
- [ ] Nenhuma semana sem nova avaliação; respostas do dono em <48h
- [x] `grep -i "sala 306\|pio xii" index.html` → nada (garantido)
- [x] Categoria primária do GBP = "Serviços de engenharia"/"Engenheiro civil" (2026-08-13, configurado)
- [x] Badge verificado visível no GBP (2026-08-13, admin obtido)

---

## 10. Backlog (mês a mês)

- Fotos do GBP: manter 15–30 (fachada + equipe + obras).
- Posts no GBP: 2–4/mês.
- Semear Q&A no GBP (5–10 perguntas).
- Monitorar o badge verificado.
- **Páginas de serviço criadas em 2026-08-13 (Fase 2)**: apontar o campo "site" do GBP para `/servicos/` e direcionar cada página de serviço como destino das citações.

---

## 📁 Arquivos relevantes

- `auditoria-seo-local-2026-08-13.md` — auditoria completa (evidências de cada item).
- `auditoria-seo-2026-08-13.md` — auditoria geral (baseline).
- `index.html` — site (Fase 1 já aplicada; **nada a mudar aqui na Fase 4**).
- **Fase 2** (páginas de serviço `/servicos/*`) — **FEITA em 2026-08-13** (hub + 6 páginas, schema Service/FAQ, linkagem hub-and-spoke).
