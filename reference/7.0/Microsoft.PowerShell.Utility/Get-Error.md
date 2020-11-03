---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-error?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Error
ms.openlocfilehash: 1a8e278e03d8aea4129c172d786d285d6b55b083
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193277"
---
# Get-Error

## SINOPSE

Obtém e exibe as mensagens de erro mais recentes da sessão atual.

## SYNTAX

### Mais recente (padrão)

```
Get-Error [[-Newest] <Int32>] [<CommonParameters>]
```

### Erro

```
Get-Error [-InputObject <PSObject>] [<CommonParameters>]
```

## DESCRIPTION

O `Get-Error` cmdlet obtém um objeto **PSExtendedError** que representa os detalhes do erro atual do último erro que ocorreu na sessão.

Você pode usar `Get-Error` para exibir um número especificado de erros que ocorreram na sessão atual usando o parâmetro **mais recente** .

O `Get-Error` cmdlet também recebe objetos de erro de uma coleção, como `$Error` , para exibir vários erros da sessão atual.

## EXEMPLOS

### Exemplo 1: obter os detalhes de erro mais recentes

Neste exemplo, `Get-Error` exibe os detalhes do erro mais recente que ocorreu na sessão atual.

```powershell
Get-Childitem -path /NoRealDirectory
Get-Error
```

```
Get-ChildItem: Cannot find path 'C:\NoRealDirectory' because it does not exist.

Exception             :
    ErrorRecord          :
        Exception             :
            Message : Cannot find path 'C:\NoRealDirectory' because it does not exist.
            HResult : -2146233087
        TargetObject          : C:\NoRealDirectory
        CategoryInfo          : ObjectNotFound: (C:\NoRealDirectory:String) [], ParentContainsErrorRecordException
        FullyQualifiedErrorId : PathNotFound
    ItemName             : C:\NoRealDirectory
    SessionStateCategory : Drive
    TargetSite           :
        Name          : GetChildItems
        DeclaringType : System.Management.Automation.SessionStateInternal
        MemberType    : Method
        Module        : System.Management.Automation.dll
    StackTrace           :
   at System.Management.Automation.SessionStateInternal.GetChildItems(String path, Boolean recurse, UInt32 depth,
CmdletProviderContext context)
   at System.Management.Automation.ChildItemCmdletProviderIntrinsics.Get(String path, Boolean recurse, UInt32
depth, CmdletProviderContext context)
   at Microsoft.PowerShell.Commands.GetChildItemCommand.ProcessRecord()
    Message              : Cannot find path 'C:\NoRealDirectory' because it does not exist.
    Source               : System.Management.Automation
    HResult              : -2146233087
TargetObject          : C:\NoRealDirectory
CategoryInfo          : ObjectNotFound: (C:\NoRealDirectory:String) [Get-ChildItem], ItemNotFoundException
FullyQualifiedErrorId : PathNotFound,Microsoft.PowerShell.Commands.GetChildItemCommand
InvocationInfo        :
    MyCommand        : Get-ChildItem
    ScriptLineNumber : 1
    OffsetInLine     : 1
    HistoryId        : 57
    Line             : Get-Childitem -path c:\NoRealDirectory
    PositionMessage  : At line:1 char:1
                       + Get-Childitem -path c:\NoRealDirectory
                       + ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    InvocationName   : Get-Childitem
    CommandOrigin    : Internal
ScriptStackTrace      : at <ScriptBlock>, <No file>: line 1
PipelineIterationInfo :
```

### Exemplo 2: obter o número especificado de mensagens de erro que ocorreram na sessão atual

Este exemplo mostra como usar `Get-Error` com o parâmetro **mais recente** . Neste exemplo, o **mais recente** retorna os detalhes dos três erros mais recentes que ocorreram nesta sessão.

```powershell
Get-Error -Newest 3
```

### Exemplo 3: Enviar uma coleção de erros para receber mensagens detalhadas

A `$Error` variável automática contém uma matriz de objetos de erro na sessão atual. A matriz de objetos pode ser canalizada para `Get-Error` receber mensagens de erro detalhadas.

Neste exemplo, `$Error` é canalizado para o `Get-Error` cmdlet. o resultado é uma lista de mensagens de erro detalhadas, semelhante ao resultado do exemplo 1.

```powershell
$Error | Get-Error
```

## PARAMETERS

### -Mais recente

Especifica o número de erros a serem exibidos que ocorreram na sessão atual.

```yaml
Type: System.Int32
Parameter Sets: Newest
Aliases: Last

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Esse parâmetro é usado para entrada de pipeline.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: Error
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### PSObject

Dá suporte à entrada de qualquer **PSObject** , mas os resultados variam, a menos que um objeto **ErrorRecord** ou de **exceção** seja fornecido.

## SAÍDAS

### System. Management. Automation. ErrorRecord # PSExtendedError

Saída em um objeto **PSExtendedError** .

## OBSERVAÇÕES

`Get-Error` aceita a entrada do pipeline. Por exemplo, `$Error | Get-Error`.

## LINKS RELACIONADOS

[about_Try_Catch_Finally](../Microsoft.PowerShell.Core/About/about_Try_Catch_Finally.md)
