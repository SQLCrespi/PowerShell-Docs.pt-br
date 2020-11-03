---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-pssnapin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSSnapin
ms.openlocfilehash: e74aff3e52c61f41a54664efbab9c0f195b0d409
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193511"
---
# Remove-PSSnapin

## SINOPSE
Remove os snap-ins do Windows PowerShell da sessão atual.

## SYNTAX

```
Remove-PSSnapin [-Name] <String[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Remove-PsSnapin** remove um snap-in do Windows PowerShell da sessão atual.
Você pode usá-lo para remover snap-ins que você adicionou ao Windows PowerShell. você não pode usar este cmdlet para remover os snap-ins instalados com o Windows PowerShell.

Depois de remover um snap-in da sessão atual, o snap-in ainda é carregado, mas os cmdlets e provedores no snap-in não estão mais disponíveis na sessão.

## EXEMPLOS

### Exemplo 1: remover um snap-in

```
PS C:\> remove-pssnapin -Name Microsoft.Exchange
```

Esse comando Remove o snap-in **Microsoft. Exchange** da sessão atual.
Quando o comando for concluído, os cmdlets e provedores suportados pelo snap-in não estarão disponíveis na sessão.

### Exemplo 2: remover snap-ins usando nomes com o pipeline

```
PS C:\> Get-PSSnapIn smp* | Remove-PSSnapIn
```

Esse comando remove os snap-ins do Windows PowerShell que têm nomes que iniciam com o SMP da sessão atual.

O comando usa o cmdlet **Get-PSSnapin** para obter objetos que representam os snap-ins. O operador de pipeline (|) envia os resultados para o cmdlet **Remove-PsSnapin** , que os remove da sessão.
Os provedores e cmdlets que esse snap-in suporta não estão mais disponíveis na sessão.

Quando você canaliza objetos para **Remove-PsSnapin** , os nomes dos objetos são associados ao parâmetro *Name* , que aceita objetos do pipeline que têm uma propriedade **Name** .

### Exemplo 3: remover snap-ins usando nomes

```
PS C:\> Remove-PSSnapin -Name *event*
```

Esse comando Remove todos os snap-ins do Windows PowerShell que têm nomes que incluem o evento.

## PARAMETERS

### -Name
Especifica os nomes dos snap-ins do Windows PowerShell a remover da sessão atual.
Caracteres curinga (*) são permitidos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Retorna um objeto que representa o snap-in.
Por padrão, este cmdlet não gera saída.

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

### System. Management. Automation. PSSnapInInfo
É possível canalizar um objeto de snap-in para este cmdlet.

## SAÍDAS

### Nenhum, System. Management. Automation. PSSnapInInfo
Esse cmdlet gera um objeto **System. Management. Automation. PSSnapInInfo** que representa o snap-in, se você especificar o parâmetro *PassThru* .
Por padrão, **Remove-PsSnapin** não gera nenhuma saída.

## OBSERVAÇÕES

* **Remove-PsSnapin** não verifica a versão do Windows PowerShell antes de remover um snap-in da sessão. Se um snap-in não pode ser removido, um aviso é exibido e o comando falha.
* **Remove-PsSnapin** afeta apenas a sessão atual. Se tiver adicionado um comando Add-PSSnapin para seu perfil do Windows PowerShell, você deve excluir o comando para remover o snap-in de futuras sessões. Para obter instruções, digite `Get-Help about_Profiles` .

## LINKS RELACIONADOS

[Add-PSSnapin](Add-PSSnapin.md)

[Get-PSSnapin](Get-PSSnapin.md)
