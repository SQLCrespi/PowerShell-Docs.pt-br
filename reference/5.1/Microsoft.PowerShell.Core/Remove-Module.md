---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-module?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Module
ms.openlocfilehash: a1052c357f19fd8f06eb39a14f8e8eded0c881a9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193513"
---
# Remove-Module

## SINOPSE
Remove módulos da sessão atual.

## SYNTAX

### name

```
Remove-Module [-Name] <String[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FullyQualifiedName

```
Remove-Module [-FullyQualifiedName] <ModuleSpecification[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ModuleInfo

```
Remove-Module [-ModuleInfo] <PSModuleInfo[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Remove-Module** remove os membros de um módulo, como cmdlets e funções, da sessão atual.

Se o módulo incluir um assembly (.dll), todos os membros que são implementados pelo assembly serão removidos, mas o assembly não será descarregado.

Esse cmdlet não desinstala o módulo nem o exclui do computador.
Ele afeta apenas a sessão atual do PowerShell.

## EXEMPLOS

### Exemplo 1: remover um módulo

```powershell
Remove-Module -Name "BitsTransfer"
```

Este comando remove o módulo BitsTransfer da sessão atual.

### Exemplo 2: remover todos os módulos

```powershell
Get-Module | Remove-Module
```

Este comando remove todos os módulos da sessão atual.

### Exemplo 3: remover módulos usando o pipeline

```powershell
"FileTransfer", "PSDiagnostics" | Remove-Module -Verbose
```

```Output
VERBOSE: Performing operation "Remove-Module" on Target "filetransfer (Path: 'C:\Windows\system32\WindowsPowerShell\v1.0\Modules\filetransfer\filetransfer.psd1')".
VERBOSE: Performing operation "Remove-Module" on Target "Microsoft.BackgroundIntelligentTransfer.Management (Path: 'C:\Windows\assembly\GAC_MSIL\Microsoft.BackgroundIntelligentTransfer.Management\1.0.0.0__31bf3856ad364e35\Microsoft.BackgroundIntelligentTransfe
r.Management.dll')".
VERBOSE: Performing operation "Remove-Module" on Target "psdiagnostics (Path: 'C:\Windows\system32\WindowsPowerShell\v1.0\Modules\psdiagnostics\psdiagnostics.psd1')".
VERBOSE: Removing imported function 'Start-Trace'.
VERBOSE: Removing imported function 'Stop-Trace'.
VERBOSE: Removing imported function 'Enable-WSManTrace'.
VERBOSE: Removing imported function 'Disable-WSManTrace'.
VERBOSE: Removing imported function 'Enable-PSWSManCombinedTrace'.
VERBOSE: Removing imported function 'Disable-PSWSManCombinedTrace'.
VERBOSE: Removing imported function 'Set-LogProperties'.
VERBOSE: Removing imported function 'Get-LogProperties'.
VERBOSE: Removing imported function 'Enable-PSTrace'.
VERBOSE: Removing imported function 'Disable-PSTrace'.
VERBOSE: Performing operation "Remove-Module" on Target "PSDiagnostics (Path: 'C:\Windows\system32\WindowsPowerShell\v1.0\Modules\psdiagnostics\PSDiagnostics.psm1')".
```

Este comando remove os módulos BitsTransfer e PSDiagnostics da sessão atual.

O comando usa um operador de pipeline (|) para enviar os nomes do módulo para **Remove-Module** .
Ele usa o parâmetro comum *Verbose* para obter informações detalhadas sobre os membros que serão removidos.

As mensagens *detalhadas* mostram os itens que são removidos.
As mensagens são diferentes porque o módulo BitsTransfer inclui um assembly que implementa seus cmdlets e um módulo aninhado com seu próprio assembly.
O módulo PSDiagnostics inclui um arquivo de script de módulo (.psm1) que exporta as funções.

### Exemplo 4: remover um módulo usando ModuleInfo

```powershell
$a = Get-Module BitsTransfer
Remove-Module -ModuleInfo $a
```

Esse comando usa o parâmetro *ModuleInfo* para remover o módulo BitsTransfer.

## PARAMETERS

### -Force

Indica que este cmdlet Remove módulos somente leitura.
Por padrão, **Remove-Module** remove somente módulos de leitura/gravação.

Os valores **ReadOnly** e **ReadWrite** são armazenados na propriedade **AccessMode** de um módulo.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FullyQualifiedName

Especifica os nomes totalmente qualificados dos módulos a serem removidos.

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: FullyQualifiedName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ModuleInfo

Especifica os objetos do módulo a ser removido.
Insira uma variável que contém um objeto de módulo ( **PSModuleInfo** ) ou um comando que obtém um objeto de módulo, como um comando Get-Module.
Você também pode redirecionar objetos do módulo para **Remove-Module** .

```yaml
Type: System.Management.Automation.PSModuleInfo[]
Parameter Sets: ModuleInfo
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Especifica os nomes dos módulos a serem removidos.
Caracteres curinga são permitidos.
Também é possível redirecionar cadeias de caracteres de nomes para **Remove-Module** .

```yaml
Type: System.String[]
Parameter Sets: name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### -Confirm

Solicita sua confirmação antes de executar o cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Mostra o que aconteceria se o cmdlet fosse executado.
O cmdlet não é executado.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. String, System. Management. Automation. PSModuleInfo

Você pode canalizar nomes de módulo e objetos de módulo para **Remove-Module** .

## SAÍDAS

### Nenhum

Este cmdlet não gera saída.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Get-Module](Get-Module.md)

[Import-Module](Import-Module.md)

[about_Modules](About/about_Modules.md)
