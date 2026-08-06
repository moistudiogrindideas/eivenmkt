# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Stack

WordPress + WooCommerce + Dokan Professional (multi-vendor backend), CRM HubSpot. Front-end design system built via wireframes/telas-mestras before rollout.

## Users

Primary user: o consumidor final — atleta ou praticante de alta performance escolhendo suplementos. Ele não tem dificuldade de acesso ao produto (já encontra em qualquer lugar — Amazon, Mercado Livre, site da marca); sua dificuldade é decidir qual produto faz sentido pra ele.

Fase 1 do projeto cobre exclusivamente a jornada do consumidor (desktop/mobile). Não há usuário-marca/seller nesta fase (ver Capabilities and Constraints).

## Product Purpose

Marketplace multi-marcas de suplementos wellness que não vende por categoria de produto — vende curadoria por objetivo/perfil do usuário. O produto existe para resolver a dúvida de decisão do consumidor, não o acesso ao produto. Sucesso = o usuário confia na recomendação e compra através da curadoria (quiz/objetivo), não navegando por prateleira.

## Positioning

"A Eiven não vende produtos. A Eiven entrega certeza." A concorrência real não é Amazon/Mercado Livre — é a dúvida do consumidor. Mercado atual compete por preço/marca/sabor/desconto; a Eiven compete por confiança, descoberta, conveniência e inteligência de curadoria.

Ordem de prioridade de valor percebido pelo consumidor (pesquisa com usuários): confiança > preço > cashback/cupom/variedade > personalização — personalização é sentida como obrigação mínima, não diferencial.

## Operating Context

- **Home:** ação prioritária é levar o usuário a responder o quiz de objetivos (reforçado em múltiplos pontos, não um CTA único), com sinais de confiança no topo, navegação alternativa por objetivo pra quem não quiser fazer o quiz, vitrines curadas e captura de lead.
- **Quiz/Onboarding:** versão rápida (~60s) mostra resultado e oferece aprofundamento opcional (5-10min). 92% topam iniciar, só 46-49% topam a versão longa. Ponto de risco de QA validado por benchmark: falha ao exibir recomendação no final do quiz.
- **Busca/Navegação:** três eixos — por objetivo, por tipo de produto, por marca.
- **Páginas por objetivo (resultado do quiz):** cada objetivo (7 perfis, nomenclatura tbd) tem página própria — não é filtro nem card. É onde a curadoria se materializa: contexto, produtos recomendados e conteúdo mudam por objetivo. Referência mais detalhada: "Preparar" funciona como dashboard de programa (fases antes/durante/depois, timeline).
- **PDP:** painel lateral (Detalhes, Como usar, Ingredientes, Alérgicos, Avaliações, FAQ, Frete, Trocas), reaproveitado também na página pós-quiz.
- **Carrinho/Checkout:** cross-sell acima do resumo do pedido; banner de oferta ao abrir a sacola; pesquisa pós-checkout perguntando onde a pessoa conheceu a marca.
- **Fulfillment (fase 1):** a própria Eiven recebe os pedidos, monta e faz a entrega — não são as marcas que acessam ou cadastram produtos nesta fase. Rastreio fica com a Eiven.

## Capabilities and Constraints

- **Fase 1 = fulfillment 100% centralizado na Eiven.** A Eiven é o próprio "seller" — recebe pedidos, monta e entrega. As marcas (DUX, Z2, Vitafor, etc.) não acessam a plataforma nem cadastram produtos nesta fase. Isso significa: **nenhum painel/conta de marca é necessário na fase 1** — sem telas de despacho, etiqueta ou cadastro por marca.
- Split de pagamento entre marcas ainda existe, mas é só financeiro (comissão/repasse) — não gera nenhuma tela ou fluxo operacional visível ao consumidor ou à Eiven-como-seller.
- Fonte de verdade do estoque (WMS vs. WooCommerce) ainda indefinida — em Discovery.
- Nomenclatura final dos 7 objetivos do quiz (Evoluir, Preparar, Regenerar, Viver Melhor, Construir, Transformar, Recompor) ainda tbd.
- Direção visual (paleta preto/verde-oliva/dourado, tom editorial/lifestyle) ainda tbd em Discovery — decisão de DESIGN.md, não deste documento.
- Qualquer fluxo assistido por IA/WhatsApp deve fechar a compra no mesmo canal — sem desviar o usuário (aprendizado do case Jungle/Positive Co., onde o desvio pro WhatsApp foi percebido como "dinheiro jogado fora").
- Evitar posicionar a Eiven como "uma IA que recomenda suplementos" — nutricionista é o maior influenciador de consumo (76%), então a reputação deve soar mais próxima de ciência/técnica do que de lifestyle/creator.
- Nenhum requisito de acessibilidade definido pelo cliente até o momento.

## Brand Commitments

Nome do produto: Eiven. Marcas participantes citadas na pesquisa: DUX, Z2, Vitafor (fornecedoras de produto, sem interface própria na fase 1). Tom aspiracional/editorial, inspirado em referências como thefeed.com, thrivemarket.com, hourglasscosmetics.com, moss.nyc, lifetime.life, equinox-hotels.com.

## Evidence on Hand

- Pesquisa com usuários: 10 insights + síntese (PDF "Projeto Eiven - Site.pdf", pág. 80-94), incluindo taxas de conclusão do quiz, ranking de fatores de decisão de compra (confiança 73% > preço 70% > entrega 41% > cupom 19% > frete 8%), e share de marcas concorrentes pesquisadas (Liquidz 59%, Z2 49%, Dux 41%, Dobro 38%, Caffeine Army 32%, Essential 24%, Jungle 24%, Pura Vida 14%, Maurten 8%).
- Case negativo de benchmark: agente de IA que desvia pro WhatsApp (Jungle/Positive Co.) — usar como anti-referência.
- Arquivos na pasta do projeto: `Eiven - Resumo do Projeto.md`, `Projeto Eiven - Site.pdf` (109 pág., faltam ler pág. 71-79 e 95-109), `Sitemap - Eiven MKT place.png`, `WON - Fluxo do marketplace.pdf`.
- Figma "Eiven MKT Place" (sitemap, cards brancos borda preta, chips pretos de ator) e FigJam com decisões pendentes — links em `Eiven - Resumo do Projeto.md`.

## Product Principles

1. Curadoria por objetivo/perfil é o mecanismo central do produto — todo fluxo deve conduzir ou reforçar o quiz, não a navegação por categoria.
2. Confiança e descoberta superam preço e personalização como motor de decisão — priorizar sinais de credibilidade sobre promoções.
3. Fase 1 é fulfillment 100% centralizado na Eiven — sem contas, cadastro ou telas de despacho para marcas; escopo de design fica restrito à jornada do consumidor.
4. Personalização é expectativa mínima, não diferencial — não gastar espaço de UI vendendo "personalização" como recurso.
5. Qualquer interação assistida por IA/WhatsApp deve fechar a compra no mesmo canal — nenhum desvio que quebre o funil.
