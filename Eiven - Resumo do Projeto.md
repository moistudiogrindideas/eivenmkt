# Eiven — Contexto e Fluxos do Projeto

*Última atualização: 06/08/2026*

## Visão geral
- **Projeto:** Eiven — marketplace wellness multi-marcas.
- **Cliente:** Eiven. Contato principal: Júlia Vieira.
- **Marcas participantes citadas:** DUX, Z2, Vitafor.
- **Escopo Mói:** UX → UI (jornada do consumidor desktop/mobile + painel do seller) e desenvolvimento em WordPress + WooCommerce + Dokan Professional, com CRM Hubspot.
- **Classificação:** projeto L (150–400h, 6–12 semanas).
- **Status atual (22/07/2026):** Discovery iniciado, primeira imersão feita. Checkpoints semanais com a cliente às sextas.

## Posicionamento estratégico
- **Frase-síntese (pesquisa):** *"A Eiven não vende produtos. A Eiven entrega certeza."*
- **Frase-síntese para pitch/investidor:** *"A Eiven é a plataforma que reduz a ansiedade de decisão do atleta de alta performance, conectando-o aos suplementos certos por meio de uma curadoria inteligente, confiável e personalizada."*
- **Insight central:** a Eiven é um marketplace que não vende produtos por categoria — pode até vender, mas o cerne é ser uma curadoria para o cliente: ele compra com base nos seus objetivos e perfil, não navegando por categoria de produto.
- **Por que isso importa:** o problema do usuário não é acesso a suplementos (ele já acha em qualquer lugar — Amazon, ML, site oficial), é decidir qual comprar. A concorrência real da Eiven não é Amazon/ML, é "a dúvida" do consumidor.
- **Ordem de prioridade de valor percebido** (da pesquisa, 10 insights, pág. 80-94 do PDF "Projeto Eiven - Site.pdf"): confiança > preço > cashback/cupom/variedade > personalização (personalização é sentida como obrigação mínima, não diferencial — usar como critério ao priorizar features).
- Nutricionista é o maior influenciador de consumo (76%) — recomendação: reputação mais próxima de ciência/técnica do que de lifestyle/creator. Evitar posicionar a Eiven como "uma IA que recomenda suplementos".

## Escopo do projeto
Fulfillment centralizado: a Eiven (cliente) faz estoque e entrega via plataforma logística própria — as marcas não despacham, e o consumidor recebe um pacote só. O split de pagamento entre marcas continua existindo, mas a quebra é só financeira (comissão/repasse), não operacional. O rastreio para o consumidor fica na Eiven, alimentado pela plataforma logística. Isso implica um escopo de dev novo: integração WooCommerce ↔ WMS (pedido pago → WMS; WMS → rastreio + baixa de estoque em tempo real), e o painel do seller encolhe — a marca vira fornecedora, sem telas de despacho/etiqueta/rastreio. A fonte de verdade do estoque (WMS vs. WooCommerce) ainda será definida em Discovery. A nomenclatura final dos objetivos/perfis do quiz (atualmente 7 nomes em português: Evoluir, Preparar, Regenerar, Viver Melhor, Construir, Transformar, Recompor — tbd) e a paleta/direção visual (preto/verde-oliva/dourado, tom editorial/lifestyle) também serão fechadas em Discovery.

## Fluxos principais

### Home
- **Ação prioritária ao chegar:** o usuário deve ser impactado a responder o quiz de objetivos — é a ação central da home, antes de qualquer navegação por categoria (coerente com o insight central de curadoria por objetivo/perfil).
- **O que a home precisa conter:** reforço do quiz de objetivos em mais de um ponto da página (não só um CTA único); sinais de confiança logo no topo (frete, parcelamento, compra segura); navegação alternativa por objetivo/perfil pra quem não quer fazer o quiz; vitrines de produto (lançamentos, mais vendidos); prova social e elementos que reforcem credibilidade da curadoria; conteúdo curado pela própria Eiven (kits/coleções), não só produtos soltos; espaço leve pra conteúdo institucional/editorial; e captura de lead (newsletter, cupom de primeira compra).

### Quiz / Onboarding
- **Validado:** 92% topam responder o quiz, mas só ~46-49% topam gastar 5-10min nele.
- **Recomendação de UX:** quiz rápido de 60s → mostra resultado → oferece "quer deixar a recomendação mais precisa?" como segunda etapa opcional.
- Email cedo no fluxo, incluir pergunta de preço/budget. Botão de refazer o quiz sempre visível no menu superior.
- **Risco crítico (citado pela cliente):** um benchmark falhou em mostrar as recomendações no final ("péssima experiência") — fluxo pós-quiz é ponto de atenção de QA.

### Busca / Navegação
- 3 eixos de busca: por objetivo, por tipo de produto, por marca.
- Página de busca ideal: carrossel pós-quiz → categorias (endurance/build/recovery) → tipo de produto.
- Página da marca: categorias vendidas + banner de checkout com 2 produtos da marca.

### Páginas por objetivo (resultado do quiz)
- **Conceito:** cada objetivo/perfil do quiz (Evoluir, Preparar, Regenerar, Viver Melhor, Construir, Transformar, Recompor — tbd) gera sua própria página de destino, não é só um filtro ou card na home. É onde a curadoria por objetivo — o insight central do produto — se materializa: o conteúdo, os produtos recomendados e o contexto mudam de acordo com o objetivo respondido no quiz.
- **Objetivo da página:** funcionar como um espaço dedicado ao objetivo do usuário, indo além de vitrine de produto — trazendo contexto (ex. progresso, fase, rotina), produtos recomendados pra aquele momento específico e conteúdo/prova social relacionados, reforçando a percepção de recomendação personalizada em vez de compra genérica.
- **Referência mais detalhada até agora — "Preparar":** funciona como um dashboard de programa (ex. contagem de dias pra uma prova), com produtos organizados por fase (antes/durante/depois) e timeline de uso. Serve como exemplo do nível de profundidade que uma página de objetivo pode ter, mas cada um dos demais objetivos ainda precisa ter seu próprio conceito definido — o contexto de "Preparar" (treino pra um evento) não necessariamente se aplica a objetivos como "Regenerar" ou "Viver Melhor".

### PDP (página de produto)
- Painel de detalhes/accordion na lateral direita: Detalhes, Como usar, Ingredientes, Alérgicos, Avaliações, FAQ, Frete, Trocas.
- Mesmo painel de cross-sell também na página de recomendação pós-quiz, não só na PDP normal.

### Carrinho / Checkout
- Cross-sell deve ficar ACIMA do resumo do pedido, não abaixo.
- Banner ao abrir a sacola (modal com produto/promoção, preço riscado + promo, CTA "adicionar à sacola") antes de mostrar os itens.
- Recomendar produtos por marca OU por objetivo (decisão em aberto).
- Se houver assinatura: mostrar economia em R$, oferecer recorrência mensal.
- Pesquisa pós-checkout perguntando onde a pessoa conheceu a marca.

## Insights de pesquisa com usuários (10 insights + síntese, PDF pág. 80-94)
- 4 tipos de fidelidade (emocional, racional, técnica, por performance) — a assinatura Eiven substitui as das marcas, não compete com elas.
- Mercado hoje compete por preço/marca/sabor/desconto; oportunidade da Eiven é competir por confiança/descoberta/conveniência/inteligência.
- Mercado aberto à descoberta (81% nota 8-10 pra conhecer novas marcas) — não vender "a melhor marca", vender "a melhor escolha pra você".
- Confiança (73%) > preço (70%) > entrega (41%) > cupom (19%) > frete (8%) na decisão de compra.
- Conceito validado: 92% usariam uma plataforma que centraliza suplementos e recomenda por rotina/objetivo — primeiro sinal de product-market fit.
- Consumidor ainda compra direto da marca (site oficial 86%, Amazon/ML 57%) — não existe agregador confiável ainda; oportunidade segue aberta.
- Mercado pulverizado sem líder dominante (Liquidz 59%, Z2 49%, Dux 41%, Dobro 38%, Caffeine Army 32%, Essential 24%, Jungle 24%, Pura Vida 14%, Maurten 8%).
- 3 problemas do usuário que a Eiven resolve: (1) tem que pesquisar dezenas de marcas, (2) não sabe qual produto faz sentido pra ele, (3) acaba comprando sempre nos mesmos lugares.
- Case Jungle (Positive Co.): agente de IA no site desvia pro WhatsApp e depois volta — cliente achou "dinheiro jogado fora". Na Eiven, se usar IA/WhatsApp, a compra deve fechar no próprio canal.

## Referências e benchmarks
- **Sites-referência da cliente:** thefeed.com (melhor referência — busca visível no header, filtros laterais, hover mostra variações/marcas), thrivemarket.com, hourglasscosmetics.com, moss.nyc, lifetime.life, equinox-hotels.com (apresentação aspiracional de produto).
- **Diferenciais que a cliente quer:** lojas próprias das marcas dentro do marketplace, personalização, destaque pros benefícios do produto, tom aspiracional, curadoria/conteúdo informativo, apoio nutricional, member-get-member, comunidade, assinatura, parcerias/cashback, página de lançamentos, integração com Strava e Whoop, acessórios/roupas.
- **Direção de marca (lifestyle premium):** benchmarks analisados fora do PDF do cliente — rhodeskin.com (fotografia editorial P&B, copy sensorial curta, "one of everything really good" como filosofia de catálogo enxuto), phlur.com (tipografia serifada editorial, macro de ingrediente em vez de still de produto, framing de membership), on.com (navegação por atividade/intenção em vez de taxonomia de produto, bloco de manifesto). Direção adotada: tipografia mista — Playfair Display (display/serifado, momentos emocionais) + Inter (UI/corpo) — grid vertical de 56px entre seções, wireframes sempre em cinza puro (sem cor) e botões 100% retangulares (sem pill).
- **Levantamento completo do benchmark do PDF do cliente** (`Projeto Eiven - Site.pdf`, pág. 6-60 — arquitetura do site, busca, PDP, quiz/personalização, checkout, estudo de marca): tabela com 34 linhas (Seção / Componente / Solicitação / Link / Nossa solução) já compilada — ver arquivo entregue ao Werner (paste-ready markdown, ainda não colado no Notion do projeto por falta de autenticação no ambiente de trabalho). Achado mais valioso: a página 45 do PDF mostra a página de resultado de quiz da própria **Z2** (marca parceira da Eiven) já resolvendo com métricas personalizadas + kit de produtos + guia de uso por momento de treino — é a referência mais forte pra página "Preparar"/resultado do quiz, e é interna ao próprio ecossistema de marcas da Eiven. Decisão de PDP confirmada: "Opção A" (accordion lateral direita, ref. hourglasscosmetics.com) em vez de "Opção B" (sem accordion, ref. essential.com.br), incorporando o cross-sell da Opção B abaixo do CTA.
- **Gaps reais sem decisão de design ainda** (mapeados no benchmark, não resolvidos): pop-up de cupom de primeira compra na home; botão de quiz fixo no header (pedido explícito da cliente, ainda não implementado nos wireframes); página de busca/PLP com filtros laterais; hover de mega-menu no card de produto (sugerido como fase 2); onde comunicar desconto no checkout; página dedicada da marca (ref. duxhumanhealth.com).
- **Avaliação de ideias de feature (curadoria visível, PLP, PDP, checkout) contra viabilidade WP/Dokan:** picks fortes e baratos — nota do curador na PDP, selo de curadoria, laudos/certificados em accordion, preço por dose, toggle "compatível com meu perfil" (reaproveita resultado do quiz como filtro persistente), comunicar o diferencial do CD único ("3 marcas, 1 frete"), e a versão enxuta (só cafeína) do alerta de duplicidade de ingrediente no carrinho. Ideias que parecem baratas mas não são: avaliação por sabor (WooCommerce não separa review por variação nativamente), busca em linguagem natural (resolver com dicionário curado sintoma→tag, não NLP de verdade), comparador lado a lado (o gargalo é governança de atributo por marca, não a UI). Regra reforçada: nunca publicar estatística de pesquisa interna (ex. "X% das marcas aprovadas") como prova social pro consumidor — só afirmação de processo/critério real e auditável.

## Wireframes — Home (exploração de direção)
Feitos no arquivo Figma de trabalho (ver abaixo), página "✏️ Wireframe", lado a lado com as 4 iterações anteriores em cinza-caixa já existentes ali (não mexidas).
- **v1 — "T01 · Home — Direção Lifestyle Premium"** (node `4808:2`): primeira aplicação da direção lifestyle — hero editorial, seletor de 7 objetivos, grid assimétrico "curadoria não catálogo", cards de loja por marca, quote de manifesto centralizada, seção de 3 pilares de confiança, CTA duplo de quiz+newsletter.
- **v2 — "T01 · Home — Curadoria Visível (v2)"** (node `4835:2`): evolução da v1 respondendo à provocação de que a curadoria só existia no admin — adiciona selo "Curadoria Eiven" nos cards de produto (+ variante "Seu Perfil" prevendo o toggle de compatibilidade com o quiz), preço por dose em todo card de produto, storytelling "por que escolhemos essa marca" nos cards de marca, e uma seção nova "Como Curamos" (processo em 4 passos, sem estatística inventada).
- **Revisão de UX (skill Impeccable, 06/08):** nota 22/28 (79%, "Good") nas 10 heurísticas de Nielsen aplicáveis. Achado principal (P0): as seções Manifesto → Como Curamos → Prova Social repetiam a mesma mensagem de confiança 3x seguidas, com Como Curamos e Prova Social reusando literalmente o mesmo grid de 4 colunas — **já corrigido**, seção Prova Social removida (conteúdo era 100% redundante com Como Curamos + a linha de confiança do hero). Também corrigidos: bug estrutural de margem no CTA Final (bloco de assinatura terminava 234px antes da borda padrão de 64px) e margem do header (estava 48px, não 64px). **Ainda pendente, não aplicado:** rebaixar visualmente a seção Categorias (hoje compete de igual pra igual com Objetivos, contradizendo o próprio Manifesto — "por objetivo, não por categoria") e adicionar descritor curto em cada um dos 7 cards de objetivo (hoje só têm o nome, sem contexto pra quem chega pela primeira vez).

## Wireframes — Quiz de Perfil (fluxo completo)
Feitos no mesmo Figma de trabalho, página "✏️ Wireframe", ao lado dos frames Home v1/v2 (mesma linha, y `8712`) — 9 telas, uma por frame (`T02 · Quiz — ...`), 1440px de largura, layout split-screen (pergunta à esquerda, imagem editorial à direita) inspirado na navegação/estrutura de um quiz de referência (site real "Salt & Stone"), adaptado à identidade Eiven (Playfair Display + Inter, cinza puro, botões 100% retangulares).
- **01 Landing** (node `4891:67`) — hero com CTA "Começar".
- **02 Nome + E-mail** (node `4891:68`) — captura de lead logo no início do fluxo, não replicando a etapa de e-mail pré-resultado da referência.
- **03 Objetivo** (node `4891:69`, Pergunta 1 de 5, single-select) — 6 opções.
- **04 Esportes** (node `4891:70`, Pergunta 2 de 5, multi-select) — 5 opções.
- **04b Prova · condicional** (node `4891:71`, mesmo rótulo "2 de 5", não incrementa o contador) — só aparece pra quem indicou corrida/ciclismo/triathlon; pergunta Sim/Não + distância (5k/10km, 21km, 42km+).
- **05 Rotina de treino** (node `4891:72`, 3 de 5, single-select).
- **06 Hábitos alimentares** (node `4891:73`, 4 de 5, single-select) — renomeada de "Alimentação" pra não sobrepor com a Tela 07 (resolução de uma inconsistência apontada na revisão).
- **07 Restrições e preferências** (node `4891:74`, 5 de 5, multi-select + campo de texto livre "Outro").
- **08 Resultado** (node `4891:75`) — banner de perfil (exemplo ilustrativo: "Evoluir") + seção "Sua base recomendada" (produtos essenciais com dois botões por card: "Adicionar ao carrinho" primário e "Guardar para depois" secundário) + sidebar "Seu carrinho" que **nasce vazia e só populasr quando o usuário confirma cada item** (decisão deliberada — diverge da referência, que pré-popula o carrinho sozinha, porque contraria o pedido do cliente de "com a palavra final do usuário") + seção "Também pode fazer sentido pra você" (grid de descoberta, sem pré-seleção).
- **Processo:** rodados 4 agentes especializados (UX, arquitetura de informação, UX writer, QA de revisão final) pra fechar a espec antes de desenhar — decisões registradas incluem: e-mail mantido na Tela 02 (nunca criar gate entre o usuário e a recomendação, dado que um concorrente já falhou nisso), branch condicional de prova não conta como pergunta extra na numeração percebida, nomenclatura de perfil "Evoluir" usada como exemplo ilustrativo na tela de resultado (perfil "Recompor" segue sem regra de mapeamento definida, fora do escopo do wireframe).
- **Bug corrigido durante a montagem:** frame de texto do banner de resultado tinha fundo branco padrão sobrepondo o fundo escuro do banner, deixando o texto branco invisível — corrigido tornando o frame transparente.
- **08 Resultado — v2, carrinho pré-preenchido** (node `4910:73`, ao lado da v1, sem substituí-la): variação a pedido do Werner onde os essenciais já entram no carrinho automaticamente (sidebar populasda desde o início, subtotal real R$ 369,70, CTA "Finalizar pedido" ativo). Como a decisão de compra já foi tomada pelo sistema, a área que antes vendia o produto ("Adicionar ao carrinho" / "Guardar para depois") foi substituída por **"Por que essa é a sua base"** — cada card explica o motivo da curadoria daquele item pro perfil ("por que faz parte da sua base") e uma tag de uso ("Como usar — Pós-treino/Diariamente/Pela manhã"), reforçando o pilar de confiança/curadoria da marca em vez de repetir um CTA de compra redundante. O controle do usuário (Nielsen #3) se mantém via "Remover da base" em cada card e "✕" na sidebar. Frame inclui notas visuais (faixa amarela no topo + caixa no rodapé) explicando a lógica da variação — remover quando a direção for validada, não fazem parte da UI final.

## Artefatos e arquivos
- **Figma Design** (sitemap, cards brancos borda preta, chips pretos de ator): projeto "Eiven MKT Place" (id 629566871) — https://www.figma.com/design/PLPjHax7rWc3kJBeYSi1aX
- **Figma de trabalho** (wireframes de home v1/v2, moodboard de inspiração, sitemap, style guide): "Eiven MKT Place - WORK" — https://www.figma.com/design/RT2gMNXYziFNdS9gEI4IXe
- **FigJam** (versão simples): https://www.figma.com/board/5hzK6dRrVtw0apR01LlDPg
- **Notion:** sitemap mermaid + decisões pendentes; cronograma em database, página "Eiven MKT place" — https://app.notion.com/p/3a5ac4676fa980b0b6b0f15084f05ea3 (formato tabela igual ao Festa do Brincar, ordenada por Início)
- **Já dentro de `~/eiven mkt place/`:**
  - `Projeto Eiven - Site.pdf` (109 pág. — lidas até agora: pág. 1-70 e 80-94; faltam pág. 71-79 e 95-109)
  - `Sitemap - Eiven MKT place.png`
  - `WON - Fluxo do marketplace.pdf`
- **Ainda fora da pasta (não copiados):**
  - `~/Downloads/Projeto Eiven - Site.pptx` e versão `(1).pptx` (04/08/2026)
  - `~/Downloads/WON_Guia_Desenvolvimento_Marketplace.pdf`
  - `~/Downloads/Recibo Entrada MKT Place.pdf` e `~/Desktop/Recibo Entrada MKT Place.pdf` (tamanhos diferentes, possível duplicata — não decidido qual é a válida)
  - `~/Desktop/pc10_REV-07-07-26-Desenvolvimento MKT Place WON.pdf`

## Cronograma (datas ainda não validadas contra capacity board)
- **Dev em 4 ondas:** infra (03-28/08) → front consumidor (31/08-11/09) → integrações (07-18/09) → painel seller (21/09-02/10).
- **Modelo em esteira (wireframes por jornada):** S3-S6 — navegação+onboarding → home+busca → vitrine+produto → checkout+perfil. Pedro+Werner desenham conceito e telas-mestras (onboarding, home, vitrine — definem o design system); Sthefany faz rollout do resto.
- Protótipo da jornada do consumidor: **11/09**.
- UI Seller: movido para **14-18/09**.
- Go-live: **08-09/10** (era 02/10).

