# 📍 Auditoria de SEO Local — Engeplena Engenharia

**Negócio:** Engeplena Engenharia LTDA · CNPJ 07.936.059/0001-35 · Itabirito/MG
**URL auditada:** https://www.engeplena.com.br
**Data:** 2026-08-13
**Método:** `render_page.py` (HTML ao vivo + renderizado), fonte local `index.html`, registros públicos de CNPJ (maiscnpj, consultacnpjfacil, Bendito Guia, GuiaMais), Bing Maps/busca Bing, DuckDuckGo, Instagram. Referências `local-seo-signals.md` e `local-schema-types.md` aplicadas.

---

## 0. Dados Oficiais Confirmados (2026-08-13) — CONFEA + CNPJ

Consulta direta ao CONFEA (registro profissional) e ao CNPJ da Receita Federal. Resolvem as incógnitas da Seção 5 (NAP) e da Seção 7 (schema/CREA).

### Registros CREA (fonte: CONFEA)

| Engenheiro(a) | Registro Nacional | Data de Registro | CREA | Situação | Título | Atribuições |
|---|---|---|---|---|---|---|
| **ANTONIO CARLOS CUNHA JUNIOR** | 1402661576 | 09/04/2003 | CREA-MG | Ativo | Engenheiro Civil | Art. 7º Res. 218/73 CONFEA |
| **JUNAIA DE PAULA LACERDA** | 1402661533 | 28/06/2004 | CREA-MG | Ativo | Engenheira Civil | Art. 7º Res. 218/73 CONFEA |

- Sem vistos em outros CREAs. O CONFEA não registra pós-graduações (dados UFOP/INBEC/IETEC/IPOG vêm dos currículos, não do registro profissional).
- "Registro Nacional" é o identificador oficial CONFEA → usar na exibição e no schema `identifier`/`hasCredential`.

### CNPJ (fonte: Receita Federal)

- **Razão Social:** ENGEPLENA ENGENHARIA LTDA - ME · **CNPJ:** 07.936.059/0001-35
- **Fundação:** 05/04/2006 · **Situação:** Ativa · Natureza 206 (Sociedade Empresária Limitada) · Matriz
- **Endereço oficial:** **Rua Carlos Michel, 66 — Centro, Itabirito/MG, CEP 35450-078** (sem complemento/sala)
- **CNAE principal:** 7112-0/00 Serviços de engenharia (+ secundários que mapeiam os 6 `Service` do schema)

### Decisões que estes dados destravam

1. **NAP canônico (Seção 5, item 1 CRÍTICO):** o registro oficial confirma **Carlos Michel 66, CEP 35450-078, sem sala**. A "Sala 306" do schema era um artefato do cluster Pio XII 109 (registros agregadores desatualizados) → **remover do schema**. Endereço canônico = `R. Carlos Michel, 66, Centro, Itabirito/MG, CEP 35450-078`.
2. **Schema (Seção 7):** preencher `foundingDate: "2006-04-05"`, `taxID: "07.936.059/0001-35"`, `legalName: "ENGEPLENA ENGENHARIA LTDA - ME"`, `addressRegion: "MG"`, `postalCode: "35450-078"` e os `identifier` CREA das Person:
   - Junaia → `1402661533`
   - Antônio → `1402661576`
3. **Homônima do RJ** (CNPJ 00.562.202/0001-27) confirmada como entidade distinta — não usar seus dados em nenhuma citação da Engeplena de Itabirito.

---

## 1. Score de SEO Local: **45/100**

| Dimensão | Peso | Nota /10 | Ponderado | Evidência |
|---|---|---|---|---|
| Sinais GBP | 25% | 6.5 | **16.25** | Maps embed com place ID `0x3cf05f87311d2d10`; horários visíveis; título com "Itabirito-MG". Categoria, posts, Q&A, fotos, badge NÃO verificáveis/ausentes. |
| Avaliações & Reputação | 20% | 2.0 | **4.00** | Sem `aggregateRating`, sem widget de avaliações, sem avaliações visíveis, sem padrão de resposta, sem programa de reviews. Instagram 104 seguidores, último post ~jan/2026. |
| SEO Local On-Page | 20% | 4.5 | **9.00** | Cidade no título ✓; keyword local do H1 comentada; NAP visível ✓; **zero páginas de serviço dedicadas** (#1 fator local orgânico); sem `tel:`; `lang="en"` em site pt-BR. |
| NAP & Citações | 15% | 4.0 | **6.00** | Conflação da "Sala 306" comprovada; CEP 35450-000 vs 35450-078; Pio XII vs Carlos Michel; footprint GuiaMais = homônima do RJ; Bing Places ausente. |
| Schema Local | 10% | 7.5 | **7.50** | JSON-LD `HomeAndConstructionBusiness` válido com geo (15 decimais), horários, areaServed, 6 `Service`. Porém subtipo genérico, erros de NAP, geo ~13 m do pin do GBP, sem @id/email/logo/foundingDate/taxID/hasCredential/Person. |
| Links & Autoridade Local | 10% | 2.5 | **2.50** | Sem sinais de câmara/BBB/CREA/imprensa/"best of"; links de parceiros placeholder vazam equity para domínios mortos; perfil de backlinks quase zero. |
| **TOTAL** | | | **45.25 → 45/100** | |

**Reconciliação com a auditoria anterior (54/100):** a queda é baseada em evidência, não em mudança de método. Verificações ao vivo de hoje confirmaram: a citação Bendito Guia carrega **endereço Pio XII errado + horários errados (09–18h/Sáb 09–13h)** + linha de nota internamente contraditória ("4.3" mas "0 avaliações"); **Bing Places genuinamente ausente**; a **homônima do RJ no GuiaMais ao vivo** na categoria errada ("Pedras/Artefatos de Cimento"); e **sem aggregateRating/widget de avaliações na página**. NAP e Reviews estão piores do que a auditoria anterior conseguia verificar.

---

## 2. Tipo de Negócio + Vertical da Indústria

**Tipo: HÍBRIDO** (confirmado).
- Sinais brick-and-mortar: endereço visível no rodapé "R. Carlos Michel, 66, Centro - Itabirito/MG" (`index.html:946`), Google Maps embed (`index.html:836-844`) com link de direções, serviço walk-in de plotagem.
- Sinais SAB: "Itabirito e região Central de Minas Gerais" (`index.html:911`), `areaServed` no schema.
- Manter o endereço visível no GBP — o balcão de plotagem/impressão é oferta walk-in genuína.

**Vertical: HOME SERVICES / ENGENHARIA PROFISSIONAL + CONSULTORIA AMBIENTAL** (vertical híbrida).
- Sinais presentes: linguagem de área de serviço, "Solicitar orçamento", 6 linhas de serviço. Sinais **ausentes**: licenciado/registrado (sem CREA em lugar nenhum), emergência/24-7, "orçamento grátis".
- CNAE 7112000 "Serviços de engenharia" (primário) + 5 secundários (plotagem 1813099, elétrica 4321500, hidráulica 4322301, acabamento 4330499, alvenaria 4399103, atividades técnicas 7119799) — os 6 `Service` do schema mapeiam de forma limpa para os códigos de atividade registrados. Boa aderência de entidade.

**Avaliação do subtipo de schema:**
- `HomeAndConstructionBusiness` é o genérico. `GeneralContractor` (suportado pelo Google) só serve o braço "Execução de Obras", não projeto/consultoria/plotagem. `ProfessionalService` é um tipo Schema.org, mas não é um subtipo LocalBusiness distinto para rich results do Google.
- **Recomendação: manter `HomeAndConstructionBusiness`** para o `@type` do schema (cobertura mais limpa do portfólio misto), mas a decisão que afeta ranking é a **categoria primária do GBP**, não o tipo de schema. Pela lista de categorias do Google no Brasil, a categoria primária correta para o CNAE registrado é **"Serviços de engenharia"** ou **"Engenheiro civil"**; adicionar **"Empreiteiro"** e **"Serviços de consultoria ambiental"** como secundárias. A homônima do RJ na categoria "Pedras — Artefatos de Cimento" é exatamente a falha de categoria errada que o Google mais penaliza (score 176).

---

## 3. Checklist de Otimização GBP

| Sinal | Status | Evidência |
|---|---|---|
| Categoria primária (#1 fator, score 193) | **NÃO VERIFICADA — maior risco desconhecido** | Sem acesso ao painel. Se for algo diferente de "Serviços de engenharia"/"Engenheiro civil", é o #1 fator negativo (176). |
| Keywords no título do GBP (fator #2, score 181) | Parcialmente verificado | Título do lugar = "ENGEPLENA ENGENHARIA LTDA." (embed Maps `!2s` + auditoria anterior). Sem keyword stuffing (correto — não adicionar). |
| Badge verificado (substituiu Guaranteed/Screened out/2025) | Não verificável | Precisa do painel. |
| Categorias secundárias (ideal ~4 adicionais) | Não verificável | Precisa do painel. Recomendar Empreiteiro + Consultoria ambiental + Serviços de engenharia. |
| Fotos/vídeo (45% mais pedidos de direção) | Não verificável no GBP | Site tem imagens de portfólio, mas contagem de fotos do GBP inacessível. Recomendar 15–30 fotos incl. fachada + equipe. |
| Posts | Não detectado | Instagram com postagens esparsas (última ~jan/2026); sem evidência de posts no GBP. |
| Horários visíveis na página (fator #5, aberto no momento da busca) | **PRESENTE** | Rodapé (`index.html:927-936`): Seg–Qui 08–17h, Sex 08–16h30, fechado fim de semana. Devem bater exatamente com o GBP — **Bendito Guia contradiz** (09–18h/Sáb 09–13h), citação que pode confundir a entidade. |
| Estratégia de link do GBP (Sterling Sky Diversity Update) | OK hoje, em risco amanhã | Rodapé linka para short link `maps.app.goo.gl`, não a homepage. **Quando páginas de serviço existirem, NÃO definir o campo "site" do GBP como a homepage** — apontar para página de serviço ou URL rastreada para não suprimir o orgânico. |
| Q&A | Não detectado / não verificável | Sem evidência de Q&A do proprietário. Limitado por categoria/região. |
| Maps embed / referência de lugar | **PRESENTE** | iframe com place ID `0x3cf05f87311d2d10`, pin `-20.2529953,-43.8041709` (`index.html:837`). |

---

## 4. Snapshot de Saúde de Avaliações

| Métrica | Status | Benchmark | Veredito |
|---|---|---|---|
| Contagem de avaliações Google | Não verificável ao vivo; nenhuma avaliação em lugar algum; Bendito Guia se contradiz ("4.3" + "0 avaliações") | Magic-10 (Sterling Sky) | **FALHA** — quase certamente <10 |
| Velocidade de avaliações | Sem programa, sem evidência de novas | Regra dos 18 dias — queda após 3 semanas parado | **FALHA** |
| Nota média | Desconhecida / não visível | 68% dos consumidores só usam 4+; 31% só 4.5+ | Não verificada |
| Recência | Sem evidência de avaliações recentes | 74% só se importam com os últimos 3 meses | **FALHA** |
| Respostas do proprietário | Sem padrão observável | 88% usariam uma empresa que responde | **FALHA** |
| `aggregateRating` no schema | **AUSENTE** | — | **FALHA** |
| Presença multi-plataforma | Instagram (104 seguidores, baixa atividade); sem Yelp/TripAdvisor/BBB/Apple | Consumidores usam em média 6 sites; Google 71%, Instagram 37%, Apple Maps 27% | **FRACA** |
| Gating de avaliações | Nenhum detectado (bom) | Proibido pelo Google + FTC (US$ 53.088/violação) | **PASSA** |

Esta é a dimensão mais fraca. Não há mecanismo de geração de avaliações, nenhum schema de nota, nenhuma prova social on-page, e o único dado de "nota" de terceiros é contraditório.

---

## 5. Auditoria de Consistência NAP

| Fonte | Nome | Rua | Complemento | Cidade/UF | CEP | Telefone |
|---|---|---|---|---|---|---|
| Rodapé (`index.html:946`) | Engeplena Engenharia Ltda. (implícito) | R. Carlos Michel, 66 | — | Centro – Itabirito/MG | — | (31) 3561-3966 |
| Schema JSON-LD (`index.html:27-34`) | Engeplena Engenharia Ltda. | R. Carlos Michel, 66 | **Sala 306** | Itabirito, **Minas Gerais** (não MG) | 35450-000 | +55-31-3561-3966 |
| GBP / Maps embed | ENGEPLENA ENGENHARIA LTDA. | Carlos Michel, 66 | — | Itabirito/MG | — | (31) 3561-3966 |
| Registro CNPJ (maiscnpj, consultacnpjfacil, cnpjá) | ENGEPLENA ENGENHARIA LTDA | Rua Carlos Michel, 66 | nenhum | CENTRO, ITABIRITO/MG | **35450-078** | (31) 3561-3966 |
| Agregadores CNPJ (Casa dos Dados, Cylex, Bendito Guia) | ENGEPLENA ENGENHARIA LTDA | **Rua Pio XII, 109** | **306** | Centro, Itabirito/MG | 35450-000 | (31) 3561-3966 |
| GuiaMais (homônima RJ, CNPJ 00.562.202/0001-27) | ENGEPLENA ENGENHARIA LTDA | R Senador Dantas, 75 | SALA | Centro, Rio de Janeiro/RJ | 20031-200 | — |

**Discrepâncias confirmadas:**
1. **Conflação da "Sala 306" (comprovada hoje).** A ficha ao vivo do Bendito Guia lê *"R. Pio XII, 109 - 306"*. A sala 306 pertence ao endereço **Pio XII 109**, não ao Carlos Michel 66. A string do schema "R. Carlos Michel, 66, Sala 306" **funde dois endereços diferentes**. Rodapé e GBP omitem corretamente; o schema está errado.
2. **Pio XII vs Carlos Michel.** Dois clusters de registro independentes discordam sobre o endereço legal registrado. maiscnpj/consultacnpjfacil/cnpjá → Carlos Michel 66 (CEP 35450-078); Casa dos Dados/Cylex/Bendito Guia → Pio XII 109, 306. Exige consulta à Receita Federal para resolver.
3. **CEP 35450-000 (site/GBP/schema) vs 35450-078 (registro).** O CEP de rua por dois registros é 35450-078.
4. **`addressRegion: "Minas Gerais"`** no schema vs `MG` em todo o resto (rodapé, GBP).
5. **Risco de entidade homônima do RJ.** Footprint do nome exato no GuiaMais ocupado por empresa do Rio (categoria errada "Pedras/Cerâmica", endereço errado, zero avaliações). O Google não tem desambiguação verificada por CNPJ na página — risco de resolução de entidade no Knowledge Graph e problema da classe de fator #2 negativo (entidade duplicada/confusa).

**Recomendação:** escolher um endereço operacional canônico (o escritório físico = **Rua Carlos Michel, 66, Centro, Itabirito/MG, CEP 35450-078** se o CEP do registro for o verdadeiro da rua — verificar), remover "Sala 306" do schema a menos que o escritório físico tenha genuinamente sala, normalizar `addressRegion` para `MG`, e deixar rodapé + schema + GBP + todas as citações idênticos.

---

## 6. Verificação de Citações

| Tier | Fonte | Status | Evidência |
|---|---|---|---|
| Tier 1 | Google Business Profile | **PRESENTE, não otimizado** | Place ID `0x3cf05f87311d2d10`; embed Maps na página; pin `-20.2529953,-43.8041709` |
| Tier 1 | Bing Places | **AUSENTE** | Busca Bing Maps sem ficha; busca Bing por "Engeplena" traz só a homônima do RJ no GuiaMais. **Bing Places alimenta ChatGPT/Copilot/Alexa** — lacuna crítica. |
| Tier 1 | Apple Business Connect | Não verificável | Sem acesso; recomendar claim (uso do Apple Maps 14%→27%). |
| Tier 1 | Facebook | **PRESENTE, baixa atividade** | facebook.com/engeplena existe; categoria/engajamento não totalmente avaliáveis deslogado. |
| Tier 1 | Yelp | N/A (Brasil) | Centrado nos EUA; não é sinal real para Itabirito/MG. |
| Tier 2 | BBB / YellowPages / Manta / Foursquare / Nextdoor | N/A ou ausente | Centrados nos EUA; irrelevantes para PME brasileira. |
| BR | **GuiaMais** | **NEGATIVO — homônima do RJ ocupa o nome exato** | Ao vivo: "ENGEPLENA ENGENHARIA LTDA | Centro, Rio De Janeiro, RJ" categoria "Pedras (Artefatos de Cimento)", endereço R Senador Dantas 75, 0 avaliações. |
| BR | Cylex | **PRESENTE mas endereço ERRADO** | "Rua Pio XII 109, Itabirito/MG" (403 no fetch direto, visível no snippet de busca). |
| BR | Bendito Guia | **PRESENTE mas dados ERRADOS** | Pio XII 109-306 + horários errados (09–18h/Sáb 09–13h) + texto template de Atibaia + contradição "4.3/0 avaliações". |
| BR | todosnegocios | **PRESENTE** | 403 no fetch direto; snippet mostra (31) 3561-3966, Itabirito. |
| BR | Apontador, MaisEmpresas, TeleListas, Solutudo | Não encontrados nas buscas | Lacuna. |
| Agregadores | Data Axle, Foursquare, Neustar/TransUnion | Não verificáveis / provavelmente não submetidos | Lacuna de distribuição downstream; 3 dos top 5 fatores de visibilidade em IA são ligados a citações (Whitespark 2026). |

**Matemática de citação para IA:** o ChatGPT NÃO lê o GBP — ele usa Bing, Yelp, TripAdvisor, BBB, Reddit. A Engeplena tem: sem Bing Places, sem Yelp/BBB (N/A, mas também sem presença no Reddit), entidade GuiaMais corrompida, e Facebook de baixa atividade. A superfície de citação visível para IA é fina e parcialmente errada.

---

## 7. Status do Schema Local

**JSON válido presente** (1 bloco, validado pelo render: `valid: true`, tipos incluem HomeAndConstructionBusiness, PostalAddress, GeoCoordinates, OpeningHoursSpecification, Service, Offer, ContactPoint), mas **com falhas**:

- **Obrigatório:** `name` ✓, `address` ✓
- **Recomendado presente:** `geo` ✓ (15 decimais — precisão excelente) mas **~13 m do pin do GBP** (`-20.25287449508203,-43.80417090275286` vs pin `-20.2529953,-43.8041709`); `openingHoursSpecification` ✓ (Seg–Qui 08–17, Sex 08–16:30); `telephone` ✓ (como array — schema.org tipa como `Text`, deveria ser string única); `url` ✓ (sem barra final); `priceRange` ✓; `image` ✓; `areaServed` ✓ (Itabirito + Região Central + MG — adequado ao híbrido); `makesOffer` com 6 `Service` ✓ (padrão Home Services atendido).
- **Ausente:** `@id`, `logo`, `email`, `foundingDate` (2006-04-05), `taxID` (CNPJ), `hasCredential` (CREA), entidades `Person` para os dois sócios.
- **Erros:** streetAddress conflata "Sala 306"; `addressRegion: "Minas Gerais"` deveria ser `MG`; geo desalinhado; bloco colocado em `index.html:3`, dentro de `<html>` mas **antes do `<head>`** (colocação malformada — mover para o `<head>`).

### JSON-LD corrigido pronto para colar (bloco principal)

```json
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "HomeAndConstructionBusiness",
  "@id": "https://www.engeplena.com.br/#business",
  "name": "Engeplena Engenharia Ltda.",
  "url": "https://www.engeplena.com.br/",
  "image": "https://www.engeplena.com.br/images/logo_colorida.png",
  "logo": "https://www.engeplena.com.br/images/logo_colorida.png",
  "email": "contato@engeplena.com.br",
  "telephone": "+55-31-3561-3966",
  "foundingDate": "2006-04-05",
  "taxID": "07.936.059/0001-35",
  "priceRange": "$$",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "R. Carlos Michel, 66",
    "addressLocality": "Itabirito",
    "addressRegion": "MG",
    "postalCode": "35450-078",
    "addressCountry": "BR"
  },
  "geo": {
    "@type": "GeoCoordinates",
    "latitude": -20.2529953,
    "longitude": -43.8041709
  },
  "areaServed": [
    { "@type": "City", "name": "Itabirito" },
    { "@type": "AdministrativeArea", "name": "Região Central de Minas Gerais" },
    { "@type": "State", "name": "Minas Gerais" }
  ],
  "openingHoursSpecification": [
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": ["Monday", "Tuesday", "Wednesday", "Thursday"],
      "opens": "08:00",
      "closes": "17:00"
    },
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": "Friday",
      "opens": "08:00",
      "closes": "16:30"
    }
  ],
  "contactPoint": [
    {
      "@type": "ContactPoint",
      "telephone": "+55-31-3561-3966",
      "contactType": "customer service",
      "areaServed": "BR",
      "availableLanguage": "Portuguese"
    },
    {
      "@type": "ContactPoint",
      "telephone": "+55-31-98795-0463",
      "contactType": "WhatsApp",
      "areaServed": "BR",
      "availableLanguage": "Portuguese"
    }
  ],
  "sameAs": [
    "https://www.instagram.com/engeplena/",
    "https://www.facebook.com/engeplena"
  ],
  "founder": [
    { "@id": "https://www.engeplena.com.br/#junaia" },
    { "@id": "https://www.engeplena.com.br/#antonio" }
  ],
  "employee": [
    { "@id": "https://www.engeplena.com.br/#junaia" },
    { "@id": "https://www.engeplena.com.br/#antonio" }
  ],
  "makesOffer": [
    { "@type": "Offer", "itemOffered": { "@type": "Service", "name": "Projetos de Engenharia Civil e BIM", "description": "Projetos estruturais em concreto e metálicas, elétricos, hidrossanitários e modelagem arquitetônica (BIM)." } },
    { "@type": "Offer", "itemOffered": { "@type": "Service", "name": "Consultoria Ambiental", "description": "Regularização, licenciamento ambiental e estudos de impacto com foco em sustentabilidade em MG." } },
    { "@type": "Offer", "itemOffered": { "@type": "Service", "name": "Plotagem, Impressão e Cópias", "description": "Impressão técnica de projetos em grandes formatos (A0, A1, A2) e plotagem de alta definição." } },
    { "@type": "Offer", "itemOffered": { "@type": "Service", "name": "Gestão e Administração de Obras", "description": "Gerenciamento completo: orçamento, contratação de mão de obra e suporte fiscal." } },
    { "@type": "Offer", "itemOffered": { "@type": "Service", "name": "Laudos Técnicos e Perícias", "description": "Pareceres técnicos, vistoria de vizinhança, análise de viabilidade e regularização de imóveis." } },
    { "@type": "Offer", "itemOffered": { "@type": "Service", "name": "Execução e Construção Civil", "description": "Execução completa de obras residenciais e comerciais, da fundação ao acabamento." } }
  ]
}
</script>
```

### Entidades Person (blocos separados, ou mesclados em um)

```json
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Person",
  "@id": "https://www.engeplena.com.br/#junaia",
  "name": "Junaia de Paula Lacerda",
  "jobTitle": "Sócia-Administradora · Engenheira Civil",
  "worksFor": { "@id": "https://www.engeplena.com.br/#business" },
  "alumniOf": { "@type": "CollegeOrUniversity", "name": "Universidade Federal de Ouro Preto (UFOP)" },
  "hasCredential": [
    { "@type": "EducationalOccupationalCredential", "credentialCategory": "Mestrado", "name": "Mestra em Engenharia Ambiental (UFOP)" },
    { "@type": "EducationalOccupationalCredential", "credentialCategory": "Especialização", "name": "Estruturas de Concreto Armado (INBEC)" },
    { "@type": "EducationalOccupationalCredential", "credentialCategory": "Registro Profissional", "name": "CREA-MG" }
  ]
}
</script>
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Person",
  "@id": "https://www.engeplena.com.br/#antonio",
  "name": "Antônio Carlos Cunha Júnior",
  "jobTitle": "Sócio-Administrador · Eng. Civil (Ênfase em Estruturas)",
  "worksFor": { "@id": "https://www.engeplena.com.br/#business" },
  "alumniOf": { "@type": "CollegeOrUniversity", "name": "Universidade Federal de Ouro Preto (UFOP)" },
  "hasCredential": [
    { "@type": "EducationalOccupationalCredential", "credentialCategory": "Especialização", "name": "Gestão de Projetos (IETEC)" },
    { "@type": "EducationalOccupationalCredential", "credentialCategory": "Especialização", "name": "Estruturas Metálicas (INBEC)" },
    { "@type": "EducationalOccupationalCredential", "credentialCategory": "Especialização", "name": "Patologia das Estruturas (IPOG)" },
    { "@type": "EducationalOccupationalCredential", "credentialCategory": "Registro Profissional", "name": "CREA-MG" }
  ]
}
</script>
```

**Notas sobre o template:** `postalCode` = **35450-078** e endereço = **R. Carlos Michel, 66** confirmados pelo registro do CNPJ (Seção 0). **"Sala 306" removida** — o CNPJ não registra sala (a sala pertencia ao cluster Pio XII 109). Números de CREA agora preenchidos (Seção 0): Junaia **1402661533**, Antônio **1402661576**. A única regra rígida continua sendo rodapé + schema + GBP + citações idênticos. `taxID` deve permanecer no schema mesmo que você não exiba o CNPJ em texto visível (é público).

---

## 8. Qualidade de Páginas de Localização

**N/A — local único** (sitemap tem exatamente 1 URL). Porém, o #1 fator de orgânico local E #2 fator de visibilidade em IA é **páginas de serviço dedicadas** (Whitespark 2026), e o site tem **zero** — seis serviços de receita comprimidos em cards de ~25 palavras numa homepage única (`index.html:423-548`). Todos os itens do menu são âncoras `#`; URLs `/servicos` retornam 404. Esse é o teto estrutural de todo sinal downstream: sem páginas profundas para ranquear por "projeto estrutural mg" / "consultoria ambiental itabirito" / "laudo técnico regularização", sem páginas para apontar citações/links, e extratores de boilerplate retêm só ~5% do texto da página para sistemas de IA. Quando as páginas de serviço forem adicionadas, seguir o padrão de subdiretório `/servicos/projeto-estrutural/`, um schema LocalBusiness/Service único com `@id` por página, >60–70% de conteúdo único, e linkagem interna hub-and-spoke.

---

## 9. Top 10 Ações Priorizadas (com falsificabilidade + indicadores antecedentes)

### CRÍTICO

1. **Resolver o NAP canônico (Pio XII vs Carlos Michel + Sala 306 + CEP + addressRegion).** Consultar a Receita Federal para decidir o endereço legal registrado; escolher o endereço operacional físico (Carlos Michel 66) como canônico; deletar "Sala 306" do schema; setar addressRegion para `MG`; alinhar o CEP.
   - *Falsificabilidade:* um diff único de rodapé vs schema vs GBP vs todas as citações mostra strings de endereço byte-idênticas; `grep -i "sala 306\|pio xii" index.html` retorna nada.
   - *Indicador antecedente:* taxa de correspondência de entidade melhora no Knowledge Panel; o cluster "Engeplena + Pio XII" deixa de aparecer nos SERPs.

2. **Retomar o footprint do GuiaMais + neutralizar a homônima do RJ.** Criar ficha no GuiaMais para a entidade de Itabirito na categoria correta ("Engenharia civil" / "Serviços de engenharia"), reivindicá-la, e sinalizar/solicitar supressão ou desambiguação da ficha "ENGEPLENA ENGENHARIA LTDA" do RJ (CNPJ 00.562.202/0001-27, "Pedras").
   - *Falsificabilidade:* `site:guiamais.com.br "Engeplena"` mostra o resultado de Itabirito (endereço/telefone/categoria corretos) acima ou substituindo o do RJ em até 60 dias.
   - *Indicador antecedente:* o SERP de marca de correspondência exata resolve para a empresa correta sem resultado de cidade errada.

3. **Construir as 6 páginas de serviço dedicadas** (`/servicos/*`) com ~800 palavras cada, schema de Serviço, FAQ local, processo/entregáveis/regulamentações.
   - *Falsificabilidade:* em 8–12 semanas, `site:engeplena.com.br/servicos` retorna páginas indexadas; uma busca de serviço ("projeto estrutural mg") mostra página de serviço no top 20.
   - *Indicador antecedente:* contagem de páginas indexadas no Google sobe de 1; profundidade do grafo de links internos para páginas de serviço ≤3 cliques.

4. **Publicar o JSON-LD corrigido (Seção 7).**
   - *Falsificabilidade:* Rich Results Test / validador de schema retorna zero erros; o bloco de schema agora fica dentro do `<head>`; `grep` encontra `@id`, `foundingDate`, `taxID`, `email`, dois blocos `Person`.
   - *Indicador antecedente:* endereço/geo do Knowledge Panel corresponde à página dentro de ~13 m do pin do GBP.

### ALTO

5. **Lançar programa de avaliações em conformidade visando o limiar mágico de 10, depois ≥1 avaliação a cada 18 dias.** Pedir a clientes satisfeitos (pós-projeto, pós-ART) diretamente via link de WhatsApp; nunca filtrar/rastrear satisfação antes de direcionar ao Google (proibição FTC + Google).
   - *Falsificabilidade:* contagem de avaliações do GBP chega a 10 em 60–90 dias e nunca fica 21 dias consecutivos sem nova avaliação; taxa de resposta do proprietário 100%.
   - *Indicador antecedente:* delta semanal de contagem >0; tempo de resposta <48h.

6. **Reivindicar e otimizar Bing Places + Apple Business Connect + submeter a 3 agregadores de dados (Data Axle, Foursquare, Neustar/TransUnion).** Bing Places está ausente e alimenta ChatGPT/Copilot/Alexa.
   - *Falsificabilidade:* o Bing Maps retorna a ficha da Engeplena Itabirito com NAP correto; uma consulta local do Copilot/ChatGPT a cita.
   - *Indicador antecedente:* painel do Bing Places mostra ficha "ao vivo"; e-mails de confirmação dos agregadores recebidos.

7. **Adicionar `tel:` click-to-call, restaurar a keyword local do H1 e corrigir `lang="pt-BR"`.** O telefone (31) 3561-3966 está hoje embrulhado em link `wa.me` (`index.html:949`), não `tel:`; a keyword da cidade no H1 está comentada (`index.html:276`); `<html lang="en">` (`index.html:2`).
   - *Falsificabilidade:* `grep -c 'href="tel:'` > 0; H1 renderiza "em Itabirito e Região"; `lang="pt-BR"`.
   - *Indicador antecedente:* eventos de tap-to-call no GA4; melhora de CTR mobile para buscas locais.

8. **Publicar credenciais CREA/CNPJ/ART + remover logos de clientes placeholder.** Zero ocorrências de CREA/CNPJ/ART hoje; `#s-partners` (`index.html:776-818`) envia 4 links-follow para `site-do-parceiro.com`/`site-parceiro-c.com` além de nomes falsos ("Empresa Parceira 1", "Construtora Rocha", "Imobiliária Silva") — prova social falsa e equity desperdiçado.
   - *Falsificabilidade:* `grep -c 'site-do-parceiro\|site-parceiro-c' index.html` = 0; rodapé mostra CNPJ 07.936.059/0001-35 e números CREA.
   - *Indicador antecedente:* sinais de E-E-A-T/entidade; menos flags de "parceiro falso" em revisão manual.

### MÉDIO

9. **Construir o conjunto de citações brasileiras Tier-2** (CREA-MG, Prefeitura de Itabirito, SINDUSCON-MG, Apontador, MaisEmpresas, TeleListas, Solutudo) e **corrigir as fichas existentes do Cylex/Bendito Guia/todosnegocios** (endereço errado, horários errados, texto template de Atibaia).
   - *Falsificabilidade:* todos os diretórios retornam NAP idêntico; score de consistência de citação BrightLocal/Whitespark ≥90%.
   - *Indicador antecedente:* SERPs "Engeplena + <diretório>" convergem para um único endereço.

10. **RP digital local + listas "best of" + presença comunitária** (câmara ACI-Itabirito, eventos do SINDUSCON-MG, imprensa local sobre o trabalho na região de Vale/mineração, diretórios de fornecedores de mineração).
    - *Falsificabilidade:* 5–10 links locais de qualidade/mês por 6 meses; uma colocação em lista "melhor engenharia/consultoria Itabirito/Quadrilátero Ferrífero".
    - *Indicador antecedente:* menções de marca (Ahrefs/Google Alerts) de domínios locais; tráfego de referência de itabirito.mg.gov.br, sinduscon-mg.org.br, imprensa local.

### BAIXO (backlog, incorporar às operações mensais)
Fotos do GBP (15–30 incl. fachada/equipe), 2–4 posts no GBP/mês, semeadura de Q&A do GBP, monitorar o badge verificado, e — uma vez que as páginas de serviço existirem — definir o campo "site" do GBP para URL que não seja a homepage (Sterling Sky Diversity Update) para que a página mais forte não seja suprimida.

---

## 10. Declaração de Limitações

O que NÃO pôde ser avaliado sem ferramentas pagas ou acesso ao painel:
- **Dados ao vivo do GBP:** contagem de avaliações, nota média, categorias primária/secundárias, badge verificado, posts, Q&A, contagem de fotos — nada acessível a partir da página pública do Maps (Google Maps bloqueia fetch headless). A categoria é o #1 fator do pacote (193) e a categoria errada o #1 negativo (176); segue sendo a maior incógnita.
- **Posições ao vivo do pacote local / geo-grid:** sem dados de SERP localizados/geofenced; proximidade (55,2% da variância, Search Atlas) é imensurável aqui e fora do controle da Engeplena de qualquer forma. Itabirito (~25k hab., Quadrilátero Ferrífero, bacia de mineração da Vale) dá à Engeplena vantagem natural de proximidade contra especialistas de BH/Ouro Preto em buscas locais.
- **Estado do Bing Places:** ausência confirmada via fetch do Bing Maps, mas uma ficha reivindicada-porém-oculta poderia existir; estado do Apple Business Connect não verificável.
- **Atividade do Facebook** não totalmente avaliável (visão deslogada).
- **Perfil de backlinks** é estimativa da auditoria anterior (18/100; domínio ausente do Common Crawl 2024-2026) — sem Ahrefs/Moz/DataForSEO configurados neste ambiente.
- **Endereço do CNPJ:** dois clusters de registro conflitantes; só uma consulta à Receita Federal resolve.
- **Yelp/BBB/diretórios Tier-2 dos EUA** considerados N/A para PME brasileira.
- **Ferramentas pagas para preencher lacunas:** DataForSEO `business_data_business_listings_search` (GBP ao vivo + auditoria de diretórios), `serp_organic_live_advanced` (posições de pacote local localizadas), BrightLocal/Whitespark (tracker de citações), Places Scout (geo-grid), Ahrefs/Moz (backlinks).

---

## 11. Contexto de Busca com IA (Local)

- **AI Overviews aparecem em até 68% das buscas locais** (Whitespark Q2 2025); o ChatGPT converte a 15,9% vs. 1,76% do orgânico Google (Seer Interactive).
- **3 dos 5 principais fatores de visibilidade em IA são ligados a citações** (Whitespark 2026) — mas a superfície de citações da Engeplena é fina, parcialmente errada (Bendito Guia), e o footprint do nome exato está nas mãos da entidade errada (GuiaMais/RJ).
- **O ChatGPT NÃO acessa o GBP diretamente** — ele usa o índice Bing, Yelp, TripAdvisor, BBB, Reddit. A Engeplena não tem **Bing Places**, não tem presença em Reddit/BBB, e tem Facebook de baixa atividade. A superfície visível para IA é portanto quase zero e hoje resolve de forma ambígua.
- Esta auditoria cobre apenas os fatos de IA relevantes ao local. Para a análise completa de visibilidade em IA (scoring de citabilidade, checagem de llms.txt, auditoria de menções de marca), executar **`/seo geo https://www.engeplena.com.br`**.

---

## 📁 Arquivos relevantes

- `/Users/redguy/Documents/landing_page/index.html` — site de página única; JSON-LD na linha 3, comentário do H1 na linha 276, embed Maps na linha 837, NAP do rodapé linhas 942–982, parceiros placeholder linhas 776–818.
- `/Users/redguy/Documents/landing_page/sitemap.xml` — 1 URL, `lastmod` desatualizado.
- `/Users/redguy/Documents/landing_page/auditoria-seo-2026-08-13.md` — auditoria completa anterior (SEO Local 54/100) usada como baseline verificado de GBP.

**Conclusão:** site tecnicamente limpo e com schema válido, cujo teto local é definido pela arquitetura (sem páginas de serviço), um programa de avaliações quebrado, uma identidade NAP de dois endereços não resolvida, e um footprint de citações que hoje resolve para a empresa errada. Corrigir a identidade primeiro (NAP + GuiaMais + schema), depois a arquitetura (páginas de serviço), depois a geração de demanda (avaliações + citações + RP local).
