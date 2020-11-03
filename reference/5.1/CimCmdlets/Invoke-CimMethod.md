---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 01/21/2020
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/invoke-cimmethod?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-CimMethod
ms.openlocfilehash: 328abb5776366f6e2d9b5106c93337f5d45533ed
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93194862"
---
# Invoke-CimMethod

## SINOPSE
Invoca um método de uma classe CIM.

## SYNTAX

### ClassNameComputerSet (padrão)

```
Invoke-CimMethod [-ClassName] <String> [-ComputerName <String[]>] [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ClassNameSessionSet

```
Invoke-CimMethod [-ClassName] <String> -CimSession <CimSession[]> [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ResourceUriComputerSet

```
Invoke-CimMethod -ResourceUri <Uri> [-ComputerName <String[]>] [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### CimInstanceSessionSet

```
Invoke-CimMethod [-ResourceUri <Uri>] [-InputObject] <CimInstance> -CimSession <CimSession[]>
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### CimInstanceComputerSet

```
Invoke-CimMethod [-ResourceUri <Uri>] [-InputObject] <CimInstance> [-ComputerName <String[]>]
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ResourceUriSessionSet

```
Invoke-CimMethod -ResourceUri <Uri> -CimSession <CimSession[]> [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### CimClassComputerSet

```
Invoke-CimMethod [-CimClass] <CimClass> [-ComputerName <String[]>] [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CimClassSessionSet

```
Invoke-CimMethod [-CimClass] <CimClass> -CimSession <CimSession[]> [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### QueryComputerSet

```
Invoke-CimMethod -Query <String> [-QueryDialect <String>] [-ComputerName <String[]>]
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### QuerySessionSet

```
Invoke-CimMethod -Query <String> [-QueryDialect <String>] -CimSession <CimSession[]>
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Invoke-CimMethod` cmdlet invoca um método de uma classe CIM ou uma instância CIM usando os pares nome-valor especificados pelo parâmetro **arguments** .

Se o parâmetro **InputObject** não for especificado, o cmdlet funcionará de uma das seguintes maneiras:

- Se nem o parâmetro **ComputerName** nem o parâmetro **CimSession** for especificado, esse cmdlet funcionará no Instrumentação de gerenciamento do Windows local (WMI) usando uma sessão Component Object Model (com).
- Se o parâmetro **ComputerName** ou o parâmetro **CimSession** for especificado, esse cmdlet funcionará no servidor CIM especificado pelo parâmetro **ComputerName** ou pelo parâmetro **CimSession** .

Se o parâmetro **InputObject** for especificado, o cmdlet funcionará de uma das seguintes maneiras:

- Se nem o parâmetro **ComputerName** nem o parâmetro **CimSession** for especificado, esse cmdlet usará a sessão CIM ou o nome do computador do objeto de entrada.
- Se o parâmetro **ComputerName** ou o parâmetro **CimSession** for especificado, esse cmdlet usa o valor do parâmetro **CimSession** ou o valor do parâmetro **ComputerName** . Esse não é um cenário comum.

## EXEMPLOS

### Exemplo 1: invocar um método

Este exemplo invoca o método **Terminate** da classe **Win32_Process** .

```powershell
Invoke-CimMethod -Query 'select * from Win32_Process where name like "notepad%"' -MethodName "Terminate"
```

### Exemplo 2: invocar um método usando o objeto de instância CIM

Este exemplo recupera o objeto de instância CIM e o armazena em uma variável chamada `$x` usando o `Get-CimInstance` cmdlet. O conteúdo da variável é usado como **InputObject** para o `Invoke-CimMethod` cmdlet. O método **GetOwner** é invocado para o **CimInstance** .

```powershell
$x = Get-CimInstance -Query 'Select * from Win32_Process where name like "notepad%"'
Invoke-CimMethod -InputObject $x -MethodName GetOwner
```

### Exemplo 3: invocar um método estático usando argumentos

Este exemplo invoca o método **Create** chamado usando o parâmetro **arguments** .

```powershell
Invoke-CimMethod -ClassName Win32_Process -MethodName "Create" -Arguments @{
  CommandLine = 'notepad.exe'; CurrentDirectory = "C:\windows\system32"
}
```

### Exemplo 4: validação no lado do cliente

Este exemplo executa a validação do lado do cliente para o método **XYZ** passando um objeto **CimClass** para `Invoke-CimMethod` .

```powershell
$c = Get-CimClass -ClassName Win32_Process
Invoke-CimMethod -CimClass $c -MethodName "xyz" -Arguments @{ CommandLine = 'notepad.exe' }
```

## PARAMETERS

### -Arguments

Especifica os parâmetros a passar para o método chamado. Especifique os valores para esse parâmetro como pares de nome-valor, armazenados em uma tabela de hash. A ordem dos valores inseridos não é importante.

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CimClass

Especifica um objeto de classe CIM que representa uma definição de classe CIM no servidor. Use esse parâmetro ao invocar um método estático de uma classe.

Você pode usar o `Get-CimClass` cmdlet para recuperar uma definição de classe do servidor.

O uso desse parâmetro resulta em validações de esquema melhores do cliente.

```yaml
Type: Microsoft.Management.Infrastructure.CimClass
Parameter Sets: CimClassComputerSet, CimClassSessionSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CimSession

Executa o comando usando a sessão CIM especificada. Insira uma variável que contenha a sessão CIM ou um comando que cria ou obtém a sessão CIM, como os `New-CimSession` `Get-CimSession` cmdlets ou. Para obter mais informações, consulte [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: ClassNameSessionSet, CimInstanceSessionSet, CimClassSessionSet, QuerySessionSet, ResourceUriSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ClassName

Especifica o nome da classe CIM para a qual executar a operação. Esse parâmetro é usado somente para métodos estáticos. Você pode usar o preenchimento com Tab para procurar a lista de classes, porque o PowerShell Obtém uma lista de classes do servidor WMI local para fornecer uma lista de nomes de classe.

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet
Aliases: Class

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName

Especifica o nome do computador no qual você deseja executar a operação CIM. Você pode especificar um FQDN (nome de domínio totalmente qualificado), um nome NetBIOS ou um endereço IP.

Ao usar esse parâmetro, o cmdlet cria uma sessão temporária para o computador especificado usando o protocolo WsMan. Caso contrário, o cmdlet executará a operação no computador local usando a Component Object Model (COM).

Conecte-se usando uma sessão CIM para melhorar o desempenho quando várias operações estiverem sendo executadas no mesmo computador.

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, ResourceUriComputerSet, CimClassComputerSet, CimInstanceComputerSet, QueryComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject

Especifica um objeto de instância CIM a ser usado como entrada para invocar um método. Esse parâmetro só pode ser usado para invocar métodos de instância. Para invocar métodos estáticos de classe, use o parâmetro de **classe** ou o parâmetro **CimClass** .

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

### -MethodName

Especifica o nome do método CIM a ser invocado. Este parâmetro é obrigatório e não pode ser nulo ou vazio. Para invocar o método estático de uma classe CIM, use o **ClassName** ou o parâmetro **CimClass** .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Namespace

Especifica o namespace para a operação CIM. O namespace padrão é **root/cimv2** . Você pode usar o preenchimento com Tab para navegar na lista de namespaces, pois o PowerShell Obtém uma lista de namespaces do servidor WMI local para fornecer a lista de namespaces.

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet, ResourceUriComputerSet, ResourceUriSessionSet, QueryComputerSet, QuerySessionSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OperationTimeoutSec

Especifica a quantidade de tempo que o cmdlet aguarda uma resposta do computador. Por padrão, o valor é 0, o que significa que o cmdlet usa o valor de tempo limite padrão para o servidor.

Se o parâmetro **OperationTimeoutSec** for definido como um valor menor que o tempo limite de repetição de conexão padrão de 3 minutos, as falhas de rede que durar mais do que o valor do parâmetro **OperationTimeoutSec** não serão recuperáveis.

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

Especifica uma consulta a ser executada no servidor CIM. Um método é invocado nas instâncias recebidas como resultado da consulta. Você pode especificar o dialeto da consulta usando o parâmetro **QueryDialect** .

Se o valor especificado contiver aspas duplas ( `"` ), aspas simples ( `'` ) ou barra invertida ( `\` ), você deverá escapar desses caracteres prefixando-os com o caractere de barra invertida ( `\` ). Se o valor especificado usar o operador LIKE WQL, você deverá escapar os caracteres a seguir, colocando-os entre colchetes ( `[]` ): porcentagem ( `%` ), sublinhado ( `_` ) ou colchete de abertura ( `[` ).

```yaml
Type: System.String
Parameter Sets: QueryComputerSet, QuerySessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -QueryDialect

Especifica a linguagem de consulta usada para o parâmetro de consulta. Os valores aceitáveis para esse parâmetro são: **WQL** ou **CQL** .

O valor padrão é **WQL** .

```yaml
Type: System.String
Parameter Sets: QueryComputerSet, QuerySessionSet
Aliases:

Required: False
Position: Named
Default value: WQL
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceURI

Especifica o URI (Uniform Resource Identifier) do recurso da classe ou instância de recurso.
O URI é utilizado para identificar um tipo específico de recurso, como discos ou processos em um computador.

Um URI consiste em um prefixo e um caminho para um recurso. Por exemplo:

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

Por padrão, se você não especificar esse parâmetro, o URI de recurso padrão do DMTF `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` será usado e o nome da classe será anexado a ele.

O **ResourceURI** só pode ser usado com sessões CIM criadas usando o protocolo WSMan ou ao especificar o parâmetro **ComputerName** , que cria uma sessão CIM usando WSMan.

Quando você especifica esse parâmetro sem especificar o parâmetro **ComputerName** , ou quando você especifica uma sessão CIM criada usando o protocolo DCOM, recebe um erro. O protocolo DCOM não oferece suporte ao parâmetro **ResourceURI** .

Se o parâmetro **ResourceURI** e o parâmetro **Filter** forem especificados, o parâmetro **Filter** será ignorado.

```yaml
Type: System.Uri
Parameter Sets: ResourceUriSessionSet, ResourceUriComputerSet
Aliases:

Required: True (ResourceUriSessionSet, ResourceUriComputerSet), False (CimInstanceSessionSet, CimInstanceComputerSet)
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

### Microsoft. Management. Infrastructure. CimClass

Esse cmdlet aceita uma classe CIM como um objeto de entrada.

### Microsoft. Management. Infrastructure. CimInstance

Esse cmdlet aceita uma instância CIM como um objeto de entrada.

## SAÍDAS

### System. Management. Automation. PSCustomObject

Esse cmdlet retorna um objeto.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Get-CimClass](get-cimclass.md)

[Get-CimInstance](get-ciminstance.md)

[Get-CimSession](Get-CimSession.md)

[New-CimSession](New-CimSession.md)
