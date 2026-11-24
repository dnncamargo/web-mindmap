# Compatibilidade e plataformas

**Status:** requisitos iniciais definidos  
**Última atualização:** 2026-11-23

## 1. Princípio

A compatibilidade deve ser definida por superfície. Chrome 81 não será o denominador comum do produto e não deverá limitar bibliotecas, APIs, recursos ou funcionalidades do Editor, Control e Player moderno.

A prioridade é entregar uma experiência completa nos ambientes principais. A compatibilidade antiga será tratada como uma adaptação posterior e isolada.

## 2. Matriz de prioridade

| Prioridade | Superfície | Ambiente | Requisito |
|---|---|---|---|
| P0 | Editor | Chromebook, Chrome 156 64 bits | Ambiente crítico de compatibilidade e validação |
| P0 | Control | Chromebook, Chrome 156 64 bits | Ambiente crítico de compatibilidade e validação |
| P0 | Player moderno | Firefox 116+ | Versão de projeção principal |
| P1 | Editor / Control / Player | Navegadores atuais em desktop e mobile | Experiência responsiva |
| P2 | Player Legacy | Chrome 81 em Android 11 | Compatibilidade de baixa prioridade |

P0 é requisito fundamental. P1 amplia a cobertura. P2 só será abordado depois que as superfícies principais estiverem estabilizadas.

## 3. Editor e Control

- Devem funcionar em navegadores atuais, incluindo desktop e dispositivos móveis.
- O Chromebook com Chrome 156 de 64 bits é o ambiente mais crítico para validação.
- Não devem carregar restrições artificiais para acomodar o Chrome 81.
- Recursos modernos podem ser adotados quando trouxerem benefício real ao produto, respeitando os alvos P0 e P1.

## 4. Player moderno

- Firefox 116 é a referência mínima declarada para a projeção moderna.
- A experiência de projeção deve suportar telas grandes e telas touchscreen.
- Android 11 é o sistema operacional do cenário de projeção touchscreen mencionado.
- A versão exata do navegador e a possibilidade de uso de Android System WebView devem ser verificadas nos equipamentos reais.

## 5. Player Legacy

O cenário Chrome 81 em Android 11 tem prioridade P2, a mais baixa entre as compatibilidades declaradas.

Diretrizes:

- Não reduzir o alvo tecnológico do produto principal para suportar Chrome 81.
- Avaliar um build Legacy separado somente após o Player moderno estar funcional e validado.
- Reutilizar documento e lógica de renderização sempre que tecnicamente viável.
- Isolar polyfills, alternativas de CSS e adaptações específicas.
- Não presumir que baixar o alvo de compilação resolve incompatibilidades de APIs ou dependências.
- Não implementar antecipadamente uma segunda aplicação ou duplicar o motor do canvas sem evidência de necessidade.

## 6. Estratégia de validação

Os testes deverão ser organizados por superfície e plataforma:

| Ambiente | Cobertura |
|---|---|
| Chrome 156 64 bits / Chromebook | Editor e Control; Player quando aplicável |
| Firefox 116 | Player moderno; demais superfícies conforme necessidade |
| Navegadores atuais desktop | Fluxos principais e responsividade |
| Navegadores atuais mobile | Responsividade e interação por toque |
| Chrome 81 / Android 11 | Somente quando a etapa Legacy for priorizada |

A validação real deverá considerar também desempenho, memória, precisão dos gestos e características do hardware, não apenas a identificação do navegador.

## 7. Itens a confirmar posteriormente

- Modelos exatos dos dispositivos Android 11.
- Se a execução ocorrerá em Chrome Browser ou Android System WebView.
- Resolução, orientação e densidade das telas de projeção.
- Versões efetivamente instaladas nos equipamentos.
- Requisitos de operação em tela cheia e prevenção de suspensão.
