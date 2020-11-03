---
description: Descreve a funcionalidade de compatibilidade do Windows PowerShell para o PowerShell 7.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_windows_powershell_compatibility?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_PowerShell_Compatibility
ms.openlocfilehash: 777dab1cce4329958337a7c0857b0d712b4387a9
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195929"
---
# <a name="about-windows-powershell-compatibility"></a>Sobre a compatibilidade do Windows PowerShell

## <a name="short-description"></a>DESCRIÇÃO BREVE

Descreve a funcionalidade de compatibilidade do Windows PowerShell para o PowerShell 7.

## <a name="long-description"></a>DESCRIÇÃO LONGA

A menos que o manifesto do módulo indique que o módulo é compatível com o PowerShell Core, os módulos na `%windir%\system32\WindowsPowerShell\v1.0\Modules` pasta são carregados em um processo em segundo plano do Windows powershell 5,1 pelo recurso de compatibilidade do Windows PowerShell.

### <a name="using-the-compatibility-feature"></a>Usando o recurso de compatibilidade

Quando o primeiro módulo é importado usando o recurso de compatibilidade do Windows PowerShell, o PowerShell cria uma sessão remota chamada `WinPSCompatSession` que está sendo executada em um processo em segundo plano do Windows powershell 5,1. Esse processo é criado quando o recurso de compatibilidade importa o primeiro módulo. O processo é fechado quando o último módulo é removido (usando `Remove-Module` ) ou quando o processo do PowerShell é encerrado.

Os módulos carregados na `WinPSCompatSession` sessão são usados por meio de comunicação remota implícita e refletidos na sessão atual do PowerShell. Esse é o mesmo método de transporte usado para trabalhos do PowerShell.

Quando um módulo é importado para a `WinPSCompatSession` sessão, a comunicação remota implícita gera um módulo de proxy no diretório do usuário `$env:Temp` e importa esse módulo de proxy para a sessão atual do PowerShell. Isso permite que o PowerShell detecte que o módulo foi carregado usando a funcionalidade de compatibilidade do Windows PowerShell.

Depois que a sessão é criada, ela pode ser usada para operações que não funcionam corretamente em objetos desserializados. Todo o pipeline é executado no Windows PowerShell e apenas o resultado final é retornado. Por exemplo:

```powershell
$s = Get-PSSession -Name WinPSCompatSession
Invoke-Command -Session $s -ScriptBlock {
  "Running in Windows PowerShell version $($PSVersionTable.PSVersion)"
}
```

O recurso de compatibilidade pode ser invocado de duas maneiras:

- Explicitamente importando um módulo usando o parâmetro **UseWindowsPowerShell**

   ```powershell
   Import-Module -Name ScheduledTasks -UseWindowsPowerShell
   ```

- Implicitamente, importando um módulo do Windows PowerShell por nome do módulo, caminho ou carregamento automático via descoberta de comando.

   ```powershell
   Import-Module -Name ServerManager
   Get-AppLockerPolicy -Local
   ```

   Se ainda não tiver sido carregado, o módulo do AppLocker será carregado com autocarga quando você executar  `Get-AppLockerPolicy` .

A compatibilidade do Windows PowerShell bloqueia o carregamento de módulos listados na `WindowsPowerShellCompatibilityModuleDenyList` configuração no arquivo de configuração do PowerShell.

O valor padrão dessa configuração é:

```json
"WindowsPowerShellCompatibilityModuleDenyList":  [
   "PSScheduledJob","BestPractices","UpdateServices"
]
```

### <a name="managing-implicit-module-loading"></a>Gerenciando o carregamento de módulo implícito

Para desabilitar o comportamento de importação implícito do recurso de compatibilidade do Windows PowerShell, use a `DisableImplicitWinCompat` configuração em um arquivo de configuração do PowerShell. Essa configuração pode ser adicionada ao `powershell.config.json` arquivo. Para obter mais informações, consulte [about_powershell_config](about_powershell_config.md).

Este exemplo mostra como criar um arquivo de configuração que desabilita o recurso de carregamento de módulo implícito da compatibilidade do Windows PowerShell.

```powershell
$ConfigPath = "$PSHOME\DisableWinCompat.powershell.config.json"
$ConfigJSON = ConvertTo-Json -InputObject @{
  "DisableImplicitWinCompat" = $true
  "Microsoft.PowerShell:ExecutionPolicy" = "RemoteSigned"
}
$ConfigJSON | Out-File -Force $ConfigPath
pwsh -settingsFile $ConfigPath
```

Para obter mais informações sobre a compatibilidade de módulo, consulte a lista de [compatibilidade de módulo do PowerShell 7](https://aka.ms/PSModuleCompat) .

### <a name="managing-cmdlet-clobbering"></a>Gerenciando cmdlet sobreporem

O recurso de compatibilidade do Windows PowerShell usa a comunicação remota implícita para carregar módulos no modo de compatibilidade. O resultado é que os comandos exportados pelo módulo têm precedência sobre os comandos de mesmo nome na sessão atual do PowerShell 7. Na versão 7.0.0 do PowerShell, isso incluiu os módulos principais fornecidos com o PowerShell.

No PowerShell 7,1, o comportamento foi alterado para que os seguintes módulos principais do PowerShell não sejam sobrescrito:

- Microsoft. PowerShell. ConsoleHost
- Microsoft.PowerShell.Diagnostics
- Microsoft.PowerShell.Host
- Microsoft.PowerShell.Management
- Microsoft.PowerShell.Security
- Microsoft.PowerShell.Utility
- Microsoft.WSMan.Management

O PowerShell 7,1 também adicionou a capacidade de listar módulos adicionais que não devem ser sobrescritodos pelo modo de compatibilidade.

Você pode adicionar a `WindowsPowerShellCompatibilityNoClobberModuleList` configuração ao arquivo de configuração do PowerShell. O valor dessa configuração é uma lista separada por vírgulas de nomes de módulo. O valor padrão dessa configuração é:

```json
"WindowsPowerShellCompatibilityNoClobberModuleList": [ ]
```

## <a name="limitations"></a>Limitações

A funcionalidade de compatibilidade do Windows PowerShell:

1. Funciona apenas localmente em computadores com Windows
1. Requer que o Windows PowerShell 5,1
1. Opera em parâmetros de cmdlet serializados e valores de retorno, não em objetos dinâmicos
1. Todos os módulos importados para a sessão remota do Windows PowerShell compartilham o mesmo runspace.

## <a name="keywords"></a>Palavras-chave

about_Windows_PowerShell_Compatibility

## <a name="see-also"></a>Confira também

[about_Modules](about_Modules.md)

[Import-Module](xref:Microsoft.PowerShell.Core.Import-Module)
