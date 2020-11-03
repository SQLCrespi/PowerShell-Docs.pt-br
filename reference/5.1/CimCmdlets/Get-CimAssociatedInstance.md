---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-cimassociatedinstance?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimAssociatedInstance
ms.openlocfilehash: 10790507b24bc4212db062589cf76d5260554b30
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93194859"
---
# Get-CimAssociatedInstance

## SINOPSE
Recupera as instâncias CIM que estão conectadas a uma instância CIM específica por uma associação.

## SYNTAX

### ComputerSet (padrão)

```
Get-CimAssociatedInstance [[-Association] <String>] [-ResultClassName <String>]
 [-InputObject] <CimInstance> [-Namespace <String>] [-OperationTimeoutSec <UInt32>]
 [-ResourceUri <Uri>] [-ComputerName <String[]>] [-KeyOnly] [<CommonParameters>]
```

### Sessionset

```
Get-CimAssociatedInstance [[-Association] <String>] [-ResultClassName <String>]
 [-InputObject] <CimInstance> [-Namespace <String>] [-OperationTimeoutSec <UInt32>]
 [-ResourceUri <Uri>] -CimSession <CimSession[]> [-KeyOnly] [<CommonParameters>]
```

## DESCRIPTION

O `Get-CimAssociatedInstance` cmdlet recupera as instâncias de CIM conectadas a uma instância de CIM específica, chamada de instância de origem, por uma associação.

Em uma associação, cada instância de CIM tem uma função nomeada e a mesma instância de CIM pode participar de uma associação em funções diferentes.

Se o parâmetro InputObject não for especificado, o cmdlet funcionará de uma das seguintes maneiras:

- Se nem o parâmetro **ComputerName** nem o parâmetro **CimSession** for especificado, esse cmdlet funcionará no Instrumentação de gerenciamento do Windows local (WMI) usando uma sessão Component Object Model (com).
- Se o parâmetro **ComputerName** ou o parâmetro **CimSession** for especificado, esse cmdlet funcionará no servidor CIM especificado pelo parâmetro **ComputerName** ou pelo parâmetro **CimSession** .

## EXEMPLOS

### Exemplo 1: obter todas as instâncias associadas de uma instância específica

```powershell
$disk = Get-CimInstance -ClassName Win32_LogicalDisk -KeyOnly
Get-CimAssociatedInstance -InputObject $disk[1]
```

Esse conjunto de comandos recupera as instâncias da classe denominada Win32_LogicalDisk e armazena as informações em uma variável chamada `$disk` usando o `Get-CimInstance` cmdlet. A primeira instância de disco lógico na variável é usada como o objeto de entrada para o `Get-CimAssociatedInstance` cmdlet obter todas as instâncias de CIM associadas da instância CIM especificada.

### Exemplo 2: obter todas as instâncias associadas de um tipo específico

```powershell
$disk = Get-CimInstance -ClassName Win32_LogicalDisk -KeyOnly
Get-CimAssociatedInstance -InputObject $disk[1] -ResultClass Win32_DiskPartition
```

Esse conjunto de comandos recupera todas as instâncias da classe **Win32_LogicalDisk** e as armazena em uma variável chamada `$disk` . A primeira instância de disco lógico na variável é usada como o objeto de entrada para o `Get-CimAssociatedInstance` cmdlet obter todas as instâncias associadas que estão associadas por meio da classe de associação especificada **Win32_DiskPartition** .

### Exemplo 3: obter todas as instâncias associadas por meio do qualificador de uma classe específica

```powershell
$s = Get-CimInstance -Query "Select * from Win32_Service where name like 'Winmgmt'"
Get-CimClass -ClassName *Service* -Qualifier "Association"
$c.CimClasName
```

```Output
Win32_LoadOrderGroupServiceDependencies
Win32_DependentService
Win32_SystemServices
Win32_LoadOrderGroupServiceMembers
Win32_ServiceSpecificationService
```

```powershell
Get-CimAssociatedInstance -InputObject $s -Association Win32_DependentService
```

Esse conjunto de comandos recupera os serviços que dependem do serviço WMI e os armazena em uma variável chamada `$s` . O nome da classe de associação para o **Win32_DependentService** é recuperado usando o `Get-CimClass` cmdlet especificando a **Associação** como o qualificador e, em seguida, é passado com $s ao `Get-CimAssociatedInstance` cmdlet para obter todas as instâncias associadas da classe de associação recuperada.

## PARAMETERS

### -Associação

Especifica o nome da classe de associação. Se você não especificar esse parâmetro, o cmdlet retornará todos os objetos de associação existentes de qualquer tipo.

Por exemplo, se A classe A estiver associada à classe B por meio de duas associações, AB1 e AB2, esse parâmetro poderá ser usado para especificar o tipo de associação, AB1 ou AB2.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CimSession

Executa o comando usando a sessão CIM especificada. Insira uma variável que contenha a sessão CIM ou um comando que cria ou obtém a sessão CIM, como `New-CimSession` ou `Get-CimSession` . Para obter mais informações, consulte [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: SessionSet
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
Parameter Sets: ComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Especifica a entrada para esse cmdlet. Você pode usar esse parâmetro ou é possível canalizar a entrada para esse cmdlet.

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: (All)
Aliases: CimInstance

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Somente

Retorna objetos com apenas as propriedades de chave populadas. Isso reduz a quantidade de dados transferidos pela rede.

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

### -Namespace

Especifica o namespace para a operação CIM. O namespace padrão é root/cimv2.

> [!NOTE]
> Você pode usar o preenchimento com Tab para navegar na lista de namespaces, pois o PowerShell Obtém uma lista de namespaces do servidor WMI local para fornecer a lista de namespaces.

```yaml
Type: System.String
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResultClassName

Especifica o nome de classe das instâncias associadas. Uma instância CIM pode ser associada a uma ou mais instâncias CIM. Todas as instâncias de CIM associadas serão retornadas se você não especificar o nome da classe de resultado.

Por padrão, o valor desse parâmetro é NULL e todas as instâncias de CIM associadas são retornadas.

Você pode filtrar os resultados da Associação para corresponder a um nome de classe específico. A filtragem ocorre no servidor. Se esse parâmetro não for especificado, o `Get-CIMAssociatedInstance` retornará todas as associações existentes. Por exemplo, se A classe A estiver associada às classes B, C e D, esse parâmetro poderá ser usado para restringir a saída a um tipo específico (B, C ou D).

```yaml
Type: System.String
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

### Nenhum

Esse cmdlet não aceita nenhum objeto de entrada.

## SAÍDAS

### System.Object

Esse cmdlet retorna um objeto.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Get-CimClass](get-cimclass.md)

[Get-CimInstance](get-ciminstance.md)
