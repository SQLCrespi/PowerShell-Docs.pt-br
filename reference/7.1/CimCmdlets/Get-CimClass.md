---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-cimclass?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimClass
ms.openlocfilehash: 2eaf2850f32d56fc69a44b26162be94b187c9ba1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194796"
---
# Get-CimClass

## SINOPSE
Obtém uma lista de classes CIM em um namespace específico.

## SYNTAX

### ComputerSet (padrão)

```
Get-CimClass [[-ClassName] <String>] [[-Namespace] <String>] [-OperationTimeoutSec <UInt32>]
 [-ComputerName <String[]>] [-MethodName <String>] [-PropertyName <String>]
 [-QualifierName <String>] [<CommonParameters>]
```

### Sessionset

```
Get-CimClass [[-ClassName] <String>] [[-Namespace] <String>] [-OperationTimeoutSec <UInt32>]
 -CimSession <CimSession[]> [-MethodName <String>] [-PropertyName <String>]
 [-QualifierName <String>] [<CommonParameters>]
```

## DESCRIPTION

O `Get-CimClass` cmdlet recupera uma lista de classes CIM em um namespace específico. Se não houver nenhum nome de classe fornecido, o cmdlet retornará todas as classes no namespace. Ao contrário de uma instância CIM, as classes CIM não contêm a sessão CIM ou o nome do computador do qual elas são recuperadas.

## EXEMPLOS

### Exemplo 1: obter todas as definições de classe

Este exemplo obtém todas as definições de classe sob o namespace **root/cimv2** .

```powershell
Get-CimClass
```

### Exemplo 2: obter as classes com um nome específico

Este exemplo obtém as classes que contêm a palavra de **disco** em seus nomes.

```powershell
Get-CimClass -ClassName *disk*
```

### Exemplo 3: obter as classes com um nome de método específico

Este exemplo obtém as classes que começam com o nome **Win32** e têm um nome de método que começa com **Term** .

```powershell
Get-CimClass -ClassName Win32* -MethodName Term*
```

### Exemplo 4: obter as classes com um nome de propriedade específico

Este exemplo obtém as classes que começam com o nome **Win32** e têm uma propriedade chamada **Handle** .

```powershell
Get-CimClass -ClassName Win32* -PropertyName Handle
```

### Exemplo 5: obter as classes com um nome de qualificador específico

Este exemplo obtém as classes que iniciam com o nome **Win32** , contêm a palavra **disco** em seus nomes e têm a **Associação** de qualificador especificada.

```powershell
Get-CimClass -ClassName Win32*Disk* -QualifierName Association
```

### Exemplo 6: obter as definições de classe de um namespace específico

Este exemplo obtém as definições de classe que contêm a palavra **net** em seus nomes a partir da **raiz/standardCimv2** do namespace especificado.

```powershell
Get-CimClass -Namespace root/standardCimv2 -ClassName *Net*
```

### Exemplo 7: obter as definições de classe de um servidor remoto

Este exemplo obtém as definições de classe que contêm o **disco** do Word em seus nomes dos servidores remotos especificados **Server01** e **Server02** .

```powershell
Get-CimClass -ClassName *disk* -ComputerName Server01, Server02
```

### Exemplo 8: obter as classes usando uma sessão CIM

```powershell
$s = New-CimSession -ComputerName Server01, Server02
Get-CimClass -ClassName *disk* -CimSession $s
```

Esse conjunto de comandos cria uma sessão com vários computadores e o armazena em uma variável `$s` usando o `New-CimSession` cmdlet e, em seguida, obtém as classes usando o `Get-CimClass` cmdlet.

## PARAMETERS

### -CimSession

Executa o cmdlet em uma sessão remota ou em um computador remoto. Insira um nome de computador ou um objeto de sessão, como a saída de `New-CimSession` um `Get-CimSession` cmdlet ou. O padrão é a sessão atual do computador local.

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

### -ClassName

Especifica o nome da classe CIM para a qual executar a operação. Você pode usar o preenchimento com Tab para procurar a lista de classes, porque o PowerShell Obtém uma lista de classes do servidor WMI local para fornecer uma lista de nomes de classe.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -ComputerName

Especifica o computador no qual você deseja executar a operação CIM. Você pode especificar um nome de domínio totalmente qualificado (FQDN) um nome NetBIOS ou um endereço IP.

Se você especificar esse parâmetro, o cmdlet criará uma sessão temporária para o computador especificado usando o protocolo WsMan.

Se você não especificar esse parâmetro, o cmdlet executará a operação no computador local usando Component Object Model (COM).

Se várias operações estiverem sendo executadas no mesmo computador, o uso de uma sessão CIM fornecerá um melhor desempenho.

```yaml
Type: System.String[]
Parameter Sets: ComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MethodName

Localiza as classes que têm um método correspondente a esse nome. Você pode usar caracteres curinga com esse parâmetro.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Namespace

Especifica o namespace para a operação CIM. O namespace padrão é **root/cimv2** . Você pode usar o preenchimento com Tab para navegar na lista de namespaces, pois o PowerShell Obtém uma lista de namespaces do servidor WMI local para fornecer a lista de namespaces.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
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

### -PropertyName

Localiza as classes que têm uma propriedade correspondente a esse nome. Você pode usar caracteres curinga com esse parâmetro.

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

### -Qualifiername

Filtra as classes por nome de qualificador de nível de classe. Você pode usar caracteres curinga com esse parâmetro.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Esse cmdlet não aceita nenhum objeto de entrada.

## SAÍDAS

### Microsoft. Management. Infrastructure. CimClass

Esse cmdlet retorna um objeto de classe CIM.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[New-CimSession](New-CimSession.md)

