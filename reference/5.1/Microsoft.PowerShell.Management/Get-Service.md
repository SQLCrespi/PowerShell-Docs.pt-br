---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Service
ms.openlocfilehash: 0c007f1becd7364806cfd47e18cf05995b81e0f7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194167"
---
# Get-Service

## SINOPSE
Obtém os serviços em um computador local ou remoto.

## SYNTAX

### Padrão (padrão)

```
Get-Service [[-Name] <String[]>] [-ComputerName <String[]>] [-DependentServices] [-RequiredServices]
 [-Include <String[]>] [-Exclude <String[]>] [<CommonParameters>]
```

### DisplayName

```
Get-Service [-ComputerName <String[]>] [-DependentServices] [-RequiredServices] -DisplayName <String[]>
 [-Include <String[]>] [-Exclude <String[]>] [<CommonParameters>]
```

### InputObject

```
Get-Service [-ComputerName <String[]>] [-DependentServices] [-RequiredServices] [-Include <String[]>]
 [-Exclude <String[]>] [-InputObject <ServiceController[]>] [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Get-Service** obtém objetos que representam os serviços em um computador local ou em um computador remoto, incluindo serviços em execução e interrompidos.

Você pode direcionar esse cmdlet para obter apenas serviços específicos especificando o nome do serviço ou o nome de exibição dos serviços, ou pode canalizar objetos de serviço para esse cmdlet.

## EXEMPLOS

### Exemplo 1: obter todos os serviços no computador

```powershell
Get-Service
```

Esse comando obtém todos os serviços no computador.
Ele se comporta como se você tivesse digitado `Get-Service *` .
A exibição padrão mostra o status, o nome do serviço e o nome para exibição de cada serviço.

### Exemplo 2: obter serviços que começam com uma cadeia de caracteres de pesquisa

```powershell
Get-Service "wmi*"
```

Esse comando recupera serviços com nomes de serviço que começam com WMI (o acrônimo para Instrumentação de Gerenciamento do Windows).

### Exemplo 3: Exibir serviços que incluem uma cadeia de caracteres de pesquisa

```powershell
Get-Service -Displayname "*network*"
```

Este comando exibe os serviços com um nome de exibição que inclui a palavra rede.
A pesquisa pelo nome de exibição localiza os serviços relacionados à rede mesmo quando o nome do serviço não inclui "Net", como xmlprov, o serviço de provisionamento de rede.

### Exemplo 4: obter serviços que começam com uma cadeia de caracteres de pesquisa e uma exclusão

```powershell
Get-Service -Name "win*" -Exclude "WinRM"
```

Esses comandos obtêm somente os serviços com nomes de serviço que começam com Win, exceto para o serviço WinRM.

### Exemplo 5: Exibir serviços ativos no momento

```powershell
Get-Service | Where-Object {$_.Status -eq "Running"}
```

Esse comando exibe somente os serviços que estão ativos no momento.
Ele usa o cmdlet **Get-Service** para obter todos os serviços no computador.
O operador de pipeline (|) passa os resultados para o cmdlet Where-Object, que seleciona apenas os serviços com uma propriedade de status igual a em execução.

O status é apenas uma propriedade de objetos de serviço.
Para ver todas as propriedades, digite `Get-Service | Get-Member` .

### Exemplo 6: obter os serviços em um computador remoto

```powershell
Get-Service -ComputerName "Server02"
```

Esse comando obtém os serviços no computador remoto Server02.

Como o parâmetro *ComputerName* de **Get-Service** não usa a comunicação remota do Windows PowerShell, você pode usar esse parâmetro mesmo que o computador não esteja configurado para comunicação remota no Windows PowerShell.

### Exemplo 7: listar os serviços no computador local que têm serviços dependentes

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

O primeiro comando usa o cmdlet **Get-Service** para obter os serviços no computador.
Um operador de pipeline (|) envia os serviços para o cmdlet **Where-Object** , que seleciona os serviços cuja propriedade **dependservices** não é nula.

Outro operador de pipeline envia os resultados para o cmdlet Format-List.
O comando usa seu parâmetro *Property* para exibir o nome do serviço, o nome dos serviços dependentes e uma propriedade calculada que exibe o número de serviços dependentes que cada serviço tem.

### Exemplo 8: classificar serviços por valor de propriedade

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

Esse comando mostra que quando você classifica os serviços em ordem crescente pelo valor de sua propriedade **status** , os serviços interrompidos aparecem antes de executar os serviços.
Isso acontece porque o valor de status é uma enumeração, na qual Stopped tem um valor de 1, e a execução tem um valor de 4.

Para listar os serviços em execução primeiro, use o parâmetro *decrescente* do cmdlet Sort-Object.

### Exemplo 9: obter serviços em vários computadores

```powershell
Get-Service -Name "WinRM" -ComputerName "localhost", "Server01", "Server02" |
 Format-Table -Property MachineName, Status, Name, DisplayName -auto
```

```Output
MachineName    Status  Name  DisplayName
------------   ------  ----  -----------
localhost      Running WinRM Windows Remote Management (WS-Management)
Server01       Running WinRM Windows Remote Management (WS-Management)
Server02       Running WinRM Windows Remote Management (WS-Management)
```

Esse comando usa o cmdlet **Get-Service** para executar um comando Get-Service WinRM em dois computadores remotos e no computador local ("localhost").

O comando é executado nos computadores remotos e os resultados são retornados para o computador local.
Um operador de pipeline (|) envia os resultados para o cmdlet **Format-Table** , que formata os serviços como uma tabela.
O comando **Format-Table** usa o parâmetro *Property* para especificar as propriedades exibidas na tabela, incluindo a propriedade **MachineName** .

### Exemplo 10: obter os serviços dependentes de um serviço

```powershell
Get-Service "WinRM" -RequiredServices
```

Esse comando obtém os serviços que o serviço WinRM necessita.

O comando retorna o valor da propriedade **ServicesDependedOn** do serviço.

### Exemplo 11: obter um serviço por meio do operador de pipeline

```powershell
"WinRM" | Get-Service
```

Esse comando inicia o serviço WinRM no computador local.
Este exemplo mostra que é possível canalizar uma cadeia de caracteres de nome de serviço (entre aspas) para **Get-Service** .

## PARAMETERS

### -ComputerName

Obtém os serviços em execução nos computadores especificados.
O padrão é o computador local.

Digite o nome NetBIOS, um endereço IP ou um FQDN (nome de domínio totalmente qualificado) de um computador remoto.
Para especificar o computador local, digite o nome do computador, um ponto (.) ou localhost.

Esse parâmetro não depende da comunicação remota do Windows PowerShell.
Você pode usar o parâmetro *ComputerName* de **Get-Service** mesmo se o computador não estiver configurado para executar comandos remotos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DependentServices

Indica que esse cmdlet obtém apenas os serviços que dependem do serviço especificado.

Por padrão, esse cmdlet obtém todos os serviços.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: DS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName

Especifica, como uma matriz de cadeia de caracteres, os nomes de exibição dos serviços a serem recuperados.
Caracteres curinga são permitidos.
Por padrão, esse cmdlet obtém todos os serviços no computador.

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
O valor desse parâmetro qualifica o parâmetro de *nome* .
Insira um elemento Name ou padrão, como "*s".
Caracteres curinga são permitidos.

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

Especifica, como uma matriz de cadeia de caracteres, um serviço ou serviços que esse cmdlet inclui na operação.
O valor desse parâmetro qualifica o parâmetro de *nome* .
Insira um elemento Name ou padrão, como "*s".
Caracteres curinga são permitidos.

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

Especifica objetos **ServiceController** que representam os serviços a serem recuperados.
Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.
Você também pode canalizar um objeto de serviço para esse cmdlet.

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

Especifica os nomes de serviço dos serviços a serem recuperados.
Caracteres curinga são permitidos.
Por padrão, esse cmdlet obtém todos os serviços no computador.

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

Indica que esse cmdlet obtém apenas os serviços que esse serviço requer.

Esse parâmetro Obtém o valor da propriedade **ServicesDependedOn** do serviço.
Por padrão, esse cmdlet obtém todos os serviços.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: SDO, ServicesDependedOn

Required: False
Position: Named
Default value: None
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

Você também pode se referir ao **Get-Service** por seu alias interno, "GSV". Para obter mais informações, consulte about_Aliases.

Esse cmdlet pode exibir serviços somente quando o usuário atual tem permissão para vê-los.
Se esse cmdlet não exibir serviços, talvez você não tenha permissão para vê-los.

Para localizar o nome do serviço e o nome de exibição de cada serviço em seu sistema, digite `Get-Service` .
Os nomes de serviço são exibidos na coluna Name, e os nomes de exibição aparecem na coluna DisplayName.

Quando você classifica em ordem crescente por valor de status, os serviços "Stopped" aparecem antes dos serviços "Running".
A propriedade de Status de um serviço é um valor enumerado onde os nomes de status representam valores inteiros.
A classificação baseia-se no valor do inteiro, não no nome.
"Running" aparece antes de "Stopped" porque "Stopped" tem o valor "1" e "Running" tem o valor "4".

## LINKS RELACIONADOS

[New-Service](New-Service.md)

[Restart-Service](Restart-Service.md)

[Resume-Service](Resume-Service.md)

[Set-Service](Set-Service.md)

[Start-Service](Start-Service.md)

[Stop-Service](Stop-Service.md)

[Suspend-Service](Suspend-Service.md)
