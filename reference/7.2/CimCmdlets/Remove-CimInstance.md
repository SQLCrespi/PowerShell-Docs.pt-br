---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 05/15/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/remove-ciminstance?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-CimInstance
ms.openlocfilehash: 5a23aaa59eb10ff35ecefb7365d3294cdb06f781
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596167"
---
# Remove-CimInstance

## SINOPSE
Remove uma instância CIM de um computador.

## SYNTAX

### CimInstanceComputerSet (padrão)

```
Remove-CimInstance [-ResourceUri <Uri>] [-ComputerName <String[]>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CimInstanceSessionSet

```
Remove-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### QuerySessionSet

```
Remove-CimInstance -CimSession <CimSession[]> [[-Namespace] <String>]
 [-OperationTimeoutSec <UInt32>] [-Query] <String> [-QueryDialect <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### QueryComputerSet

```
Remove-CimInstance [-ComputerName <String[]>] [[-Namespace] <String>]
 [-OperationTimeoutSec <UInt32>] [-Query] <String> [-QueryDialect <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

Esse cmdlet Remove uma instância CIM de um servidor CIM. Você pode especificar a instância CIM a ser removida usando um objeto de instância CIM recuperado pelo `Get-CimInstance` cmdlet ou especificando uma consulta.

Se o parâmetro **InputObject** não for especificado, o cmdlet funcionará de uma das seguintes maneiras:

- Se nem o parâmetro **ComputerName** nem o parâmetro **CimSession** for especificado, esse cmdlet funcionará no Instrumentação de gerenciamento do Windows local (WMI) usando uma sessão Component Object Model (com).
- Se o parâmetro **ComputerName** ou o parâmetro **CimSession** for especificado, esse cmdlet funcionará no servidor CIM especificado pelo parâmetro **ComputerName** ou pelo parâmetro **CimSession** .

## EXEMPLOS

### Exemplo 1: remover a instância CIM

Este exemplo usa o parâmetro de **consulta** para remover as instâncias de CIM da classe denominada **Win32_Environment** que começam com a cadeia de caracteres **testvar** .

```powershell
Remove-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"'
```

### Exemplo 2: remover a instância CIM usando o objeto de instância CIM

Este exemplo recupera os objetos de instância CIM filtrados pelo parâmetro de **consulta** e os armazena em `$var` uma variável chamada usando o `Get-CimInstance` cmdlet. O conteúdo da variável é passado para o `Remove-CimInstance` cmdlet, que remove as instâncias de CIM.

```powershell
notepad.exe
$var = Get-CimInstance -Query 'Select * from Win32_Process where name LIKE "notepad%"'
Remove-CimInstance -InputObject $var
```

## PARAMETERS

### -CimSession

Executa o comando usando a sessão CIM especificada. Insira uma variável que contenha a sessão CIM ou um comando que cria ou obtém a sessão CIM, como os `New-CimSession` `Get-CimSession` cmdlets ou. Para obter mais informações, consulte [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimInstanceSessionSet, QuerySessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName

Especifica o nome do computador no qual você deseja executar a operação CIM. Você pode especificar um nome de domínio totalmente qualificado (FQDN) ou um nome NetBIOS.

Se você especificar esse parâmetro, o cmdlet criará uma sessão temporária para o computador especificado usando o protocolo WsMan.

Se você não especificar esse parâmetro, o cmdlet executará a operação no computador local usando Component Object Model (COM).

Se várias operações estiverem sendo executadas no mesmo computador, a conexão usando uma sessão CIM fornecerá um melhor desempenho.

```yaml
Type: System.String[]
Parameter Sets: CimInstanceComputerSet, QueryComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Especifica um objeto de instância CIM a ser removido do servidor CIM. O objeto passado para o cmdlet não é alterado, somente a instância no servidor CIM é removida.

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet
Aliases: CimInstance

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Namespace

Especifica o namespace para a operação CIM. O namespace padrão é **root/cimv2**. Você pode usar o preenchimento com Tab para navegar na lista de namespaces, pois o PowerShell Obtém uma lista de namespaces do servidor WMI local para fornecer a lista de namespaces.

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OperationTimeoutSec

Especifica a quantidade de tempo que o cmdlet aguarda uma resposta do computador. Por padrão, o valor desse parâmetro é 0, o que significa que o cmdlet usa o valor de tempo limite padrão para o servidor.

Se o parâmetro **OperationTimeoutSec** for definido como um valor menor que o tempo limite de repetição de conexão robusto de 3 minutos, as falhas de rede que durar mais do que o valor do parâmetro **OperationTimeoutSec** não serão recuperáveis, pois a operação no servidor expirará antes que o cliente possa se reconectar.

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: OT

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Query

Especifica uma consulta a ser executada no servidor CIM. Você pode especificar o dialeto da consulta usando o parâmetro **QueryDialect** .

Se o valor especificado contiver aspas duplas ( `"` ), aspas simples ( `'` ) ou barra invertida ( `\` ), você deverá escapar desses caracteres prefixando-os com o caractere de barra invertida ( `\` ). Se o valor especificado usar o operador LIKE WQL, você deverá escapar os caracteres a seguir, colocando-os entre colchetes ( `[]` ): porcentagem ( `%` ), sublinhado ( `_` ) ou colchete de abertura ( `[` ).

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -QueryDialect

Especifica a linguagem de consulta usada para o parâmetro de consulta. Os valores aceitáveis para esse parâmetro são: **WQL** ou **CQL**. O valor padrão é **WQL**.

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: WQL
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceURI

Especifica o URI (Uniform Resource Identifier) do recurso da classe ou instância de recurso. O URI é utilizado para identificar um tipo específico de recurso, como discos ou processos em um computador.

Um URI consiste em um prefixo e um caminho para um recurso. Por exemplo:

- `http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`
- `http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

Por padrão, se você não especificar esse parâmetro, o URI de recurso padrão do DMTF `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` será usado e o nome da classe será anexado a ele.

O ResourceURI só pode ser usado com sessões CIM criadas usando o protocolo WSMan ou ao especificar o parâmetro ComputerName, que cria uma sessão CIM usando WSMan. Se você especificar esse parâmetro sem especificar o parâmetro ComputerName ou se especificar uma sessão CIM criada usando o protocolo DCOM, receberá um erro, pois o protocolo DCOM não oferece suporte ao parâmetro ResourceURI.

Se o parâmetro **ResourceURI** e o parâmetro **Filter** forem especificados, o parâmetro **Filter** será ignorado.

```yaml
Type: System.Uri
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet
Aliases:

Required: False
Position: Named
Default value: None
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

### Nenhum

Esse cmdlet não produz saídas.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[New-CimInstance](New-CimInstance.md)

[Get-CimInstance](get-ciminstance.md)

[Set-CimInstance](Set-CimInstance.md)

