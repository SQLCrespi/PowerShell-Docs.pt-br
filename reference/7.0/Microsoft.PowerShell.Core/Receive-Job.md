---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/receive-job?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Receive-Job
ms.openlocfilehash: a2dced2eabd7a9d21d8637922e576ecd7dd3e6d3
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192975"
---
# Receive-Job

## SINOPSE
Obtém os resultados dos trabalhos em segundo plano do PowerShell na sessão atual.

## SYNTAX

### Local (padrão)

```
Receive-Job [-Job] <Job[]> [[-Location] <String[]>] [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob]
 [-WriteEvents] [-WriteJobInResults] [<CommonParameters>]
```

### ComputerName

```
Receive-Job [-Job] <Job[]> [[-ComputerName] <String[]>] [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob]
 [-WriteEvents] [-WriteJobInResults] [<CommonParameters>]
```

### Session

```
Receive-Job [-Job] <Job[]> [[-Session] <PSSession[]>] [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob]
 [-WriteEvents] [-WriteJobInResults] [<CommonParameters>]
```

### NameParameterSet

```
Receive-Job [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob] [-WriteEvents] [-WriteJobInResults]
 [-Name] <String[]> [<CommonParameters>]
```

### InstanceIdParameterSet

```
Receive-Job [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob] [-WriteEvents] [-WriteJobInResults]
 [-InstanceId] <Guid[]> [<CommonParameters>]
```

### SessionIdParameterSet

```
Receive-Job [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob] [-WriteEvents] [-WriteJobInResults]
 [-Id] <Int32[]> [<CommonParameters>]
```

## DESCRIPTION

O `Receive-Job` cmdlet obtém os resultados de trabalhos em segundo plano do PowerShell, como aqueles iniciados usando o `Start-Job` cmdlet ou o parâmetro **AsJob** de qualquer cmdlet.
Você pode obter os resultados de todos os trabalhos ou identificar trabalhos pelo nome, ID, ID de instância, nome do computador, local ou sessão ou enviando um objeto de trabalho.

Quando você inicia um trabalho em segundo plano do PowerShell, o trabalho é iniciado, mas os resultados não aparecem imediatamente. Em vez disso, o comando retorna um objeto que representa o trabalho em segundo plano.
O objeto de trabalho contém informações úteis sobre o trabalho, mas não contém os resultados.
Esse método permite que você continue a trabalhar na sessão enquanto o trabalho é executado.
Para obter mais informações sobre trabalhos em segundo plano no PowerShell, consulte [about_Jobs](./About/about_Jobs.md).

O `Receive-Job` cmdlet obtém os resultados que foram gerados pela hora em que o `Receive-Job` comando foi enviado.
Se os resultados ainda não estiverem completos, você poderá executar `Receive-Job` comandos adicionais para obter os resultados restantes.

Por padrão, os resultados do trabalho são excluídos do sistema quando são recebidos, mas você pode usar o parâmetro **Keep** para salvar os resultados para poder recebê-los novamente.
Para excluir os resultados do trabalho, execute o `Receive-Job` comando novamente sem o parâmetro **Keep** , feche a sessão ou use o `Remove-Job` cmdlet para excluir o trabalho da sessão.

A partir do Windows PowerShell 3,0, `Receive-Job` o também obtém os resultados de tipos de trabalho personalizados, como trabalhos de workflow e instâncias de trabalhos agendados.
Para habilitar `Receive-Job` o a fim de obter os resultados de um tipo de trabalho personalizado, importe o módulo que dá suporte ao tipo de trabalho personalizado na sessão antes de executar um `Receive-Job` comando, seja usando o `Import-Module` cmdlet ou obtendo um cmdlet no módulo.
Para obter informações sobre um tipo específico de trabalho personalizado, consulte a documentação do recurso de tipo de trabalho personalizado.

## EXEMPLOS

### Exemplo 1: obter resultados para um trabalho específico

```powershell
$job = Start-Job -ScriptBlock {Get-Process}
Receive-Job -Job $job
```

Esses comandos usam o parâmetro de **trabalho** de `Receive-Job` para obter os resultados de um trabalho específico.

O primeiro comando inicia um trabalho com `Start-Job` e armazena o objeto de trabalho na `$job` variável.

O segundo comando usa o `Receive-Job` cmdlet para obter os resultados do trabalho.
Ele usa o parâmetro **Job** para especificar o trabalho.

### Exemplo 2: usar o parâmetro Keep

```powershell
$job = Start-Job -ScriptBlock {Get-Service dhcp, fakeservice}
$job | Receive-Job -Keep
```

```Output
Cannot find any service with service name 'fakeservice'.
    + CategoryInfo          : ObjectNotFound: (fakeservice:String) [Get-Service], ServiceCommandException
    + FullyQualifiedErrorId : NoServiceFoundForGivenName,Microsoft.PowerShell.Commands.GetServiceCommand
    + PSComputerName        : localhost

Status   Name               DisplayName
------   ----               -----------
Running  dhcp               DHCP Client
```

```powershell
$job | Receive-Job -Keep
```

```Output
Cannot find any service with service name 'fakeservice'.
    + CategoryInfo          : ObjectNotFound: (fakeservice:String) [Get-Service], ServiceCommandException
    + FullyQualifiedErrorId : NoServiceFoundForGivenName,Microsoft.PowerShell.Commands.GetServiceCommand
    + PSComputerName        : localhost

Status   Name               DisplayName
------   ----               -----------
Running  dhcp               DHCP Client
```

Este exemplo armazena um trabalho na `$job` variável e canaliza o trabalho para o `Receive-Job` cmdlet. O `-Keep` parâmetro também é usado para permitir que todos os dados de fluxo agregados sejam recuperados novamente após a primeira exibição.

### Exemplo 3: obter resultados de vários trabalhos em segundo plano

Quando você usa o parâmetro **AsJob** do `Invoke-Command` para iniciar um trabalho, o objeto de trabalho é criado no computador local, embora o trabalho seja executado nos computadores remotos.
Como resultado, você deve usar comandos locais para gerenciar o trabalho.

Além disso, quando você usa **AsJob** , o PowerShell retorna um objeto de trabalho que contém um trabalho filho para cada trabalho iniciado. Nesse caso, o objeto de trabalho contém três tarefas filhas, uma para cada trabalho em cada computador remoto.

```powershell
# Use the Invoke-Command cmdlet with the -AsJob parameter to start a background job that runs a Get-Service command on three remote computers.
# Store the resulting job object in the $j variable
$j = Invoke-Command -ComputerName Server01, Server02, Server03 -ScriptBlock {Get-Service} -AsJob
# Display the value of the **ChildJobs** property of the job object in $j.
# The display shows that the command created three child jobs, one for the job on each remote computer.
# You could also use the -IncludeChildJobs parameter of the Get-Job cmdlet.
$j.ChildJobs
```

```Output
Id   Name     State      HasMoreData   Location       Command
--   ----     -----      -----------   --------       -------
2    Job2     Completed  True          Server01       Get-Service
3    Job3     Completed  True          Server02       Get-Service
4    Job4     Completed  True          Server03       Get-Service
```

```powershell
# Use the Receive-Job cmdlet to get the results of just the Job3 child job that ran on the Server02 computer.
# Use the *Keep* parameter to allow you to view the aggregated stream data more than once.
Receive-Job -Name Job3 -Keep
```

```Output
Status  Name        DisplayName                        PSComputerName
------  ----------- -----------                        --------------
Running AeLookupSvc Application Experience             Server02
Stopped ALG         Application Layer Gateway Service  Server02
Running Appinfo     Application Information            Server02
Running AppMgmt     Application Management             Server02
```

### Exemplo 4: obter resultados de trabalhos em segundo plano em vários computadores remotos

```powershell
# Use the New-PSSession cmdlet to create three user-managed PSSessions on three servers, and save the sessions in the $s variable.
$s = New-PSSession -ComputerName Server01, Server02, Server03
# Use Invoke-Command run a Start-Job command in each of the PSSessions in the $s variable.
# The job outputs the ComputerName of each server.
# Save the job objects in the $j variable.
$j = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {$env:COMPUTERNAME}}
# To confirm that these job objects are from the remote machines, run Get-Job to show no local jobs running.
Get-Job
```

```Output

```

```powershell
# Display the three job objects in $j.
# Note that the Localhost location is not the local computer, but instead localhost as it relates to the job on each Server.
$j
```

```Output
Id   Name     State      HasMoreData   Location   Command
--   ----     -----      -----------   --------   -------
1    Job1     Completed  True          Localhost  $env:COMPUTERNAME
2    Job2     Completed  True          Localhost  $env:COMPUTERNAME
3    Job3     Completed  True          Localhost  $env:COMPUTERNAME
```

```powershell
# Use Invoke-Command to run a Receive-Job command in each of the sessions in the $s variable and save the results in the $Results variable.
# The Receive-Job command must be run in each session because the jobs were run locally on each server.
$results = Invoke-Command -Session $s -ScriptBlock {Receive-Job -Job $Using:j}
```

```Output
Server01
Server02
Server03
```

Este exemplo mostra como obter os resultados de trabalhos em segundo plano executados em três computadores remotos.
Ao contrário do exemplo anterior, usar `Invoke-Command` para executar o `Start-Job` comando efetivamente iniciou três trabalhos independentes em cada um dos três computadores. Como resultado, o comando retornou três objetos de trabalho que representam três trabalhos executados localmente nos três computadores diferentes.

> [!NOTE]
> No último comando, porque `$j` é uma variável local, o bloco de script usa o modificador de escopo de **uso** para identificar a `$j` variável. Para obter mais informações sobre o modificador de escopo de **uso** , consulte [about_Remote_Variables](./About/about_Remote_Variables.md).

### Exemplo 5: acessar trabalhos filho

O `-Keep` parâmetro preserva o estado dos fluxos agregados de um trabalho para que ele possa ser exibido novamente. Sem esse parâmetro, todos os dados de fluxo agregados são apagados quando o trabalho é recebido. Para obter mais informações, consulte [about_Job_Details](About/about_Job_Details.md#child-jobs)

> [!NOTE]
> Os fluxos agregados incluem os fluxos de todos os trabalhos filho. Você ainda pode acessar os fluxos de dados individuais por meio do objeto de trabalho e dos objetos de trabalho filho.

```powershell
Start-Job -Name TestJob -ScriptBlock {dir C:\, Z:\}
# Without the Keep parameter, aggregated child job data is displayed once.
# Then destroyed.
Receive-Job -Name TestJob
```

```Output
    Directory: C:\

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-r---        1/24/2019   7:11 AM                Program Files
d-r---        2/13/2019   8:32 AM                Program Files (x86)
d-r---        10/3/2018  11:47 AM                Users
d-----         2/7/2019   1:52 AM                Windows
Cannot find drive. A drive with the name 'Z' does not exist.
    + CategoryInfo          : ObjectNotFound: (Z:String) [Get-ChildItem], DriveNotFoundException
    + FullyQualifiedErrorId : DriveNotFound,Microsoft.PowerShell.Commands.GetChildItemCommand
    + PSComputerName        : localhost
```

```powershell
# It would seem that the child job data is gone.
Receive-Job -Name TestJob
```

```Output

```

```powershell
# Using the object model, you can still retrieve child job data and streams.
$job = Get-Job -Name TestJob
$job.ChildJobs[0].Error
```

```Output
Cannot find drive. A drive with the name 'Z' does not exist.
    + CategoryInfo          : ObjectNotFound: (Z:String) [Get-ChildItem], DriveNotFoundException
    + FullyQualifiedErrorId : DriveNotFound,Microsoft.PowerShell.Commands.GetChildItemCommand
    + PSComputerName        : localhost
```

## PARAMETERS

### -AutoRemoveJob

Indica que esse cmdlet exclui o trabalho depois de retornar os resultados do trabalho.
Se o trabalho tiver mais resultados, o trabalho ainda será excluído, mas `Receive-Job` exibirá uma mensagem.

Esse parâmetro só funciona em tipos de trabalho personalizados.
Ele é projetado para instâncias de tipos de trabalho que salvam o trabalho ou o tipo fora da sessão, como instâncias de trabalhos agendados.

Esse parâmetro não pode ser usado sem o parâmetro **Wait** .

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Especifica uma matriz de nomes de computadores.

Esse parâmetro seleciona entre os resultados do trabalho que estão armazenados no computador local.
Ele não obtém dados para trabalhos executados em computadores remotos.
Para obter os resultados do trabalho armazenados em computadores remotos, use o `Invoke-Command` cmdlet para executar um `Receive-Job` comando remotamente.

```yaml
Type: System.String[]
Parameter Sets: ComputerName
Aliases: Cn

Required: False
Position: 1
Default value: All computers available
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Force

Indica que esse cmdlet continuará aguardando se os trabalhos estiverem no estado **suspenso** ou **desconectado** . Por padrão, o parâmetro **Wait** de `Receive-Job` retorna ou encerra a espera, quando os trabalhos estão em um dos seguintes Estados:

- Concluído
- Falhou
- Parado
- Suspenso
- Desconectado

O parâmetro **Force** é válido somente quando o parâmetro **Wait** também é usado no comando.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Especifica uma matriz de IDs.
Esse cmdlet obtém os resultados de trabalhos com as IDs especificadas.

A ID é um inteiro que identifica exclusivamente o trabalho na sessão atual.
É mais fácil lembrar e digitar do que a ID da instância, mas só é exclusiva na sessão atual. Você pode digitar uma ou mais IDs separadas por vírgulas.
Para localizar a ID de um trabalho, use `Get-Job` .

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId

Especifica uma matriz de IDs de instância.
Esse cmdlet obtém os resultados de trabalhos com as IDs de instância especificadas.

Uma ID de instância é um GUID que identifica exclusivamente o trabalho no computador.
Para localizar a ID de instância de um trabalho, use o `Get-Job` cmdlet.

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: All instances
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Trabalho

Especifica o trabalho para o qual os resultados estão sendo recuperados.

Insira uma variável que contenha o trabalho ou um comando que obtenha o trabalho.
Também é possível canalizar um objeto de trabalho para `Receive-Job` .

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: Location, Session, ComputerName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Manter

Indica que esse cmdlet salva os dados de fluxo agregados no sistema, mesmo depois de você tê-los recebido. Por padrão, os dados de fluxo agregados são apagados depois de exibidos com `Receive-Job` .

Fechar a sessão ou remover o trabalho com o `Remove-Job` cmdlet também exclui dados de fluxo agregados.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Local

Especifica uma matriz de locais.
Esse cmdlet obtém apenas os resultados de trabalhos nos locais especificados.

```yaml
Type: System.String[]
Parameter Sets: Location
Aliases:

Required: False
Position: 1
Default value: All locations
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Especifica uma matriz de nomes amigáveis.
Esse cmdlet obtém os resultados de trabalhos que têm os nomes especificados.
Há suporte para caracteres curinga.

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Recorrência

Indica que esse cmdlet obtém resultados apenas do trabalho especificado.
Por padrão, `Receive-Job` o também obtém os resultados de todos os trabalhos filho do trabalho especificado.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sessão

Especifica uma matriz de sessões.
Esse cmdlet obtém os resultados de trabalhos que foram executados na sessão do PowerShell especificada ( **PSSession** ).
Insira uma variável que contém a **PSSession** ou um comando que obtém a **PSSession** , como um `Get-PSSession` comando.

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: False
Position: 1
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Wait

Indica que esse cmdlet suprime o prompt de comando até que todos os resultados do trabalho sejam recebidos.
Por padrão, `Receive-Job` o retorna imediatamente os resultados disponíveis.

Por padrão, o parâmetro **Wait** aguarda até que o trabalho esteja em um dos seguintes estados:

- Concluído
- Falhou
- Parado
- Suspenso
- Desconectado

Para direcionar o parâmetro **Wait** para continuar aguardando se o estado do trabalho for suspenso ou desconectado, use o parâmetro **Force** junto com o parâmetro **Wait** .

Este parâmetro foi introduzido no Windows PowerShell 3.0.

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

### -WriteEvents

Indica que esse cmdlet relata alterações no estado do trabalho enquanto aguarda a conclusão do trabalho.

Esse parâmetro é válido somente quando o parâmetro **Wait** é usado no comando e o parâmetro **Keep** é omitido.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WriteJobInResults

Indica que esse cmdlet retorna o objeto de trabalho seguido pelos resultados.

Esse parâmetro é válido somente quando o parâmetro **Wait** é usado no comando e o parâmetro **Keep** é omitido.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](./About/about_CommonParameters.md).

## ENTRADAS

### System. Management. Automation. Job

Você pode canalizar objetos de trabalho para este cmdlet.

## SAÍDAS

### PSObject

Esse cmdlet retorna os resultados dos comandos no trabalho.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Get-Job](Get-Job.md)

[Invoke-Command](Invoke-Command.md)

[Remove-Job](Remove-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job](Stop-Job.md)

[Wait-Job](Wait-Job.md)
