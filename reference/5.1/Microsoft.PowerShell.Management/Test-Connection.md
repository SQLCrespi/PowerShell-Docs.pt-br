---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-connection?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Connection
ms.openlocfilehash: a8d3923db69a20cfada58391944b592cf999e6ef
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193900"
---
# Test-Connection

## SINOPSE
Envia pacotes de solicitação de eco ICMP, ou pings, para um ou mais computadores.

## SYNTAX

### Padrão (padrão)

```
Test-Connection [-AsJob] [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-BufferSize <Int32>] [-ComputerName] <String[]> [-Count <Int32>]
 [-Impersonation <ImpersonationLevel>] [-ThrottleLimit <Int32>] [-TimeToLive <Int32>]
 [-Delay <Int32>] [<CommonParameters>]
```

### Fonte

```
Test-Connection [-AsJob] [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-BufferSize <Int32>] [-ComputerName] <String[]> [-Count <Int32>]
 [-Credential <PSCredential>] [-Source] <String[]> [-Impersonation <ImpersonationLevel>]
 [-ThrottleLimit <Int32>] [-TimeToLive <Int32>] [-Delay <Int32>] [<CommonParameters>]
```

### Quiet

```
Test-Connection [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-BufferSize <Int32>] [-ComputerName] <String[]> [-Count <Int32>]
 [-Impersonation <ImpersonationLevel>] [-TimeToLive <Int32>] [-Delay <Int32>] [-Quiet]
 [<CommonParameters>]
```

## DESCRIPTION

O `Test-Connection` cmdlet envia pacotes de solicitação de eco do protocolo ICMP, ou pings, para um ou mais computadores remotos e retorna as respostas de resposta de eco. Você pode usar este cmdlet para determinar se um computador específico pode ser contatado em uma rede IP.

Você pode usar os parâmetros de `Test-Connection` para especificar os computadores de envio e de recebimento, para executar o comando como um trabalho em segundo plano, definir um tempo limite e um número de pings e configurar a conexão e a autenticação.

Diferentemente do comando **ping** conhecido, `Test-Connection` retorna um objeto **Win32_PingStatus** que você pode investigar no PowerShell. O parâmetro **Quiet** retorna um valor **booliano** em um objeto **System. Boolean** para cada conexão testada. Se várias conexões forem testadas, uma matriz de valores **boolianos** será retornada.

## EXEMPLOS

### Exemplo 1: enviar solicitações de eco para um computador remoto

Este exemplo envia pacotes de solicitação de eco do computador local para o computador Server01.

```powershell
Test-Connection -ComputerName Server01
```

```Output
Source        Destination     IPV4Address     IPV6Address  Bytes    Time(ms)
------        -----------     -----------     -----------  -----    --------
ADMIN1        Server01         10.59.137.44                32       0
ADMIN1        Server01         10.59.137.44                32       0
ADMIN1        Server01         10.59.137.44                32       0
ADMIN1        Server01         10.59.137.44                32       1
```

`Test-Connection` usa o parâmetro **ComputerName** para especificar o computador Server01.

### Exemplo 2: enviar solicitações de eco para vários computadores

Este exemplo envia pings do computador local para vários computadores remotos.

```powershell
Test-Connection -ComputerName Server01, Server02, Server12
```

### Exemplo 3: enviar solicitações de eco de vários computadores a um computador

Este exemplo envia pings de computadores de origem diferentes para um único computador remoto, Server01.

```powershell
Test-Connection -Source Server02, Server12, localhost -ComputerName Server01 -Credential Domain01\Admin01
```

`Test-Connection` usa o parâmetro **Credential** para especificar as credenciais de um usuário que tem permissão para enviar uma solicitação de ping dos computadores de origem. Use esse formato de comando para testar a latência de conexões de vários pontos.

### Exemplo 4: usar parâmetros para personalizar o comando de teste

Este exemplo usa os parâmetros de `Test-Connection` para personalizar o comando. O computador local envia um teste de ping para um computador remoto.

```powershell
Test-Connection -ComputerName Server01 -Count 3 -Delay 2 -TTL 255 -BufferSize 256 -ThrottleLimit 32
```

`Test-Connection` usa o parâmetro **ComputerName** para especificar Server01. O parâmetro **Count** especifica que três pings são enviados para o computador Server01 com um **atraso** de intervalos de 2 segundos.

Você pode usar essas opções quando espera-se que a resposta de ping demore mais do que o normal, devido a um número estendido de saltos ou a uma condição de rede de tráfego alto.

### Exemplo 5: executar um teste como um trabalho em segundo plano

Este exemplo mostra como executar um `Test-Connection` comando como um trabalho em segundo plano do PowerShell.

```powershell
$job = Test-Connection -ComputerName (Get-Content Servers.txt) -AsJob
if ($job.JobStateInfo.State -ne "Running") {$Results = Receive-Job $job}
```

O `Test-Connection` comando executa ping de muitos computadores em uma empresa. O valor do parâmetro **ComputerName** é um `Get-Content` comando que lê uma lista de nomes de computador do `Servers.txt file` . O comando usa o parâmetro **AsJob** para executar o comando como um trabalho em segundo plano e salva o trabalho na `$job` variável.

O `if` comando verifica para ver se o trabalho ainda não está em execução. Se o trabalho não estiver em execução, `Receive-Job` o obterá os resultados e os armazenará na `$Results` variável.

### Exemplo 6: executar ping em um computador remoto com credenciais

Esse comando usa o `Test-Connection` cmdlet para executar ping em um computador remoto.

```powershell
Test-Connection Server55 -Credential Domain55\User01 -Impersonation Identify
```

O comando usa o parâmetro **Credential** para especificar uma conta de usuário que tenha permissão para executar ping no computador remoto e o parâmetro **Impersonation** para alterar o nível de representação a ser **identificado** .

### Exemplo 7: criar uma sessão somente se um teste de conexão tiver sucesso

Este exemplo criará uma sessão no computador Server01 somente se pelo menos um dos pings enviados para o computador for executado com sucesso.

```powershell
if (Test-Connection -ComputerName Server01 -Quiet) {New-PSSession Server01}
```

O `if` comando usa o `Test-Connection` cmdlet para executar ping no computador Server01. O comando usa o parâmetro **Quiet** , que retorna um valor **booliano** , em vez de um objeto **Win32_PingStatus** . O valor é `$True` se qualquer um dos quatro pings for bem sucedido e for, caso contrário, `$False` .

Se o `Test-Connection` comando retornar um valor de `$True` , o comando usará o `New-PSSession` cmdlet para criar a **PSSession** .

## PARAMETERS

### -AsJob

Indica que esse cmdlet é executado como um trabalho em segundo plano.

Para usar esse parâmetro, os computadores locais e remotos devem ser configurados para comunicação remota e, no Windows Vista e em versões posteriores do sistema operacional Windows, você deve abrir o PowerShell usando a opção **Executar como administrador** . Para obter mais informações, consulte [about_Remote_Requirements](../microsoft.powershell.core/about/about_remote_requirements.md).

Quando você especifica o parâmetro **AsJob** , o comando retorna imediatamente um objeto que representa o trabalho em segundo plano. É possível continuar a trabalhar na sessão enquanto o trabalho é concluído. O trabalho é criado no computador local e os resultados de computadores remotos são retornados automaticamente para o computador local. Para obter os resultados do trabalho, use o `Receive-Job` cmdlet.

Para obter mais informações sobre trabalhos em segundo plano do PowerShell, consulte [about_Jobs](../Microsoft.PowerShell.Core/About/about_jobs.md) e [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_remote_jobs.md).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default, Source
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -BufferSize

Especifica o tamanho, em bytes, do buffer enviado com esse comando. O valor padrão é 32.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: Size, Bytes, BS

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Especifica os computadores para execução do ping. Digite os nomes de computador ou endereços IP no formato IPv4 ou IPv6. Caracteres curinga não são permitidos. Este parâmetro é necessário.

Esse parâmetro não depende da comunicação remota do PowerShell. Você pode usar o parâmetro **ComputerName** mesmo que o computador não esteja configurado para executar comandos remotos.

> [!NOTE]
> O parâmetro **ComputerName** é renomeado para **TargetName** no PowerShell 6,0 e superior.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, IPAddress, __SERVER, Server, Destination

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Contagem

Especifica o número de solicitações de eco a enviar. O valor padrão é 4.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 4
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Especifica uma conta de usuário que tenha permissão para enviar uma solicitação de ping do computador de origem. Digite um nome de usuário, como User01 ou Domínio01 \ Usuário01, ou insira um objeto **PSCredential** , como um do `Get-Credential` cmdlet.

O parâmetro **Credential** é válido somente quando o parâmetro **Source** também é usado no comando. As credenciais não afetam o computador de destino.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Source
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -DcomAuthentication

Especifica o nível de autenticação que esse cmdlet usa com o WMI.
`Test-Connection` usa o WMI.
Os valores aceitáveis para esse parâmetro são:

- **Default** . Autenticação do Windows
- **None** . Não há autenticação COM
- **Conecte-se** . Autenticação COM de nível de conexão
- **Chame** . Autenticação COM de nível de chamada
- **Pacote** . Autenticação COM em nível de pacote
- **PacketIntegrity** . Autenticação COM de nível de integridade de pacote
- **PacketPrivacy** . Privacidade do pacote-autenticação COM de nível
- **Inalterado** . O mesmo que o comando anterior

O valor padrão é **pacote** que tem um valor enumerado de **4** . Para obter mais informações sobre os valores desse parâmetro, consulte enumeração [AuthenticationLevel](/dotnet/api/system.management.authenticationlevel) .

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases: Authentication
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: Packet (enumerated value of 4)
Accept pipeline input: False
Accept wildcard characters: False
```

### -Atraso

Especifica o intervalo entre pings, em segundos.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1 (second)
Accept pipeline input: False
Accept wildcard characters: False
```

### -Representação

Especifica o nível de representação a ser usado quando este cmdlet chama WMI. `Test-Connection` usa o WMI.

Os valores aceitáveis para esse parâmetro são os seguintes:

- **Default** . Representação padrão.
- **Anônimo** . Oculta a identidade do autor da chamada.
- **Identificar** . Permite que os objetos consultem as credenciais do autor da chamada.
- **Representar** . Permite que os objetos utilizem as credenciais do autor da chamada.

O valor padrão é **Impersonate** .

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: Impersonate
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol

Especifica um protocolo. Os valores aceitáveis para esse parâmetro são DCOM e WSMan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Quiet

O parâmetro **Quiet** retorna um valor **booliano** em um objeto **System. Boolean** . O uso desse parâmetro suprime todos os erros.

Cada conexão testada retorna um valor **booliano** . Se o parâmetro **ComputerName** especificar vários computadores, uma matriz de valores **boolianos** será retornada.

Se **qualquer** ping for executado com sucesso, `$True` será retornado.

Se **todos os** pings falharem, `$False` será retornado.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Quiet
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source

Especifica os nomes dos computadores de onde se origina o ping. Digite uma lista separada por vírgulas de nomes de computador. O padrão é o computador local.

```yaml
Type: System.String[]
Parameter Sets: Source
Aliases: FCN, SRC

Required: True
Position: 1
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Especifica o número máximo de conexões simultâneas que podem ser estabelecidas para executar o comando.
Se você omite esse parâmetro ou digita um valor 0, o valor padrão, 32, é usado.

O limite de aceleração aplica-se somente ao comando atual e não à sessão ou ao computador.

```yaml
Type: System.Int32
Parameter Sets: Default, Source
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeToLive

Especifica o número máximo de vezes que um pacote pode ser encaminhado. Para cada salto em gateways, roteadores, etc. o valor **TimeToLive** é reduzido em um. Em zero, o pacote é Descartado e um erro é retornado.
No **Windows** , o valor padrão é **128** . O alias do parâmetro **TimeToLive** é **TTL** .

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TTL

Required: False
Position: Named
Default value: 128 in Windows
Accept pipeline input: False
Accept wildcard characters: False
```

### -WsmanAuthentication

Especifica o mecanismo usado para autenticar as credenciais do usuário quando este cmdlet usa o protocolo WSMan.
Os valores aceitáveis para esse parâmetro são:

- Básico
- CredSSP
- Padrão
- Digest
- Kerberos
- Negotiate.

O valor padrão é Default.

Para obter mais informações sobre os valores desse parâmetro, consulte [Enumeração AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism?view=powershellsdk-1.1.0).

Cuidado: a autenticação CredSSP (provedor de serviços de segurança de credencial), na qual as credenciais do usuário são passadas a um computador remoto para ser autenticado, foi projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remoto.
Esse mecanismo aumenta o risco de segurança da operação remota.
Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, CredSSP, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Não é possível canalizar a entrada para este cmdlet.

## SAÍDAS

### System. Management. ManagementObject # root\cimv2\ Win32_PingStatus, System. Management. Automation. RemotingJob, System. Boolean

Esse cmdlet retorna um objeto de trabalho, se você especificar o parâmetro **AsJob** .

Se você especificar o parâmetro **Quiet** , ele retornará um valor **booliano** . Se várias conexões forem testadas, uma matriz de valores **boolianos** será retornada. Caso contrário, `Test-Connection` retorna um objeto **Win32_PingStatus** para cada ping.

## OBSERVAÇÕES

Esse cmdlet usa a classe **Win32_PingStatus** . Um `Get-WMIObject Win32_PingStatus` comando é equivalente a um `Test-Connection` comando.

O conjunto de parâmetros de **origem** foi introduzido no PowerShell 3,0.

## LINKS RELACIONADOS

[Add-Computer](Add-Computer.md)

[Restart-Computer](Restart-Computer.md)

[Stop-Computer](Stop-Computer.md)
