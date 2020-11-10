---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/set-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ScheduledJob
ms.openlocfilehash: 6144d9f19b86727bc09d07e94f4bcf158e3b7071
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94387899"
---
# Set-ScheduledJob

## SINOPSE
Altera trabalhos agendados.

## SYNTAX

### ScriptBlock (padrão)

```
Set-ScheduledJob [-Name <String>] [-ScriptBlock <ScriptBlock>] [-Trigger <ScheduledJobTrigger[]>]
 [-InitializationScript <ScriptBlock>] [-RunAs32] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-ScheduledJobOption <ScheduledJobOptions>]
 [-InputObject] <ScheduledJobDefinition> [-MaxResultCount <Int32>] [-PassThru] [-ArgumentList <Object[]>]
 [-RunNow] [-RunEvery <TimeSpan>] [<CommonParameters>]
```

### FilePath

```
Set-ScheduledJob [-Name <String>] [-FilePath <String>] [-Trigger <ScheduledJobTrigger[]>]
 [-InitializationScript <ScriptBlock>] [-RunAs32] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-ScheduledJobOption <ScheduledJobOptions>]
 [-InputObject] <ScheduledJobDefinition> [-MaxResultCount <Int32>] [-PassThru] [-ArgumentList <Object[]>]
 [-RunNow] [-RunEvery <TimeSpan>] [<CommonParameters>]
```

### Execução

```
Set-ScheduledJob [-InputObject] <ScheduledJobDefinition> [-ClearExecutionHistory] [-PassThru]
 [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Set-ScheduledJob** altera as propriedades dos trabalhos agendados, como os comandos que os trabalhos executam ou as credenciais necessárias para executar o trabalho.
Você também pode usar isso para limpar o histórico de execução do trabalho agendado.

Para usar esse cmdlet, comece usando o cmdlet Get-ScheduledJob para obter o trabalho agendado.
Em seguida, redirecione o trabalho agendado para **set-ScheduledJob** ou salve o trabalho em uma variável e use o parâmetro *InputObject* para identificar o trabalho.
Use os parâmetros restantes do **Set-ScheduledJob** para alterar as propriedades do trabalho ou limpar o histórico de execução.

Embora você possa usar **set-ScheduledJob** para alterar os gatilhos e as opções de um trabalho agendado, os cmdlets Add-JobTrigger, Set-JobTrigger e Set-ScheduledJobOption fornecem maneiras muito mais fáceis de realizar essas tarefas.
Para criar um novo trabalho agendado, use o cmdlet Register-ScheduledJob.

O parâmetro *Trigger* de **set-ScheduledJob** adiciona um ou mais gatilhos de trabalho que iniciam o trabalho.
O parâmetro *Trigger* é opcional, de modo que você pode adicionar gatilhos ao criar o trabalho agendado, adicionar gatilhos de trabalho mais tarde, adicionar o parâmetro *RunNow* para iniciar o trabalho imediatamente, usar o cmdlet Start-Job para iniciar o trabalho imediatamente a qualquer momento ou salvar o trabalho agendado não disparado como um modelo para outros trabalhos.

**Set-ScheduledJob** é um de uma coleção de cmdlets de agendamento de trabalho no módulo PSScheduledJob que está incluído no Windows PowerShell.

Para obter mais informações sobre trabalhos agendados, consulte os tópicos sobre o módulo PSScheduledJob.
Importe o módulo PSScheduledJob e, em seguida, digite: `Get-Help about_Scheduled*` ou consulte about_Scheduled_Jobs.

Este cmdlet foi introduzido no Windows PowerShell 3.0.

## EXEMPLOS

### Exemplo 1: alterar o script que um trabalho executa

```
PS C:\> Get-ScheduledJob -Name "Inventory"
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          Inventory       {1}             C:\Scripts\Get-Inventory.ps1             True

The second command uses the Get-ScheduledJob cmdlet to get the Inventory scheduled job. A pipeline operator (|) sends the scheduled job to the **Set-ScheduledJob** cmdlet. The **Set-ScheduledJob** cmdlet uses the *Script* parameter to specify a new script, Get-FullInventory.ps1. The command uses the *Passthru* parameter to return the scheduled job after the change.
PS C:\> Get-ScheduledJob -Name "Inventory" | Set-ScheduledJob -FilePath "C:\Scripts\Get-FullInventory.ps1" -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          Inventory       {1}             C:\Scripts\Get-FullInventory.ps1         True
```

Este exemplo mostra como alterar o script que é executado em um trabalho agendado.

O primeiro comando usa o cmdlet Get-ScheduledJob para obter o trabalho agendado de inventário.
A saída mostra que o trabalho executa o script Get-Inventory.ps1.

Este comando não é obrigatório. Ele está incluído apenas para mostrar o efeito da alteração do script.

### Exemplo 2: excluir o histórico de execução de um trabalho agendado

```
PS C:\> Get-ScheduledJob BackupArchive | Set-ScheduledJob -ClearExecutionHistory
```

Esse comando exclui o histórico de execução atual e salva os resultados do trabalho para o trabalho agendado BackupArchive.

O comando usa o cmdlet Get-ScheduledJob para obter o trabalho agendado do BackupArchive.
Um operador de pipeline (|) envia o trabalho para o cmdlet **Set-ScheduledJob** para alterá-lo.
O cmdlet **set-ScheduledJob** usa o parâmetro *ClearExecutionHistory* para excluir o histórico de execução e os resultados salvos.

Para obter mais informações sobre o histórico de execução e os resultados do trabalho dos trabalhos agendados salvos, consulte about_Scheduled_Jobs.

### Exemplo 3: alterar os trabalhos agendados em um computador remoto

```
PS C:\> Invoke-Command -Computer "Server01, Server02" -ScriptBlock {Get-ScheduledJob | Set-ScheduledJob -InitializationScript \\SrvA\Scripts\SetForRun.ps1}
```

Esse comando altera o script de inicialização em todos os trabalhos agendados nos computadores Server01 e Server02.

O comando usa o cmdlet Invoke-Command para executar um comando nos computadores Server01 e Server02.

O comando remoto começa com um comando Get-ScheduledJob que obtém todos os trabalhos agendados no computador.
Os trabalhos agendados são canalizados para o cmdlet **set-ScheduledJob** , que altera o script de inicialização para SetForRun.ps1.

## PARAMETERS

### -ArgumentList
Especifica valores para os parâmetros do script especificados pelo parâmetro *FilePath* ou para o comando especificado pelo parâmetro *ScriptBlock*.

```yaml
Type: System.Object[]
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Autenticação
Especifica o mecanismo usado para autenticar as credenciais do usuário.
Os valores aceitáveis para esse parâmetro são:

- Padrão
- Basic
- CredSSP
- Digest
- Kerberos
- Negotiate
- NegotiateWithImplicitCredential

O valor padrão é Default. Para obter mais informações sobre os valores desse parâmetro, consulte [Enumeração AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism) no SDK do PowerShell.

Cuidado: a autenticação do Credential Security Support Provider (CredSSP), na qual as credenciais do usuário são passadas para um computador remoto a ser autenticado, foi projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remoto.
Esse mecanismo aumenta o risco de segurança da operação remota.
Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ScriptBlock, FilePath
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClearExecutionHistory
Exclui o histórico de execução atual e os resultados salvos do trabalho agendado.

O histórico de execução de trabalho e os resultados do trabalho são salvos com o trabalho agendado no diretório $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs no computador onde o trabalho é criado.
Para ver o histórico de execução, use o cmdlet Get-Job.
Para obter os resultados do trabalho, use o cmdlet Receive-Job.

Esse parâmetro não afeta os eventos que o Agendador de tarefas grava nos logs de eventos do Windows e não impede que o Windows PowerShell salve os resultados do trabalho.
Para gerenciar o número de resultados de trabalho que são salvos, use o parâmetro *MaxResultCount*.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Execution
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Especifica uma conta de usuário que tenha permissão para executar o trabalho agendado.
O padrão é o usuário atual.

Digite um nome de usuário, como User01 ou Domínio01 \ Usuário01, ou insira um objeto **PSCredential** , como um do cmdlet Get-Credential.
Se você inserir apenas um nome de usuário, uma senha será solicitada.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath
Especifica um script que o trabalho agendado executa.
Insira o caminho para um arquivo .ps1 no computador local.
Para especificar valores padrão para os parâmetros de script, use o parâmetro *ArgumentList*.
Cada trabalho agendado deve ter um valor *ScriptBlock* ou *FilePath*.

```yaml
Type: System.String
Parameter Sets: FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InitializationScript
Especifica o caminho totalmente qualificado para um script do Windows PowerShell (.ps1).
O script de inicialização é executado na sessão criada para o trabalho em segundo plano antes dos comandos especificados pelo parâmetro *ScriptBlock* ou pelo script especificado pelo parâmetro *FilePath*.
Você pode usar o script de inicialização para configurar a sessão, adicionando arquivos, funções ou aliases, criando diretórios ou verificando pré-requisitos.

Para especificar um script que execute os comandos de trabalho principal, use o parâmetro *FilePath*.

Se o script de inicialização gerar um erro, incluindo um erro de não finalização, a instância atual do trabalho agendado não será executada e seu status falhará.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Especifica o trabalho agendado a ser alterado.
Insira uma variável que contenha objetos **ScheduledJobDefinition** ou digite um comando ou uma expressão que obtenha objetos **ScheduledJobDefinition** , como um comando Get-ScheduledJob.
Você também pode canalizar um objeto **ScheduledJobDefinition** para **set-ScheduledJob**.

Se você especificar vários trabalhos agendados, o **Set-ScheduledJob** faz as mesmas alterações em todos os trabalhos.

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MaxResultCount
Especifica quantas entradas de resultado do trabalho são mantidas para o trabalho agendado.
O valor padrão é 32.

O Windows PowerShell salva o histórico de execução e os resultados de cada instância disparada do trabalho agendado no disco.
O valor desse parâmetro determina o número de resultados de instância de trabalho que são salvas para essa tarefa agendada.
Quando o número de resultados de instância de trabalho excede esse valor, o Windows PowerShell exclui os resultados da instância de trabalho mais antiga para abrir espaço para os resultados da instância de trabalho mais recente.

O histórico de execução do trabalho e os resultados do trabalho são salvos nos diretórios do $home \AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs \\ \<JobName\> \Output \\ \<Timestamp\> no computador em que o trabalho foi criado.
Para ver o histórico de execução, use o cmdlet Get-Job.
Para obter os resultados do trabalho, use o cmdlet Receive-Job.

O parâmetro *MaxResultCount* define o valor da propriedade ExecutionHistoryLength do trabalho agendado.

Para excluir os resultados de trabalho e o histórico de execução atuais, use o parâmetro *ClearExecutionHistory*.

```yaml
Type: System.Int32
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Especifica um novo nome para o trabalho agendado e instâncias do trabalho agendado.
O nome deve ser exclusivo no computador local.

Para identificar o trabalho agendado a ser alterado, use o parâmetro *InputObject* ou redirecione um trabalho agendado de Get-ScheduledJob para **set-ScheduledJob**.

Esse parâmetro não altera os nomes das instâncias de trabalho em disco.
Ele afeta somente instâncias de trabalho que foram iniciadas após a conclusão do comando.

```yaml
Type: System.String
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Retorna um objeto que representa o item com que você está trabalhando.
Por padrão, este cmdlet não gera saída.

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

### -RunAs32
Executa o trabalho agendado em um processo de 32 bits.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ScriptBlock, FilePath
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
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunNow
Inicia um trabalho imediatamente, assim que o cmdlet **set-ScheduledJob** é executado.
Esse parâmetro elimina a necessidade de disparar o Agendador de tarefas para executar um script do Windows PowerShell imediatamente após o registro e não exige que os usuários criem um disparador que especifica a data e a hora de início.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduledJobOption
Define opções para o trabalho agendado.
Insira um objeto **ScheduledJobOptions** , como um que você cria usando o cmdlet New-ScheduledJobOption ou um valor de tabela de hash.

Você pode definir opções para um trabalho agendado ao registrar o trabalho agendado ou usar os cmdlets Set-ScheduledJobOption ou **set-ScheduledJob** para definir ou alterar opções.

Muitas das opções e seus valores padrão determinam se e quando um trabalho agendado será executado.
Certifique-se de examinar essas opções antes de agendar um trabalho.
Para obter uma descrição das opções de trabalho agendado, incluindo os valores padrão, consulte New-ScheduledJobOption.

Para enviar uma tabela de hash, use as seguintes chaves.
Na tabela de hash a seguir, as chaves são exibidas com seus valores padrão.

`@{# Power SettingsStartIfOnBattery=$False;StopIfGoingOnBattery=$True; WakeToRun=$False; # Idle SettingsStartIfNotIdle=$False; IdleDuration="00:10:00"; IdleTimeout="01:00:00"; StopIfGoingOffIdle=$True; RestartOnIdleResume=$False;# Security settingsShowInTaskScheduler=$TrueRunElevated=$False;# MiscRunWithoutNetwork=$False;DoNotAllowDemandStart=$False;MultipleInstancePolicy=IgnoreNew# Can be IgnoreNew, Parallel, Queue, StopExisting}`

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptBlock
Especifica os comandos que o trabalho agendado executa.
Coloque os comandos entre chaves ({}) para criar um bloco de script.
Para especificar valores padrão para os parâmetros de comando, use o parâmetro *ArgumentList*.

Cada comando Register-ScheduledJob deve usar o parâmetro *ScriptBlock* ou *FilePath*.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Gatilho
Especifica os gatilhos para o trabalho agendado.
Insira um ou mais objetos **ScheduledJobTrigger** , como os objetos retornados pelo cmdlet New-JobTrigger ou uma tabela de hash de chaves e valores de gatilho de trabalho.

Um gatilho de trabalho inicia um trabalho agendado automaticamente em um único tempo ou recorrente agendado ou quando ocorre um evento.

Disparadores de trabalho são opcionais.
Você pode adicionar um gatilho ao criar o trabalho agendado, usar os cmdlets Add-JobTrigger ou **set-ScheduledJob** para adicionar gatilhos posteriormente ou usar o cmdlet Start-Job para iniciar o trabalho agendado imediatamente.
Você também pode criar e manter um trabalho agendado sem nenhum disparador de trabalho.

Para enviar uma tabela de hash, use as seguintes chaves.

`@{Frequency="Once" (or Daily, Weekly, AtStartup, AtLogon);At="3am"` (ou qualquer cadeia de hora válida); `DaysOfWeek="Monday", "Wednesday"` (ou qualquer combinação de nomes de dias); `Interval=2` (ou qualquer intervalo de frequência válido); `RandomDelay="30minutes"` (ou qualquer cadeia de caracteres TimeSpan válida); `User="Domain1\User01"` (ou qualquer usuário válido; usado somente com o valor de frequência AtLogon)

}

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: ScriptBlock, FilePath
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

### Microsoft. PowerShell. ScheduledJob. ScheduledJobDefinition
Você pode direcionar trabalhos agendados para **Set-ScheduledJob**.

## SAÍDAS

### Nenhum ou Microsoft. PowerShell. ScheduledJob. ScheduledJobDefinition
Se você usar o parâmetro *Passthru* , **Set-ScheduledJob** retorna o trabalho agendado que foi alterado.
Caso contrário, este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

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
