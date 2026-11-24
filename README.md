# Web Mindmap

Ferramenta web para criação, organização e apresentação de mapas mentais em um canvas visual livre.

O produto está em fase de **planejamento**. Este repositório começa pela documentação de produto e arquitetura; o roteiro de implementação será elaborado depois que os domínios funcionais e as decisões fundamentais forem discutidos e aprovados.

## Objetivo

Permitir que uma pessoa construa mapas de conhecimento em uma área de trabalho visual, combinando diferentes tipos de conteúdo e conectando-os por relações explícitas. O mapa deve poder ser editado, controlado durante uma apresentação e exibido em uma tela de projeção.

## Superfícies do produto

- **Editor** — criação e edição dos mapas.
- **Control** — controle de uma sessão de apresentação.
- **Player** — projeção e exploração do mapa.

As três superfícies compartilham o mesmo documento canônico, mas têm responsabilidades e estados distintos.

## Documentação

- [Visão do produto e requisitos](docs/planning/PRODUCT.md)
- [Superfícies: Editor, Control e Player](docs/planning/SURFACES.md)
- [Compatibilidade e plataformas](docs/planning/COMPATIBILITY.md)
- [Princípios de dados e arquitetura](docs/planning/ARCHITECTURE.md)
- [Decisões e questões em aberto](docs/planning/DECISIONS.md)

## Estado atual

Estamos consolidando o planejamento. As decisões registradas nos documentos representam o que já foi definido nas conversas; itens explicitamente marcados como **em aberto** ainda precisam ser discutidos.

Não iniciar a implementação com base em hipóteses sobre os itens em aberto. O roteiro de desenvolvimento será produzido após a aprovação da especificação funcional e técnica.

## Referências de arquitetura

- [web-slideshow](https://github.com/dnncamargo/web-slideshow) — referência principal para separação Editor / Control / Player, documento canônico, renderização compartilhada, histórico e estado de apresentação.
- [web-wordcloud](https://github.com/dnncamargo/web-wordcloud) — referência complementar para superfícies públicas e administrativas, visualização e atualização em tempo real.

Esses repositórios são referências de padrões e decisões, não modelos a serem copiados integralmente. O Web Mindmap deverá adotar somente a complexidade necessária ao seu próprio domínio.
