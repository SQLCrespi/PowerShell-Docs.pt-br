---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/21/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-ciminstance?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimInstance
ms.openlocfilehash: 468b0e62925774fb838263b9bd9aea6a74151b5f
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93194861"
---
# Get-CimInstance

## SINOPSE
Obtém as instâncias CIM de uma classe de um servidor CIM.

## SYNTAX

### ClassNameComputerSet (padrão)

```
Get-CimInstance [-ClassName] <String> [-ComputerName <String[]>] [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-QueryDialect <String>] [-Shallow] [-Filter <String>]
 [-Property <String[]>] [<CommonParameters>]
```

### ResourceUriSessionSet

```
Get-CimInstance -CimSession <CimSession[]> -ResourceUri <Uri> [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-Shallow] [-Filter <String>] [-Property <String[]>]
 [<CommonParameters>]
```

### QuerySessionSet

```
Get-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] -Query <String> [-QueryDialect <String>] [-Shallow]
 [<CommonParameters>]
```

### ClassNameSessionSet

```
Get-CimInstance -CimSession <CimSession[]> [-ClassName] <String> [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-QueryDialect <String>] [-Shallow] [-Filter <String>]
 [-Property <String[]>] [<CommonParameters>]
```

### CimInstanceSessionSet

```
Get-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [<CommonParameters>]
```

### CimInstanceComputerSet

```
Get-CimInstance [-ResourceUri <Uri>] [-ComputerName <String[]>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [<CommonParameters>]
```

### ResourceUriComputerSet

```
Get-CimInstance -ResourceUri <Uri> [-ComputerName <String[]>] [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-Shallow] [-Filter <String>] [-Property <String[]>]
 [<CommonParameters>]
```

### QueryComputerSet

```
Get-CimInstance [-ResourceUri <Uri>] [-ComputerName <String[]>] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] -Query <String> [-QueryDialect <String>] [-Shallow]
 [<CommonParameters>]
```

## DESCRIPTION

O `Get-CimInstance` cmdlet obtém as instâncias CIM de uma classe de um servidor CIM. Você pode especificar o nome da classe ou uma consulta para este cmdlet. Esse cmdlet retorna um ou mais objetos de instância CIM que representam um instantâneo das instâncias de CIM presentes no servidor CIM.

Se o parâmetro **InputObject** não for especificado, o cmdlet funcionará de uma das seguintes maneiras:

- Se nem o parâmetro **ComputerName** nem o parâmetro **CimSession** for especificado, esse cmdlet funcionará no Instrumentação de gerenciamento do Windows local (WMI) usando uma sessão Component Object Model (com).
- Se o parâmetro **ComputerName** ou o parâmetro **CimSession** for especificado, esse cmdlet funcionará no servidor CIM especificado pelo parâmetro **ComputerName** ou pelo parâmetro **CimSession** .

Se o parâmetro **InputObject** for especificado, o cmdlet funcionará de uma das seguintes maneiras:

- Se nem o parâmetro **ComputerName** nem o parâmetro **CimSession** for especificado, esse cmdlet usará a sessão CIM ou o nome do computador do objeto de entrada.
- Se o parâmetro **ComputerName** ou o parâmetro **CimSession** for especificado, esse cmdlet usa o valor do parâmetro CimSession ou o valor do parâmetro **ComputerName** .

## EXEMPLOS

### Exemplo 1: obter as instâncias de CIM de uma classe especificada

Este exemplo recupera as instâncias de CIM de uma classe chamada **Win32_Process** .

```powershell
Get-CimInstance -ClassName Win32_Process
```

### Exemplo 2: obter uma lista de namespaces de um servidor WMI

Este exemplo recupera uma lista de namespaces no namespace **raiz** em um servidor WMI.

```powershell
Get-CimInstance -Namespace root -ClassName __Namespace
```

### Exemplo 3: obter instâncias de uma classe filtrada usando uma consulta

Este exemplo recupera todas as instâncias de CIM que começam com a letra **P** de uma classe chamada **Win32_Process** usando a consulta especificada por um parâmetro de **consulta** .

```powershell
Get-CimInstance -Query "SELECT * from Win32_Process WHERE name LIKE 'P%'"
```

### Exemplo 4: obter instâncias de uma classe filtrada usando um nome de classe e uma expressão de filtro

Este exemplo recupera todas as instâncias CIM que começam com a letra **P** de uma classe chamada **Win32_Process** usando o parâmetro Filter.

```powershell
Get-CimInstance -ClassName Win32_Process -Filter "Name like 'P%'"
```

### Exemplo 5: obter as instâncias de CIM com apenas as propriedades de chave preenchidas

Este exemplo cria uma nova instância CIM na memória para uma classe chamada **Win32_Process** com a propriedade de chave `@{ "Handle"=0 }` e a armazena em uma variável chamada `$x` . A variável é passada como uma instância CIM para o `Get-CimInstance` cmdlet para obter uma instância específica.

```powershell
$x = New-CimInstance -ClassName Win32_Process -Namespace root\cimv2 -Property @{ "Handle"=0 } -Key Handle -ClientOnly
Get-CimInstance -CimInstance $x
```

### Exemplo 6: recuperar instâncias de CIM e reutilizá-las

Este exemplo obtém as instâncias de CIM de uma classe chamada **Win32_Process** e as armazena nas variáveis `$x` e `$y` . Em seguida, a variável `$x` é formatada em uma tabela que contém apenas as propriedades **Name** e **KernelModeTime** , a tabela definida como **AutoSize** .

```powershell
$x,$y = Get-CimInstance -ClassName Win32_Process
$x | Format-Table -Property Name,KernelModeTime -AutoSize
```

```Output
Name                 KernelModeTime
----                 --------------
System Idle Process 157238797968750
```

### Exemplo 7: obter instâncias de CIM do computador remoto

Este exemplo recupera as instâncias de CIM de uma classe chamada **Win32_ComputerSystem** dos computadores remotos chamados **Server01** e **Server02** .

```powershell
Get-CimInstance -ClassName Win32_ComputerSystem -ComputerName Server01,Server02
```

### Exemplo 8: obtendo apenas as propriedades de chave, em vez de todas as propriedades

Este exemplo recupera apenas as propriedades de chave, o que reduz o tamanho do objeto e do tráfego de rede.

```powershell
$x = Get-CimInstance -Class Win32_Process -KeyOnly
$x | Invoke-CimMethod -MethodName GetOwner
```

### Exemplo 9: obtendo apenas um subconjunto de propriedades, em vez de todas as propriedades

Este exemplo recupera apenas um subconjunto de propriedades, o que reduz o tamanho do objeto e do tráfego de rede.

```powershell
Get-CimInstance -Class Win32_Process -Property Name,KernelModeTime
$x = Get-CimInstance -Class Win32_Process -Property Name,KernelModeTime
$x | Invoke-CimMethod -MethodName GetOwner
```

A instância recuperada com o parâmetro **Property** pode ser usada para executar outras operações CIM, por exemplo, `Set-CimInstance` ou `Invoke-CimMethod` .

### Exemplo 10: obter a instância CIM usando a sessão CIM

Este exemplo cria uma sessão CIM nos computadores chamados **Server01** e **Server02** usando o `New-CimSession` cmdlet e armazena as informações da sessão em uma variável chamada `$s` . O conteúdo da variável é passado para o `Get-CimInstance` usando o parâmetro **CimSession** para obter as instâncias de CIM da classe denominada **Win32_ComputerSystem** .

```powershell
$s = New-CimSession -ComputerName Server01,Server02
Get-CimInstance -ClassName Win32_ComputerSystem -CimSession $s
```

## PARAMETERS

### -CimSession

Especifica a sessão CIM a ser usada para este cmdlet. Insira uma variável que contenha a sessão CIM ou um comando que cria ou obtém a sessão CIM, como os `New-CimSession` `Get-CimSession` cmdlets ou. Para obter mais informações, consulte [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: ResourceUriSessionSet, QuerySessionSet, ClassNameSessionSet, CimInstanceSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ClassName

Especifica o nome da classe CIM para a qual recuperar as instâncias de CIM. Você pode usar o preenchimento com Tab para procurar a lista de classes, porque o PowerShell Obtém uma lista de classes do servidor WMI local para fornecer uma lista de nomes de classe.

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName

Especifica o computador no qual você deseja executar a operação CIM. Você pode especificar um FQDN (nome de domínio totalmente qualificado), um nome NetBIOS ou um endereço IP. Se você não especificar esse parâmetro, o cmdlet executará a operação no computador local usando Component Object Model (COM).

Se você especificar esse parâmetro, o cmdlet criará uma sessão temporária para o computador especificado usando o protocolo WsMan.

Se várias operações estiverem sendo executadas no mesmo computador, conecte-se usando uma sessão CIM para melhorar o desempenho.

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, CimInstanceComputerSet, ResourceUriComputerSet, QueryComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Filter

Especifica uma cláusula WHERE para usar como um filtro. Especifique a cláusula na linguagem de consulta **WQL** ou **CQL** . Não inclua a `WHERE` palavra-chave no valor do parâmetro.

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, ClassNameSessionSet, ResourceUriComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject

Especifica um objeto de instância CIM a ser usado como entrada.

Se você já estiver trabalhando com um objeto de instância CIM, poderá usar esse parâmetro para passar o objeto de instância CIM a fim de obter o instantâneo mais recente do servidor CIM. Quando você passa um objeto de instância CIM como uma entrada, `Get-CimInstance` o retorna o objeto do servidor usando uma operação obter CIM, em vez de uma operação de enumerar ou de consulta. O uso de uma operação get CIM é mais eficiente do que recuperar todas as instâncias e, em seguida, filtrá-las.

Se a classe CIM não implementar a operação get, a especificação do parâmetro **InputObject** retornará um erro.

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: CimInstanceSessionSet, CimInstanceComputerSet
Aliases: CimInstance

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Somente

Indica que somente objetos com as propriedades de chave populadas são retornados. A especificação do parâmetro **keyonly** reduz a quantidade de dados transferidos pela rede.

Use o parâmetro **keyonly** para retornar apenas uma pequena parte do objeto, que pode ser usada para outras operações, como os `Set-CimInstance` `Get-CimAssociatedInstance` cmdlets ou.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, ClassNameSessionSet, ResourceUriComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Namespace

Especifica o namespace da classe CIM.

O namespace padrão é **root/cimv2** . Você pode usar o preenchimento com Tab para navegar na lista de namespaces, pois o PowerShell Obtém uma lista de namespaces do servidor WMI local para fornecer a lista de namespaces.

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, QuerySessionSet, ClassNameSessionSet, ResourceUriComputerSet, QueryComputerSet
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

### -Propriedade

Especifica um conjunto de propriedades de instância a serem recuperadas. Use esse parâmetro quando precisar reduzir o tamanho do objeto retornado, seja na memória ou pela rede. O objeto retornado também contém as propriedades de chave, mesmo que você não as liste usando o parâmetro **Property** . Outras propriedades da classe estão presentes, mas não são populadas.

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, ClassNameSessionSet, ResourceUriComputerSet
Aliases: SelectProperties

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Query

Especifica uma consulta a ser executada no servidor CIM. Se o valor especificado contiver aspas duplas `"` , aspas simples `'` ou uma barra invertida `\` , você deverá escapar desses caracteres prefixando-os com o caractere de barra invertida. Se o valor especificado usar o operador **like** WQL, você deverá escapar os caracteres a seguir, colocando-os entre colchetes `[]` : percentual `%` , sublinhado `_` ou colchete de abertura `[` .

Você não pode usar uma consulta de metadados para recuperar uma lista de classes ou uma consulta de evento. Para recuperar uma lista de classes, use o `Get-CimClass` cmdlet. Para recuperar uma consulta de evento, use o `Register-CimIndicationEvent` cmdlet.

Você pode especificar o dialeto da consulta usando o parâmetro **QueryDialect** .

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -QueryDialect

Especifica a linguagem de consulta usada para o parâmetro de consulta. Os valores aceitáveis para esse parâmetro são: **WQL** ou **CQL** . O valor padrão é **WQL** .

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, QuerySessionSet, ClassNameSessionSet, QueryComputerSet
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

O **ResourceURI** só pode ser usado com sessões CIM criadas usando o protocolo WSMan ou ao especificar o parâmetro **ComputerName** , que cria uma sessão CIM usando WSMan. Se você especificar esse parâmetro sem especificar o parâmetro **ComputerName** ou se especificar uma sessão CIM criada usando o protocolo DCOM, receberá um erro, pois o protocolo DCOM não oferece suporte ao parâmetro **ResourceURI** .

Se o parâmetro **ResourceURI** e o parâmetro **Filter** forem especificados, o parâmetro **Filter** será ignorado.

```yaml
Type: System.Uri
Parameter Sets: ResourceUriSessionSet, ResourceUriComputerSet, QuerySessionSet, QueryComputerSet, CimInstanceSessionSet, CimInstanceComputerSet
Aliases:

Required: True (ResourceUriSessionSet, ResourceUriComputerSet), False (QuerySessionSet, QueryComputerSet, CimInstanceSessionSet, CimInstanceComputerSet)
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Superficial

Indica que as instâncias de uma classe são retornadas sem incluir as instâncias de quaisquer classes filhas. Por padrão, o cmdlet retorna as instâncias de uma classe e suas classes filhas.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, QuerySessionSet, ClassNameSessionSet, ResourceUriComputerSet, QueryComputerSet
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

### Microsoft. Management. Infrastructure. CimInstance

Esse cmdlet aceita um objeto de entrada especificado com o parâmetro InputObject.

## SAÍDAS

### Microsoft. Management. Infrastructure. CimInstance

Esse cmdlet retorna um ou mais objetos de instância CIM que representam um instantâneo das instâncias de CIM no servidor CIM.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Format-Table](../microsoft.powershell.utility/format-table.md)

[Get-CimAssociatedInstance](Get-CimAssociatedInstance.md)

[Get-CimClass](Get-CimClass.md)

[Invoke-CimMethod](invoke-cimmethod.md)

[New-CimInstance](New-CimInstance.md)

[Register-CimIndicationEvent](Register-CimIndicationEvent.md)

[Remove-CimInstance](remove-ciminstance.md)

[Set-CimInstance](Set-CimInstance.md)
