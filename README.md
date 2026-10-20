# Reset 5 Dias — Página de produto do Distribuidor Independente Herbalife

Repositório: `edusidegum/reset` (GitHub Pages)
Publicação: https://edusidegum.github.io/reset/
Responsável: Edu Sidegum — Distribuidor Independente Herbalife — Novo Hamburgo/RS/Brasil
Última revisão deste README: 20/10/2026

## Estrutura do repositório

    reset/
    ├── index.html      # Landing do Reset (réplica do formato hypedrink)
    ├── reset.html      # "Como Fazer o Reset de 5 Dias" (indexável, com FAQPage)
    ├── robots.txt      # Allow all (sem bloqueios — reset.html é indexável)
    ├── sitemap.xml     # index + reset.html
    ├── README.md       # este arquivo
    └── img/            # imagens LOCAIS do projeto
        ├── Resset1.png # PENDENTE de upload (nome exato, case-sensitive)
        └── reset2.png  # PENDENTE de upload (nome exato, case-sensitive)

## Pendências (bloqueiam visual e preview social)

| Item | Onde é usado | Efeito se ausente |
|---|---|---|
| `img/Resset1.png` | Preload LCP, hero do index, og:image e twitter:image (index e reset.html) | LCP sem imagem, preview social sem imagem, hero quebrado |
| `img/reset2.png` | Botão-imagem do index (link → reset.html) | Botão invisível; rota de conversão via imagem inativa |

Requisitos de upload:

- Nome EXATO (case-sensitive): `Resset1.png` e `reset2.png`.
- Pasta correta: `img/` na raiz do repositório (mesma convenção do hypedrink).
- Informar as dimensões reais dos arquivos; os atributos atuais (800×600 e 400×400) devem ser conferidos para evitar CLS.

### Se suas imagens estão em `assets/img/` (layout local divergente)

Ou mova para `img/` na raiz (recomendado — zero alteração de código), ou ajuste os caminhos `src`/`href`:

- `index.html`: preload (href), `<img>` do hero, `<img>` do botão, og:image, twitter:image → `assets/img/Resset1.png` / `assets/img/reset2.png`
- `reset.html`: og:image, twitter:image → `assets/img/Resset1.png`

## Dependências externas (assets compartilhados — decisão: sem duplicação)

| Recurso | Origem | Risco |
|---|---|---|
| CSS do tema | https://edusidegum.github.io/hypedrink/assets/css/style.css | Se o hypedrink sair do ar, o layout das duas páginas quebra |
| Logo no header | https://edusidegum.github.io/hypedrink/img/Herbalife-Logo.webp | idem |
| Menu injetado | https://edusidegum.github.io/menu/scripts/bloco-incluir.js | idem |
| Imagens do corpo (jornada, ciência, atletas, 14 selos) | hypedrink/img/... | idem |

## Rotas e links-chave

- **Contato (assunto fixo):** https://wa.me/5551999663200?text=Resset%2C%20como%20fazer%20%3F — decodifica `Resset, como fazer ?`. Usado no header, no CTA do reset.html e nos CTAs intermediários do index.
- **Duas imagens do index → reset.html** (página "Como Fazer").
- Catálogo oficial (externo): https://catalogoherbalife.com.br/edusidegum
- Cadastro (externo): https://edusidegum.github.io/cadastro/cadastro.html

## Checklist de publicação

1. [ ] Enviar as duas imagens com nomes exatos em `img/`.
2. [ ] Push e aguardar build do GitHub Pages.
3. [ ] Teste no celular: index → clique nas 2 imagens → reset.html → WhatsApp com assunto preenchido.
4. [ ] Rich Results Test nas 2 URLs (JSON-LD: Organization, WebSite, WebPage, BreadcrumbList, FAQPage) — alvo: 0 erros.
5. [ ] Search Console: enviar sitemap e solicitar indexação das 2 URLs.
6. [ ] PageSpeed mobile ≥ 90; conferir o preload da Resset1.png (LCP).
7. [ ] Conferir dimensões reais das PNGs e ajustar width/height se necessário.
8. [ ] Conferir o slug do repositório: se criado com outro nome (ex.: `resset`), atualizar canonical, og:url, sitemap e links internos.

## Conformidade Herbalife (fonte: Manual de Normas REV 17-12-2025)

- Sem preços/descontos públicos na página (norma 3.5): valores só por atendimento pessoal ou página protegida por senha. A "Tabela 2026" citada nas diretrizes NÃO foi verificada e NÃO está publicada.
- Sem declarações terapêuticas/médicas (norma 3.1): doses alinhadas ao Guia de Produtos 2025; advertências de rótulo mantidas (cafeína; não indicado para gestantes, lactantes e crianças).
- Sem fracionamento/revenda de sachês avulsos (norma 2.6): execução via produtos fechados e rotulados ou preparações servidas no Espaço Vida Saudável (norma 6.4).
- Identificação "Distribuidor Independente Herbalife" visível em header e rodapé (norma 3.2).

## Origem dos dados (rastreabilidade)

- Estrutura e head: replicados literalmente do `index.html` de edusidegum/hypedrink (raw GitHub).
- Descrição do programa: "Reset 5 Dias" / "RESET+", lançamento oficial Herbalife Brasil (fontes oficiais verificadas em 20/10/2026).
- Protocolo, doses e produtos: GuiaDeProdutos2025.txt (anexo) + diretrizes fornecidas pelo distribuidor. Doses de N-R-G e Fiber Concentrate: pendentes de conferência no rótulo.
- Normas de conduta: Manual-de-Normas-2025.pdf (REV 17-12-2025).
- Nada inventado: preços, depoimentos, avaliações e promessas de resultado não foram incluídos por ausência de fonte autorizada.

## Manutenção

- Alteração de conteúdo → atualizar `dateModified` (reset.html) e `lastmod` (sitemap.xml).
- Troca de imagens → preservar nomes case-sensitive e revalidar PageSpeed.
- Alteração do assunto do WhatsApp → trocar em TODOS os links (header e CTAs) de uma vez.
