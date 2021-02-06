---
title: Como enviar solicitações de pull
description: Este artigo explica como enviar solicitações de pull ao repositório do PowerShell-Docs.
ms.date: 12/09/2020
ms.topic: conceptual
ms.openlocfilehash: 1a21c25e19189aec4f48ad034147b02f4f804f9d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "99598810"
---
# <a name="how-to-submit-pull-requests"></a>Como enviar solicitações de pull

Para fazer alterações no conteúdo, envie uma solicitação de pull do seu fork. Uma solicitação de pull deve ser revisada antes que possa ser mesclada. Para obter melhores resultados, revise a [lista de verificação editorial](editorial-checklist.md) antes de enviar sua solicitação de pull.

## <a name="using-git-branches"></a>Usando ramificações git

A ramificação padrão para PowerShell-Docs é a `staging` ramificação. As alterações feitas em ramificações de trabalho são mescladas na `staging` ramificação antes de serem publicadas. A `staging` ramificação é mesclada na `live` ramificação a cada dia da semana às 3:00 PM (hora do Pacífico). A `live` ramificação contém o conteúdo que é publicado em docs.Microsoft.com.

Antes de iniciar as alterações, crie um Branch de trabalho em sua cópia local do repositório de PowerShell-Docs. Ao trabalhar localmente, certifique-se de sincronizar seu repositório local antes de criar seu Branch de trabalho. A ramificação de trabalho deve ser criada a partir de uma cópia atualizada até a data do `staging` Branch.

Todas as solicitações de pull devem ter como destino o branch `staging`. Não envie alteração para a `live` ramificação.
As alterações realizadas no branch `staging` são mescladas no `live`, substituindo as alterações feitas no `live`.

## <a name="make-the-pull-request-process-work-better-for-everyone"></a>Melhorar o funcionamento do processo de solicitação de pull para todos

Quanto mais simples e focada for a PR (solicitação de pull), mais rápido ela poderá ser revisada e mesclada.

### <a name="avoid-pull-requests-that-update-large-numbers-of-files-or-contain-unrelated-changes"></a>Evitar solicitações pull que atualizam um grande número de arquivos ou contêm alterações não relacionadas

Evite criar PRs que contenham alterações não relacionadas. Separe as pequenas atualizações feitas nos artigos existentes dos novos artigos ou das principais regravações. Trabalhe nessas alterações em branches de trabalho separados.

Alterações em massa criam PRs com um grande número de arquivos alterados. Limite as PRs a um máximo de 50 arquivos alterados. PRs grandes são difíceis de revisar e mais propensas a conter erros.

### <a name="renaming-or-deleting-files"></a>Renomear ou excluir arquivos

Ao renomear ou excluir arquivos, deve haver um problema associado à PR. Esse problema deve discutir a necessidade de renomear ou excluir os arquivos.

Evite misturar adições ou alterações de conteúdo com renomeações e exclusões de arquivos. Qualquer arquivo renomeado ou excluído deve ser adicionado ao arquivo de redirecionamento global. Quando possível, atualize todos os arquivos vinculados ao conteúdo renomeado ou excluído, incluindo todos os arquivos de Sumário.

## <a name="docs-pr-validation-service"></a>Serviço de validação de PR do Docs

O serviço de validação docs PR é um aplicativo GitHub que executa regras de validação em suas alterações. Você deve corrigir todos os erros ou avisos relatados pelo serviço de validação.

Você verá o seguinte comportamento:

1. Você envia uma PR.
1. No comentário do GitHub que indica o status da PR, você verá o status de "verificações" habilitadas no repositório. Neste exemplo, há duas verificações habilitadas, "confirmar validação" e "OpenPublishing. Build":

   ![Status de validação – Algumas verificações falharam](media/pull-requests/validation-failed.png)

   O build poderá passar mesmo se a validação do commit falhar.

1. Clique em **Detalhes** para obter mais informações.
1. Na página Detalhes, você verá todas as verificações de validação que falharam, com informações sobre como corrigir os problemas.
1. Quando a validação é bem-sucedida, o seguinte comentário é adicionado à PR:

   ![Status da validação: sucesso](media/pull-requests/build-validation.png)

> [!NOTE]
> Se você for um colaborador externo (não funcionário da Microsoft), não terá acesso aos relatórios detalhados de build nem aos links de visualização.

Quando a PR for revisada, você poderá ser solicitado a fazer alterações ou corrigir mensagens de aviso de validação. A equipe de PowerShell-Docs pode ajudá-lo a entender os erros de validação e os requisitos editoriais.

## <a name="next-steps"></a>Próximas etapas

[Guia de estilo do PowerShell-Docs](powershell-style-guide.md)

## <a name="additional-resources"></a>Recursos adicionais

[Como gerenciamos solicitações de pull](managing-pull-requests.md)

<!--link refs-->
[fork]: /contribute/get-started-setup-local#fork-the-repository
