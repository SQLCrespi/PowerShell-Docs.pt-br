---
ms.openlocfilehash: d94024926a8ff8c33df08b4a8b58e9f8b0430f9b
ms.sourcegitcommit: fcf7bd222f5ee3fdbe21ffddcae47050cffe7e42
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "93239877"
---
# <a name="microsoft-open-source-code-of-conduct"></a>Código de Conduta Aberto da Microsoft

> Atualização: 02/11/2020

Este projeto adotou o [Código de Conduta de Software Livre da Microsoft](https://opensource.microsoft.com/codeofconduct/). Para saber mais, confira as [Perguntas Frequentes sobre o Código de Conduta](https://opensource.microsoft.com/codeofconduct/faq/) ou contate [opencode@microsoft.com](mailto:opencode@microsoft.com) com perguntas ou comentários adicionais.

[live-badge]: https://powershell.visualstudio.com/PowerShell-Docs/_apis/build/status/PowerShell-Docs-CI?branchName=live
[staging-badge]: https://powershell.visualstudio.com/PowerShell-Docs/_apis/build/status/PowerShell-Docs-CI?branchName=staging

## <a name="build-status"></a>Status do build

|          Branch dinâmica          |           Branch de preparo            |
| :---------------------------- | :---------------------------------- |
| [![live-badge][]][live-badge] | [![staging-badge][]][staging-badge] |

## <a name="powershell-documentation"></a>Documentação do PowerShell

Bem-vindo(a) ao repositório de documentos do PowerShell, o lar da documentação oficial do PowerShell.

## <a name="repository-structure"></a>Estrutura do Repositório

A lista a seguir descreve as pastas principais neste repositório.

- `.github` – Contém as definições de configuração usadas pelo GitHub para esse repositório
- `.vscode` – Contém definições de configuração e extensões recomendadas para o VS Code (Visual Studio Code)
- `assets` – Contém arquivos para download vinculados na documentação
- `reference` – Contém a documentação publicada em [docs.microsoft.com]([https://docs.microsoft.com/powershell/scripting/). Isso inclui o conteúdo conceitual e de referência.
  - `5.1` – Contém a referência de cmdlet e sobre os tópicos para o PowerShell 5.1
  - `6` – Contém a referência de cmdlet e sobre os tópicos para o PowerShell 6
  - `7.0` – Contém a referência de cmdlet e sobre os tópicos para o PowerShell 7.0
  - `7.1` – Contém a referência de cmdlet e sobre os tópicos para o PowerShell 7.1
  - `bread` – Contém o Sumário usado para a navegação estrutural
  - `docs-conceptual` – Contém os artigos conceituais publicados no site do Docs. Em geral, a estrutura de pastas espelha o Sumário.
  - `mapping` – Contém a configuração de mapeamento de versão usada pelo sistema de build
  - `media` – Contém arquivos de imagem usados na documentação. Há pastas de mídia em todo o conteúdo `docs-conceptual`. Confira o Guia do Colaborador para obter informações sobre como usar imagens na documentação.
  - `module` – Contém a origem do markdown para a página do Module Browser
- `tests` – Contém os testes Pester usados pelo sistema de build
- `tools` – Contém outras ferramentas usadas pelo sistema de build

> OBSERVAÇÃO: O conteúdo de referência (nas pastas numeradas) é usado para criar as páginas da Web no site do Docs, bem como a ajuda atualizável usada pelo PowerShell.
> Os artigos na pasta `docs-conceptual` são publicados apenas no site do Docs.

## <a name="contributing"></a>Participante

Estamos abertos a contribuições públicas neste repositório por meio de [solicitações de pull](https://help.github.com/articles/using-pull-requests/) no branch de _preparo_.
Observe que, para aceitarmos sua solicitação de pull, assine nosso [Contrato de Licença de Contribuição](https://cla.microsoft.com/). Esse é um requisito avulso.

Saiba mais sobre como contribuir no [guia do colaborador](https://aka.ms/PSDocsContributor). Ele traz informações detalhadas sobre como contribuir com a documentação, ferramentas sugeridas e requisitos de formatação e estilo. Use os modelos de Solicitação Pull e de Problemas para ajudar a manter a consistência da documentação em diferentes versões.

## <a name="licenses"></a>Licenças

Há dois arquivos de licença para este projeto. A licença do MIT aplica-se ao código contido neste repositório. A licença Creative Commons aplica-se à documentação.
