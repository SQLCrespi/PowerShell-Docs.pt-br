---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/out-default?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Default
ms.openlocfilehash: 3d5fb12371e9ad329323b9d95d7151a43eb5924a
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192980"
---
# Out-Default

## SINOPSE
Envia a saída para o formatador padrão e para o cmdlet de saída padrão.

## SYNTAX

```
Out-Default [-Transcript] [-InputObject <PSObject>] [<CommonParameters>]
```

## DESCRIPTION

O PowerShell é adicionado automaticamente `Out-Default` ao final de cada pipeline. `Out-Default` decide como formatar e gerar a saída do fluxo de objeto. Se o fluxo do objeto for um fluxo de cadeias de caracteres, o `Out-Default` canalizará diretamente para `Out-Host` o qual chamará as APIs apropriadas fornecidas pelo host. Se o fluxo de objeto não contiver cadeias de caracteres, `Out-Default` o inspecionará o objeto para determinar o que fazer.
Em primeiro lugar, ele examina o tipo de objeto e determina se há uma _exibição_ registrada para esse tipo de objeto.

O PowerShell define o esquema XML e um mecanismo (o `Update-FormatData` cmdlet) em que qualquer pessoa pode registrar exibições para um tipo de objeto. Você pode especificar exibições **amplas** , de **lista** , de **tabela** ou **personalizadas** para qualquer tipo de objeto. As exibições especificam quais propriedades exibir e como elas devem ser exibidas. Se uma exibição for registrada, ela definirá qual formatador usar. Portanto, se a exibição registrada for uma exibição de **tabela** , `Out-Default` o transmitirá os objetos para `Format-Table | Out-Host` . `Format-Table` transforma os objetos em um fluxo de registros de formatação (controlados pelos dados na definição da exibição) e `Out-Host` transforma os registros de formatação em chamadas na interface do host.

## EXEMPLOS

### Exemplo 1

Embora esse cmdlet não se destinar a ser executado diretamente pelo usuário final, ele pode ser.

```powershell
Get-Process | Select-Object -First 5 | Out-Default
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     12     2.56       5.20       0.00    7376   0 aesm_service
     48    34.32      18.10      26.64    9320  13 AlertusDesktopAlert
     24    13.97      12.74       0.77   12656  13 ApplicationFrameHost
      8     1.79       4.41       0.00    8180   0 AppVShNotify
      9     1.99       5.07       0.19   19320  13 AppVShNotify
```

## PARAMETERS

### -InputObject

Aceita entradas para o cmdlet.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Transcrição

Determina se a saída deve ser enviada aos serviços de transcrição do PowerShell.

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

## SAÍDAS

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Format-Custom](../Microsoft.PowerShell.Utility/Format-Custom.md)

[Format-List](../Microsoft.PowerShell.Utility/Format-List.md)

[Format-Table](../Microsoft.PowerShell.Utility/Format-Table.md)

[Format-Wide](../Microsoft.PowerShell.Utility/Format-Wide.md)

[about_Format.ps1xml](About/about_Format.ps1xml.md)

[Como a formatação e a saída do PowerShell realmente funcionam](https://devblogs.microsoft.com/powershell/how-powershell-formatting-and-outputting-really-works/)
