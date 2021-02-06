---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-psdrive?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSDrive
ms.openlocfilehash: d20a348f3f5ba193eb85e0f9d0e2cc11ad083b47
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597631"
---
# Remove-PSDrive

## SINOPSE
Exclui unidades temporárias do PowerShell e desconecta unidades de rede mapeadas.

## SYNTAX

### Nome (padrão)

```
Remove-PSDrive [-Name] <String[]> [-PSProvider <String[]>] [-Scope <String>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Valor literal

```
Remove-PSDrive [-LiteralName] <String[]> [-PSProvider <String[]>] [-Scope <String>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Remove-PSDrive` cmdlet exclui unidades temporárias do PowerShell que foram criadas usando o `New-PSDrive` cmdlet.

A partir do Windows PowerShell 3,0, o `Remove-PSDrive` também desconecta unidades de rede mapeadas, incluindo, mas não se limitando a, unidades criadas usando o `Persist` parâmetro de `New-PSDrive` .

`Remove-PSDrive` Não é possível excluir unidades físicas ou lógicas do Windows.

A partir do Windows PowerShell 3,0, quando uma unidade externa é conectada ao computador, o PowerShell adiciona automaticamente um PSDrive ao sistema de arquivos que representa a nova unidade.
Você não precisa reiniciar o PowerShell.
Da mesma forma, quando uma unidade externa é desconectada do computador, o PowerShell exclui automaticamente o PSDrive que representa a unidade removida.

## EXEMPLOS

### Exemplo 1: remover uma unidade do sistema de arquivos

Este comando remove uma unidade de sistema de arquivos temporária chamada "smp".

```powershell
Remove-PSDrive -Name smp
```

### Exemplo 2: remover unidades de rede mapeadas

Esse comando usa `Remove-PSDrive` para desconectar as unidades de rede de X: e S: mapeadas.

```powershell
Get-PSDrive X, S | Remove-PSDrive
```

## PARAMETERS

### -Force

Remove a unidade atual do PowerShell.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -LiteralName

Especifica o nome da unidade.

O valor de **LiteralName** é usado exatamente como digitado.
Nenhum caractere é interpretado como caractere curinga.
Se o nome inclui caracteres de escape, coloque-o entre aspas simples (').
As aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

```yaml
Type: System.String[]
Parameter Sets: LiteralName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Especifica os nomes das unidades a remover.
Não digite dois-pontos (:) após o nome da unidade.

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -PSProvider

Especifica uma matriz de objetos **PSProvider** .
Esse cmdlet Remove e desconecta todas as unidades associadas ao provedor do PowerShell especificado.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Escopo

Especifica um escopo para a unidade.
Os valores aceitáveis para esse parâmetro são: global, local e script, ou um número relativo ao escopo atual. O número de escopos é 0 com o número de escopos. O número de escopo atual é 0 e seu pai é 1.
Para obter mais informações, consulte [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
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

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### System.Management.Automation.PSDriveInfo

É possível canalizar um objeto de unidade, como um do `Get-PSDrive` cmdlet, para o `Remove-PSDrive` cmdlet.

## SAÍDAS

### Nenhum

Este cmdlet não retorna nenhuma saída.

## OBSERVAÇÕES

- O `Remove-PSDrive` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor do PowerShell. Para listar os provedores em sua sessão, use o `Get-PSProvider` cmdlet. Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## LINKS RELACIONADOS

[Get-PSDrive](Get-PSDrive.md)

[New-PSDrive](New-PSDrive.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

