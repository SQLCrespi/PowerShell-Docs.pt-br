---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/remove-cimsession?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-CimSession
ms.openlocfilehash: eae279aa9c5d3a99a9a522254c5b792970f74297
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194784"
---
# Remove-CimSession

## SINOPSE
Remove uma ou mais sessões CIM.

## SYNTAX

### CimSessionSet (padrão)

```
Remove-CimSession [-CimSession] <CimSession[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ComputerNameSet

```
Remove-CimSession [-ComputerName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SessionIdset

```
Remove-CimSession [-Id] <UInt32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InstanceIdset

```
Remove-CimSession -InstanceId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Nome do

```
Remove-CimSession -Name <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Remove-CimSession` cmdlet Remove um ou mais objetos de sessão CIM da sessão do PowerShell local.

## EXEMPLOS

### Exemplo 1: remover todas as sessões CIM

Este exemplo recupera todas as sessões CIM disponíveis no computador local usando o cmdlet [Get-CimSession](Get-CimSession.md) e, em seguida, as remove usando o `Remove-CimSession` .

```powershell
Get-CimSession | Remove-CimSession
```

### Exemplo 2: remover uma sessão CIM específica

Este exemplo remove a sessão CIM que tem um valor de **ID** de 5.

```powershell
Remove-CimSession -Id 5
```

### Exemplo 3: mostrar a lista de sessões CIM a serem removidas usando o parâmetro WhatIf

Este exemplo usa o parâmetro comum **WhatIf** para especificar que a remoção não deve ser feita, mas apenas saída o que aconteceria se fosse feito.

```powershell
Remove-CimSession -Name a* -WhatIf
```

## PARAMETERS

### -CimSession

Especifica os objetos de sessão das sessões CIM a serem fechadas.

Insira uma variável que contenha a sessão CIM ou um comando que cria ou obtém a sessão CIM, como os [`New-CimSession`](New-CimSession.md) [`Get-CimSession`](Get-CimSession.md) cmdlets ou.
Para obter mais informações, consulte [about_CimSessions](../Microsoft.PowerShell.Core/About/about_CimSession.md).

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ComputerName

Especifica uma matriz de nomes de computadores. Remove as sessões que se conectam aos computadores especificados. Você pode especificar um nome de domínio totalmente qualificado (FQDN) ou um nome NetBIOS.

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet
Aliases: CN, ServerName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Id

Especifica a ID da sessão CIM a ser removida. Especifique uma ou mais IDs separadas por vírgulas ou use o operador de intervalo ( `..` ) para especificar um intervalo de IDs. Uma **ID** é um inteiro que identifica exclusivamente a sessão CIM na sessão atual do PowerShell.

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

Especifica a ID da instância da sessão CIM a ser removida. **InstanceId** é um GUID (identificador global exclusivo) que identifica exclusivamente uma sessão CIM. A **InstanceId** é exclusiva, mesmo quando você tem várias sessões em execução no PowerShell.

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

Especifica o nome amigável da sessão CIM a ser removida. Você pode usar caracteres curinga com esse parâmetro.

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

Mostra o que aconteceria se o cmdlet fosse executado. O cmdlet não é executado.

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

### Nenhum

Esse cmdlet não aceita nenhum objeto de entrada.

## SAÍDAS

### System.Object

Esse cmdlet retorna um objeto que contém informações de sessão CIM.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Get-CimSession](Get-CimSession.md)

[New-CimSession](New-CimSession.md)

[about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md)

