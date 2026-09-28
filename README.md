# Vitta Vision — Landing Page

Landing page de lançamento da **Vitta Vision**, armação de óculos de grau da marca (fictícia) **Vitta Eyewear**. Construída em HTML5, CSS3 e JavaScript puro, sem frameworks nem etapa de build.

## Como rodar localmente

Não há build. Basta servir a pasta como arquivos estáticos:

```bash
python -m http.server 8765
# depois abra http://localhost:8765
```

(Abrir `index.html` diretamente no navegador também funciona — a página não depende de `fetch`/módulos que exigiriam um servidor.)

## Estrutura do projeto

```
index.html            Marcação das 10 seções da página
style.css              Todo o CSS (variáveis, componentes, seções, responsivo)
script.js               Menu mobile, header, accordion do FAQ, troca de cor/vista do produto,
                        rótulo ativo na seção "Detalhes", animações de entrada ao rolar

assets/images/
  banner.png             Imagem original enviada para o hero e o CTA final
  banner.jpg              Cópia otimizada (~115 KB) usada de fato no <img> — mesma imagem,
                          recomprimida para performance

docs/                   Briefing e planejamento originais do projeto (fonte de conteúdo,
                        público, estrutura e estratégia de conversão)
  projeto.md
  conteudo + planejamento.md
  conteúdo final.md
  prompt.md

reference/              Versões alternativas geradas por outras IAs durante o processo,
                        mantidas apenas como referência de comparação — não fazem parte
                        do site publicado
  gemini.html
  gpt.html
```

## Conteúdo pendente de validação

Para a página não ficar com espaços em branco durante a revisão visual, alguns textos foram
preenchidos com conteúdo **ilustrativo/plausível**, não confirmado pela marca. Revisar antes de publicar:

- **Seção "Detalhes da armação"** — material, construção, acabamento, peso, medidas e garantia
- **Seção "Prova e confiança"** — avaliação de clientes e garantia (o número de clientes atendidos,
  "+5.000", *é* real — vem de `docs/projeto.md`)
- **FAQ** — todas as respostas, exceto a última (sobre grau alto), que já vinha pronta do
  planejamento original

## Imagens

Todas as fotos do site (exceto o hero e o CTA final, que usam `banner.jpg`) são fotos reais do
Unsplash, usadas como placeholder até haver material fotográfico próprio do produto. Basta trocar
o `src` de cada `<img>` por arquivos reais quando disponíveis — a marcação já está pronta para isso
(mesmas proporções, `alt` descritivo, `loading="lazy"` nas imagens fora da primeira dobra).

## Identidade visual

| Cor | Uso |
|---|---|
| `#97705a` (mocha) | Títulos grandes |
| `#7a5b48` (mocha escuro) | Títulos menores, logo, itens do FAQ — melhor contraste em textos pequenos |
| `#5c3d28` / `#432c1c` (marrom) | Botões primários, blocos de destaque (`--color-accent` / `--color-accent-dark`) |
| `#f3ece3` / `#faf7f2` (creme) | Fundos alternados |
| `#2b2622` (ink) | Texto de corpo, footer |

Tipografia: **Fraunces** (serifada, títulos) + **Inter** (corpo, botões, textos pequenos), via Google Fonts.

## Acessibilidade e performance

- HTML semântico (`header`, `nav`, `main`, `section`, `figure`, `footer`), hierarquia de headings respeitada
- Skip link, foco visível, áreas de toque grandes, `prefers-reduced-motion` respeitado em todas as animações
- Imagens abaixo da primeira dobra usam `loading="lazy"`; hero usa `fetchpriority="high"`
- Sem dependências externas além das fontes do Google Fonts
