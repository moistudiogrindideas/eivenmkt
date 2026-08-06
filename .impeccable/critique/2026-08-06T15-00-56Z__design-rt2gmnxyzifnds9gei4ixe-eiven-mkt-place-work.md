---
target: Eiven home v2 - Curadoria Visível (Figma)
total_score: 22
max_score: 28
na_heuristics: 7,9,10
p0_count: 1
p1_count: 3
timestamp: 2026-08-06T15-00-56Z
slug: design-rt2gmnxyzifnds9gei4ixe-eiven-mkt-place-work
---
## Design Health Score

| # | Heurística | Nota | Achado-chave |
|---|---|---|---|
| 1 | Visibilidade do status do sistema | 2/4 | Só "Sacola (0)" mostra estado; sem indicador de progresso/seção ativa |
| 2 | Correspondência com o mundo real | 4/4 | Copy natural em PT-BR, objetivos nomeados como metas reais |
| 3 | Controle e liberdade do usuário | 3/4 | Escapes existem (card "não sei", Categorias); sem affordance de skip/voltar |
| 4 | Consistência e padrões | 4/4 | Cards/badges/tipografia consistentes; mesmo grid 4-colunas reaparece 2x (ver P0) |
| 5 | Prevenção de erros | 2/4 | Único campo testável (e-mail) sem hint de formato/erro definido |
| 6 | Reconhecimento > memorização | 4/4 | Rótulos curtos, badges reconhecíveis à primeira vista |
| 7 | Flexibilidade e eficiência | n/a | Superfície de persuasão estática — não se aplica |
| 8 | Design estético e minimalista | 3/4 | Boa respiração, mas densidade de confiança em 08-10 compromete o minimalismo |
| 9 | Ajuda a reconhecer/diagnosticar erros | n/a | Sem estados de erro definidos nesta etapa (pré-interação) |
| 10 | Ajuda e documentação | n/a | Não se aplica a uma home/landing |
| **Total** | | **22/28** | **79% — Good** |

## Design Specificity Verdict

**LLM (Assessment A):** Positivo, com ressalva. O hero recusa navegação por categoria explicitamente, o seletor central é por objetivo, os cards de produto carregam selos de curadoria + preço-por-dose (mecânica específica de suplemento), os cards de marca têm justificativa editorial em vez de só logo, e existe uma seção de processo ("Como Curamos") que nenhum catálogo genérico teria — é autoral pra Eiven. Ressalva: a seção 06 · Categorias reintroduz a lógica de catálogo que o resto da página nega.

**Varredura determinística (Assessment B):** Detector CLI inaplicável ao alvo (canvas Figma, não HTML/CSS — puppeteer não resolveria isso mesmo instalado); injeção de DOM pulada pelo mesmo motivo. Auditoria mecânica alternativa sobre os 208 nós do frame: **100% de conformidade com o mandato de botões retangulares** (0/71 nós com cornerRadius ≠ 0) e **100% de conformidade com grayscale puro** (13 fills distintos, todos R=G=B, zero matiz). Espaçamento vertical entre as 12 seções é **exatamente 56px em 11/11 gaps**. Dois desvios estruturais reais encontrados: margem do Header (48px vs 64px padrão) e margem direita da seção CTA Final (234px — quase 4x o padrão, espaço morto real confirmado por screenshot).

**Overlay visual:** não aplicável — o alvo é um canvas nativo do Figma, sem DOM injetável; a evidência visual veio de screenshots via API do Figma, não de um overlay no navegador.

## Overall Impression

O wireframe já é claramente autoral (curadoria como mecânica, não decoração) e tecnicamente limpo nas regras que o cliente mandou (grayscale puro, botões retangulares, grid vertical de 56px). O problema não é falta de trabalho — é excesso dele no mesmo lugar: três seções seguidas (Manifesto → Como Curamos → Prova Social) tentam provar a mesma coisa com a mesma gramática visual, e a página oferece duas portas de entrada de peso igual (por objetivo vs. por categoria) que competem entre si — a maior delas, inclusive, contradiz a frase-síntese do próprio Manifesto duas seções antes.

## What's Working

1. **Hero (02)** — CTA único, copy afiada, e a linha de confiança já faz dupla função (posicionamento + prova) sem sobrecarregar o hero.
2. **Destaques (05)** — selos "Curadoria Eiven"/"Seu Perfil" + preço-por-dose são mecânica de card genuinamente específica pra Eiven; grid assimétrico cria hierarquia em vez de virar catálogo plano.
3. **Curadoria por Marca (07)** — a legenda "Por que escolhemos: ..." transforma a lista de marcas num argumento editorial.
4. **Disciplina técnica** — 100% dos botões retangulares, 100% grayscale puro, 56px de gap consistente entre as 12 seções (confirmado por varredura mecânica, não só visual).

## Priority Issues

**[P0] Fadiga de seções de confiança redundantes (08→09→10)**
Why it matters: Manifesto, Como Curamos e Prova Social são 3 seções consecutivas repetindo "avaliamos/confiamos" — Como Curamos e Prova Social inclusive reusam literalmente o mesmo grid de 4 colunas numeradas com divisores verticais. Isso dilui o pico emocional do Manifesto e cria fadiga de leitura no momento em que o usuário deveria migrar pra decisão/CTA.
Fix: fundir Como Curamos e Prova Social numa seção só — "zero favorecimento" e "3 marcas, 1 frete" viram 2 dos 4 critérios do processo, ou Prova Social encolhe pra uma faixa fina de 1 linha.
Suggested command: /impeccable layout

**[P1] Arquitetura de informação dupla e concorrente (03 vs 06)**
Why it matters: Perfis/Objetivos e Categorias oferecem dois pontos de entrada de peso visual equivalente, a 3 seções de distância — contradiz o próprio Manifesto ("recomendação por objetivo — não por categoria") e retreina o usuário pro comportamento antigo, corroendo a centralidade do quiz.
Fix: rebaixar Categorias pra tratamento mais utilitário/compacto, ou reenquadrar como via secundária ("já sabe o que procura?").
Suggested command: /impeccable layout

**[P1] Fileira de 8 cards em Perfis/Objetivos sem apoio textual**
Why it matters: 7 objetivos + 1 assistido, todos só com rótulo de uma palavra. Pra um visitante de primeira vez, "Evoluir" vs "Transformar" vs "Construir" não são autoevidentes — empurra reconhecimento pra recall.
Fix: adicionar descritor de 4-6 palavras por card, ou reduzir exposição inicial a 4 objetivos + "ver todos".
Suggested command: /impeccable clarify

**[P1] CTA Final (11) — desvio estrutural de margem (234px à direita vs. 64px padrão)**
Why it matters: achado mecânico confirmado por medição de nó + screenshot — o bloco "Assinar" termina bem antes da borda de conteúdo usada nas outras 11 seções, deixando espaço morto real que quebra o grid consistente do resto da página.
Fix: realinhar o bloco de newsletter (input + botão) pra terminar na mesma margem de 64px das demais seções.
Suggested command: /impeccable layout

**[P2] CTA de quiz repetido 3x sem progressão de copy**
Why it matters: Hero, Reforço do Quiz e CTA Final pedem a mesma ação com copy quase idêntica — nenhuma escala valor/urgência com base no que o usuário acabou de ver, e o card "Reforço do Quiz" repete quase palavra por palavra o card "não sei por onde começar" visto ~150px antes.
Fix: variar a copy por contexto de scroll (ex: pós-Destaques, "quer ver a curadoria pro SEU objetivo?").
Suggested command: /impeccable clarify

## Persona Red Flags

**Jordan (Confuso, primeira vez):** Chega bem pelo Hero. Trava em 03 · Perfis/Objetivos sem descrição em nenhum dos 8 cards. Esbarra em 04 · Reforço do Quiz, que repete o que acabou de ver em 03 — parece bug de conteúdo duplicado, não reforço. Em 06 · Categorias, tem grande chance de recorrer ao grid "por tipo" familiar em vez do quiz — o comportamento que a Eiven mais quer evitar no público que mais precisa de curadoria.

**Riley (Testador rigoroso):** Cobra o preço-por-dose do card Creatina (05) — sem unidade/porção declarada, o número parece confiável mas não é verificável. Nota "zero favorecimento" afirmado duas vezes (07 e pilar 02 de 10) sem nenhum mecanismo de prova. Clica no card "Recompor (em breve)" (03) esperando estado desabilitado ou explicação — nada indica se é clicável ou leva a lista de espera.

**Casey (Mobile, avaliando tradução futura):** A fileira de 8 cards em 03 só funciona como scan horizontal completo em desktop — em mobile, itens 5-8 (Construir/Transformar/Recompor) provavelmente ficam fora da dobra inicial. 09 e 10, ambos grids de 4 colunas com divisores, precisam virar 8 blocos verticais consecutivos em mobile — maior risco de abandono no scroll do fluxo inteiro.

## Minor Observations

- Nav do header lista "Editorial", mas nenhuma das 12 seções corresponde a conteúdo editorial — link solto nesta versão.
- Nenhum card de produto mostra os dois selos ("Curadoria Eiven" + "Seu Perfil") ao mesmo tempo — e a auditoria mecânica confirma que os dois badges têm padding interno direito diferente (6px vs 12px), sem base de componente real do Figma (0 nós INSTANCE/COMPONENT no arquivo) — risco real de inconsistência se algum dia coexistirem no mesmo card.
- Margem do Header é 48px, não os 64px usados nas outras 10 seções com margem lateral definida.
- Escala tipográfica pouco disciplinada: 17 tamanhos de fonte distintos, 10 deles usados 4x ou menos — inclui um par suspeito (10px em preço/dose vs 10.5px em "por que escolhemos") que parece drift acidental, não degrau de escala deliberado.
- Cupom de 10% (11) tem peso visual igual ao CTA de quiz — driver mais fraco da pesquisa (19%) competindo visualmente com o driver mais forte (confiança, 73%) no momento final de conversão.

## Questions to Consider

1. Se Manifesto + Como Curamos + Prova Social já cobrem 100% do "por que confiar" em 3 seções seguidas, por que ainda existe um 4º empurrão (CTA Final) depois disso? A estrutura está otimizada pra convencer, ou pra "não deixar nenhuma mensagem de confiança de fora"?
2. Se a Eiven se define como "não vende produtos, entrega certeza" e a pesquisa mostra confiança dominando preço, por que dar à seção "por tipo de produto" o mesmo peso visual que "por objetivo"?
3. Como o rail de 8 objetivos vai se comportar em mobile — carrossel, grid 2x4, lista? Essa decisão muda completamente qual objetivo o usuário vê primeiro.
