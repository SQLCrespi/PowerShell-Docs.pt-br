---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/set-ciminstance?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-CimInstance
ms.openlocfilehash: af2346ed0dddb8de660cb2431ccfcac846644679
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93194916"
---
# Set-CimInstance

## SINOPSE
Modifica uma instância CIM em um servidor CIM chamando o método ModifyInstance da classe CIM.

## SYNTAX

### CimInstanceComputerSet (padrão)

```
Set-CimInstance [-ComputerName <String[]>] [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [-Property <IDictionary>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### CimInstanceSessionSet

```
Set-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [-Property <IDictionary>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### QuerySessionSet

```
Set-CimInstance -CimSession <CimSession[]> [-Namespace <String>] [-OperationTimeoutSec <UInt32>]
 [-Query] <String> [-QueryDialect <String>] -Property <IDictionary> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### QueryComputerSet

```
Set-CimInstance [-ComputerName <String[]>] [-Namespace <String>] [-OperationTimeoutSec <UInt32>]
 [-Query] <String> [-QueryDialect <String>] -Property <IDictionary> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

Esse cmdlet modifica uma instância CIM em um servidor CIM.

Se o parâmetro **InputObject** não for especificado, o cmdlet funcionará de uma das seguintes maneiras:

- Se nem o parâmetro **ComputerName** nem o parâmetro **CimSession** for especificado, esse cmdlet funcionará no Instrumentação de gerenciamento do Windows local (WMI) usando uma sessão Component Object Model (com).
- Se o parâmetro **ComputerName** ou o parâmetro **CimSession** for especificado, esse cmdlet funcionará no servidor CIM especificado pelo parâmetro **ComputerName** ou pelo parâmetro **CimSession** .

Se o parâmetro **InputObject** for especificado, o cmdlet funcionará de uma das seguintes maneiras:

- Se nem o parâmetro **ComputerName** nem o parâmetro **CimSession** for especificado, esse cmdlet usará a sessão CIM ou o nome do computador do objeto de entrada.
- Se o parâmetro **ComputerName** ou o parâmetro **CimSession** for especificado, esse cmdlet usa o valor do parâmetro **CimSession** ou o valor do parâmetro **ComputerName** . Isso não é muito comum.

## EXEMPLOS

### Exemplo 1: definir a instância de CIM

Este exemplo define o valor da propriedade **VariableValue** como **ABCD** usando o parâmetro de **consulta** . Você pode modificar instâncias que correspondem a uma consulta WQL (linguagem de consulta Instrumentação de Gerenciamento do Windows).

```powershell
Set-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' -Property @{VariableValue="abcd"}
```

### Exemplo 2: definir a propriedade de instância CIM usando pipeline

Este exemplo recupera o objeto de instância CIM filtrado pelo parâmetro de **consulta** usando o `Get-CimInstance` cmdlet. O `Set-CimInstance` cmdlet modifica o valor da propriedade **VariableValue** como **ABCD** .

```powershell
Get-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' |
  Set-CimInstance -Property @{VariableValue="abcd"}
```

### Exemplo 3: definir a propriedade de instância CIM usando o objeto de entrada

```powershell
$x = Get-CimInstance -Query 'Select * from Win32_Environment where Name="testvar"'
Set-CimInstance -InputObject $x -Property @{VariableValue="somevalue"} -PassThru
```

Este exemplo recupera os objetos de instância CIM filtrados pelo parâmetro de consulta em para uma variável `$x` usando `Get-CimInstance` e, em seguida, passa o conteúdo da variável para o `Set-CimInstance` cmdlet. `Set-CimInstance` em seguida, modifica a propriedade **VariableValue** para **someValue** . Como o parâmetro **PassThru** é usado, este exemplo retorna um objeto de instância CIM modificado.

### Exemplo 4: definir a propriedade de instância CIM

Este exemplo recupera o objeto de instância CIM que é especificado no parâmetro de **consulta** em uma variável `$x` usando o `Get-CimInstance` cmdlet e altera o valor da propriedade **VariableValue** do objeto a ser alterado. O objeto de instância CIM é salvo usando o `Set-CimInstance` cmdlet.
Como o parâmetro **PassThru** é usado, este exemplo retorna um objeto de instância CIM modificado.

```powershell
$x = Get-CimInstance -Query 'Select * from Win32_Environment where name="testvar"'
$x.VariableValue = "Change"
Set-CimInstance -CimInstance $x -PassThru
```

### Exemplo 5: mostrar a lista de instâncias de CIM a serem modificadas usando WhatIf

Este exemplo usa o parâmetro comum **WhatIf** para especificar que a modificação não deve ser feita, mas apenas saída o que aconteceria se fosse feito.

```powershell
Set-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' -Property @{VariableValue="abcd"} -WhatIf
```

### Exemplo 6: definir a instância de CIM após a confirmação do usuário

Este exemplo usa o parâmetro comum **Confirm** para especificar que a modificação deve ser feita somente após a confirmação do usuário.

```powershell
Set-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' -Property @{VariableValue="abcd"} -Confirm
```

### Exemplo 7: definir a instância de CIM criada

Este exemplo cria uma instância CIM com as propriedades especificadas usando o `New-CimInstance` cmdlet e recupera seu conteúdo em uma variável `$x` . Em seguida, a variável é passada para o `Set-CimInstance` cmdlet, que modifica o valor da propriedade **VariableValue** para **someValue** .
Como o parâmetro **PassThru** é usado, este exemplo retorna um objeto de instância CIM modificado.

```powershell
$x = New-CimInstance -ClassName Win32_Environment -Property @{Name="testvar";UserName="domain\user"} -Keys Name,UserName -ClientOnly
Set-CimInstance -CimInstance $x -Property @{VariableValue="somevalue"} -PassThru
```

## PARAMETERS

### -CimSession

Executa os cmdlets em um computador remoto. Insira um nome de computador ou um objeto de sessão, como a saída de `New-CimSession` um `Get-CimSession` cmdlet ou.

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

Se você não especificar esse parâmetro, o cmdlet executará a operação no computador local usando Component Object Model (COM).

Se você especificar esse parâmetro, o cmdlet criará uma sessão temporária para o computador especificado usando o protocolo WsMan.

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

Especifica um objeto de instância CIM a ser usado como entrada.

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet
Aliases: CimInstance

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Namespace

Especifica o namespace para a operação CIM. O namespace padrão é root/cimv2. Você pode usar o preenchimento com Tab para navegar na lista de namespaces, pois o PowerShell Obtém uma lista de namespaces do servidor WMI local para fornecer a lista de namespaces.

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
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

### -PassThru

Retorna um objeto que representa o item com que você está trabalhando. Por padrão, este cmdlet não gera saída.

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

### -Propriedade

Especifica as propriedades da instância CIM como uma tabela de hash (usando pares de nome-valor). Somente as propriedades especificadas usando esse parâmetro são alteradas. Outras propriedades da instância CIM não são alteradas.

```yaml
Type: System.Collections.IDictionary
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet, QuerySessionSet, QueryComputerSet
Aliases: Arguments

Required: True (QuerySessionSet, QueryComputerSet), False (CimInstanceComputerSet, CimInstanceSessionSet)
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Query

Especifica uma consulta a ser executada no servidor CIM para recuperar as instâncias de CIM nas quais o cmdlet será executado. Você pode especificar o dialeto da consulta usando o parâmetro QueryDialect.

Se o valor especificado contiver aspas duplas ( `"` ), aspas simples ( `'` ) ou barra invertida ( `\` ), você deverá escapar desses caracteres prefixando-os com o caractere de barra invertida ( `\` ). Se o valor especificado usar o operador **like** WQL, você deverá escapar os caracteres a seguir, colocando-os entre colchetes ( `[]` ): porcentagem ( `%` ), sublinhado ( `_` ) ou colchete de abertura ( `[` ).

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -QueryDialect

Especifica a linguagem de consulta usada para o parâmetro de consulta. Os valores aceitáveis para esse parâmetro são: **WQL** ou **CQL** . O valor padrão é **WQL** .

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
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

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### Microsoft. Management. Infrastructure. CimInstance

## SAÍDAS

### Microsoft. Management. Infrastructure. CimInstance

Quando o parâmetro **PassThru** é especificado, esse cmdlet retorna um objeto de instância CIM modificado.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Get-CimInstance](get-ciminstance.md)

[New-CimInstance](New-CimInstance.md)

[Remove-CimInstance](remove-ciminstance.md)

