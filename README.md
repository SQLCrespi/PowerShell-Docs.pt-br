---
ms.openlocfilehash: 0d91230aa063e58106b35a4ada1d577f316f8f27
ms.sourcegitcommit: c752ae8d0fa47eaaf3c5eae2a5a770f06c63921c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/26/2020
ms.locfileid: "83840987"
---
# <a name="microsoft-open-source-code-of-conduct"></a>Código de Conduta Aberto da Microsoft

Este projeto adotou o [Código de Conduta de Software Livre da Microsoft](https://opensource.microsoft.com/codeofconduct/). Para saber mais, confira as [Perguntas Frequentes sobre o Código de Conduta](https://opensource.microsoft.com/codeofconduct/faq/) ou contate [opencode@microsoft.com](mailto:opencode@microsoft.com) com perguntas ou comentários adicionais.

[live-badge]: https://powershell.visualstudio.com/PowerShell-Docs/_apis/build/status/PowerShell-Docs-CI?branchName=live
[staging-badge]: https://powershell.visualstudio.com/PowerShell-Docs/_apis/build/status/PowerShell-Docs-CI?branchName=staging

## <a name="build-status"></a>Status do build

|          Branch dinâmica          |           Branch de preparo            |
| :---------------------------- | :---------------------------------- |
| [![live-badge][]][live-badge] | [![staging-badge][]][staging-badge] |

## <a name="powershell-documentation"></a>Documentação do PowerShell

Bem-vindo ao repositório de documentos do PowerShell, que abriga a documentação oficial do PowerShell.

## <a name="repository-structure"></a>Estrutura do Repositório

Cada uma das seguintes pastas de nível superior neste repositório contém um DocSet publicado no [Microsoft Docs](https://docs.microsoft.com/powershell).

- [/reference/](https://docs.microsoft.com/powershell/scripting/) é para tópicos conceituais do PowerShell e referência de módulo nas versões 5.1, 6.0 e 7.0. Este conteúdo também é a origem do conteúdo da Ajuda recuperado pelo cmdlet `Get-Help`.
  - [docs-conceptual/](https://docs.microsoft.com/powershell) – esta pasta contém a documentação conceitual e os seguintes documentos:
    - [developer/](https://docs.microsoft.com/powershell/scripting/developer/) é a documentação do SDK do PowerShell (migrada do MSDN)
    - [dsc/](https://docs.microsoft.com/powershell/scripting/dsc/) é para o recurso Desired State Configuration
    - [gallery/](https://docs.microsoft.com/powershell/scripting/gallery) é para a [Galeria do PowerShell](https://www.powershellgallery.com/)
    - [jea/](https://docs.microsoft.com/powershell/scripting/learn/remoting/jea/overview) é para o recurso Administração Apenas Suficiente
    - [wmf/](https://docs.microsoft.com/powershell/scripting/windows-powershell/wmf/overview) contém notas de versão do Windows Management Framework, o pacote usado para distribuir novas versões do PowerShell para versões anteriores do Windows.

## <a name="contributing"></a>Participante

Mesclamos ativamente as contribuições neste repositório por meio de [solicitações de pull](https://help.github.com/articles/using-pull-requests/) no branch de _preparo_.
Observe que, antes do envio de uma solicitação de pull, é necessário assinar um [Contrato de Licença de Contribuição](https://cla.microsoft.com/) a fim de verificar se a comunidade está livre para usar os envios.

Saiba mais sobre como contribuir no [guia do colaborador](https://docs.microsoft.com/powershell/scripting/community/contributing/overview).
Ele traz informações detalhadas sobre como contribuir com a documentação, ferramentas sugeridas e requisitos de formatação e estilo. Use os modelos de Solicitação Pull e de Problemas para ajudar a manter a consistência da documentação em diferentes versões.

## <a name="licenses"></a>Licenças

Há dois arquivos de licença para este projeto. A licença do MIT aplica-se ao código contido neste repositório. A licença Creative Commons aplica-se à documentação.
