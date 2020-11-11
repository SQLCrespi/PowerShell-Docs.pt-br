---
title: Como gerenciamos problemas
description: Este artigo explica como a equipe do PowerShell-Docs gerencia problemas.
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: 56f0ea5b4c5c700db8fdd0b16e3ce1c4040a43dc
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "93354585"
---
# <a name="how-we-manage-issues"></a>Como gerenciamos problemas

Este artigo documenta como gerenciamos problemas no repositório do PowerShell-Docs. O artigo foi projetado para ser um auxílio de trabalho para membros da equipe do PowerShell-Docs. Publicamos aqui para fornecer transparência quanto ao processo para nossos colaboradores públicos.

## <a name="sources-of-issues"></a>Fontes de problemas

- Colaboradores da Comunidade
- Colaboradores internos
- Transcrições de comentários de canais de mídia social
- Comentários por meio do formulário de comentários do Docs

## <a name="response-time-targets"></a>Metas de tempo de resposta

- Triagem - 5 dias úteis
- Correção ou alteração - nenhuma meta específica - melhor esforço

### <a name="labeling--milestones"></a>Rótulos & marcos

#### <a name="label-types"></a>Tipos de rótulo

|Prefixo  | Descrição                                                         |
|------- | --------------------------------------------------------------------|
|Área    | Usado para indicar qual parte do PowerShell ou os documentos que o problema está discutindo.<br>Útil para os proprietários de recursos encontrarem problemas para seus recursos.|
|Pri     | Usado para indicar a prioridade do problema. Intervalo de valores de 0 a 4.        |
|Problema   | Usado para classificar o tipo de comentário para o problema                     |
|Revisão  | Usado para problemas que exigem uma análise adicional da equipe              |
|Status  | Usado para indicar o status do item de trabalho                        |
|Aguardando | Usado para indicar que estamos aguardando algo                   |

#### <a name="milestones"></a>Marcos

Os problemas e solicitações de pull devem ser marcados com o marco apropriado. Se o problema não for direcionado a uma versão específica, nenhum marco será usado. Os problemas para solicitações de pulls de documentação para alterações que ainda precisam ser mescladas na base de código do PowerShell devem ser atribuídos ao marco **Futuro**. Após a alteração do código ter sido mesclada, altere o marco para a versão apropriada.

|    Marco     |                    Descrição                     |
| ---------------- | -------------------------------------------------- |
| 6.x              | Itens de trabalho relacionados ao PowerShell 6.0 a 6.2. x |
| 7.0.0            | Itens de trabalho relacionados ao PowerShell 7.0               |
| 7.1.0            | Itens de trabalho relacionados ao PowerShell 7.1               |
| Futuro           | Itens de trabalho relacionados a uma versão futura do PowerShell          |
| PSReadline-vNext | Itens de trabalho relacionados a uma versão futura do PSReadline          |

## <a name="triage-process"></a>Processo de triagem

A equipe de documentação do PowerShell se reúne uma vez por semana para discutir os problemas adicionados desde a última reunião. Considera-se que um problema passou por triagem quando os rótulos foram atribuídos ou um proprietário foi atribuído. Os membros da equipe de documentação do PowerShell são incentivados a revisar os problemas diariamente e fazer a triagem de novos problemas à medida que chegam. A reunião semanal de triagem pode ser usada para discutir os novos problemas em mais detalhes, conforme necessário.

### <a name="misplaced-product-feedback"></a>Comentários incorretos sobre o produto

- Insira um comentário para o cliente indicando que são comentários sobre o produto e forneça um link para o canal de comentários apropriado.
- Opcional: Copie o problema no local apropriado para comentários do produto, adicione um link ao item copiado e encerre o problema. NÃO copie problemas para o UserVoice.

  | DocSet    | URL de comentários do produto                                           |
  | --------- | -------------------------------------------------------------- |
  | developer | `https://github.com/PowerShell/PowerShell/issues/new/choose`   |
  | dsc       | `https://windowsserver.uservoice.com/forums/301869-powershell` |
  | gallery   | `https://github.com/powershell/powershellgallery/issues/new`   |
  | jea       | `https://github.com/powershell/jea/issues/new`                 |
  | reference | `https://github.com/PowerShell/PowerShell/issues/new/choose`   |
  | wmf       | `https://windowsserver.uservoice.com/forums/301869-powershell` |

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
- Cada ocorrência disso deve ser discutida na triagem semanal para determinar a necessidade de mais ações (relatório no GitHub ou Jurídico da Microsoft).
