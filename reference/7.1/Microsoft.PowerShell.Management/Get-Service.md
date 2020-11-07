---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/30/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-service?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Service
ms.openlocfilehash: 1cbecd37217c4c0113079dfa9ac7008dd0d91823
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94342222"
---
# Get-Service

## SINOPSE
Obtém os serviços no computador.

## SYNTAX

### Padrão (padrão)

```
Get-Service [[-Name] <String[]>] [-DependentServices] [-RequiredServices] [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

### DisplayName

```
Get-Service [-DependentServices] [-RequiredServices] -DisplayName <String[]> [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

### InputObject

```
Get-Service [-DependentServices] [-RequiredServices] [-Include <String[]>] [-Exclude <String[]>]
 [-InputObject <ServiceController[]>] [<CommonParameters>]
```

## DESCRIPTION

O `Get-Service` cmdlet obtém objetos que representam os serviços em um computador, incluindo serviços em execução e interrompidos. Por padrão, quando `Get-Service` o é executado sem parâmetros, todos os serviços do computador local são retornados.

Você pode direcionar esse cmdlet para obter apenas serviços específicos especificando o nome do serviço ou o nome de exibição dos serviços, ou pode canalizar objetos de serviço para esse cmdlet.

## EXEMPLOS

### Exemplo 1: obter todos os serviços no computador

Este exemplo obtém todos os serviços no computador. Ele se comporta como se você tivesse digitado `Get-Service *` . A exibição padrão mostra o status, o nome do serviço e o nome para exibição de cada serviço.

```powershell
Get-Service
```

### Exemplo 2: obter serviços que começam com uma cadeia de caracteres de pesquisa

Este exemplo recupera serviços com nomes de serviço que começam com WMI (Instrumentação de Gerenciamento do Windows).

```powershell
Get-Service "wmi*"
```

### Exemplo 3: Exibir serviços que incluem uma cadeia de caracteres de pesquisa

Este exemplo exibe serviços com um nome de exibição que inclui a palavra Network. Pesquisar o nome de exibição localiza serviços relacionados à rede mesmo quando o nome do serviço não inclui net, como xmlprov, o serviço de provisionamento de rede.

```powershell
Get-Service -Displayname "*network*"
```

### Exemplo 4: obter serviços que começam com uma cadeia de caracteres de pesquisa e uma exclusão

Este exemplo só obtém os serviços com nomes de serviço que começam com **Win** , exceto para o serviço WinRM.

```powershell
Get-Service -Name "win*" -Exclude "WinRM"
```

### Exemplo 5: Exibir serviços ativos no momento

Este exemplo exibe somente os serviços com um status de em execução.

```powershell
Get-Service | Where-Object {$_.Status -eq "Running"}
```

`Get-Service` Obtém todos os serviços no computador e envia os objetos por meio do pipeline. O `Where-Object` cmdlet seleciona apenas os serviços com uma propriedade de **status** igual a em execução.

O status é apenas uma propriedade de objetos de serviço. Para ver todas as propriedades, digite `Get-Service | Get-Member` .

### Exemplo 6: listar os serviços no computador que têm serviços dependentes

Este exemplo obtém serviços que têm serviços dependentes.

```powershell
Get-Service |
  Where-Object {$_.DependentServices} |
    Format-List -Property Name, DependentServices, @{
      Label="NoOfDependentServices"; Expression={$_.dependentservices.count}
    }
```

```Output
Name                  : AudioEndpointBuilder
DependentServices     : {AudioSrv}
NoOfDependentServices : 1

Name                  : Dhcp
DependentServices     : {WinHttpAutoProxySvc}
NoOfDependentServices : 1
...
```

O `Get-Service` cmdlet obtém todos os serviços no computador e envia os objetos por meio do pipeline. O `Where-Object` cmdlet seleciona os serviços cuja propriedade **dependservices** não é nula.

Os resultados são enviados para o pipeline para o `Format-List` cmdlet. O parâmetro **Property** exibe o nome do serviço, o nome dos serviços dependentes e uma propriedade calculada que exibe o número de serviços dependentes para cada serviço.

### Exemplo 7: classificar serviços por valor de propriedade

Este exemplo mostra que quando você classifica os serviços em ordem crescente pelo valor de sua propriedade **status** , os serviços interrompidos aparecem antes de executar os serviços. O motivo é que o valor de **status** é uma enumeração, na qual Stopped tem um valor de 1, e a execução tem um valor de 4. Para obter mais informações, consulte [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).

Para listar os serviços em execução primeiro, use o parâmetro **decrescente** do `Sort-Object` cmdlet.

```powershell
Get-Service "s*" | Sort-Object status
```

```Output
Status   Name               DisplayName
------   ----               -----------
Stopped  stisvc             Windows Image Acquisition (WIA)
Stopped  SwPrv              MS Software Shadow Copy Provider
Stopped  SysmonLog          Performance Logs and Alerts
Running  Spooler            Print Spooler
Running  srservice          System Restore Service
Running  SSDPSRV            SSDP Discovery Service
Running  ShellHWDetection   Shell Hardware Detection
Running  Schedule           Task Scheduler
Running  SCardSvr           Smart Card
Running  SamSs              Security Accounts Manager
Running  SharedAccess       Windows Firewall/Internet Connectio...
Running  SENS               System Event Notification
Running  seclogon           Secondary Logon
```

### Exemplo 8: obter os serviços dependentes de um serviço

Este exemplo obtém os serviços que o serviço WinRM requer. O valor da propriedade **ServicesDependedOn** do serviço é retornado.

```powershell
Get-Service "WinRM" -RequiredServices
```

### Exemplo 9: obter um serviço por meio do operador de pipeline

Este exemplo obtém o serviço WinRM no computador local. A cadeia de caracteres do nome do serviço, entre aspas, é enviada ao pipeline para `Get-Service` .

```powershell
"WinRM" | Get-Service
```

## PARAMETERS

### -DependentServices

Indica que esse cmdlet obtém apenas os serviços que dependem do serviço especificado.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: DS

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName

Especifica, como uma matriz de cadeia de caracteres, os nomes de exibição dos serviços a serem recuperados. Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: DisplayName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Excluir

Especifica, como uma matriz de cadeia de caracteres, um serviço ou serviços que esse cmdlet exclui da operação.
O valor desse parâmetro qualifica o parâmetro de **nome** . Insira um elemento de nome ou padrão, como `s*` . Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Incluir

Especifica, como uma matriz de cadeia de caracteres, um serviço ou serviços que esse cmdlet inclui na operação. O valor desse parâmetro qualifica o parâmetro de **nome** . Insira um elemento de nome ou padrão, como `s*` . Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -InputObject

Especifica objetos **ServiceController** que representam os serviços a serem recuperados. Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos. É possível canalizar um objeto de serviço para este cmdlet.

```yaml
Type: System.ServiceProcess.ServiceController[]
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Especifica os nomes de serviço dos serviços a serem recuperados. Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Obrigatórioservices

Indica que esse cmdlet obtém apenas os serviços que esse serviço requer. Esse parâmetro Obtém o valor da propriedade **ServicesDependedOn** do serviço.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: SDO, ServicesDependedOn

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: True
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. ServiceProcess. ServiceController, System. String

É possível canalizar um objeto de serviço ou um nome de serviço para esse cmdlet.

## SAÍDAS

### System.ServiceProcess.ServiceController

Esse cmdlet retorna objetos que representam os serviços no computador.

## OBSERVAÇÕES

Esse cmdlet só está disponível em plataformas Windows.

A partir do PowerShell 6,0, as seguintes propriedades são adicionadas aos objetos **ServiceController** : **username** , **Description** , **DelayedAutoStart** , **BinaryPathName** e **StartupType** .

Você também pode consultar `Get-Service` por seu alias interno, `gsv` . Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

Esse cmdlet pode exibir serviços somente quando o usuário atual tem permissão para vê-los. Se esse cmdlet não exibir serviços, talvez você não tenha permissão para vê-los.

Para localizar o nome do serviço e o nome de exibição de cada serviço em seu sistema, digite `Get-Service` . Os nomes de serviço aparecem na coluna nome e os nomes de exibição aparecem na coluna **DisplayName** .

Quando você classifica em ordem crescente pelo valor da propriedade **status** , os serviços interrompidos aparecem antes de executar os serviços. A propriedade **status** do serviço é um valor enumerado e os nomes de status representam valores inteiros. A ordem de classificação é baseada no valor inteiro, não no nome. Parado aparece antes porque a execução foi interrompida tem um valor de 1 e a execução tem um valor de 4. Para obter mais informações, consulte [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).

## LINKS RELACIONADOS

[New-Service](New-Service.md)

[Restart-Service](Restart-Service.md)

[Resume-Service](Resume-Service.md)

[Set-Service](Set-Service.md)

[Start-Service](Start-Service.md)

[Stop-Service](Stop-Service.md)

[Suspend-Service](Suspend-Service.md)

[Remove-Service](Remove-Service.md)
