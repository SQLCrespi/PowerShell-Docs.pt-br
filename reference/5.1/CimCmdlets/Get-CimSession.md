---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-cimsession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimSession
ms.openlocfilehash: 83425948e5fc4d7170a2e3a6e883f71df386fdb5
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193424"
---
# Get-CimSession

## SINOPSE
Obtém os objetos de sessão CIM da sessão atual.

## SYNTAX

### ComputerNameSet (padrão)

```
Get-CimSession [[-ComputerName] <String[]>] [<CommonParameters>]
```

### SessionIdset

```
Get-CimSession [-Id] <UInt32[]> [<CommonParameters>]
```

### InstanceIdset

```
Get-CimSession -InstanceId <Guid[]> [<CommonParameters>]
```

### Nome do

```
Get-CimSession -Name <String[]> [<CommonParameters>]
```

## DESCRIPTION

Por padrão, o cmdlet obtém todas as sessões CIM criadas na sessão atual do PowerShell. Você pode usar os parâmetros de `Get-CimSession` para obter as sessões que são para computadores específicos ou pode identificar sessões por seus nomes ou outros identificadores. `Get-CimSession` Não Obtém as sessões CIM que foram criadas em outras sessões do PowerShell ou que foram criadas em outros computadores.

Para obter mais informações sobre sessões CIM, consulte [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).

## EXEMPLOS

### Exemplo 1: obter sessões CIM da sessão atual do PowerShell

Este exemplo cria sessões CIM usando [New-CimSession](New-CimSession.md)e, em seguida, obtém as sessões CIM usando `Get-CimSession` .

```powershell
New-CimSession -ComputerName Server01,Server02
Get-CimSession
```

```Output
Id           : 1
Name         : CimSession1
InstanceId   : d1413bc3-162a-4cb8-9aec-4d2c61253d59
ComputerName : Server01
Protocol     : WSMAN

Id           : 2
Name         : CimSession2
InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710
ComputerName : Server02
Protocol     : WSMAN
```

### Exemplo 2: obter as sessões CIM para um computador específico

Este exemplo obtém as sessões CIM que estão conectadas ao computador chamado **Server02** .

```powershell
Get-CimSession -ComputerName Server02
```

```Output
Id           : 2
Name         : CimSession2
InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710
ComputerName : Server02
Protocol     : WSMAN
```

### Exemplo 3: obter uma lista de sessões CIM e formatar a lista

Este exemplo obtém todas as sessões CIM na sessão atual do PowerShell e exibe uma tabela que contém apenas as propriedades **ComputerName** e **InstanceId** .

```powershell
Get-CimSession | Format-Table -Property ComputerName,InstanceId
```

```Output
ComputerName InstanceId
------------ ----------
Server01     d1413bc3-162a-4cb8-9aec-4d2c61253d59
Server02     c0095981-52c5-4e7f-a5bb-c4c680541710
```

### Exemplo 4: obter todas as sessões CIM que têm nomes específicos

Este exemplo obtém todas as sessões CIM que têm nomes que começam com o **serv** .

```powershell
Get-CimSession -ComputerName Serv*
```

```Output
Id           : 1
Name         : CimSession1
InstanceId   : d1413bc-162a-4cb8-9aec-4d2c61253d59
ComputerName : Server01
Protocol     : WSMAN

Id           : 2
Name         : CimSession2
InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710
ComputerName : Server02
Protocol     : WSMAN
```

### Exemplo 5: obter uma sessão CIM específica

Este exemplo obtém a sessão CIM que tem uma **ID** de 2.

```powershell
Get-CimSession -ID 2
```

```Output
Id           : 2
Name         : CimSession2
InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710
ComputerName : Server02
Protocol     : WSMAN
```

## PARAMETERS

### -ComputerName

Especifica o nome do computador para o qual as sessões CIM serão conectadas. Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet
Aliases: CN, ServerName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Id

Especifica o identificador da sessão CIM a ser obtido. Para várias IDs, use vírgulas para separar as IDs ou use o operador de intervalo ( `..` ) para especificar um intervalo de IDs. Uma **ID** é um inteiro que identifica exclusivamente a sessão CIM dentro da sessão atual do PowerShell.

Para obter mais informações sobre o operador Range, consulte [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md).

```yaml
Type: System.UInt32[]
Parameter Sets: SessionIdSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId

Especifica as IDs de instância da sessão CIM a ser obtida.

**InstanceId** é um GUID (identificador globalmente exclusivo) que identifica exclusivamente uma sessão CIM. A **InstanceId** é exclusiva, mesmo quando você tem várias sessões em execução no PowerShell.

A **InstanceId** é armazenada na propriedade **InstanceId** do objeto que representa uma sessão CIM.

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Obtém uma ou mais sessões CIM que contêm os nomes amigáveis especificados. Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: NameSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### CommonParameters
Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

## SAÍDAS

### Microsoft.Management.Infrastructure.CimSession

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Format-Table](../microsoft.powershell.utility/format-table.md)

[New-CimSession](New-CimSession.md)

[Remove-CimSession](remove-cimsession.md)

[about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md)
