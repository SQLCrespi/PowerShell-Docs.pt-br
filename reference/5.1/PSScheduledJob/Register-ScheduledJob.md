---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/register-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-ScheduledJob
ms.openlocfilehash: 89887474142490a71d372577576fb0059b4ff12e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193670"
---
# Register-ScheduledJob

## SINOPSE
Cria um trabalho agendado.

## SYNTAX

### ScriptBlock (padrão)

```
Register-ScheduledJob [-ScriptBlock] <ScriptBlock> [-Name] <String>
 [-Trigger <ScheduledJobTrigger[]>] [-InitializationScript <ScriptBlock>] [-RunAs32]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-ScheduledJobOption <ScheduledJobOptions>] [-ArgumentList <Object[]>] [-MaxResultCount <Int32>]
 [-RunNow] [-RunEvery <TimeSpan>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FilePath

```
Register-ScheduledJob [-FilePath] <String> [-Name] <String> [-Trigger <ScheduledJobTrigger[]>]
 [-InitializationScript <ScriptBlock>] [-RunAs32] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-ScheduledJobOption <ScheduledJobOptions>]
 [-ArgumentList <Object[]>] [-MaxResultCount <Int32>] [-RunNow] [-RunEvery <TimeSpan>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Register-ScheduledJob` cmdlet cria trabalhos agendados no computador local.

Um trabalho agendado é um trabalho em segundo plano do Windows PowerShell que pode ser iniciado automaticamente em um agendamento de uso único ou recorrente. Os trabalhos agendados são armazenados em disco e registrados em Agendador de Tarefas.
Os trabalhos podem ser gerenciados em Agendador de Tarefas ou usando os cmdlets de trabalho agendado no Windows PowerShell.

Quando um trabalho agendado é iniciado, ele cria uma instância do trabalho agendado. Instâncias de trabalho agendado são idênticas aos trabalhos em segundo plano do Windows PowerShell, exceto que os resultados são salvos em disco. Use os cmdlets de trabalho, como `Start-Job` , `Get-Job` e `Receive-Job` para iniciar, exibir e obter os resultados das instâncias de trabalho.

Use `Register-ScheduledJob` para criar um novo trabalho agendado. Para especificar os comandos que o trabalho agendado executa, use o parâmetro **scriptblock** . Para especificar um script que o trabalho executa, use o parâmetro **FilePath** .

Windows PowerShell-os trabalhos agendados usam os mesmos gatilhos de trabalho e opções de trabalho que o Agendador de Tarefas usa para as tarefas agendadas.

O parâmetro **Trigger** de `Register-ScheduledJob` adiciona um ou mais gatilhos de trabalho que iniciam o trabalho. O parâmetro **Trigger** é opcional, de modo que você pode adicionar gatilhos ao criar o trabalho agendado, adicionar gatilhos de trabalho mais tarde, adicionar o parâmetro **RunNow** para iniciar o trabalho imediatamente, usar o `Start-Job` cmdlet para iniciar o trabalho imediatamente a qualquer momento ou salvar o trabalho agendado não disparado como um modelo para outros trabalhos.

O parâmetro **Options** permite que você personalize as configurações de opções do trabalho agendado. O parâmetro **Options** é opcional, de modo que você pode definir opções de trabalho ao criar o trabalho agendado ou alterá-los a qualquer momento. Como as configurações de opção de trabalho podem impedir o trabalho agendado de ser executado, examine as opções de trabalho e as defina com cuidado.

`Register-ScheduledJob` é um de uma coleção de cmdlets de agendamento de trabalho no módulo **PSScheduledJob** que está incluído no Windows PowerShell.

Para obter mais informações sobre trabalhos agendados, consulte os artigos about no módulo **PSScheduledJob** .
Importe o módulo **PSScheduledJob** e, em seguida, digite: `Get-Help about_Scheduled*` ou consulte [about_Scheduled_Jobs](./about/about_scheduled_jobs.md).

Este cmdlet foi introduzido no Windows PowerShell 3.0.

## EXEMPLOS

### Exemplo 1: criar um trabalho agendado

Este exemplo cria um trabalho agendado no computador local.

```powershell
Register-ScheduledJob -Name "Archive-Scripts" -ScriptBlock {
  Get-ChildItem $home\*.ps1 -Recurse |
    Copy-Item -Destination "\\Server\Share\PSScriptArchive"
}
```

`Register-ScheduledJob` usa o parâmetro **Name** para criar o trabalho agendado de **scripts de arquivo** .
O parâmetro **scriptblock** executa `Get-ChildItem` que pesquisa o `$home` diretório recursivamente para `.ps1` arquivos. O `Copy-Item` cmdlet copia os arquivos para um diretório especificado pelo parâmetro de **destino** .

Como o trabalho agendado não contém um gatilho, ele não é iniciado automaticamente. Você pode adicionar gatilhos de trabalho com `Add-JobTrigger` o, usar o `Start-Job` cmdlet para iniciar o trabalho sob demanda ou usar o trabalho agendado como um modelo para outros trabalhos agendados.

### Exemplo 2: criar um trabalho agendado com gatilhos e opções personalizadas

Este exemplo mostra como criar um trabalho agendado com um gatilho de trabalho e opções de trabalho personalizadas.

```powershell
$O = New-ScheduledJobOption -WakeToRun -StartIfIdle -MultipleInstancePolicy Queue
$T = New-JobTrigger -Weekly -At "9:00 PM" -DaysOfWeek Monday -WeeksInterval 2
$path = "\\Srv01\Scripts\UpdateVersion.ps1"
Register-ScheduledJob -Name "UpdateVersion" -FilePath $path -ScheduledJobOption $O -Trigger $T
```

A `$O` variável armazena o objeto de opção de trabalho que o `New-ScheduledJobOption` cmdlet criou. As opções iniciam o trabalho agendado mesmo que o computador não esteja ocioso, ativa o computador para executar o trabalho, se necessário, e permite que várias instâncias do trabalho sejam executadas em uma série.

A `$T` variável armazena o resultado do `New-JobTrigger` cmdlet para criar um gatilho de trabalho que inicia um trabalho a cada segunda-feira às 9:00 PM.

A `$path` variável armazena o caminho para o `UpdateVersion.ps1` arquivo de script.

`Register-ScheduledJob` usa o parâmetro de **nome** para criar o trabalho agendado do **UpdateVersion** .
O parâmetro **FilePath** usa `$path` para especificar o script que o trabalho executa. O parâmetro **ScheduledJobOption** usa as opções de trabalho armazenadas em `$O` . O parâmetro **Trigger** usa os gatilhos de trabalho armazenados no `$T` .

### Exemplo 3: usar tabelas de hash para especificar um gatilho e opções de trabalho agendado

Este exemplo tem o mesmo efeito que o comando no exemplo 2. Ele cria um trabalho agendado, usando tabelas de hash para especificar os valores dos parâmetros **Trigger** e **ScheduledJobOption** . As `$O` `$T` variáveis e definidas no exemplo 2 são substituídas por tabelas de hash.

```powershell
$T = @{
  Frequency="Weekly"
  At="9:00PM"
  DaysOfWeek="Monday"
  Interval=2
}
$O = @{
  WakeToRun=$true
  StartIfNotIdle=$false
  MultipleInstancePolicy="Queue"
}
Register-ScheduledJob -Trigger $T -ScheduledJobOption $O -Name UpdateVersion -FilePath "\\Srv01\Scripts\Update-Version.ps1"
```

### Exemplo 4: criar trabalhos agendados em computadores remotos

Neste exemplo, o trabalho agendado **EnergyData** é criado em vários computadores remotos. O trabalho agendado executa um script que reúne dados brutos e os salva em um log em execução no computador remoto.

```powershell
$Cred = Get-Credential
$O = New-ScheduledJobOption -WakeToRun -StartIfIdle -MultipleInstancePolicy Queue
$T = New-JobTrigger -Weekly -At "9:00 PM" -DaysOfWeek Monday -WeeksInterval 2
Invoke-Command -ComputerName (Get-Content Servers.txt) -Credential $Cred -ScriptBlock {
  $params = @{
      Name = "Get-EnergyData"
      FilePath = "\\Srv01\Scripts\Get-EnergyData.ps1"
      ScheduledJobOption = $using:O
      Trigger = $using:T
  }
  Register-ScheduledJob @params
}
```

A `$Cred` variável armazena as credenciais em um objeto **PSCredential** para um usuário com permissões para criar trabalhos agendados. A `$O` variável armazena as opções de trabalho criadas com `New-ScheduledJobOption` . A `$T` variável armazena os gatilhos de trabalho criados com `New-JobTrigger` .

O `Invoke-Command` cmdlet usa o parâmetro **ComputerName** para obter uma lista de nomes de servidor do `Servers.txt` arquivo. O parâmetro **Credential** Obtém o objeto de credencial armazenado no `$Cred` .
O parâmetro **scriptblock** executa um `Register-ScheduledJob` comando nos computadores do `Servers.txt` arquivo.

Os parâmetros para `Register-ScheduledJob` são definidos por `$params` . Os parâmetros de **nome** especificam que o trabalho é denominado **Get-EnergyData** em cada computador remoto. **FilePath** fornece o local do `EnergyData.ps1` script. O script está localizado em um servidor de arquivos que está disponível para todos os computadores participantes. O trabalho é executado no agendamento especificado pelos disparadores de trabalho no `$T` e nas opções de trabalho no `$O` .

O `Register-ScheduledJob @params` comando cria o trabalho agendado com os parâmetros do bloco de script.

### Exemplo 5: criar um trabalho agendado que executa um script em computadores remotos

Este exemplo cria o trabalho agendado do **CollectEnergyData** no computador local. O trabalho é executado em vários computadores remotos.

```powershell
$Admin = Get-Credential
$T = New-JobTrigger -Weekly -At "9:00 PM" -DaysOfWeek Monday -WeeksInterval 2
Register-ScheduledJob -Name "CollectEnergyData" -Trigger $T -MaxResultCount 99 -ScriptBlock {
  $params = @{
    AsJob = $true
    ComputerName = (Get-Content Servers.txt)
    FilePath = '\\Srv01\Scripts\Get-EnergyData.ps1'
    Credential = $using:Admin
    Authentication = 'CredSSP'
  }
  Invoke-Command @params
}
```

A `$Admin` variável armazena as credenciais de um usuário com permissões para executar os comandos em um objeto **PSCredential** . A `$T` variável armazena os gatilhos de trabalho criados com `New-JobTrigger` .

O `Register-ScheduledJob` cmdlet usa o parâmetro **Name** para criar o trabalho agendado do **CollectEnergyData** no computador local. O parâmetro **Trigger** especifica os gatilhos de trabalho no `$T` e o parâmetro **MaxResultCount** aumenta o número de resultados salvos em 99.

O parâmetro **scriptblock** define os `Invoke-Command` parâmetros com `$params` . O parâmetro **AsJob** cria o objeto de trabalho em segundo plano no computador local, embora o `Energydata.ps1` script seja executado nos computadores remotos. O parâmetro **ComputerName** Obtém uma lista de nomes de servidor do `Servers.txt` arquivo. O parâmetro **Credential** especifica uma conta de usuário que tem permissão para executar scripts nos computadores remotos. E, o parâmetro de **autenticação** especifica um valor de **CredSSP** para permitir credenciais delegadas.

O `Invoke-Command @params` executa o comando com os parâmetros do bloco de script.

## PARAMETERS

### -ArgumentList

Especifica valores para os parâmetros do script especificados pelo parâmetro **FilePath** ou para o comando especificado pelo parâmetro **ScriptBlock** .

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Autenticação

Especifica o mecanismo usado para autenticar as credenciais do usuário. O valor padrão é Default.

Os valores aceitáveis para esse parâmetro são:

- Padrão
- Básico
- CredSSP
- Digest
- Kerberos
- Negotiate
- NegotiateWithImplicitCredential

Para obter mais informações sobre os valores desse parâmetro, consulte [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

> [!CAUTION]
> A autenticação CredSSP (Credencial Security Service Provider), na qual as credenciais do usuário são transmitidas a um computador remoto para autenticação, foi projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remota. Esse mecanismo aumenta o risco de segurança da operação remota. Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
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

### -Credential

Especifica uma conta de usuário que tenha permissão para executar o trabalho agendado. O padrão é o usuário atual.

Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** , como um do `Get-Credential` cmdlet. Se você inserir apenas um nome de usuário, você será solicitado a fornecer uma senha.

As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

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

### -FilePath

Especifica um script que o trabalho agendado executa. Insira o caminho para um `.ps1` arquivo no computador local. Para especificar valores padrão para os parâmetros de script, use o parâmetro **ArgumentList** .
Cada `Register-ScheduledJob` comando deve usar os parâmetros **scriptblock** ou **FilePath** .

```yaml
Type: System.String
Parameter Sets: FilePath
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InitializationScript

Especifica o caminho totalmente qualificado para um script do Windows PowerShell ( `.ps1` ). O script de inicialização é executado na sessão criada para o trabalho em segundo plano antes dos comandos especificados pelo parâmetro **ScriptBlock** ou pelo script especificado pelo parâmetro **FilePath** . Você pode usar o script de inicialização para configurar a sessão, adicionando arquivos, funções ou aliases, criando diretórios ou verificando pré-requisitos.

Para especificar um script que execute os comandos de trabalho principal, use o parâmetro **FilePath** .

Se o script de inicialização gerar um erro, mesmo um erro de não encerramento, a instância atual do trabalho agendado não será executada e seu status **falhará** .

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxResultCount

Especifica quantas entradas de resultado do trabalho são mantidas para o trabalho agendado. O valor padrão é 32.

O Windows PowerShell salva o histórico de execução e os resultados de cada instância disparada do trabalho agendado no disco. O valor desse parâmetro determina o número de resultados de instância de trabalho que são salvas para essa tarefa agendada. Quando o número de resultados de instância de trabalho excede esse valor, o Windows PowerShell exclui os resultados da instância de trabalho mais antiga para abrir espaço para os resultados da instância de trabalho mais recente.

O histórico de execução do trabalho e os resultados do trabalho são salvos no `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs\<JobName>\Output\<Timestamp>`
diretórios no computador no qual o trabalho é criado. Para ver o histórico de execução, use o `Get-Job` cmdlet. Para obter os resultados do trabalho, use o `Receive-Job` cmdlet.

O parâmetro **MaxResultCount** define o valor da propriedade ExecutionHistoryLength do trabalho agendado.

Para excluir o histórico de execução atual e os resultados do trabalho, use o parâmetro **ClearExecutionHistory** do `Set-ScheduledJob` cmdlet.

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

### -Name

Especifica um nome para o trabalho agendado. O nome também é usado para todas as instâncias de trabalho agendado. O nome deve ser exclusivo no computador. Este parâmetro é necessário.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAs32

Executa o trabalho agendado em um processo de 32 bits.

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

### -RunEvery

Usado para especificar a frequência de execução do trabalho. Por exemplo, use esta opção para executar um trabalho a cada 15 minutos.

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunNow

Inicia um trabalho imediatamente, assim que o `Register-ScheduledJob` cmdlet é executado. Esse parâmetro elimina a necessidade de disparar Agendador de Tarefas para executar um script do Windows PowerShell imediatamente após o registro e não exige que os usuários criem um gatilho que especifique uma data e hora de início.

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

### -ScheduledJobOption

Define opções para o trabalho agendado. Insira um objeto **ScheduledJobOptions** , como um que você cria usando o `New-ScheduledJobOption` cmdlet ou um valor de tabela de hash.

Você pode definir opções para um trabalho agendado ao registrar o trabalho de agendamento ou usar `Set-ScheduledJobOption` os `Set-ScheduledJob` cmdlets ou para alterar as opções.

Muitas das opções e seus valores padrão determinam se e quando um trabalho agendado será executado. Certifique-se de examinar essas opções antes de agendar um trabalho. Para obter uma descrição das opções de trabalho agendado, incluindo os valores padrão, consulte `New-ScheduledJobOption` .

Para enviar uma tabela de hash, use as seguintes chaves. Na tabela de hash a seguir, as chaves são exibidas com seus valores padrão.

`@{StartIfOnBattery=$False; StopIfGoingOnBattery=$True; WakeToRun=$False; StartIfNotIdle=$False; IdleDuration="00:10:00"; IdleTimeout="01:00:00"; StopIfGoingOffIdle=$True; RestartOnIdleResume=$False; ShowInTaskScheduler=$True; RunElevated=$False; RunWithoutNetwork=$False; DoNotAllowDemandStart=$False; MultipleInstancePolicy="IgnoreNew"}`

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptBlock

Especifica os comandos que o trabalho agendado executa. Coloque os comandos entre chaves ( `{}` ) para criar um bloco de script. Para especificar valores padrão para os parâmetros de comando, use o parâmetro **ArgumentList** .

Cada `Register-ScheduledJob` comando deve usar os parâmetros **scriptblock** ou **FilePath** .

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Gatilho

Especifica os gatilhos para o trabalho agendado. Insira um ou mais objetos **ScheduledJobTrigger** , como os objetos que o `New-JobTrigger` cmdlet retorna ou uma tabela de hash de chaves e valores de gatilho de trabalho.

Um gatilho de trabalho inicia o trabalho de agendamento. O gatilho pode especificar um agendamento único ou recorrente ou um evento, como quando um usuário faz logon ou o Windows é iniciado.

O parâmetro **Trigger** é opcional. Você pode adicionar um gatilho ao criar o trabalho agendado, usar os `Add-JobTrigger` `Set-JobTrigger` `Set-ScheduledJob` cmdlets, ou para adicionar ou alterar gatilhos de trabalho mais tarde, ou usar o `Start-Job` cmdlet para iniciar o trabalho agendado imediatamente. Você também pode criar e manter um trabalho agendado sem um gatilho que é usado como modelo.

Para enviar uma tabela de hash, use as seguintes chaves:

- **Frequência** : diária, semanal, AtStartup, AtLogon
- **Em** : qualquer cadeia de caracteres de tempo válida
- **DaysOfWeek** -qualquer combinação de nomes de dias
- **Intervalo** -qualquer intervalo de frequência válido
- **RandomDelay** : qualquer cadeia de TimeSpan válida
- **Usuário** : qualquer usuário válido. Usado somente com o valor de frequência AtLogon

Por exemplo:

`@{Frequency="Once"; At="3am"; DaysOfWeek="Monday", "Wednesday"; Interval=2; RandomDelay="30minutes"; User="Domain1\User01"}`

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Mostra o que aconteceria se o cmdlet fosse executado. O cmdlet não é executado.

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

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Você não pode enviar a entrada do pipeline para esse cmdlet.

## SAÍDAS

### Microsoft. PowerShell. ScheduledJob. ScheduledJobDefinition

## OBSERVAÇÕES

Cada trabalho agendado é salvo em um subdiretório do `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` diretório no computador local.
O subdiretório é nomeado para o trabalho agendado e contém um arquivo XML para o trabalho agendado e registros de seu histórico de execução. Para obter mais informações sobre os trabalhos agendados no disco, consulte [about_Scheduled_Jobs_Advanced](./about/about_scheduled_jobs_advanced.md).

Os trabalhos agendados que você cria no Windows PowerShell aparecem no Agendador de Tarefas na `Library\Microsoft\Windows\PowerShell\ScheduledJobs` pasta Agendador de tarefas. Você pode usar o Agendador de tarefas para exibir e editar o trabalho agendado.

Você pode usar Agendador de Tarefas, a ferramenta de linha de comando **schtasks.exe** e os cmdlets Agendador de tarefas para gerenciar os trabalhos agendados que você cria com os cmdlets de trabalho agendado. No entanto, você não pode usar os cmdlets do trabalho agendado para gerenciar tarefas que você cria no Agendador de Tarefas.

Se um comando de trabalho agendado falha, o Windows PowerShell retorna uma mensagem de erro. No entanto, se o trabalho falhar quando Agendador de Tarefas tentar executá-lo, o erro não estará disponível para o Windows PowerShell.

Se um trabalho agendado não for executado, use os seguintes métodos para encontrar o motivo:

- Verifique se o gatilho do trabalho está definido corretamente.
  - Verifique se as condições definidas nas opções de trabalho estão satisfeitas.
- Verifique se a conta de usuário sob a qual o trabalho é executado tem permissão para executar os comandos ou scripts no trabalho.
- Verifique se há erros no histórico de Agendador de Tarefas.
- Verifique se há erros na Agendador de Tarefas log de eventos.

Para obter mais informações, consulte [about_Scheduled_Jobs_Troubleshooting](./about/about_scheduled_jobs_troubleshooting.md).

## LINKS RELACIONADOS

[Add-JobTrigger](Add-JobTrigger.md)

[Disable-JobTrigger](Disable-JobTrigger.md)

[Disable-ScheduledJob](Disable-ScheduledJob.md)

[Enable-JobTrigger](Enable-JobTrigger.md)

[Enable-ScheduledJob](Enable-ScheduledJob.md)

[Get-JobTrigger](Get-JobTrigger.md)

[Get-ScheduledJob](Get-ScheduledJob.md)

[Get-ScheduledJobOption](Get-ScheduledJobOption.md)

[New-JobTrigger](New-JobTrigger.md)

[New-ScheduledJobOption](New-ScheduledJobOption.md)

[Register-ScheduledJob](Register-ScheduledJob.md)

[Remove-JobTrigger](Remove-JobTrigger.md)

[Set-JobTrigger](Set-JobTrigger.md)

[Set-ScheduledJob](Set-ScheduledJob.md)

[Set-ScheduledJobOption](Set-ScheduledJobOption.md)

[Unregister-ScheduledJob](Unregister-ScheduledJob.md)
