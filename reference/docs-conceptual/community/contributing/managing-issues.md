---
title: Como gerenciamos problemas
description: Este artigo explica como a equipe do PowerShell-Docs gerencia problemas.
ms.date: 12/09/2020
ms.topic: conceptual
ms.openlocfilehash: 72267137a2657f51e5f616113adf92d80647acad
ms.sourcegitcommit: 61765d08321623743dc5db5367160f6982fe7857
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "99596158"
---
# <a name="how-we-manage-issues"></a>Como gerenciamos problemas

Este artigo documenta como gerenciamos problemas no repositório do PowerShell-Docs. O artigo foi projetado para ser um auxílio de trabalho para membros da equipe do PowerShell-Docs. Ele é publicado aqui para fornecer transparência de processo para nossos colaboradores públicos.

## <a name="sources-of-issues"></a>Fontes de problemas

- Colaboradores da Comunidade
- Colaboradores internos
- Transcrições de comentários de canais de mídia social
- Comentários por meio do formulário de comentários do Docs

## <a name="response-time-targets"></a>Metas de tempo de resposta

80% dos novos problemas são fechados dentro de 3 dias úteis.

- Triantigos-1 dias úteis
- Corrigir ou alterar-10 dias úteis

### <a name="labeling--milestones"></a>Rótulos & marcos

#### <a name="label-types"></a>Tipos de rótulo

|   Tipo   | Descrição                                                         |
| -------- | ------------------------------------------------------------------- |
| Área     | Usado para indicar qual parte do PowerShell ou os documentos que o problema está discutindo.<br>Útil para os proprietários de recursos encontrarem problemas para seus recursos. |
| Problema    | Indica o tipo de problema                                         |
| Prioridade | Indica a prioridade do problema. Intervalo de valores 0 (alto)-4 (baixo)  |
| Status   | Indica o status do item de trabalho ou por que ele foi fechado          |
| Marca      | Rótulos usados para para classificação adicional                        |
| Aguardando  | Indica que estamos aguardando alguém ou algum outro evento         |

#### <a name="milestones"></a>Marcos

Os problemas e solicitações de pull devem ser marcados com o marco apropriado. Se o problema não se aplicar a uma versão específica, nenhuma etapa será usada. PRs e problemas relacionados a alterações que ainda precisam ser mescladas na base de código do PowerShell devem ser atribuídos à etapa **futura** . Após a alteração do código ter sido mesclada, altere o marco para a versão apropriada.

|    Marco     |                    Descrição                     |
| ---------------- | -------------------------------------------------- |
| 7.0.0            | Itens de trabalho relacionados ao PowerShell 7.0               |
| 7.1.0            | Itens de trabalho relacionados ao PowerShell 7.1               |
| 7.2.0            | Itens de trabalho relacionados ao PowerShell 7,2               |
| Futuro           | Itens de trabalho relacionados a uma versão futura do PowerShell          |

## <a name="triage-process"></a>Processo de triagem

Os membros da equipe do PowerShell revisam os problemas diários e fazem triagem de novos problemas à medida que chegam. A equipe atende semanalmente para discutir problemas que precisam de triagem ou permanecem indefinidos.

### <a name="misplaced-product-feedback"></a>Comentários incorretos sobre o produto

- Insira um comentário redirecionando o cliente para o canal de comentários correto.
- Opcional: Copie o problema no local apropriado para comentários do produto, adicione um link ao item copiado e encerre o problema. NÃO copie problemas para o UserVoice.

  O local padrão para problemas do PowerShell é [https://github.com/PowerShell/PowerShell/issues/new/choose](https://github.com/PowerShell/PowerShell/issues/new/choose) .

  As seguintes áreas de assunto têm locais diferentes para problemas:

  | Entidades |                                                     URL de comentários do produto                                                     |
  | -------- | ---------------------------------------------------------------------------------------------------------------------------- |
  | dsc      | [https://windowsserver.uservoice.com/forums/301869-powershell](https://windowsserver.uservoice.com/forums/301869-powershell) |
  | gallery  | [https://github.com/powershell/powershellgallery/issues/new](https://github.com/powershell/powershellgallery/issues/new)     |
  | jea      | [https://github.com/powershell/jea/issues/new](https://github.com/powershell/jea/issues/new)                                 |
  | wmf      | [https://windowsserver.uservoice.com/forums/301869-powershell](https://windowsserver.uservoice.com/forums/301869-powershell) |

### <a name="support-requests"></a>Solicitações de suporte

- Se a pergunta de suporte for simples, responda-a educadamente e encerre o problema.
- Se a pergunta for mais complicada ou se o emissor responder com mais perguntas, redirecione-as para fóruns e canais de suporte. Texto sugerido para redirecionamento para fóruns:

  ```Markdown
  > This is not the right forum for these kinds of questions. Try posting your question in a
  > community support forum. For a list of community forums see:
  > https://docs.microsoft.com/powershell/scripting/community/community-support
  ```

### <a name="code-of-conduct-violations"></a>Violações do código de conduta

- Edite o problema para remover qualquer conteúdo ofensivo, se necessário.
- Insira um comentário indicando que o problema é spam, feche o problema e bloqueie-o para evitar mais comentários.
- Cada violação deve ser discutida na triagem semanal para determinar a necessidade de uma ação adicional (relatório para GitHub ou legal da Microsoft).
