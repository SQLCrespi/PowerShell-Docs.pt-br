---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/20/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/register-cimindicationevent?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-CimIndicationEvent
ms.openlocfilehash: 11690649b2e7918785eb39c81b2099ad55e49ef5
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193420"
---
# Register-CimIndicationEvent

## SINOPSE
Assina indicações usando uma expressão de filtro ou uma expressão de consulta.

## SYNTAX

### ClassNameComputerSet (padrão)

```
Register-CimIndicationEvent [-Namespace <String>] [-ClassName] <String>
 [-OperationTimeoutSec <UInt32>] [-ComputerName <String>] [[-SourceIdentifier] <String>]
 [[-Action] <ScriptBlock>] [-MessageData <PSObject>] [-SupportEvent] [-Forward]
 [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

### ClassNameSessionSet

```
Register-CimIndicationEvent [-Namespace <String>] [-ClassName] <String>
 [-OperationTimeoutSec <UInt32>] -CimSession <CimSession> [[-SourceIdentifier] <String>]
 [[-Action] <ScriptBlock>] [-MessageData <PSObject>] [-SupportEvent] [-Forward]
 [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

### QueryExpressionSessionSet

```
Register-CimIndicationEvent [-Namespace <String>] [-Query] <String> [-QueryDialect <String>]
 [-OperationTimeoutSec <UInt32>] -CimSession <CimSession> [[-SourceIdentifier] <String>]
 [[-Action] <ScriptBlock>] [-MessageData <PSObject>] [-SupportEvent] [-Forward]
 [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

### QueryExpressionComputerSet

```
Register-CimIndicationEvent [-Namespace <String>] [-Query] <String> [-QueryDialect <String>]
 [-OperationTimeoutSec <UInt32>] [-ComputerName <String>] [[-SourceIdentifier] <String>]
 [[-Action] <ScriptBlock>] [-MessageData <PSObject>] [-SupportEvent] [-Forward]
 [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

## DESCRIPTION

O `Register-CimIndicationEvent` cmdlet assina indicações usando um nome de classe de indicação ou uma expressão de consulta. Use o parâmetro **SourceIdentifier** para fornecer um nome para a assinatura.

Esse cmdlet retorna um objeto **EventSubscription** . Você pode usar esse objeto para cancelar a assinatura.

## EXEMPLOS

### Exemplo 1: registrar os eventos gerados por uma classe

Este exemplo assina os eventos gerados pela classe chamada **Win32_ProcessStartTrace** . Esta classe dispara um evento sempre que um processo é iniciado.

```powershell
Register-CimIndicationEvent -ClassName 'Win32_ProcessStartTrace' -SourceIdentifier "ProcessStarted"
Get-Event -SourceIdentifier "ProcessStarted"
```

O `Get-Event` cmdlet obtém os eventos com a assinatura **ProcessStarted** . Para obter mais informações, consulte [Get-Event](../Microsoft.PowerShell.Utility/Get-Event.md).

> [!NOTE]
> Para este exemplo, você deve executar o PowerShell como administrador.

### Exemplo 2: registrar os eventos usando uma consulta

Este exemplo usa uma consulta para assinar um evento gerado sempre que há uma alteração na instância de uma classe chamada **Win32_LocalTime** .

```powershell
$query = "SELECT * FROM CIM_InstModification WHERE TargetInstance ISA 'Win32_LocalTime'"
Register-CimIndicationEvent -Query $query -SourceIdentifier "Timer"
```

### Exemplo 3: executar um script quando o evento chegar

Este exemplo mostra como usar uma ação em resposta a um evento. A variável `$action` contém o bloco de script para **ação** , que usa a `$event` variável para acessar o evento recebido do CIM.

```powershell
$action = {
  $name = $event.SourceEventArgs.NewEvent.ProcessName
  $id = $event.SourceEventArgs.NewEvent.ProcessId
  Write-Host -Object "New Process Started : Name = $name
 ID = $id"
}
Register-CimIndicationEvent -ClassName 'Win32_ProcessStartTrace' -SourceIdentifier "ProcessStarted" -Action $action
```

Para obter mais informações, consulte [Win32_ProcessStartTrace](/previous-versions/windows/desktop/krnlprov/win32-processstarttrace).

### Exemplo 4: registrar os eventos em um computador remoto

Este exemplo assina eventos em um computador remoto chamado **SERVER01** . Os eventos recebidos do servidor CIM são armazenados na fila de eventos na sessão atual do PowerShell e, em seguida, executam um local `Get-Event` para recuperar os eventos.

```powershell
Register-CimIndicationEvent -ClassName 'Win32_ProcessStartTrace' -SourceIdentifier "ProcessStarted" -ComputerName Server01
Get-Event -SourceIdentifier "ProcessStarted"
```

## PARAMETERS

### -Action

Especifica os comandos que manipulam os eventos. Os comandos especificados por esse parâmetro são executados quando um evento é gerado, em vez de enviar o evento para a fila de eventos. Coloque os comandos entre chaves ( `{}` ) para criar um bloco de script.

O bloco de script especificado com **Action** pode incluir `$Event` as `$EventSubscriber` `$Sender` variáveis automáticas,,, `$SourceEventArgs` e `$SourceArgs` , que fornecem informações sobre o evento para o bloco de script de **ação** . Para obter mais informações, consulte [sobre variáveis automáticas](../microsoft.powershell.core/about/about_automatic_variables.md).

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession

Executa o comando usando a sessão CIM especificada. Insira uma variável que contenha a sessão CIM ou um comando que cria ou obtém a sessão CIM, como os `New-CimSession` `Get-CimSession` cmdlets ou. Para obter mais informações, consulte [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).

```yaml
Type: Microsoft.Management.Infrastructure.CimSession
Parameter Sets: ClassNameSessionSet, QueryExpressionSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClassName

Especifica a classe de indicação à qual você está se inscrevendo. Você pode usar o preenchimento com Tab para procurar a lista de classes, porque o PowerShell Obtém uma lista de classes do servidor WMI local para fornecer uma lista de nomes de classe.

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Especifica o nome do computador no qual você deseja executar a operação CIM. Você pode especificar um FQDN (nome de domínio totalmente qualificado), um nome NetBIOS ou um endereço IP.

Se você especificar esse parâmetro, o cmdlet criará uma sessão temporária para o computador especificado usando o protocolo WsMan. Se você não especificar esse parâmetro, o cmdlet executará a operação no sistema local usando Component Object Model (COM).

Se várias operações estiverem sendo executadas no mesmo computador, conecte-se usando uma sessão CIM para melhorar o desempenho.

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, QueryExpressionComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Avançar

Indica que os eventos para a assinatura são encaminhados para a sessão no computador local. Utilize esse parâmetro ao registrar eventos em um computador remoto ou em uma sessão remota.

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

Para indicar que o registro do Assinante deve ser cancelado automaticamente após ser disparado por horários especificados. Se o valor for igual ou menor que zero, não haverá limite para o número de vezes que o evento pode ser disparado sem ter sido cancelado.

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

Especifica os dados adicionais a serem associados a essa assinatura de evento. O valor desse parâmetro é exibido na propriedade **MessageData** de todos os eventos associados a essa assinatura.

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

Especifica o namespace para a operação CIM. O namespace padrão é **root/cimv2** . Você pode usar o preenchimento com Tab para navegar na lista de namespaces, pois o PowerShell Obtém uma lista de namespaces do servidor WMI local para fornecer a lista de namespaces.

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

Especifica uma consulta a ser executada no servidor CIM. Se o valor especificado contiver aspas duplas `"` , aspas simples `'` ou uma barra invertida `\` , você deverá escapar desses caracteres prefixando-os com o caractere de barra invertida. Se o valor especificado usar o operador LIKE WQL, você deverá escapar os caracteres a seguir, colocando-os entre colchetes `[]` : percentual `%` , sublinhado `_` ou colchete de abertura `[` .

```yaml
Type: System.String
Parameter Sets: QueryExpressionSessionSet, QueryExpressionComputerSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -QueryDialect

Especifica a linguagem de consulta usada para o parâmetro de **consulta** . Os valores aceitáveis para esse parâmetro são: **WQL** ou **CQL** . O valor padrão é **WQL** .

```yaml
Type: System.String
Parameter Sets: QueryExpressionSessionSet, QueryExpressionComputerSet
Aliases:

Required: False
Position: Named
Default value: WQL
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceIdentifier

Especifica um nome para a assinatura. O nome especificado deve ser exclusivo na sessão atual. O valor padrão é um GUID atribuído pelo PowerShell. Esse valor aparece no valor da propriedade **SourceIdentifier** do objeto de assinante e de todos os objetos de evento associados a essa assinatura.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SupportEvent

Indica que a assinatura do evento está oculta. Utilize esse parâmetro quando a assinatura atual faz parte de um mecanismo de registro de evento mais complexo e não deve ser descoberto independentemente.

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Esse cmdlet não aceita nenhum objeto de entrada.

## SAÍDAS

### System.Object

Esse cmdlet gera um objeto **EventSubscription** .

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Get-Event](../microsoft.powershell.utility/get-event.md)

[Remove-Event](../microsoft.powershell.utility/remove-event.md)

[Unregister-Event](../microsoft.powershell.utility/unregister-event.md)

[Write-Host](../microsoft.powershell.utility/write-host.md)

[Get-CimSession](Get-CimSession.md)

[New-CimSession](New-CimSession.md)
