---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/02/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/uninstall-module?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Module
ms.openlocfilehash: 9ba7e786acad0ffb2fffd8459561516ea8541109
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194447"
---
# Uninstall-Module

## SINOPSE
Desinstala um módulo.

## SYNTAX

### NameParameterSet (padrão)

```
Uninstall-Module [-Name] <String[]> [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-AllowPrerelease] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject

```
Uninstall-Module [-InputObject] <PSObject[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Uninstall-Module` cmdlet desinstala um módulo especificado do computador local. Você não poderá desinstalar um módulo se ele tiver outros módulos como dependências.

## EXEMPLOS

### Exemplo 1: desinstalar um módulo

Este exemplo desinstala um módulo.

```powershell
Uninstall-Module -Name SpeculationControl
```

`Uninstall-Module` usa o parâmetro **Name** para especificar o módulo a ser desinstalado do computador local.

### Exemplo 2: usar o pipeline para desinstalar um módulo

Neste exemplo, o pipeline é usado para desinstalar um módulo.

```powershell
Get-InstalledModule -Name SpeculationControl | Uninstall-Module
```

`Get-InstalledModule` usa o parâmetro **Name** para especificar o módulo. O objeto é enviado ao pipeline para `Uninstall-Module` e é desinstalado.

## PARAMETERS

### -AllowPrerelease

Permite desinstalar um módulo marcado como um pré-lançamento.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Próprias versões

Especifica que você deseja incluir todas as versões disponíveis de um módulo. Você não pode usar o parâmetro de todas as **versões** com os parâmetros **MinimumVersion** , **MaximumVersion** ou **RequiredVersion** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Solicita a confirmação antes de executar o `Uninstall-Module` .

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

### -Force

Forças `Uninstall-Module` a serem executadas sem solicitar a confirmação do usuário.

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

### -InputObject

Aceita um objeto **PSRepositoryItemInfo** . Por exemplo, saída `Get-InstalledModule` para uma variável e use essa variável como o argumento **InputObject** .

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -MaximumVersion

Especifica a versão máxima ou mais recente do módulo a ser desinstalada. Os parâmetros **MaximumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MinimumVersion

Especifica a versão mínima do módulo a ser desinstalada. Os parâmetros **MinimumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Especifica uma matriz de nomes de módulo a desinstalar.

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RequiredVersion

Especifica o número de versão exato do módulo a ser desinstalado.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf

Mostra o que aconteceria se `Uninstall-Module` for executado. O cmdlet não é executado.

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

### System.String[]

### System. Management. Automation. PSObject []

### System.String

## SAÍDAS

### System.Object

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Find-Module](Find-Module.md)

[Get-InstalledModule](Get-InstalledModule.md)

[Publish-Module](Publish-Module.md)

[Save-Module](Save-Module.md)

[Update-Module](Update-Module.md)
