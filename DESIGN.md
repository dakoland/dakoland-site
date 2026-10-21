# Design Reference - Dakoland Foods

Identidade visual derivada do guia de estilos da marca (versão 1.0, outubro de 2026), em `~/workspace/dakoland/dakoland-stylebook`.

## Símbolo

A letra D, de Dakoland, com um broto de duas folhas nascendo de dentro. Folha manga = sabor e sol da ilha; folha verde = origem natural.

| Versão | D | Folha grande | Folha pequena | Fundo |
|---|---|---|---|---|
| A (original) | `#0F4C3A` | `#F2A541` | `#8CC084` | claro |
| B (mono) | `#0F4C3A` | `#FBF6EC` | `#FBF6EC` | claro |
| F (fundo escuro) | `#F2A541` | `#0F4C3A` | `#FBF6EC` | `#0F4C3A` |

ViewBox justo do símbolo: `44 28 124 144`. Não distorcer, girar, trocar cores, aplicar sombra ou contorno, nem mudar o símbolo de lado. Versão A não vai sobre fundo manga.

Área de proteção: 1/4 da altura do símbolo. Tamanho mínimo: horizontal 160 px, vertical 64 px de símbolo, símbolo isolado 16 px.

## Paleta

| Token | Hex | Uso |
|---|---|---|
| floresta | `#0F4C3A` | Primária: títulos, botões, seção de contato |
| floresta-hover | `#0A3328` | Hover de botão |
| manga | `#F2A541` | Destaque: botão sobre fundo escuro, ilustrações |
| broto | `#8CC084` | Apoio, só em símbolo e ilustração |
| creme | `#FBF6EC` | Fundo da página |
| areia | `#F3EBDA` | Seções alternadas, cards |
| terra | `#9A5518` | Labels de seção, "FOODS" |
| texto | `#2B2620` | Texto corrido |
| texto-2 | `#5A5148` | Texto secundário |
| borda | `#E8DCC4` | Divisores de nav e rodapé |

Proporção de referência: floresta 45%, creme 35%, manga 12%, broto 5%, terra 3%.

## Tipografia

| Nível | Fonte | Tamanho | Uso |
|---|---|---|---|
| Display | Fraunces 700 | 48-76px | H1 |
| H2 | Fraunces 700 | 36-56px | Títulos de seção |
| H3 | Fraunces 700 | 28-34px | Cards |
| Body | Inter 400 | 15-19px | Parágrafos |
| Label | Inter 600 | 12px, `tracking-[0.3em]`, uppercase, `#9A5518` | Labels de seção |
| FOODS | Inter 600 | `letter-spacing: 0.52em`, `#9A5518` | Wordmark (classe `.foods`) |

## Layout

Container `max-width: 1120px`, padding 32px (16px no mobile). Seções com 104-112px de respiro vertical. Two-col `7fr 5fr` / `5fr 7fr`, three-col `repeat(3,1fr)`, colapsam em uma coluna abaixo de 768px.

## Componentes

- Botão primário: `bg-[#0F4C3A] text-[#FBF6EC] rounded-full px-7 py-3.5 font-semibold`, hover `#0A3328`
- Botão secundário: `border border-[#0F4C3A]/30 text-[#0F4C3A] rounded-full`, hover `bg-[#F3EBDA]`
- Botão sobre floresta: `bg-[#F2A541] text-[#0F4C3A] rounded-full`
- Painel de marca: `rounded-[28px]`, fundo floresta (símbolo F) ou creme (símbolo A)
- Hero da home: sem painel nem símbolo grande. Arte de fundo com as duas folhas do símbolo em tamanho grande (SVG inline `.hero-arte`, escala 8x), brotando de um ponto na borda de baixo do hero, à direita, com um círculo areia e nervuras creme a 60%. A seção Produtos logo abaixo tem fundo areia, e essa troca de cor é o "chão" de onde as folhas brotam. No desktop fica absoluta à direita (largura até 620px, encolhe para não invadir o texto); no celular a arte fica atrás do texto, translúcida (opacidade 0,2), 92% da largura, ancorada embaixo à direita
- Carrossel de marcas (home, `#produtos`): faixa de ponta a ponta, painéis colados com corte a 15° (`clip-path`, `--marca-off = altura × tan 15°`), altura 520px (420px no mobile), passo 460px (até 78vw). Foto original do produto, sem filtro, com escurecimento embaixo; categoria em manga, marca em Fraunces creme, link. Flui sozinho em movimento contínuo a 40px/s (pausa com mouse em cima, foco, durante o arraste ou com movimento reduzido), arraste livre e loop infinito (clones antes e depois). Sem setas. Sem pontos de posição. A faixa encosta na seção de contato (sem espaço embaixo).
- Blocos de tela cheia (as 4 páginas, celular e desktop): cada `main > section` tem no mínimo a altura visível menos a nav (`100svh - 65px`), com o conteúdo centralizado na vertical; o contato desconta também a altura do rodapé (`--rodape-h`, medida por script), para contato + rodapé fecharem a última tela. No celular o conteúdo é compactado para não passar da tela de 390x664: seções com 40px em cima e embaixo, títulos h2 30px, textos 15px, itens e listas com menos respiro
- Hero das páginas de marca no celular: textos menores, botões lado a lado e a foto ocupa o espaço que sobra (mínimo 160px, recorte `object-cover`)
- Carrossel: a faixa cresce para preencher a altura que sobra na seção (mínimo 520px no desktop, 360px no celular), e o corte a 15° é recalculado pela altura real
- Contato + rodapé no celular: compactos (seção com 32px em cima e embaixo, símbolo 48px, título 32px, texto 15px, botões mais baixos; no rodapé, símbolo + wordmark e ícones de redes na mesma linha)

## Tom visual

Caloroso e direto. Formas cheias e arredondadas, como o símbolo. Sem gradiente, sem sombra. Fotos só no carrossel e nas páginas de marca, sempre as originais fornecidas pela marca, sem filtro de cor (o dono achou sem vida).
