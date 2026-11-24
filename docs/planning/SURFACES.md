# Superfícies do produto

**Status:** planejamento inicial  
**Última atualização:** 2026-11-23

O produto terá três superfícies integradas: Editor, Control e Player. Cada uma possui responsabilidade própria e não deve duplicar o modelo de conteúdo.

## 1. Editor

**Responsabilidade:** autoria do mapa.

O Editor será o ambiente completo de construção e alteração do documento. Os recursos já identificados como necessários ou candidatos incluem:

- Criar, editar, excluir e duplicar elementos.
- Arrastar e posicionar elementos.
- Redimensionar cartões.
- Criar, editar e remover conexões.
- Editar estilos dos elementos e das conexões.
- Upload e associação de imagens e documentos.
- Seleção individual e múltipla.
- Desfazer e refazer operações.
- Atalhos de teclado e menus contextuais.
- Salvamento e recuperação do documento.

A lista é inicial. A semântica e a prioridade de cada operação serão detalhadas no planejamento do Editor.

## 2. Control

**Responsabilidade:** conduzir uma sessão de apresentação sem editar o documento.

O Control será uma superfície separada, que poderá ser aberta em outro dispositivo ou monitor. Deverá enviar comandos ao Player e apresentar feedback do estado efetivamente aplicado.

Capacidades levantadas para discussão:

- Selecionar o mapa/sessão a controlar.
- Iniciar e encerrar uma apresentação.
- Navegar pelo mapa.
- Definir elemento em foco.
- Controlar zoom e posição da câmera.
- Alternar modos de visualização.
- Consultar o estado atual do Player.

A lista de comandos, o modelo de sessão, a autenticação, o emparelhamento e o tratamento de desconexões permanecem em aberto.

## 3. Player

**Responsabilidade:** renderizar e permitir explorar o mapa na tela de projeção.

O Player deve ser independente das ferramentas de autoria. Ele utiliza o documento do mapa e recebe separadamente o estado e os comandos da sessão de apresentação.

Requisitos já estabelecidos:

- Ter uma versão moderna compatível com Firefox 116 ou superior.
- Priorizar a experiência de projeção e a exploração do canvas.
- Suportar interação touchscreen no cenário de Android 11.
- Não impor ao Editor e ao Control as limitações de navegadores antigos.
- Não incluir a janela de webcam/vídeo observada na captura de referência.

O comportamento exato de navegação local, foco, menus de projeção e modos de exibição ainda será especificado.

## 4. Relação entre as superfícies

Fluxo conceitual:

```text
Biblioteca / abertura de mapa
          |
          v
        Editor
          |
    Documento salvo
          |
          v
        Control  ------ comandos/estado ao vivo ------> Player
                                                          |
                                                          v
                                                     Projeção
```

O documento representa o conteúdo persistente. O estado da sessão de apresentação representa a navegação e a visualização temporárias. Uma alteração no estado da apresentação não deve modificar inadvertidamente o documento.

## 5. Renderização compartilhada

A direção arquitetural proposta é compartilhar o contrato de documento e a lógica de renderização entre Editor e Player.

O Editor poderá acrescentar ferramentas e camadas de interação próprias. O Player deverá reutilizar a representação visual, sem carregar recursos de edição que não utiliza.

A implementação e os limites exatos de compartilhamento serão decididos após a especificação do canvas e a avaliação técnica.
