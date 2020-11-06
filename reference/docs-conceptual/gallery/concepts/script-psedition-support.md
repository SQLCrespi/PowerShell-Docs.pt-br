---
ms.date: 06/12/2017
title: Script com edições compatíveis do PowerShell
description: Este artigo explica como os cmdlets do PowerShellGet dão suporte às edições Desktop e Core dos scripts do PowerShell.
ms.openlocfilehash: c9d8af24be8138283027263c62140b3fd04d6b24
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92656053"
---
# <a name="script-with-compatible-powershell-editions"></a>Script com edições compatíveis do PowerShell

Da versão 5.1 em diante, o PowerShell está disponível nas edições diferentes que denotam diferentes conjuntos de recursos e compatibilidade de plataforma.

- **Desktop Edition:** criado no .NET Framework; fornece compatibilidade com scripts e módulos destinados a versões do PowerShell em execução em edições de volume completo do Windows, como Server Core e Windows Desktop.

- **Core Edition:** criada no .NET Core e oferece compatibilidade com scripts e módulos destinados a versões do PowerShell executando em edições de superfície reduzida do Windows, como o Nano Server e Windows IoT.

A edição de execução do PowerShell é mostrada na propriedade PSEdition do $PSVersionTable.

```powershell
$PSVersionTable

Name                           Value
----                           -----
PSVersion                      5.1.14300.1000
PSEdition                      Desktop
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0...}
CLRVersion                     4.0.30319.42000
BuildVersion                   10.0.14300.1000
WSManStackVersion              3.0
PSRemotingProtocolVersion      2.3
SerializationVersion           1.1.0.1
```

Os autores de scripts podem impedir que um script seja executado a menos que ele seja executado em uma edição compatível do PowerShell usando o parâmetro PSEdition em uma instrução `#requires`.

```powershell
Set-Content C:\script.ps1 -Value "#requires -PSEdition Core
Get-Process -Name PowerShell"
Get-Content C:\script.ps1
#requires -PSEdition Core
Get-Process -Name PowerShell

C:\script.ps1
C:\script.ps1 : The script 'script.ps1' cannot be run because it contained a "#requires" statement for PowerShell editions 'Core'. The edition of PowerShell that is required by the script does not match the currently running PowerShell Desktop edition.
At line:1 char:1
+ C:\script.ps1
+ ~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (script.ps1:String) [], RuntimeException
    + FullyQualifiedErrorId : ScriptRequiresUnmatchedPSEdition
```

Os usuários da Galeria do PowerShell podem encontrar a lista de scripts com suporte em uma edição específica do PowerShell.
Scripts sem as marcas PSEdition_Desktop e PSEdition_Core funcionam corretamente na edição do PowerShell Desktop.

```powershell
# Find scripts supported on PowerShell Desktop edition
Find-Script -Tag PSEdition_Desktop

# Find scripts supported on PowerShell Core edition
Find-Script -Tag PSEdition_Core
```

## <a name="more-details"></a>Mais detalhes

- [Módulos com PSEditions](module-psedition-support.md)
- [Suporte do PSEditions na PowerShellGallery](../how-to/finding-packages/searching-by-compatibility.md)
