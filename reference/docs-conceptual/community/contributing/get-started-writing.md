---
title: Iniciar a contribuição para a documentação do PowerShell
description: Este artigo é uma visão geral de como começar como um colaborador da documentação do PowerShell.
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: 95eb2c3157a99fcb6560914da8464022e1b64fad
ms.sourcegitcommit: 18d832858a7b8ea094763afa753e0f48f01372e7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/10/2020
ms.locfileid: "79060301"
---
# <a name="get-started-contributing-to-powershell-documentation"></a>Iniciar a contribuição para a documentação do PowerShell

Este artigo é uma visão geral de como começar como um colaborador da documentação do PowerShell.

## <a name="powershell-docs-structure"></a>Estrutura do PowerShell-Docs

O [repositório do PowerShell-Docs][psdocs] é dividido em dois grupos de conteúdo. Os GIT branches são usados para gerenciar como e quando a documentação é publicada.

### <a name="reference-content"></a>Conteúdo de referência

O conteúdo de referência é a referência de cmdlet do PowerShell para os cmdlets fornecidos no PowerShell.
A [referência][ref] é coletada nas pastas de versões (5.1, 6, 7.0 e 7.1). Esse conteúdo contém referências de cmdlet somente para os módulos fornecidos com o PowerShell. Esse conteúdo também é usado para criar as informações de ajuda exibidas pelo cmdlet `Get-Help`.

> [!NOTE]
> O TOC (Sumário) do conteúdo de referência é gerado automaticamente pelo sistema de publicação. Você não precisa atualizar o TOC.

### <a name="conceptual-content"></a>Conteúdo conceitual

A documentação conceitual inclui os seguintes conteúdos:

- Notas de versão
- Instruções de configuração
- Scripts de exemplo e artigos de instruções
- Documentação do DSC
- Documentação do SDK

A [documentação conceitual][conceptual] não está organizada por versão. Todos os artigos são exibidos para cada versão do PowerShell. Estamos trabalhando para criar artigos específicos da versão. Quando esse recurso estiver disponível em nossa documentação, este guia será atualizado com as informações apropriadas.

> [!NOTE]
> Sempre que um artigo conceitual é adicionado, removido ou renomeado, o TOC deve ser atualizado e incluído na solicitação de pull.

## <a name="using-git-branches"></a>Usar GIT branches

O branch padrão para o PowerShell-Docs é o `staging`. As alterações feitas em branches de trabalho são mescladas no branch `staging` antes de serem publicadas. Aproximadamente uma vez por semana, o branch `staging` é mesclado no branch `live`. O branch `live` inclui o conteúdo publicado em docs.microsoft.com. As alterações nunca devem ser feitas diretamente no branch `live`.

Se você estiver enviando uma alteração da documentação que se aplica somente a uma versão não lançada do PowerShell, verifique se há um branch de lançamento para essa versão. Todas as alterações que se aplicam a uma versão futura específica devem ser direcionadas para o branch de lançamento. Os branches de lançamento têm o seguinte padrão de nome: `release-<version>`.

Antes de iniciar as alterações, crie um branch de trabalho na cópia local do repositório do PowerShell-Docs. Isso deve ser um [clone da sua bifurcação][fork]. Certifique-se de sincronizar seu repositório local antes de criar seu branch de trabalho. O branch de trabalho deve ser criado a partir de uma cópia atualizada do branch `staging` ou `release`.

Faça as alterações que você deseja enviar seguindo o processo na seção [Fazer sua alteração][making-changes] do Guia do colaborador central.

### <a name="creating-new-articles"></a>Criar novos artigos

Um problema do GitHub deve ser criado para qualquer novo documento em que você deseja contribuir. Verifique se há problemas existentes para garantir que você não esteja duplicando os esforços. Os problemas atribuídos a alguém são considerados "em andamento". Se você quiser colaborar em um problema, entre em contato com a pessoa atribuída a ele.

Semelhante ao [processo RFC][rfc] do PowerShell, a criação de um problema antes de escrever o conteúdo garante que você não gaste muito tempo e esforço em algo que é rejeitado pela equipe do PowerShell-Docs. Isso também nos permite entrar em contato com você sobre o escopo do conteúdo e onde ele deve se encaixar na documentação do PowerShell.

### <a name="updating-existing-articles"></a>Atualizar artigos existentes

Quando aplicável, o artigo de referência do cmdlet é duplicado em todas as versões do PowerShell. Ao relatar um problema sobre uma referência de cmdlet ou um artigo `About_`, você deve especificar quais versões são afetadas pelo problema. O modelo de problema no GitHub inclui uma lista de verificação de versões. Use as caixas de seleção para especificar quais versões do conteúdo são afetadas. Ao enviar uma alteração de um artigo para um problema que afeta várias versões do conteúdo, você deve aplicar a alteração apropriada a cada versão do arquivo.

## <a name="next-steps"></a>Próximas etapas

Confira [Enviar uma solicitação de pull](pull-requests.md)

<!--link refs-->
[conceptual]: https://github.com/MicrosoftDocs/PowerShell-Docs/tree/staging/reference/docs-conceptual
[fork]: /contribute/get-started-setup-local#fork-the-repository
[making-changes]: /contribute/how-to-write-workflows-major#making-your-changes
[psdocs]: https://github.com/MicrosoftDocs/PowerShell-Docs
[ref]: https://github.com/MicrosoftDocs/PowerShell-Docs/tree/staging/reference
[rfc]: https://github.com/PowerShell/powershell-rfc/blob/master/RFC0000-RFC-Process.md