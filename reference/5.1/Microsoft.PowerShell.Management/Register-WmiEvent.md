---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 07/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/register-wmievent?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-WmiEvent
ms.openlocfilehash: be29ce6376dea7686c0c063cc5528fbc7d840a9d
ms.sourcegitcommit: 41b072f0b6046d619b0e7f758982783fb648a3d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/31/2020
ms.locfileid: "93195096"
---
# Register-WmiEvent

## SINOPSE
Assina um evento de WMI (Instrumentação de Gerenciamento do Windows).

## SYNTAX

### classe (padrão)

```
Register-WmiEvent [-Namespace <String>] [-Credential <PSCredential>] [-ComputerName <String>] [-Class] <String>
 [-Timeout <Int64>] [[-SourceIdentifier] <String>] [[-Action] <ScriptBlock>] [-MessageData <PSObject>]
 [-SupportEvent] [-Forward] [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

### Consulta

```
Register-WmiEvent [-Namespace <String>] [-Credential <PSCredential>] [-ComputerName <String>] [-Query] <String>
 [-Timeout <Int64>] [[-SourceIdentifier] <String>] [[-Action] <ScriptBlock>] [-MessageData <PSObject>]
 [-SupportEvent] [-Forward] [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

## DESCRIPTION

O `Register-WmiEvent` cmdlet assina os eventos de instrumentação de gerenciamento do Windows (WMI) no computador local ou em um computador remoto.

Quando o evento WMI assinado é gerado, ele é adicionado à fila de eventos de sua sessão local, mesmo se o evento ocorrer em um computador remoto. Para obter eventos na fila de eventos, use o `Get-Event` cmdlet.

Você pode usar os parâmetros de `Register-WmiEvent` para assinar eventos em computadores remotos e especificar os valores de propriedade dos eventos que podem ajudá-lo a identificar o evento na fila. Você também pode usar o parâmetro **Action** para especificar ações a serem tomadas quando um evento assinado for gerado.

Quando você se inscreve em um evento, um assinante de evento é adicionado à sua sessão. Para obter os assinantes de evento na sessão, use o `Get-EventSubscriber` cmdlet. Para cancelar a assinatura, use o `Unregister-Event` cmdlet, que exclui o Assinante de evento da sessão.

Novos cmdlets do CIM (modelo CIM), introduzidos no Windows PowerShell 3,0, executam as mesmas tarefas que os cmdlets do WMI. Os cmdlets do CIM estão em conformidade com os padrões do WSMan (WS-Management) e com o padrão CIM, que permite que os cmdlets usem as mesmas técnicas para gerenciar computadores que executam o sistema operacional Windows e aqueles que executam outros sistemas operacionais. Em vez de usar `Register-WmiEvent` , considere usar o cmdlet [Register-CimIndicationEvent](../cimcmdlets/register-cimindicationevent.md) .

## EXEMPLOS

### Exemplo 1: assinar eventos gerados por uma classe

Esse comando assina os eventos gerados pela classe **Win32_ProcessStartTrace** . Esta classe dispara um evento sempre que um processo é iniciado.

```powershell
Register-WmiEvent -Class 'Win32_ProcessStartTrace' -SourceIdentifier "ProcessStarted"
```

### Exemplo 2: assinar eventos de criação para um processo

Esse comando usa uma consulta para assinar eventos de criação de instância Win32_process.

```powershell
$wmiParameters = @{
  Query = "select * from __instancecreationevent within 5 where targetinstance isa 'win32_process'"
  SourceIdentifier = "WMIProcess"
  MessageData = "Test 01"
  TimeOut = 500
}
Register-WmiEvent @wmiParameters
```

### Exemplo 3: usar uma ação para responder a um evento

Este exemplo mostra como usar uma ação para responder a um evento. Nesse caso, quando um processo é iniciado, todos os `Start-Process` comandos na sessão atual são gravados em um arquivo XML.

```powershell
$action = { Get-History | where { $_.commandline -like "*start-process*" } | export-cliXml "commandHistory.clixml" }
Register-WmiEvent -Class 'Win32_ProcessStartTrace' -SourceIdentifier "ProcessStarted" -Action $action
```

```Output
Id    Name            State      HasMoreData   Location  Command
--    ----            -----      -----------   --------  -------
1     ProcessStarted  NotStarted False                   get-history | where {...
```

Quando você usa o parâmetro **Action** , o `Register-WmiEvent` retorna um trabalho em segundo plano que representa a ação do evento. Você pode usar os cmdlets de **trabalho** , como `Get-Job` e `Receive-Job` , para gerenciar o trabalho de evento.

Para obter mais informações, consulte about_Jobs.

### Exemplo 4: registrar-se para eventos em um computador remoto

Este exemplo registra eventos no computador remoto Server01.

```powershell
Register-WmiEvent -Class 'Win32_ProcessStartTrace' -SourceIdentifier "Start" -Computername Server01
Get-Event -SourceIdentifier "Start"
```

WMI retorna os eventos ao computador local e os armazena na fila de eventos da sessão atual. Para recuperar os eventos, execute um `Get-Event` comando local.

## PARAMETERS

### -Action

Especifica comandos que lidam com os eventos. Os comandos no parâmetro **Action** são executados quando um evento é gerado em vez de enviar o evento para a fila de eventos. Coloque os comandos entre chaves ( `{}` ) para criar um bloco de script.

O valor da **ação** pode incluir as `$Event` `$EventSubscriber` `$Sender` `$EventArgs` variáveis automáticas,,, e `$Args` , que fornecem informações sobre o evento para o bloco de script de **ação** . Para obter mais informações, consulte about_Automatic_Variables.

Quando você especifica uma ação, `Register-WmiEvent` o retorna um objeto de trabalho de evento que representa essa ação. Você pode usar os cmdlets que contêm o substantivo do **trabalho** (os cmdlets de **trabalho** ) para gerenciar o trabalho de evento.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: 101
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Classe

Especifica o evento que você está assinando. Insira a classe WMI que gera os eventos. Um parâmetro de **classe** ou de **consulta** é necessário em cada comando.

```yaml
Type: System.String
Parameter Sets: class
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Especifica o nome do computador no qual o comando é executado. O padrão é o computador local.

Digite o nome da NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado do computador. Para especificar o computador local, digite o nome do computador, um ponto ( `.` ) ou localhost.

Esse parâmetro não depende da comunicação remota do Windows PowerShell. Você pode usar o parâmetro **ComputerName** , mesmo que seu computador não esteja configurado para executar comandos remotos.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Especifica uma conta de usuário que tem permissão para executar esta ação. O padrão é o usuário atual.

Digite um nome de usuário, como User01 ou Domínio01 \ Usuário01, ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet. Se você digitar um nome de usuário, esse cmdlet solicitará uma senha.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Avançar

Indica que esse cmdlet envia eventos para essa assinatura para a sessão no computador local.
Utilize esse parâmetro ao registrar eventos em um computador remoto ou em uma sessão remota.

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

### -MaxTriggerCount

Especifica a contagem máxima de gatilhos.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MessageData

Especifica dados adicionais a serem associados essa assinatura do evento. O valor desse parâmetro é exibido na propriedade **MessageData** de todos os eventos associados a essa assinatura.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Namespace

Especifica o namespace da classe de WMI.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Query

Especifica uma consulta em linguagem WQL (WQL) que identifica a classe de evento WMI, como: `select * from __InstanceDeletionEvent` .

```yaml
Type: System.String
Parameter Sets: query
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceIdentifier

Especifica um nome para a assinatura selecionada. O nome que você selecionar deve ser exclusivo na sessão atual. O valor padrão é o GUID que o Windows PowerShell atribui.

O valor desse parâmetro aparece no valor da propriedade **SourceIdentifier** do objeto assinante e de todos os objetos de evento associados a esta assinatura.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 100
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SupportEvent

Indica que esse cmdlet oculta a assinatura do evento. Utilize esse parâmetro quando a assinatura atual faz parte de um mecanismo de registro de evento mais complexo e não deve ser descoberto independentemente.

Para exibir ou cancelar uma assinatura que foi criada usando o parâmetro **SupportEvent** , especifique o parâmetro **Force** dos `Get-EventSubscriber` `Unregister-Event` cmdlets e.

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

### -Tempo limite

Especifica por quanto tempo o Windows PowerShell aguarda até que esse comando seja concluído.

O valor padrão, 0 (zero), significa que não há nenhum tempo limite, e faz com que o Windows PowerShell aguarde indefinidamente.

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases: TimeoutMSec

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

Não é possível transferir objetos para esse cmdlet.

## SAÍDAS

### Nenhum

Este cmdlet não gera saída.

## OBSERVAÇÕES

Para usar esse cmdlet no Windows Vista ou em uma versão posterior do sistema operacional Windows, inicie o Windows PowerShell usando a opção Executar como administrador.

Eventos, assinaturas de evento e a fila de eventos existem apenas na sessão atual. Se você fechar a sessão atual, a fila de eventos será descartada e a inscrição do evento será cancelada.

## LINKS RELACIONADOS
