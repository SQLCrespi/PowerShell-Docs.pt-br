---
title: Nomeando arquivos de ajuda | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf54eac7-88c6-4108-a5f6-2f0906d1662b
caps.latest.revision: 5
ms.openlocfilehash: f65a90023df88fceafae1d1875ddf46b9088e2b8
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367005"
---
# <a name="naming-help-files"></a>Nomear arquivos de ajuda

Este tópico explica como nomear um arquivo de ajuda baseado em XML para que o cmdlet [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) possa encontrá-lo. Os requisitos de nome são diferentes para cada tipo de comando.

## <a name="cmdlet-help-files"></a>Arquivos de ajuda de cmdlet

O arquivo de ajuda para C# um cmdlet deve ser nomeado para o assembly no qual o cmdlet é definido. Use o seguinte formato de nome de arquivo:

```
<AssemblyName>.dll-help.xml
```

O formato do nome do assembly é necessário mesmo quando o assembly é um módulo aninhado.

Por exemplo, o [Get-WinEvent; PSITPro5_Diagnostic;](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent) o cmdlet é definido no assembly Microsoft. PowerShell. Diagnostics. dll. O cmdlet `Get-Help` procura um tópico de ajuda para o cmdlet `Get-WinEvent` somente no arquivo Microsoft. PowerShell. Diagnostics. dll-help. xml no diretório do módulo.

## <a name="provider-help-files"></a>Arquivos de ajuda do provedor

O arquivo de ajuda para um provedor do Windows PowerShell deve ser nomeado para o assembly no qual o provedor é definido. Use o seguinte formato de nome de arquivo:

```
<AssemblyName>.dll-help.xml
```

O formato do nome do assembly é necessário mesmo quando o assembly é um módulo aninhado.

Por exemplo, o provedor de certificado é definido no assembly Microsoft. PowerShell. Security. dll. O cmdlet `Get-Help` procura um tópico de ajuda para o provedor de certificado somente no arquivo Microsoft. PowerShell. Security. dll-help. xml no diretório do módulo.

## <a name="function-help-files"></a>Arquivos de ajuda da função

As funções podem ser documentadas usando [a ajuda baseada em comentários](/powershell/module/microsoft.powershell.core/about/about_comment_based_help) ou documentadas em um arquivo de ajuda XML. Quando a função é documentada em um arquivo XML, a função deve ter uma palavra-chave de comentário `.ExternalHelp` que associa a função ao arquivo XML. Caso contrário, o cmdlet `Get-Help` não poderá localizar o arquivo de ajuda.

Não há requisitos técnicos para o nome de um arquivo de ajuda de função. No entanto, uma prática recomendada é nomear o arquivo de ajuda para o módulo de script no qual a função é definida. Por exemplo, a função a seguir é definida no arquivo MyModule. psm1.

```csharp
#.ExternalHelp MyModule.psm1-help.xml
function Test-Function { ... }
```

## <a name="cim-command-help-files"></a>Arquivos de ajuda do comando CIM

O arquivo de ajuda para um comando CIM deve ser nomeado para o arquivo CDXML no qual o comando CIM está definido. Use o seguinte formato de nome de arquivo:

```
<FileName>.cdxml-help.xml
```

Os comandos CIM são definidos em arquivos CDXML que podem ser incluídos em módulos como módulos aninhados. Quando o comando CIM é importado para a sessão como uma função, o Windows PowerShell adiciona uma palavra-chave de comentário `.ExternalHelp` à definição de função que associa a função a um arquivo de ajuda XML nomeado para o arquivo CDXML no qual o comando CIM é definido.

## <a name="script-workflow-help-files"></a>Arquivos de ajuda do fluxo de trabalho de script

Os fluxos de trabalho de script incluídos em módulos podem ser documentados em arquivos de ajuda baseados em XML. Não há requisitos técnicos para o nome do arquivo de ajuda. No entanto, uma prática recomendada é nomear o arquivo de ajuda para o módulo de script no qual o fluxo de trabalho de script é definido. Por exemplo:

```
<ScriptModule>.psm1-help.xml
```

Ao contrário de outros comandos com script, os fluxos de trabalho de script não exigem uma palavra-chave de comentário `.ExternalHelp` para associá-los a um arquivo de ajuda. Em vez disso, o Windows PowerShell pesquisa os subdiretórios específicos da cultura da interface do diretório do módulo para arquivos de ajuda baseados em XML e procura ajuda para o fluxo de trabalho de script em todos os arquivos. a palavra-chave de comentário `.ExternalHelp` é ignorada.

Como a palavra-chave comment de `.ExternalHelp` é ignorada, o cmdlet `Get-Help` pode encontrar ajuda para fluxos de trabalho de script somente quando eles são incluídos em módulos.