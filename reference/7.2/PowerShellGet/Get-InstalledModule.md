---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 02/27/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/get-installedmodule?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-InstalledModule
ms.openlocfilehash: 33621a89f846ca277c21aaf0ad8cd788b428da33
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595989"
---
# Get-InstalledModule

## SINOPSE
Obtém uma lista de módulos no computador que foram instalados pelo PowerShellGet.

## SYNTAX

```
Get-InstalledModule [[-Name] <String[]>] [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-AllowPrerelease] [<CommonParameters>]
```

## DESCRIPTION

O `Get-InstalledModule` cmdlet obtém os módulos do PowerShell que estão instalados em um computador usando o PowerShellGet. Para ver todos os módulos instalados no sistema, use o `Get-Module -ListAvailable` comando.

## EXEMPLOS

### Exemplo 1: obter todos os módulos instalados

```powershell
Get-InstalledModule
```

```Output
Version    Name                                Type       Repository     Description
-------    ----                                ----       ----------     -----------
2.0.0      PSGTEST-UploadMultipleVersionOfP... Module     GalleryINT     Module for DAC functionality
1.3.5      AzureAutomationDebug                Module     PSGallery      Module for debugging Azure Automation runbooks, emulating AA native cmdlets
1.0.1      AzureRM.Automation                  Module     PSGallery      Microsoft Azure PowerShell - Automation service cmdlets for Azure Resource Manager
```

Este comando obtém todos os módulos instalados.

### Exemplo 2: obter versões específicas de um módulo

```powershell
Get-InstalledModule -Name "AzureRM.Automation" -MinimumVersion 1.0 -MaximumVersion 2.0
```

```Output
Version    Name                                Type       Repository     Description
-------    ----                                ----       ----------     -----------
1.0.1      AzureRM.Automation                  Module     PSGallery      Microsoft Azure PowerShell - Automation service cmdlets for Azure Resource Manager
```

Este comando obtém as versões do módulo AzureRM. Automation da versão 1,0 até a versão 2,0.

## PARAMETERS

### -AllowPrerelease

Inclui nos módulos de resultados marcados como um pré-lançamento.

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

### -Próprias versões

Indica que você deseja obter todas as versões disponíveis de um módulo.
Você não pode usar o parâmetro de todas as **versões** com os parâmetros **MinimumVersion**, **MaximumVersion** ou **RequiredVersion** .

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

### -MaximumVersion

Especifica a versão máxima ou mais recente de um módulo a ser obtida. Os parâmetros **MaximumVersion** e **RequiredVersion** são mutuamente exclusivos; Você não pode usar ambos os parâmetros no mesmo comando.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MinimumVersion

Especifica a versão mínima de um único módulo a ser obtido. Os parâmetros **MinimumVersion** e **RequiredVersion** são mutuamente exclusivos; Você não pode usar ambos os parâmetros no mesmo comando.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Especifica uma matriz de nomes de módulos a serem obtidos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RequiredVersion

Especifica a versão exata de um módulo a ser obtido.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### System.String[]

### System.String

## SAÍDAS

### System. Management. Automation. PSCustomObject

## OBSERVAÇÕES

## LINKS RELACIONADOS

