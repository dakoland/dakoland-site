# CLAUDE.md

Guidance for Claude Code when working in this repository.

## Development

No build step. Open `index.html` directly or serve with `npx serve .` / `python3 -m http.server 8080`. Tailwind CSS, Fraunces and Inter load via CDN.

## Architecture

Static site for **Dakoland Foods**, indústria de alimentos (Punhado, The Sauce, Amahoo!). Pages: `index.html` (home), `sobre.html` (Sobre nós), `the-sauce.html` e `amahoo.html` (páginas de marca). Punhado tem site próprio (punhado.com.br) e não ganha página aqui. All assets in `assets/`. See `DESIGN.md` for identity and component patterns.

Base de conhecimento: `~/obsidian/dakoland/dakoland-foods/`. O guia de estilos da marca é a fonte da identidade visual.

## Nav

Logo: `assets/simbolo.svg` (`h-9 w-auto`) + "Dakoland" em Fraunces 22px + "FOODS" em Inter 8px (classe `.foods`), links to `index.html`.

Links: **Conceito | Produtos | Sobre nós** (fora da home, âncoras viram `index.html#...` e o link ativo usa `font-semibold text-[#0F4C3A]` com `aria-current="page"`) (`hidden md:block`, `text-sm text-[#2B2620] hover:opacity-50`). CTA "Fale com a gente" (`bg-[#0F4C3A]` hover `#0A3328`, `rounded-full`) aponta para `#contato`.

## Sections

`index.html`: hero, `#produtos` (carrossel), `#contato`. `sobre.html`: hero, `#conceito` (Um D que brota), No que acreditamos, Nossas marcas, Dados da empresa, `#contato`. Páginas de marca: hero (categoria, marca, subtítulo, foto, CTA "Quero revender" com `mailto:` e assunto `<Marca> - Revenda`), Como usar/Como tomar, Outras marcas Dakoland, `#contato`. Nav, contato e rodapé são iguais em todas as páginas: mudou em uma, replique nas outras. Seções alternam fundo `#FBF6EC` e `#F3EBDA`; contato em `#0F4C3A`.

## Footer

Símbolo + wordmark e ícones de redes à esquerda; endereço, telefone/WhatsApp/e-mail, razão social + CNPJ e `© 2026 Dakoland Foods` à direita. Contato (`#contato`): botão de e-mail + WhatsApp.

## Dados da empresa

- Site conceitual (decisão do dono em 2026-10-20: "vale tudo"). Rodapé e bloco Dados da empresa em `sobre.html` mostram a empresa como ela vai ser: Dakoland Indústria e Comércio de Alimentos Ltda, CNPJ 51.927.202/0001-14, mesmo antes da alteração contratual da CODECRAFT.
- Endereço real desde 2026-10-21 (sede oficial, o mesmo da Codecraft): "Rua João Bettega, 644, Portão, Curitiba / PR, 81070-000", no rodapé das 4 páginas e no bloco Dados da empresa de `sobre.html`. Sem menções a Maringá no site (pedido do dono em 2026-10-21): a empresa é "indústria de alimentos do Paraná".
- Telefone e WhatsApp reais desde 2026-10-21: "(41) 99907-3688", com `tel:+5541999073688` e `https://wa.me/5541999073688`.
- Dados fictícios (criados em 2026-10-20 a pedido do dono, site conceitual): redes Instagram/Facebook/LinkedIn, que apontam para `#`, para não mandar visitantes a perfis de terceiros. Trocar pelos reais quando existirem. Nunca voltar aos telefones fictícios "(44) 3027-2026" e "(44) 99702-2026".
- Nunca usar o CNPJ 22.623.439/0001-03 (fictício), nem `(44) 99000-0000`, `atendimento@punhado.com.br` ou "Rua Exemplo, 100" (valores simulados do canvas do Punhado).
- Contato: `mailto:contato@dakoland.com.br`

## Marcas

| Categoria | Marca | Observação |
|---|---|---|
| Granola | Punhado | Projeto próprio, link para https://punhado.com.br |
| Molho para tacos | The Sauce | |
| Suco de milho | Amahoo! | Exclamação faz parte do nome. Amahoo! é a linha de milho da Dakoland; por enquanto só suco, outras linhas no futuro (não anunciar) |

Home: marcas em carrossel (ver `DESIGN.md`); categoria como label, marca como título. Marca nova entra como mais um `.marca-slide` no `#marcas-trilho`.

## Domínio e SEO

Domínio: https://dakoland.com.br (`CNAME`). Toda página tem `link[canonical]` e `og:url` absolutos (`https://dakoland.com.br/<arquivo>.html`, home em `/`), `og:image` absoluta e entrada no `sitemap.xml`. Página nova: adicionar as três coisas. `robots.txt` aponta para o sitemap.

## Content Rules

- Language: Brazilian Portuguese
- No trailing period on any title or subtitle (h1-h6)
- Never use em dash anywhere - use hyphen (-) or comma
- Não falar sobre Dako (o fundador) nem explicar o nome Dako/Land/Foods no site. O D do símbolo é de Dakoland
- O site é conceitual: pode afirmar o que está na base, inclusive ideias de produto e marketing (decisão de 2026-10-20). Não inventar ingrediente, certificação, ponto de venda ou dado de produção que não esteja lá
- The Sauce: receita base sem pimenta, então não chamar de picante (a versão com pimenta é só ideia)

## Asset Paths

| Arquivo | Uso |
|---|---|
| `assets/simbolo.svg` | Símbolo versão A (cores), fundo claro |
| `assets/simbolo-escuro.svg` | Símbolo versão F, sobre `#0F4C3A` |
| `assets/favicon.ico` / `favicon.svg` / `favicon-{16,32,96}x*.png` | Favicons |
| `assets/apple-touch-icon.png` | 180x180, fundo verde, símbolo F |
| `assets/android-chrome-*.png` / `android-maskable-*.png` / `site.webmanifest` | Android e PWA |
| `assets/mstile-150x150.png` / `browserconfig.xml` / `safari-pinned-tab.svg` | Windows e Safari |
| `assets/og-image.png` | 1200x630, versão F horizontal |
| `assets/produto-punhado.jpg` | Foto do Punhado no carrossel, 1024x768 |
| `assets/the-sauce-destaque.jpg` / `amahoo-destaque.jpg` | Foto vertical (832x1040, 4:5) do hero da página da marca |

Fonte dos ícones e logos: `~/obsidian/dakoland/dakoland-foods/marca/` (ver `README.md` de lá). Ao trocar a marca, copie de lá em vez de gerar de novo.

## Image Rules

- All `<img>` must have `width`, `height`, and `loading="lazy"` - except nav/footer logos and hero (above fold)
- Símbolo decorativo ao lado do wordmark leva `alt=""`
