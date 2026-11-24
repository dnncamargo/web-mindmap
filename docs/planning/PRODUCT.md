# Visão do produto e requisitos

**Status:** planejamento inicial  
**Última atualização:** 2026-11-23

## 1. Visão

O Web Mindmap é uma ferramenta de organização visual do conhecimento baseada em um canvas livre. O usuário cria mapas compostos por cartões de conteúdo posicionados espacialmente e conectados por relações explícitas.

O produto não se limita a uma árvore hierárquica ou a um mapa radial tradicional. Um elemento poderá se relacionar com vários outros elementos, inclusive em diferentes regiões do mapa.

## 2. Objetivos do produto

1. Oferecer um canvas visual amplo para organizar ideias e informações.
2. Permitir a composição de um mapa com diferentes tipos de conteúdo.
3. Permitir relações visuais independentes da hierarquia espacial.
4. Separar autoria, condução da apresentação e projeção.
5. Preservar o conteúdo e a organização do mapa entre sessões.
6. Permitir explorar um mapa em telas grandes e em dispositivos touchscreen.

## 3. Fora do escopo inicial

- Janela de webcam ou vídeo do apresentador sobreposta ao canvas. A janela observada na imagem de referência pertence a outro software e não faz parte do produto.
- Colaboração simultânea, até que seja definida como requisito.
- Recursos de inteligência artificial, até que sejam discutidos e priorizados.
- Compatibilidade prioritária com Chrome 81. O Player Legacy é uma consideração posterior e de baixa prioridade.

Esses itens poderão ser reconsiderados, mas não devem condicionar o desenho inicial do núcleo do produto.

## 4. Conceito de mapa

Um mapa é composto por:

- **Canvas:** espaço de trabalho e sistema de coordenadas.
- **Nodes:** elementos de conteúdo posicionados no canvas.
- **Edges:** relações entre elementos.
- **Assets:** arquivos e mídias associados aos elementos.
- **Configurações do mapa:** preferências visuais e parâmetros próprios do documento.

A representação definitiva e os campos do modelo ainda serão especificados no domínio de dados. Esta descrição é conceitual, não um contrato de código.

## 5. Tipos de conteúdo inicialmente considerados

Os seguintes tipos foram levantados como candidatos:

| Tipo | Conteúdo esperado | Situação |
|---|---|---|
| Texto | Título, texto descritivo, listas e formatação | Proposto |
| Imagem | Imagem, legenda e dimensões ajustáveis | Proposto |
| Link | URL, título, descrição e possível prévia | Proposto |
| Documento | Arquivo e possibilidade de visualização/abertura | Proposto |
| Vídeo | Referência ou incorporação de vídeo | Proposto |
| Código | Bloco de código com identificação de linguagem | Proposto |

A lista não está fechada. Formatos, limites, regras de incorporação, upload e apresentação serão definidos no planejamento dos elementos.

## 6. Princípios de experiência

- **Liberdade espacial:** os elementos não precisam obedecer a uma árvore ou a uma disposição radial.
- **Conteúdo heterogêneo:** um mapa poderá misturar tipos de conteúdo.
- **Relações explícitas:** conexões são elementos próprios do mapa.
- **Navegação visual:** o usuário explora o espaço por movimentação e zoom.
- **Responsabilidades distintas:** editar o mapa não é a mesma coisa que conduzir ou projetar uma apresentação.
- **Identidade visual sóbria:** a interface deve priorizar o conteúdo, evitar excesso de decoração e manter controles compactos.

## 7. Domínios funcionais a especificar

| Domínio | Escopo |
|---|---|
| Canvas | Coordenadas, extensão, grade, navegação, zoom, seleção e gestos |
| Nodes | Tipos de conteúdo, edição, dimensões, posicionamento e comportamento |
| Edges | Pontos de conexão, geometria, direção, rótulos e aparência |
| Editor | Ferramentas, seleção múltipla, menus, atalhos e histórico |
| Control | Sessões, comandos, sincronização e feedback de estado |
| Player | Renderização, navegação, foco e interação de projeção |
| Dados | Documento canônico, persistência, arquivos, importação e exportação |
| Experiência | Responsividade, acessibilidade, desempenho e identidade visual |

## 8. Referência visual

A imagem de referência apresenta um canvas escuro com grade pontilhada, cartões de tamanhos variados, diferentes conteúdos e linhas curvas coloridas. Os elementos têm posições livres e conexões visuais. A janela de vídeo presente na captura é externa ao produto e está excluída do escopo.

A referência serve como inspiração para a experiência, não como especificação visual fechada.
