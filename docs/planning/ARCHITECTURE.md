# Princípios de dados e arquitetura

**Status:** direção arquitetural inicial  
**Última atualização:** 2026-11-23

Este documento registra princípios e hipóteses de arquitetura. Não representa ainda uma especificação técnica fechada nem autoriza a escolha definitiva de bibliotecas.

## 1. Documento canônico

O mapa deverá possuir uma representação semântica independente do estado visual transitório da interface.

Conceitualmente, o documento contém:

- Identidade e metadados do mapa.
- Nodes e seus dados específicos.
- Posições e dimensões dos nodes.
- Edges e suas propriedades.
- Referências a assets.
- Configurações persistentes do mapa.

O documento não deverá armazenar estado temporário de seleção, hover, arraste em andamento, foco de apresentação ou posição transitória da câmera, salvo decisão específica que os torne parte do conteúdo persistente.

## 2. Separação de estados

Três categorias devem ser consideradas:

### 2.1 Conteúdo persistente

Informações que compõem o mapa e devem sobreviver ao fechamento do Editor: conteúdo dos cartões, relações, posições, dimensões e configurações autorais.

### 2.2 Estado local da interface

Informações transitórias de cada cliente: seleção, painel aberto, ferramenta ativa, arraste em andamento, menus e preferências temporárias.

### 2.3 Estado da sessão de apresentação

Informações necessárias para conduzir e sincronizar o Player: foco atual, câmera, zoom, modo de visualização e outros comandos que forem aprovados.

A fronteira exata entre preferências persistentes e temporárias será definida no planejamento de dados e de apresentação.

## 3. Renderização

Direção proposta:

- Um contrato de documento compartilhado.
- Um núcleo de renderização reutilizado pelo Editor e pelo Player.
- Interações de autoria pertencentes ao Editor.
- Interações de navegação e apresentação pertencentes ao Player.
- Estado da sessão transmitido separadamente do documento.

A tecnologia de canvas e as bibliotecas ainda não foram escolhidas.

## 4. Integridade do documento

O planejamento técnico deverá considerar:

- Validação explícita do documento em fronteiras de persistência e leitura.
- Identificadores estáveis para elementos e conexões.
- Referências tipadas entre conexões e elementos.
- Operações de edição consistentes.
- Undo/Redo baseado em operações ou snapshots bem definidos.
- Recuperação após falhas de salvamento.
- Importação e exportação sem depender do estado interno do editor.

Os mecanismos específicos permanecem em aberto.

## 5. Persistência e arquivos

Firebase/Firestore e Vercel Blob são tecnologias familiares nos projetos de referência do usuário, mas sua adoção no Web Mindmap ainda é uma proposta, não uma decisão aprovada.

O planejamento deverá decidir:

- Autenticação e propriedade dos mapas.
- Estrutura de coleções/documentos.
- Estratégia de salvamento e concorrência.
- Upload, exclusão e referência de arquivos.
- Importação e exportação.
- Publicação e acesso do Player.
- Regras de segurança e isolamento dos dados.

## 6. Comunicação Control–Player

Control e Player devem trocar comandos e estado de sessão sem converter essas informações em alterações do documento.

O contrato deverá definir:

- Identidade da sessão e do Player.
- Autorização para controlar uma sessão.
- Comandos permitidos e sua validação.
- Estado solicitado versus estado efetivamente aplicado.
- Reconexão, desconexão e expiração.
- Comportamento quando Control ou Player ficam indisponíveis.

Firebase Realtime Database é uma possibilidade coerente com experiências anteriores, mas ainda precisa ser avaliada e aprovada para este produto.

## 7. Arquitetura de referência

O web-slideshow é a referência principal para separação de superfícies, documento canônico, renderer compartilhado, histórico e estado ao vivo. O web-wordcloud é uma referência complementar para organização de superfícies e visualização atualizada.

O Web Mindmap deve preservar os princípios úteis sem reproduzir mecanismos que só fazem sentido em apresentações de slides ou nuvens de palavras.

## 8. Bibliotecas e decisões técnicas pendentes

A escolha do motor de canvas (por exemplo, React Flow ou outra solução), estratégia de renderização, gerenciamento de estado, transporte em tempo real, bibliotecas de gestos e organização do monorepo ocorrerá após o detalhamento dos requisitos funcionais e a realização de provas técnicas direcionadas.
