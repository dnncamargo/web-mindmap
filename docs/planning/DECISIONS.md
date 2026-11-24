# Decisões e questões em aberto

**Status:** registro vivo do planejamento  
**Última atualização:** 2026-11-23

Este arquivo distingue decisões já estabelecidas de hipóteses e questões que ainda precisam de discussão.

## 1. Decisões estabelecidas

| ID | Decisão | Situação |
|---|---|---|
| D-001 | O produto será uma ferramenta de mapas mentais em canvas visual livre. | Aprovada |
| D-002 | O produto terá três superfícies: Editor, Control e Player/Projeção. | Aprovada |
| D-003 | A captura de referência serve como inspiração visual; a janela de vídeo sobreposta pertence a outro software e está fora do produto. | Aprovada |
| D-004 | O canvas deverá comportar cartões de diferentes conteúdos e conexões visuais. | Diretriz aprovada; tipos detalhados em aberto |
| D-005 | As três superfícies compartilharão o documento canônico, com responsabilidades separadas. | Diretriz aprovada |
| D-006 | Firefox 116+ é a referência mínima do Player moderno. | Aprovada |
| D-007 | Chrome 156 64 bits em Chromebook é o ambiente crítico para Editor e Control. | Aprovada |
| D-008 | Editor e Control não serão limitados para atender Chrome 81. | Aprovada |
| D-009 | Chrome 81 em Android 11 poderá receber Player Legacy, com prioridade mais baixa. | Aprovada |
| D-010 | O roteiro de desenvolvimento será preparado depois da consolidação do planejamento. | Aprovada |

## 2. Hipóteses técnicas ainda não aprovadas

| Tema | Hipótese | Próximo passo |
|---|---|---|
| Canvas | Avaliar React Flow / @xyflow ou alternativa | Comparar requisitos, limitações e toque |
| Persistência | Avaliar Firebase/Firestore | Definir modelo e regras |
| Arquivos | Avaliar Vercel Blob | Definir ciclo de vida dos assets |
| Estado ao vivo | Avaliar Firebase Realtime Database | Definir contrato Control–Player |
| Estrutura | Avaliar monorepo com apps e packages | Decidir após delimitar compartilhamento |
| Legacy | Build separado reaproveitando o código comum | Avaliar somente após Player moderno |

## 3. Questões funcionais em aberto

### Canvas

- O espaço é matematicamente ilimitado ou possui limites virtuais muito amplos?
- Qual é o comportamento de arraste no espaço vazio?
- Como alternar entre movimentar o canvas e arrastar um elemento?
- Haverá ferramenta explícita de mão/pan?
- Como funcionará seleção por área?
- A grade pontilhada será fixa, configurável ou opcional?
- Haverá encaixe em grade, guias e alinhamento?
- Como o zoom será ancorado: centro da tela, cursor ou gesto?
- Quais gestos estarão disponíveis em mouse, touchpad e touchscreen?

### Nodes

- Quais tipos entram na primeira versão?
- Quais recursos de formatação de texto existirão?
- Como links externos serão representados?
- Quais formatos de imagem e documento serão aceitos?
- Vídeo será incorporado ou representado como link?
- Como funcionará o redimensionamento e o conteúdo excedente?
- Haverá agrupamento ou containers?

### Edges

- Quais geometrias serão permitidas?
- Os elementos terão pontos de conexão fixos ou livres?
- Haverá direção, rótulo, cor, espessura e estilos diferentes?
- Uma conexão poderá ligar portas específicas ou somente elementos?
- Como selecionar e editar uma conexão?

### Editor

- Como será a barra de ferramentas?
- Quais operações terão atalhos?
- Como funcionará Undo/Redo?
- Haverá biblioteca de mapas, pastas, duplicação e modelos?
- O salvamento será automático? Qual será o feedback?
- Haverá importação e exportação?

### Control e Player

- A projeção acompanha o estado ao vivo ou utiliza publicação imutável?
- Será possível controlar o Player por outro dispositivo?
- Como o Player será associado a uma sessão?
- Quais comandos existirão?
- O Player permitirá exploração independente pelo apresentador ou público?
- Como Control mostrará confirmação e falhas de aplicação dos comandos?
- Haverá foco em elemento, caminhos ou sequências guiadas?

### Acesso e compartilhamento

- Mapas serão privados, públicos ou ambos?
- Haverá publicação de snapshots?
- Haverá colaboração simultânea?
- Qual será o fluxo de autenticação e autorização?

## 4. Decisões não devem ser inferidas

Quando uma questão estiver em aberto, não assumir a alternativa mais comum nem transformar uma sugestão em requisito aprovado sem confirmação explícita.

Uma decisão pode ser revisada durante o planejamento. Ao ser alterada, registrar a justificativa e atualizar os documentos afetados.

## 5. Histórico

- 2026-11-23 — Início da documentação de planejamento e registro das decisões iniciais de produto, superfícies e compatibilidade.
