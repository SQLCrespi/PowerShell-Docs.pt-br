---
ms.date: 09/12/2016
ms.topic: reference
title: Nomear arquivos de ajuda
description: Nomear arquivos de ajuda
ms.openlocfilehash: b77af8f9b9510785a4198fed9da1263184a27b99
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667582"
---
# <a name="naming-help-files"></a>Nomear arquivos de ajuda

Este tópico explica como nomear um arquivo de ajuda baseado em XML para que o cmdlet [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) possa encontrá-lo. Os requisitos de nome são diferentes para cada tipo de comando.

## <a name="cmdlet-help-files"></a>Arquivos de ajuda de cmdlet

O arquivo de ajuda para um cmdlet do C# deve ser nomeado para o assembly no qual o cmdlet é definido. Use o seguinte formato de nome de arquivo:

```
<AssemblyName>.dll-help.xml
```

O formato do nome do assembly é necessário mesmo quando o assembly é um módulo aninhado.

Por exemplo, o cmdlet [Get-WinEvent](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent) é definido no assembly Microsoft.PowerShell.Diagnostics.dll. O `Get-Help` cmdlet procura um tópico de ajuda para o `Get-WinEvent` cmdlet somente no `Microsoft.PowerShell.Diagnostics.dll-help.xml` arquivo no diretório do módulo.

## <a name="provider-help-files"></a>Arquivos de ajuda do provedor

O arquivo de ajuda para um provedor do PowerShell deve ser nomeado para o assembly no qual o provedor está definido. Use o seguinte formato de nome de arquivo:

`<AssemblyName>.dll-help.xml`

O formato do nome do assembly é necessário mesmo quando o assembly é um módulo aninhado.

Por exemplo, o provedor de certificado é definido no `Microsoft.PowerShell.Security.dll` assembly. O `Get-Help` cmdlet procura um tópico de ajuda para o provedor de certificado somente no `Microsoft.PowerShell.Security.dll-help.xml` arquivo no diretório do módulo.

## <a name="function-help-files"></a>Arquivos de ajuda da função

As funções podem ser documentadas usando [a ajuda baseada em comentários](/powershell/module/microsoft.powershell.core/about/about_comment_based_help) ou documentadas em um arquivo de ajuda XML. Quando a função é documentada em um arquivo XML, a função deve ter uma `.ExternalHelp` palavra-chave comment que associa a função ao arquivo XML. Caso contrário, o `Get-Help` cmdlet não poderá localizar o arquivo de ajuda.

Não há requisitos técnicos para o nome de um arquivo de ajuda de função. No entanto, uma prática recomendada é nomear o arquivo de ajuda para o módulo de script no qual a função é definida. Por exemplo, a função a seguir é definida no `MyModule.psm1` arquivo.

```csharp
#.ExternalHelp MyModule.psm1-help.xml
function Test-Function { ... }
```

## <a name="cim-command-help-files"></a>Arquivos de ajuda do comando CIM

O arquivo de ajuda para um comando CIM deve ser nomeado para o arquivo CDXML no qual o comando CIM está definido. Use o seguinte formato de nome de arquivo:

`<FileName>.cdxml-help.xml`

Os comandos CIM são definidos em arquivos CDXML que podem ser incluídos em módulos como módulos aninhados. Quando o comando CIM é importado para a sessão como uma função, o PowerShell adiciona uma `.ExternalHelp` palavra-chave comment à definição da função que associa a função a um arquivo de ajuda XML que é nomeado para o arquivo CDXML no qual o comando CIM é definido.

## <a name="script-workflow-help-files"></a>Arquivos de ajuda do fluxo de trabalho de script

Os fluxos de trabalho de script incluídos em módulos podem ser documentados em arquivos de ajuda baseados em XML. Não há requisitos técnicos para o nome do arquivo de ajuda. No entanto, uma prática recomendada é nomear o arquivo de ajuda para o módulo de script no qual o fluxo de trabalho de script é definido. Por exemplo:

`<ScriptModule>.psm1-help.xml`

Ao contrário de outros comandos com script, os fluxos de trabalho de script não exigem uma `.ExternalHelp` palavra-chave de comentário para associá-los a um arquivo de ajuda. Em vez disso, o PowerShell pesquisa os subdiretórios específicos da cultura da interface do diretório do módulo para arquivos de ajuda baseados em XML e procura ajuda para o fluxo de trabalho do script em todos os arquivos. `.ExternalHelp` a palavra-chave Comment é ignorada.

Como a `.ExternalHelp` palavra-chave Comment é ignorada, o `Get-Help` cmdlet pode encontrar ajuda para fluxos de trabalho de script somente quando eles são incluídos em módulos.
