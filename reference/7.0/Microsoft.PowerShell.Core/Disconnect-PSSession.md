---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disconnect-pssession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disconnect-PSSession
ms.openlocfilehash: b3ee9ce8f699e66a091a017eb8c1b0c49f1b7636
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93194962"
---
# Disconnect-PSSession

## SINOPSE
Desconecta-se de uma sessão.

## SYNTAX

### Sessão (padrão)

```
Disconnect-PSSession [-Session] <PSSession[]> [-IdleTimeoutSec <Int32>]
 [-OutputBufferingMode <OutputBufferingMode>] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Name

```
Disconnect-PSSession [-IdleTimeoutSec <Int32>] [-OutputBufferingMode <OutputBufferingMode>]
 [-ThrottleLimit <Int32>] -Name <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InstanceId

```
Disconnect-PSSession [-IdleTimeoutSec <Int32>] [-OutputBufferingMode <OutputBufferingMode>]
 [-ThrottleLimit <Int32>] -InstanceId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ID

```
Disconnect-PSSession [-IdleTimeoutSec <Int32>] [-OutputBufferingMode <OutputBufferingMode>]
 [-ThrottleLimit <Int32>] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Disconnect-PSSession` cmdlet desconecta uma sessão do PowerShell ("PSSession"), como uma iniciada usando o `New-PSSession` cmdlet, da sessão atual. Como resultado, a PSSession está em um estado desconectado. Você pode conectar-se à PSSession desconectada por meio da sessão atual ou de outra sessão no computador local ou em um computador diferente.

O `Disconnect-PSSession` cmdlet desconecta apenas as PSSessions abertas que estão conectadas à sessão atual. `Disconnect-PSSession` Não é possível desconectar PSSessions rompidos ou fechados, ou PSSessions interativas iniciadas usando o `Enter-PSSession` cmdlet, e não pode desconectar PSSessions que estão conectadas a outras sessões.

Para reconectar-se a uma PSSession desconectada, use os `Connect-PSSession` `Receive-PSSession` cmdlets ou.

Quando uma PSSession é desconectada, os comandos na PSSession continuam em execução até que sejam concluídos, a menos que a PSSession expire ou os comandos na PSSession sejam bloqueados por um buffer de saída completo. Para alterar o tempo limite de inatividade, use o parâmetro **IdleTimeoutSec** . Para alterar o modo de buffer de saída, use o parâmetro **OutputBufferingMode** você também pode usar o parâmetro **InDisconnectedSession** do `Invoke-Command` cmdlet para executar um comando em uma sessão desconectada.

Para obter mais informações sobre o recurso de Sessões desconectadas, consulte [about_Remote_Disconnected_Sessions](./About/about_Remote_Disconnected_Sessions.md).

Este cmdlet é introduzido no Windows PowerShell 3.0.

## EXEMPLOS

### Exemplo 1-desconectar uma sessão por nome

Este comando desconecta UpdateSession PSSession no computador Server01 da sessão atual. O comando usa o parâmetro **Name** para identificar a PSSession.

```
PS> Disconnect-PSSession -Name UpdateSession
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
1  UpdateSession   Server01        Disconnected  Microsoft.PowerShell          None
```

A saída mostra que a tentativa de desconectar foi bem-sucedida. O estado da sessão é desconectado e a disponibilidade é nenhuma, o que indica que a sessão não está ocupada e pode ser reconectada.

### Exemplo 2-desconectar uma sessão de um computador específico

Este comando desconecta ITTask PSSession no computador Server12 da sessão atual.
A sessão ITTask foi criada na sessão atual e se conecta-se ao computador Server12. O comando usa o `Get-PSSession` cmdlet para obter a sessão e o `Disconnect-PSSession` cmdlet para desconectá-lo.

```
PS> Get-PSSession -ComputerName Server12 -Name ITTask |
  Disconnect-PSSession -OutputBufferingMode Drop -IdleTimeoutSec 86400
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
1  ITTask          Server12        Disconnected  ITTasks               None
```

O `Disconnect-PSSession` comando usa o parâmetro **OutputBufferingMode** para definir o modo de saída como **drop** . Essa configuração garante que o script em execução na sessão pode ser executado mesmo que o buffer de saída da sessão esteja cheio. Como o script grava a saída de um relatório em um compartilhamento de arquivos, outras saídas podem ser perdidas sem consequências.

O comando também usa o parâmetro **IdleTimeoutSec** para estender o tempo limite de inatividade da sessão para 24 horas. Essa configuração concede tempo para que esse e outros administradores reconectem-se à sessão para verificar se o script foi executado e solucionem os problemas necessários.

### Exemplo 3-usando várias PSSessions em vários computadores

Esta série de comandos mostra como o `Disconnect-PSSession` cmdlet pode ser usado em um cenário empresarial. Nesse caso, um novo técnico inicia um script em uma sessão em um computador remoto e encontra um problema. O técnico se desconecta da sessão para que um gerente mais experiente possa se conectar a ela e resolver o problema.

```
PS> $s = New-PSSession -ComputerName Srv1, Srv2, Srv30 -Name ITTask
PS> Invoke-Command $s -FilePath \\Server01\Scripts\Get-PatchStatus.ps1
PS> Get-PSSession -Name ITTask -ComputerName Srv1 | Disconnect-PSSession
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
1 ITTask           Srv1            Disconnected  Microsoft.PowerShell          None

PS> Get-PSSession -ComputerName Srv1, Srv2, Srv30 -Name ITTask
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Srv1            Disconnected  Microsoft.PowerShell          None
 2 ITTask          Srv2            Opened        Microsoft.PowerShell     Available
 3 ITTask          Srv30           Opened        Microsoft.PowerShell     Available

PS> Get-PSSession -ComputerName Srv1 -Name ITTask -Credential Domain01\User01
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Srv1            Disconnected  Microsoft.PowerShell          None

PS> $s = Connect-PSSession -ComputerName Srv1 -Name ITTask -Credential Domain01\User01
PS> Invoke-Command -Session $s {dir $home\Scripts\PatchStatusOutput.ps1}
PS> Invoke-Command -Session $s {mkdir $home\Scripts\PatchStatusOutput}
PS> Invoke-Command -Session $s -FilePath \\Server01\Scripts\Get-PatchStatus.ps1
PS> Disconnect-PSSession -Session $s
```

O técnico começa criando sessões em vários computadores remotos e executando um script em cada sessão. O primeiro comando usa o `New-PSSession` cmdlet para criar a sessão ITTask em três computadores remotos. O comando salva as sessões na variável $s. O segundo comando usa o parâmetro **FilePath** do `Invoke-Command` cmdlet para executar um script nas sessões na variável $s.

O script em execução no computador Srv1 gera erros inesperados. O técnico entra em contato com seu gerente e pede assistência. O gerente instrui o técnico a se desconectar da sessão para que possa investigar. O segundo comando usa o `Get-PSSession` cmdlet para obter a sessão ITTask no computador Srv1 e o `Disconnect-PSSession` cmdlet para desconectá-lo. Esse comando não afeta as sessões de ITTask nos outros computadores.

O terceiro comando usa o `Get-PSSession` cmdlet para obter as sessões de ITTask. A saída mostra que as sessões ITTask nos computadores Srv2 e Srv30 não foram afetadas pelo comando de desconectar.

O Gerenciador faz logon em seu computador doméstico, conecta-se à sua rede corporativa, inicia o PowerShell e usa o `Get-PSSession` cmdlet para obter a sessão ITTask no computador Srv1. Ele usa as credenciais do técnico para acessar a sessão.

Em seguida, o Gerenciador usa o `Connect-PSSession` cmdlet para se conectar à sessão ITTask no computador Srv1. O comando salva a sessão na variável $s.

O Gerenciador usa o `Invoke-Command` cmdlet para executar alguns comandos de diagnóstico na sessão na `$s` variável. Ele identifica que o script falhou porque não localizou um diretório necessário.
O Gerenciador usa a `MkDir` função para criar o diretório e, em seguida, ele reinicia o `Get-PatchStatus.ps1` script e se desconecta da sessão. O gerente relata suas descobertas ao técnico, sugere que ele se reconecte à sessão para concluir as tarefas e solicita que ele adicione um comando ao `Get-PatchStatus.ps1` script que cria o diretório necessário se ele não existir.

### Exemplo 4-alterar o valor de tempo limite para uma PSSession

Este exemplo mostra como corrigir o valor da propriedade **IdleTimeout** de uma sessão para que ela possa ser desconectada.

A propriedade do tempo limite de inatividade de uma sessão é crítica para sessões desconectadas, pois ela determina quanto tempo uma sessão desconectada é mantida antes de ser excluída. Você pode definir a opção de tempo limite de inatividade ao criar uma sessão e quando desconectar-se. Os valores padrão para o tempo limite de ociosidade de uma sessão são definidos na `$PSSessionOption` variável de preferência no computador local e na configuração de sessão no computador remoto. Valores definidos para a sessão têm precedência sobre valores definidos na configuração da sessão, porém os valores da sessão não podem exceder as cotas definidas na configuração da sessão, como o valor **MaxIdleTimeoutMs** .

```
PS> $Timeout = New-PSSessionOption -IdleTimeout 172800000
PS> $s = New-PSSession -Computer Server01 -Name ITTask -SessionOption $Timeout
PS> Disconnect-PSSession -Session $s
Disconnect-PSSession : The session ITTask cannot be disconnected because the specified
idle timeout value 172800(seconds) is either greater than the server maximum allowed
43200 (seconds) or less that the minimum allowed60(seconds).  Choose an idle time out
value that is within the allowed range and try again.

PS> Invoke-Command -ComputerName Server01 {Get-PSSessionConfiguration Microsoft.PowerShell} |
 Format-List -Property *

Architecture                  : 64
Filename                      : %windir%\system32\pwrshplugin.dll
ResourceUri                   : http://schemas.microsoft.com/powershell/microsoft.powershell
MaxConcurrentCommandsPerShell : 1000
UseSharedProcess              : false
ProcessIdleTimeoutSec         : 0
xmlns                         : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
MaxConcurrentUsers            : 5
lang                          : en-US
SupportsOptions               : true
ExactMatch                    : true
RunAsUser                     :
IdleTimeoutms                 : 7200000
PSVersion                     : 3.0
OutputBufferingMode           : Block
AutoRestart                   : false
SecurityDescriptorSddl        : O:NSG:BAD:P(A;;GA;;;BA)S:P(AU;FA;GA;;;WD)(AU;SA;GXGW;;;WD)
MaxMemoryPerShellMB           : 1024
MaxIdleTimeoutms              : 2147483647
Uri                           : http://schemas.microsoft.com/powershell/microsoft.powershell
SDKVersion                    : 2
Name                          : microsoft.powershell
XmlRenderingType              : text
Capability                    : {Shell}
RunAsPassword                 :
MaxProcessesPerShell          : 15
ParentResourceUri             : http://schemas.microsoft.com/powershell/microsoft.powershell
Enabled                       : true
MaxShells                     : 25
MaxShellsPerUser              : 25
Permission                    : BUILTIN\Administrators AccessAllowed
PSComputerName                : localhost
RunspaceId                    : aea84310-6dbf-4c21-90ac-13980039925a
PSShowComputerName            : True


PS> $s.Runspace.ConnectionInfo
ConnectionUri                     : http://Server01/wsman
ComputerName                      : Server01
Scheme                            : http
Port                              : 80
AppName                           : /wsman
Credential                        :
ShellUri                          : http://schemas.microsoft.com/powershell/Microsoft.PowerShell
AuthenticationMechanism           : Default
CertificateThumbprint             :
MaximumConnectionRedirectionCount : 5
MaximumReceivedDataSizePerCommand :
MaximumReceivedObjectSize         : 209715200
UseCompression                    : True
NoMachineProfile                  : False
ProxyAccessType                   : None
ProxyAuthentication               : Negotiate
ProxyCredential                   :
SkipCACheck                       : False
SkipCNCheck                       : False
SkipRevocationCheck               : False
NoEncryption                      : False
UseUTF16                          : False
OutputBufferingMode               : Drop
IncludePortInSPN                  : False
Culture                           : en-US
UICulture                         : en-US
OpenTimeout                       : 180000
CancelTimeout                     : 60000
OperationTimeout                  : 180000
IdleTimeout                       : 172800000

PS> Disconnect-PSSession $s -IdleTimeoutSec 43200
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 4 ITTask          Server01        Disconnected  Microsoft.PowerShell          None

PS> $s.Runspace.ConnectionInfo.IdleTimeout
43200000
```

O primeiro comando usa o `New-PSSessionOption` cmdlet para criar um objeto de opção de sessão. Ele usa o **IdleTimeout** para definir um tempo limite de inatividade de 48 horas (172.800.000 milissegundos). O comando salva o objeto de opção de sessão na variável $Timeout.

O segundo comando usa o `New-PSSession` cmdlet para criar a sessão ITTask no computador Server01. O comando salva a sessão na variável $s. O valor do parâmetro **SessionOption** é o tempo limite de inatividade de 48 horas na variável $Timeout.

O terceiro comando desconecta a sessão ITTask na variável $s. O comando falha porque o valor de tempo limite de inatividade da sessão excede a cota do **MaxIdleTimeoutMs** na configuração da sessão. Como o tempo limite de inatividade não é usado até que a sessão seja desconectada, essa violação pode não ser detectada enquanto a sessão estiver em uso.

O quarto comando usa o `Invoke-Command` cmdlet para executar um `Get-PSSessionConfiguration` comando para a configuração de sessão do Microsoft. PowerShell no computador Server01. O comando usa o `Format-List` cmdlet para exibir todas as propriedades da configuração de sessão em uma lista. A saída mostra que a propriedade **MaxIdleTimeoutMS** , que estabelece o valor máximo permitido de **IdleTimeout** para sessões que usam a configuração de sessão, é de 43,2 milhões milissegundos (12 horas).

O quinto comando obtém valores de opção da sessão na variável $s. Os valores de muitas opções de sessão são propriedades da propriedade **ConnectionInfo** da propriedade **runspace** da sessão. A saída mostra que o valor da propriedade **IdleTimeout** da sessão é de 172,8 milhões milissegundos (48 horas), o que viola a cota de **MaxIdleTimeoutMs** de 12 horas na configuração da sessão. Para resolver esse conflito, você pode usar o parâmetro **ConfigurationName** para selecionar uma configuração de sessão diferente ou usar o parâmetro **IdleTimeout** para reduzir o tempo limite de ociosidade da sessão.

O sexto comando desconecta a sessão. Ele usa o parâmetro **IdleTimeoutSec** para definir o tempo limite de ociosidade o máximo de 12 horas.

O sétimo comando obtém o valor da propriedade **IdleTimeout** da sessão desconectada, medido em milissegundos. A saída confirma que o comando teve êxito.

## PARAMETERS

### -Id

Desconecta-se de sessões com a ID de sessão especificada. Digite uma ou mais IDs (separadas por vírgulas) ou use o operador de intervalo (..) para especificar um intervalo de IDs.

Para obter a ID de uma sessão, use o `Get-PSSession` cmdlet. O ID de instância é armazenado na propriedade **ID** da PSSession.

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IdleTimeoutSec

Altera o valor de tempo limite de inatividade do PSSession desconectado. Insira um valor em segundos. O valor mínimo é 60 (1 minuto).

O tempo limite de inatividade determina quanto tempo a PSSession desconectada é mantida no computador remoto. Quando o tempo limite expirar, a PSSession é excluída.

PSSessions desconectadas são consideradas inativas desde o momento em que são desconectadas, ainda que comandos estejam em execução na sessão desconectada.

O valor padrão para o tempo limite de inatividade de uma sessão é definido pelo valor da propriedade **IdleTimeoutMs** da configuração de sessão. O valor padrão é 7200000 milissegundos (2 horas).

O valor deste parâmetro tem precedência sobre o valor da propriedade **IdleTimeout** da variável de preferências $PSSessionOption e o valor de tempo limite de inatividade padrão na configuração da sessão. No entanto, esse valor não pode exceder o valor da propriedade **MaxIdleTimeoutMs** da configuração de sessão. O valor padrão de **MaxIdleTimeoutMs** é de 12 horas (43.200.000 milissegundos).

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

### -InstanceId

Desconecta-se de sessões com os IDs de instância especificados.

A ID de instância é um GUID que identifica exclusivamente uma sessão em um computador local ou remoto. O ID de instância é exclusivo, mesmo em várias sessões em vários computadores.

Para obter a ID de instância de uma sessão, use o `Get-PSSession` cmdlet. A ID da instância é armazenada na propriedade **InstanceId** da sessão.

```yaml
Type: System.Guid[]
Parameter Sets: InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Desconecta de sessões com os nomes amigáveis especificados. Caracteres curinga são permitidos.

Para obter o nome amigável de uma sessão, use o `Get-PSSession` cmdlet. O nome amigável de uma sessão é armazenado na propriedade **Name** da sessão.

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Sessão

Desconecta-se de PSSessions especificadas. Insira objetos PSSession, como os que o `New-PSSession` cmdlet retorna. Também é possível canalizar um objeto PSSession para `Disconnect-PSSession` .

O `Get-PSSession` cmdlet pode obter todas as PSSessions que terminam em um computador remoto, incluindo PSSessions que são desconectados e PSSessions conectados a outras sessões em outros computadores. `Disconnect-PSSession` desconecta somente PSSession que estão conectados à sessão atual. Se você canalizar outras PSSessions para `Disconnect-PSSession` , o `Disconnect-PSSession` comando falhará.

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ThrottleLimit

Define o limite de limitação para o `Disconnect-PSSession` comando.

Especifica o número máximo de conexões simultâneas que podem ser estabelecidas para executar este comando. Se você omite esse parâmetro ou digita um valor 0, o valor padrão, 32, é usado.

O limite de aceleração aplica-se somente ao comando atual e não à sessão ou ao computador.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputBufferingMode

Determina como a saída do comando é gerenciada na sessão desconectada quando o buffer de saída está cheio. O valor padrão é **Block** .

Se o comando na sessão desconectada estiver retornando uma saída e o buffer de saída ficar cheio, o valor desse parâmetro efetivamente determina se o comando continuará a ser executado enquanto a sessão está desconectada. Um valor de **Block** suspende o comando até que a sessão seja reconectada. Um valor de **Drop** permite que o comando ser concluído, embora os dados possam ser perdidos. Ao usar o valor **Drop** , redirecione a saída do comando para um arquivo no disco.

Os valores válidos são:

- **Bloquear** : quando o buffer de saída estiver cheio, a execução será suspensa até que o buffer fique claro.
- **Remover** : quando o buffer de saída estiver cheio, a execução continuará. Conforme uma nova saída é salva, a saída mais antiga é descartada.
- **Nenhum** : nenhum modo de buffer de saída foi especificado. O valor da propriedade **OutputBufferingMode** da configuração de sessão é usada para a sessão desconectada.

```yaml
Type: System.Management.Automation.Runspaces.OutputBufferingMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Block
Accept pipeline input: False
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

Mostra o que aconteceria se o cmdlet fosse executado.
O cmdlet não é executado.

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

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](./About/about_CommonParameters.md).

## ENTRADAS

### System. Management. Automation. Runspaces. PSSession

Você pode canalizar uma sessão para `Disconnect-PSSession` .

## SAÍDAS

### System. Management. Automation. Runspaces. PSSession

`Disconnect-PSSession` Retorna um objeto que representa a sessão que ele desconectou.

## OBSERVAÇÕES

- O `Disconnect-PSSession` cmdlet funciona somente quando os computadores locais e remotos estão executando o PowerShell 3,0 ou posterior.
- Se você usar o `Disconnect-PSSession` cmdlet em uma sessão desconectada, o comando não terá nenhum efeito na sessão e não gerará erros.
- Sessões de loopback desconectadas com tokens de segurança interativos (aqueles criados com o parâmetro **EnableNetworkAccess** ) podem ser reconectados somente por meio do computador no qual a sessão foi criada. Essa restrição protege o computador contra acessos mal-intencionados.
- Quando você desconecta uma PSSession, o estado da sessão é **Disconnected** e a disponibilidade é **None** .

  O valor da propriedade **State** é relativo a sessão atual. Portanto, um valor de **Disconnected** significa que a PSSession não está conectada à sessão atual. No entanto, isso não significa que a PSSession será desconectada de todas as sessões. Ela pode ser conectada a uma sessão diferente. Para determinar se é possível conectar-se ou reconectar-se à sessão, utilize a propriedade **Availability** .

  Um valor **Availability** de **None** indica que é possível conectar-se à sessão. Um valor de **Busy** indica que não é possível se conectar à PSSession porque está conectada a outra sessão.

  Para obter mais informações sobre os valores da propriedade **State** de sessões, consulte [Enumeração RunspaceState](/dotnet/api/system.management.automation.runspaces.runspacestate).

  Para obter mais informações sobre os valores da propriedade de sessões de **disponibilidade** , consulte [Enumeração RunspaceAvailability](/dotnet/api/system.management.automation.runspaces.runspaceavailability).

## LINKS RELACIONADOS

[Connect-PSSession](Connect-PSSession.md)

[Enter-PSSession](Enter-PSSession.md)

[Exit-PSSession](Exit-PSSession.md)

[Get-PSSession](Get-PSSession.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSession](New-PSSession.md)

[New-PSSessionOption](New-PSSessionOption.md)

[New-PSTransportOption](New-PSTransportOption.md)

[Receive-PSSession](Receive-PSSession.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Remove-PSSession](Remove-PSSession.md)

[about_PSSessions](About/about_PSSessions.md)

[about_Remote](About/about_Remote.md)

[about_Remote_Disconnected_Sessions](About/about_Remote_Disconnected_Sessions.md)
