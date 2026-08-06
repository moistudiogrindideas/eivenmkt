# Eiven — Histórico da sessão (wireframes, benchmark e setup do repo)

*Registro do que foi feito nesta sessão, em ordem cronológica. Complementa `Eiven - Resumo do Projeto.md` (que guarda as decisões consolidadas) com o passo a passo de como se chegou até elas.*

## 1. Direção de marca — lifestyle premium

Werner pediu que a experiência da Eiven tivesse "pegada premium, lifestyle" — não um marketplace genérico tipo Amazon/Netshoes, coerente com a tendência de wellness como estilo de vida, não só consumo de produto.

Analisei 3 sites de referência (navegador):
- **rhodeskin.com** — fotografia editorial em P&B, copy sensorial curta ("Summer on the skin"), filosofia de catálogo enxuto ("one of everything really good"), blocos de missão/filantropia na própria home.
- **phlur.com** — tipografia serifada editorial, macro de ingrediente em vez de still de produto, framing de membership.
- **on.com** — navegação por atividade/intenção (Corrida, Maratona, Trilha) em vez de taxonomia de produto, bloco de manifesto ("Impulsionar o espírito humano pelo movimento").

Direção adotada: tipografia mista (Playfair Display pra momentos de display/emoção + Inter pra UI/corpo), wireframes sempre em cinza puro, sem cor, botões 100% retangulares (sem pill).

## 2. Wireframe v1 — "Home — Direção Lifestyle Premium"

Criado no Figma de trabalho (`RT2gMNXYziFNdS9gEI4IXe`, página "✏️ Wireframe", node `4808:2`), ao lado das 4 iterações antigas em caixa cinza já existentes (sem mexer nelas). 11 seções: Header, Hero, Perfis/Objetivos (7 cards + assistido), Reforço do Quiz, Destaques (grid assimétrico), Categorias, Curadoria por Marca, Manifesto, Prova Social, CTA Final + Newsletter, Footer.

Duas rodadas de correção depois do primeiro rascunho:
- Etiquetas internas de QA ("01 · Header" etc.) colidiam com o texto real — removidas.
- Cores estavam em tom bege/areia — convertidas pra cinza neutro puro (123 preenchimentos ajustados).
- Espaçamento entre seções aumentado (56px de gap).
- Prova Social usava estatística de pesquisa interna (92%, 76%) como se fosse prova social pro consumidor — trocada por 3 princípios sobre o processo da Eiven (curadoria nutricional, zero favorecimento, marcas selecionadas).
- Todos os botões-pílula convertidos pra retangular (7 elementos).

## 3. Avaliação de ideias de curadoria visível

Werner trouxe uma checklist de ~30 ideias de feature (curadoria visível, PLP, PDP, inovação, checkout, onboarding) com uma priorização sugerida pro MVP. Avaliei cada uma contra a viabilidade real em WordPress + WooCommerce + Dokan:

- **Fortes e baratas:** nota do curador na PDP, selo de curadoria, laudos/certificados em accordion, preço por dose, toggle "compatível com meu perfil" (reaproveita o quiz), comunicar o CD único ("3 marcas, 1 frete"), alerta de duplicidade de cafeína no carrinho (versão enxuta).
- **Parecem baratas mas não são:** avaliação por sabor (WooCommerce não separa review por variação nativamente), busca em linguagem natural (resolver com dicionário sintoma→tag, não NLP de verdade), comparador lado a lado (o gargalo é governança de atributo por marca, não a UI).
- Provocação do Werner: "a curadoria só existe no admin, o consumidor não vê em lugar nenhum" — motivou a v2 do wireframe.

## 4. Wireframe v2 — "Home — Curadoria Visível"

Nova versão (node `4835:2`), lado a lado com a v1, incorporando as ideias validadas na avaliação acima:
- Selo "Curadoria Eiven" nos cards de produto + variante "Seu Perfil" (prevendo o toggle de compatibilidade com o quiz).
- Preço por dose em todo card de produto.
- "Por que escolhemos essa marca" nos cards de marca.
- Seção nova "Como Curamos" — processo em 4 passos (ficha técnica → laudos e certificados → avaliação nutricional → aprovação final), sem estatística inventada.
- 4º pilar de confiança: "3 marcas, 1 frete, 1 entrega".

## 5. Levantamento do PDF de benchmark do cliente

Leitura de `Projeto Eiven - Site.pdf`, páginas 6-60 (arquitetura do site, busca, PDP, quiz, checkout, estudo de marca — benchmark levantado pela própria Júlia). Resultado: tabela de 34 linhas (Seção / Componente / Solicitação / Link / Nossa solução), entregue como markdown pronto pra colar no Notion (o conector do Notion não estava autenticado neste ambiente).

Achado mais valioso: a página 45 do PDF mostra a página de resultado de quiz da própria **Z2** (marca parceira) já resolvendo com métricas personalizadas + kit de produtos + guia de uso — referência interna forte pra página "Preparar"/resultado do quiz. Confirmada também a decisão de PDP: accordion lateral direita ("Opção A", ref. hourglasscosmetics.com) incorporando o cross-sell da "Opção B" (ref. essential.com.br).

## 6. Revisão de UX — skill Impeccable (v2)

Rodada dupla de avaliação (design review + auditoria mecânica isolada) sobre o wireframe v2. Nota: **22/28 (79%, "Good")** nas heurísticas de Nielsen aplicáveis.

**P0 — corrigido:** seções Manifesto → Como Curamos → Prova Social repetiam a mesma mensagem de confiança 3x seguidas (as duas últimas reusavam o mesmo grid de 4 colunas). Prova Social foi removida — conteúdo já estava 100% redundante com Como Curamos + a linha de confiança do hero.

**P1 — corrigidos:**
- Bug estrutural de margem no CTA Final (bloco de assinatura terminava 234px antes da borda padrão de 64px usada no resto da página).
- Margem do header (estava 48px, não 64px).

**P1 — ainda pendente (não aplicado, interrompido antes de terminar):**
- Rebaixar visualmente a seção Categorias (hoje compete de igual pra igual com Objetivos, contradizendo o próprio Manifesto — "por objetivo, não por categoria").
- Adicionar descritor curto nos 7 cards de objetivo (hoje só têm o nome).

Relatório completo salvo em `.impeccable/critique/2026-08-06T15-00-56Z__design-rt2gmnxyzifnds9gei4ixe-eiven-mkt-place-work.md`.

## 7. Atualização do doc do projeto

`Eiven - Resumo do Projeto.md` atualizado com: a direção de marca lifestyle, o resumo do levantamento do PDF, a avaliação de features x viabilidade WP/Dokan, e uma seção nova documentando os wireframes v1/v2 e o status da revisão de UX.

## 8. Backup no GitHub

Repositório criado por Werner em [github.com/moistudiogrindideas/eivenmkt](https://github.com/moistudiogrindideas/eivenmkt) (público). Localmente: `git init`, `.gitignore` (excluindo `.claude/settings.local.json`), commit inicial com identidade `Werner <werner@moistudio.com.br>`, remoto conectado via HTTPS e push feito com sucesso (credencial já disponível no Keychain do Mac). Conteúdo no repo: este histórico, o resumo do projeto, os PDFs de referência, o sitemap, o `PRODUCT.md` (gerado pela skill Impeccable) e o relatório de crítica de UX.
