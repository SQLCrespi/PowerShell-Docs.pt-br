---
external help file: Microsoft.Powershell.Workflow.ServiceCore.dll-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSWorkflow
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/new-psworkflowexecutionoption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSWorkflowExecutionOption
ms.openlocfilehash: db5d19396f555a41ad14552823c57f3b11c79321
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93194906"
---
# New-PSWorkflowExecutionOption

## SINOPSE

Cria um objeto que contém opções de configuração de sessão para sessões de fluxo de trabalho.

## SYNTAX

```
New-PSWorkflowExecutionOption [-PersistencePath <String>] [-MaxPersistenceStoreSizeGB <Int64>]
 [-PersistWithEncryption] [-MaxRunningWorkflows <Int32>] [-AllowedActivity <String[]>]
 [-OutOfProcessActivity <String[]>] [-EnableValidation] [-MaxDisconnectedSessions <Int32>]
 [-MaxConnectedSessions <Int32>] [-MaxSessionsPerWorkflow <Int32>] [-MaxSessionsPerRemoteNode <Int32>]
 [-MaxActivityProcesses <Int32>] [-ActivityProcessIdleTimeoutSec <Int32>]
 [-RemoteNodeSessionIdleTimeoutSec <Int32>] [-SessionThrottleLimit <Int32>]
 [-WorkflowShutdownTimeoutMSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION

O `New-PSWorkflowExecutionOption` cmdlet cria um objeto que contém opções avançadas para configurações de sessão de fluxo de trabalho, que são as configurações de sessão criadas para executar fluxos de trabalho de fluxo de trabalho do Windows PowerShell.

Você pode usar o objeto **PSWorkflowExecutionOption** que `New-PSWorkflowExecutionOption` gera como o valor do parâmetro **SessionTypeOption** de cmdlets que criam ou alteram uma configuração de sessão, como os `Register-PSSessionConfiguration` `Set-PSSessionConfiguration` cmdlets e.

Cada parâmetro do `New-PSWorkflowExecutionOption` cmdlet representa uma propriedade do objeto de opção de configuração de sessão de fluxo de trabalho que o cmdlet retorna. Se um parâmetro for omitido, o cmdlet cria o objeto com um valor padrão para a propriedade.

O `New-PSWorkflowExecutionOption` cmdlet faz parte do recurso de fluxo de trabalho do Windows PowerShell.

Também é possível adicionar parâmetros comuns de fluxo de trabalho para esse comando. Para obter mais informações sobre parâmetros comuns de fluxo de trabalho, consulte [about_WorkflowCommonParameters](About/about_WorkflowCommonParameters.md).

Este cmdlet é introduzido no Windows PowerShell 3.0.

## EXEMPLOS

### Exemplo 1: criar um objeto de opções de fluxo de trabalho

```powershell
New-PSWorkflowExecutionOption -MaxSessionsPerWorkflow 10 -MaxDisconnectedSessions 200
```

```Output
SessionThrottleLimit                       : 100
PersistencePath                            : C:\Users\User01\AppData\Local\Microsoft\Windows\PowerShell\WF\PS
MaxPersistenceStoreSizeGB                  : 10
PersistWithEncryption                      : False
MaxRunningWorkflows                        : 30
AllowedActivity                            : {PSDefaultActivities}
OutOfProcessActivity                       : {InlineScript}
EnableValidation                           : True
MaxDisconnectedSessions                    : 200
MaxConnectedSessions                       : 100
MaxSessionsPerWorkflow                     : 10
MaxSessionsPerRemoteNode                   : 5
MaxActivityProcesses                       : 5
ActivityProcessIdleTimeoutSec              : 60
RemoteNodeSessionIdleTimeoutSec            : 60
WorkflowShutdownTimeoutMSec                : 500
```

Esse comando usa o `New-PSWorkflowExecutionOption` cmdlet para aumentar o valor de **MaxSessionsPerWorkflow** para 10 e diminuir o valor de **MaxDisconnectedSessions** para 200.

A saída mostra o objeto que o cmdlet retorna.

### Exemplo 2: usando um objeto de opções de fluxo de trabalho

```powershell
# Create a Workflow Options object and save it in a variable
$wo = New-PSWorkflowExecutionOption -MaxSessionsPerWorkflow 10 -MaxDisconnectedSessions 200
# Create the ITWorkflow session configuration
Register-PSSessionConfiguration -Name ITWorkflows -SessionTypeOption $wo -Force
```

```Output
    WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin

Type            Keys                                Name
----            ----                                ----
Container       {Name=ITWorkflows}                  ITWorkflows
```

```powershell
Get-PSSessionConfiguration ITWorkflows | Format-List -Property *
```

```Output
Architecture                  : 64
Filename                      : %windir%\system32\pwrshplugin.dll
ResourceUri                   : http://schemas.microsoft.com/powershell/ITWorkflows
MaxConcurrentCommandsPerShell : 1000
allowedactivity               : PSDefaultActivities
UseSharedProcess              : false
ProcessIdleTimeoutSec         : 0
xmlns                         : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
MaxConcurrentUsers            : 5
maxsessionsperworkflow        : 10
lang                          : en-US
sessionconfigurationdata      : <SessionConfigurationData>
                                    <Param Name='PrivateData'>
                                        <PrivateData>
                                            <ParamName='enablevalidation' Value='True'/>
                                            <Param Name='allowedactivity'Value='PSDefaultActivities' />
                                            <Param Name='outofprocessactivity' Value='InlineScript'/>
                                            <Param Name='maxdisconnectedsessions' Value='200' />
                                            <ParamName='maxsessionsperworkflow' Value='10'/>
                                        </PrivateData>
                                    </Param>
                                </SessionConfigurationData>
SupportsOptions               : true
ExactMatch                    : true
RunAsUser                     :
IdleTimeoutms                 : 7200000
PSVersion                     : 3.0
OutputBufferingMode           : Block
AutoRestart                   : false
MaxShells                     : 25
MaxMemoryPerShellMB           : 1024
MaxIdleTimeoutms              : 43200000
outofprocessactivity          : InlineScript
SDKVersion                    : 2
Name                          : ITWorkflows
XmlRenderingType              : text
Capability                    : {Shell}
RunAsPassword                 :
MaxProcessesPerShell          : 15
enablevalidation              : True
Enabled                       : True
maxdisconnectedsessions       : 200
MaxShellsPerUser              : 25
Permission                    :
```

Os dois primeiros comandos criam um novo objeto de configuração de sessão e o registra.

O terceiro comando usa o `Get-PSSessionConfiguration` cmdlet para obter a configuração de sessão ITWorkflows e o `Format-List` para exibir todas as propriedades da configuração de sessão em uma lista. A saída mostra que as opções de fluxo de trabalho na configuração da sessão. Especificamente, a configuração de sessão tem uma propriedade **MaxSessionsPerWorkflow** com um valor de 10 e uma propriedade **MaxDisconnectedSessions** com um valor de 200.

## PARAMETERS

### -ActivityProcessIdleTimeoutSec

Determina por quanto tempo cada processo do host de atividade é mantido depois que o processo se torna ocioso. Quando o intervalo expira, o processo é encerrado.

Insira um valor em segundos. O valor padrão é 60.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 60
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowedActivity

Especifica as atividades que têm permissão para serem executadas na sessão.

Insira nomes de atividades qualificadas para namespace, como `Microsoft.Powershell.HyperV.Activities.*` .
Há suporte para caracteres curinga. O valor padrão, **PSDefaultActivities** , inclui as atividades internas do Windows Workflow Foundation e as atividades que representam os cmdlets do Windows PowerShell Core.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: PSDefaultActivities
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableValidation

Verifica se todas as atividades de fluxo de trabalho na sessão estão incluídas na lista de atividades permitidas.

O valor padrão é True. Para desabilitar a validação, use o seguinte formato de comando: `-EnableValidation:$false` .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxActivityProcesses

Especifica o número máximo de processos que podem ser criados na sessão para oferecer suporte a atividades de fluxo de trabalho. O valor padrão é 5.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxConnectedSessions

Especifica o número máximo de sessões remotas que estão em um estado operacional. Essa cota é aplicada as sessões conectadas a todos os nós remotos (computadores de destino). O valor padrão é 100.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxDisconnectedSessions

Especifica o número máximo de sessões remotas que estão em um estado desconectado. Essa cota é aplicada as sessões conectadas a todos os nós remotos (computadores de destino). O valor padrão é 1000.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1000
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxPersistenceStoreSizeGB

Especifica o tamanho máximo, em gigabytes, do repositório de persistência alocada para fluxos de trabalho executados na sessão. Quando o tamanho for excedido, o repositório de persistência é expandido para salvar todos os dados persistentes, mas um aviso é exibido e uma mensagem é gravada no log de eventos do fluxo de trabalho. O valor padrão é 10.

O repositório de persistência contém dados para todos os trabalhos de fluxo de trabalho. A capacidade de armazenar dados permite que os trabalhos continue sem perder o estado.

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 10
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxRunningWorkflows

Especifica o número máximo de fluxos de trabalho que podem ser executados na sessão simultaneamente.
O valor padrão é 30.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 30
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxSessionsPerRemoteNode

Especifica o número máximo de sessões que podem ser conectados a cada nó remoto (computador de destino). O valor padrão é 5.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxSessionsPerWorkflow

Especifica o número máximo de sessões que podem ser criadas para oferecer suporte a cada fluxo de trabalho. O valor padrão é 5.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutOfProcessActivity

Determina quais atividades têm permissão (especificadas pelo parâmetro **AllowedActivities** ) para serem executadas fora do processo. O valor padrão é **InlineScript** .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: InlineScript
Accept pipeline input: False
Accept wildcard characters: False
```

### -PersistencePath

Especifica o local no disco onde o estado de fluxo de trabalho e os dados são armazenados. Armazenar o estado de fluxo de trabalho e dados permite que os fluxos de trabalho sejam suspensos e retomados, e recuperados de interrupções e falhas de rede.

O valor padrão é `$env:LocalAppData\Microsoft\Windows\PowerShell\WF\PS`.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -PersistWithEncryption

Indica que o fluxo de trabalho criptografa os dados no repositório de persistência. Considere utilizar esse recurso ao armazenar dados de persistência em um compartilhamento de rede.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $env:LocalAppData\Microsoft\Windows\PowerShell\WF\PS
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoteNodeSessionIdleTimeoutSec

Especifica quanto tempo uma sessão que está conectada a um nó remoto (computador de destino) é mantida se estiver ociosa.

Insira um valor em segundos. O valor padrão é 60.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 60
Accept pipeline input: False
Accept wildcard characters: False
```

### -SessionThrottleLimit

Especifica quantas operações são criadas para oferecer suporte a todos os fluxos de trabalho iniciados na sessão. O valor padrão é 100.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkflowShutdownTimeoutMSec

Especifica quanto tempo a sessão é mantida depois que todos os fluxos de trabalho na sessão são suspensos à força. Quando o tempo limite expira, o Windows PowerShell encerra a sessão, mesmo que todos os fluxos de trabalho ainda não tenham sido suspensos.

Insira um valor em milissegundos.
O valor padrão é 500.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 500
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### Nenhum

Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### Microsoft. PowerShell. Commands. PSWorkflowExecutionOption

## OBSERVAÇÕES

Quando o valor máximo definido por uma opção for excedido, o comando para criar outra instância na sessão falha, a menos que esteja indicado na descrição do parâmetro. Por exemplo, se o valor de **MaxConnectedSessions** é 100. Falha no comando para criar a sessão de 101 para um nó remoto (computador de destino).

As propriedades de um objeto de configuração de sessão variam de acordo com as opções definidas para a configuração da sessão e os valores dessas opções. Além disso, as configurações de sessão que usam um arquivo de configuração de sessão têm propriedades adicionais.

Em particular, as propriedades de configurações de sessão que incluem um objeto **PSWorkflowExecutionOptions** variam de acordo com os valores de opção de fluxo de trabalho. Por exemplo, se a configuração de sessão inclui um objeto **PSWorkflowExecutionOptions** que define um valor não padrão para a propriedade **SessionThrottleLimit** , a configuração da sessão tem uma propriedade **SessionThrottleLimit** . Caso contrário, isso não acontece.

## LINKS RELACIONADOS

[New-PSWorkflowSession](New-PSWorkflowSession.md)

[about_Workflows](../PSWorkflow/About/about_Workflows.md)

[about_WorkflowCommonParameters](About/about_WorkflowCommonParameters.md)
