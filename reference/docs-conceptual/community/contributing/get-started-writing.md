---
title: Iniciar a contribuição para a documentação do PowerShell
description: Este artigo é uma visão geral de como começar como um colaborador da documentação do PowerShell.
ms.date: 12/09/2020
ms.topic: conceptual
ms.openlocfilehash: ddcbf79de1ab05b901ce1abd67f65b2524ed164d
ms.sourcegitcommit: 61765d08321623743dc5db5367160f6982fe7857
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "99603320"
---
# <a name="get-started-contributing-to-powershell-documentation"></a>Iniciar a contribuição para a documentação do PowerShell

Este artigo é uma visão geral de como começar como um colaborador da documentação do PowerShell.

## <a name="powershell-docs-structure"></a>Estrutura do PowerShell-Docs

O [repositório de documentos do PowerShell][psdocs] é dividido em dois grupos de conteúdo: referência e conceitual.

### <a name="reference-content"></a>Conteúdo de referência

O conteúdo de referência é a referência de cmdlet do PowerShell para os cmdlets fornecidos no PowerShell.
A [referência][ref] é coletada nas pastas de versões (5,1, 7,0, 7,1 e 7,2). Esse conteúdo contém referência de cmdlet somente para os módulos fornecidos com o PowerShell. Esse conteúdo também é usado para criar as informações de ajuda exibidas pelo `Get-Help` cmdlet.

### <a name="conceptual-content"></a>Conteúdo conceitual

A documentação conceitual inclui o seguinte conteúdo:

- Notas de versão
- Instruções de configuração
- Scripts de exemplo e artigos de instruções
- Documentação da DSC
- Documentação do SDK

A [documentação conceitual][conceptual] não é organizada por versão. Todos os artigos são exibidos para cada versão do PowerShell. Estamos trabalhando para criar artigos específicos da versão. Quando esse recurso estiver disponível em nossa documentação, este guia será atualizado com as informações apropriadas.

> [!NOTE]
> Sempre que um artigo conceitual é adicionado, removido ou renomeado, o Sumário deve ser atualizado e incluído na solicitação de pull.

## <a name="creating-new-articles"></a>Criando novos artigos

Um problema do GitHub deve ser criado para qualquer novo documento que você deseja contribuir. Verifique se há problemas existentes para certificar-se de que você não está duplicando os esforços. Problemas atribuídos são considerados `in progress` . Se você quiser colaborar em um problema, entre em contato com a pessoa atribuída ao problema.

Semelhante ao processo da [RFC][rfc]do PowerShell, crie um problema antes de gravar o conteúdo. O problema garante que você não gaste tempo e esforço no trabalho que é rejeitado pela equipe de PowerShell-Docs. O problema nos permite consultar com você sobre o escopo do conteúdo e onde ele se encaixa na documentação do PowerShell. Todos os artigos devem ser incluídos no Sumário (TOC). O local do Sumário proposto deve ser incluído na discussão do problema.

> [!NOTE]
> O Sumário para o conteúdo de referência é gerado automaticamente pelo sistema de publicação. Você não precisa atualizar o Sumário.

## <a name="updating-existing-articles"></a>Atualizando artigos existentes

Quando aplicável, os artigos de referência de cmdlet são duplicados em todas as versões do PowerShell mantidas neste repositório. Ao relatar um problema sobre uma referência de cmdlet ou um `About_` artigo, você deve especificar quais versões são afetadas pelo problema. O modelo de problema no GitHub inclui uma lista de verificação de versões. Use as caixas de seleção para especificar quais versões do conteúdo são afetadas.

Verifique todas as versões do artigo para ver se a mesma alteração é necessária nas outras versões. Aplique a alteração apropriada a cada versão do arquivo.

## <a name="localized-content"></a>Conteúdo localizado

A documentação do PowerShell é escrita em inglês e traduzida em 17 outras linguagens. O conteúdo em inglês é armazenado no repositório GitHub denominado `MicrosoftDocs/PowerShell-Docs` . O conteúdo localizado é armazenado em um repositório separado para cada idioma. Os repositórios usam o mesmo baseName, mas adicionam o nome da localidade ao final. Por exemplo, `MicrosoftDocs/PowerShell-Docs.de-de` contém o conteúdo que foi convertido em alemão.

Em geral, problemas e alterações devem ser enviados para o repositório em inglês. Todas as traduções começam do conteúdo em inglês primeiro. Usamos a tradução humana e a máquina.

| Método de tradução  |                              Idiomas                               |
| ------------------- | -------------------------------------------------------------------- |
| Tradução humana   | de-DE, es-ES, fr-FR, it-IT, ja-JP, ko-KR, pt-BR, ru-RU, zh-CN, zh-TW |
| Tradução automática | CS-CZ, hu-HU, NL-NL, pl-PL, pt-PT, SV-SE, TR-TR                      |

O conteúdo traduzido por tradução automática nem sempre pode resultar em opções corretas de palavras e gramática. Se você encontrar um erro na tradução para qualquer idioma, em vez de nos detalhes técnicos do artigo, abra um problema no repositório localizado. Explique por que você acredita que a tradução está incorreta. Nossa equipe de localização revisa e responde a esses problemas.

## <a name="next-steps"></a>Próximas etapas

Há duas maneiras comuns de enviar alterações no GitHub. Ambos os métodos são descritos no guia do colaborador central:

1. Você pode fazer [edições rápidas em documentos existentes](/contribute/#quick-edits-to-existing-documents) na interface Web do github.
1. Use o [fluxo de trabalho completo do GitHub][making-changes] para adicionar novos artigos, atualizar vários arquivos ou outras grandes alterações.

Antes de iniciar as alterações, você deve criar uma bifurcação do repositório de PowerShell-Docs. As alterações devem ser feitas em um Branch de trabalho na cópia dos documentos do PowerShell. Se você estiver usando o método de **edição rápida** no GitHub, essas etapas serão tratadas para você. Se estiver usando o **fluxo de trabalho completo do GitHub**, você deverá estar configurado para [funcionar localmente][fork].

Ambos os métodos terminam com a criação de uma solicitação pull (PR). Consulte [enviando uma solicitação de pull](pull-requests.md) para obter mais informações e práticas recomendadas.

<!--link refs-->
[conceptual]: https://github.com/MicrosoftDocs/PowerShell-Docs/tree/staging/reference/docs-conceptual
[fork]: /contribute/get-started-setup-local#fork-the-repository
[making-changes]: /contribute/how-to-write-workflows-major#making-your-changes
[psdocs]: https://github.com/MicrosoftDocs/PowerShell-Docs
[ref]: https://github.com/MicrosoftDocs/PowerShell-Docs/tree/staging/reference
[rfc]: https://github.com/PowerShell/powershell-rfc/blob/master/RFC0000-RFC-Process.md
