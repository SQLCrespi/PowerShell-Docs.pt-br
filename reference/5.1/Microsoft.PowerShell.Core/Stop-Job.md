---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/stop-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Job
ms.openlocfilehash: 0c26103f47a39cb1dbd0a9f0374f7622389329a6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193498"
---
# Stop-Job

## SINOPSE
Interrompe um trabalho em segundo plano do PowerShell.

## SYNTAX

### SessionIdParameterSet (padrão)

```
Stop-Job [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### JobParameterSet

```
Stop-Job [-Job] <Job[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### NameParameterSet

```
Stop-Job [-PassThru] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InstanceIdParameterSet

```
Stop-Job [-PassThru] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### StateParameterSet

```
Stop-Job [-PassThru] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FilterParameterSet

```
Stop-Job [-PassThru] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Stop-Job** interrompe os trabalhos em segundo plano do PowerShell que estão em andamento.
Você pode usar este cmdlet para interromper todos os trabalhos ou parar trabalhos selecionados com base em seu nome, ID, ID de instância ou estado ou passando um objeto de trabalho para **Stop-Job** .

Você pode usar **Stop-Job** para interromper trabalhos em segundo plano, como aqueles que foram iniciados usando o cmdlet Start-Job ou o parâmetro *AsJob* de qualquer cmdlet.
Quando você interrompe um trabalho em segundo plano, o PowerShell conclui todas as tarefas que estão pendentes na fila de trabalho e, em seguida, encerra o trabalho.
Nenhuma tarefa nova é adicionada à fila depois que esse comando é enviado.

Esse cmdlet não exclui os trabalhos em segundo plano.
Para excluir um trabalho, use o cmdlet Remove-Job.

A partir do Windows PowerShell 3,0, o **Stop-Job** também interrompe os tipos de trabalho personalizados, como trabalhos de workflow e instâncias de trabalhos agendados.
Para habilitar **Stop-Job** para parar um trabalho com tipo de trabalho personalizado, importe o módulo que dá suporte ao tipo de trabalho personalizado na sessão antes de executar um comando **Stop-Job** , seja usando o cmdlet Import-Module ou usando ou obtendo um cmdlet no módulo.
Para obter informações sobre um tipo específico de trabalho personalizado, consulte a documentação do recurso de tipo de trabalho personalizado.

## EXEMPLOS

### Exemplo 1: parar um trabalho em um computador remoto usando Invoke-Command

```powershell
$s = New-PSSession -ComputerName Server01 -Credential Domain01\Admin02
$j = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Invoke-Command -Session $s -ScriptBlock { Stop-job -Job $Using:j }
```

Esse exemplo mostra como usar o cmdlet **Stop-Job** para interromper um trabalho que está sendo executado em um computador remoto.

Como o trabalho foi iniciado usando o cmdlet Invoke-Command para executar um comando **Start-Job** remotamente, o objeto de trabalho é armazenado no computador remoto.
Você deve usar outro comando **Invoke-Command** para executar um comando **Stop-Job** remotamente.
Para obter mais informações sobre trabalhos remotos em segundo plano, consulte about_Remote_Jobs.

O primeiro comando cria uma sessão do PowerShell ( **PSSession** ) no computador Server01 e, em seguida, armazena o objeto de sessão na variável $s.
O comando usa as credenciais de um administrador de domínio.

O segundo comando usa o cmdlet **Invoke-Command** para executar um comando **Start-Job** na sessão.
O comando no trabalho obtém todos os eventos no log de eventos do Sistema.
O objeto de trabalho resultante é armazenado na variável $j.

O terceiro comando interrompe o trabalho.
Ele usa o cmdlet **Invoke-Command** para executar um comando **Stop-Job** em **PSSession** em Server01.
Como os objetos de trabalho são armazenados em $j, que é uma variável no computador local, o comando usa o modificador de escopo Using para identificar $j como uma variável local.
Para obter mais informações sobre o modificador de escopo de uso, consulte [about_Remote_Variables](about/about_Remote_Variables.md).

Quando o comando for concluído, o trabalho será interrompido e a **PSSession** em $s estará disponível para uso.

### Exemplo 2: parar um trabalho em segundo plano

```powershell
Stop-Job -Name "Job1"
```

Esse comando interrompe o trabalho de plano de fundo Job1.

### Exemplo 3: parar vários trabalhos em segundo plano

```powershell
Stop-Job -Id 1, 3, 4
```

Esse comando interrompe três trabalhos.
Ele os identifica por suas IDs.

### Exemplo 4: parar todos os trabalhos em segundo plano

```powershell
Get-Job | Stop-Job
```

Esse comando interrompe todos os trabalhos de segundo plano na sessão atual.

### Exemplo 5: parar todos os trabalhos em segundo plano bloqueados

```powershell
Stop-Job -State Blocked
```

Esse comando interrompe todos os trabalhos que estão bloqueados.

### Exemplo 6: parar um trabalho usando uma ID de instância

```powershell
Get-Job | Format-Table ID, Name, Command, @{Label="State";Expression={$_.JobStateInfo.State}},
InstanceID -Auto
```

```Output
Id Name Command                 State  InstanceId
-- ---- -------                 -----  ----------
1 Job1 start-service schedule Running 05abb67a-2932-4bd5-b331-c0254b8d9146
3 Job3 start-service schedule Running c03cbd45-19f3-4558-ba94-ebe41b68ad03
5 Job5 get-service s*         Blocked e3bbfed1-9c53-401a-a2c3-a8db34336adf
```

```powershell
Stop-Job -InstanceId e3bbfed1-9c53-401a-a2c3-a8db34336adf
```

Esses comandos mostram como interromper um trabalho com base em sua ID de instância.

O primeiro comando usa o cmdlet Get-Job para obter os trabalhos na sessão atual.
O comando usa um operador de pipeline (|) para enviar os trabalhos para um comando Format-Table, que exibe uma tabela das propriedades especificadas de cada trabalho.
A tabela inclui a ID da instância de cada trabalho.
Ele usa uma propriedade calculada para exibir o estado do trabalho.

O segundo comando usa um comando **Stop-Job** que tem o parâmetro *InstanceId* para interromper um trabalho selecionado.

### Exemplo 7: parar um trabalho em um computador remoto

```powershell
$j = Invoke-Command -ComputerName Server01 -ScriptBlock {Get-EventLog System} -AsJob
$j | Stop-Job -PassThru
```

```Output
Id    Name    State      HasMoreData     Location         Command
--    ----    ----       -----------     --------         -------
5     Job5    Stopped    True            user01-tablet    get-eventlog system
```

Esse exemplo mostra como usar o cmdlet **Stop-Job** para interromper um trabalho que está sendo executado em um computador remoto.

Como o trabalho foi iniciado usando o parâmetro *AsJob* do cmdlet **Invoke-Command** , o objeto de trabalho está localizado no computador local, embora o trabalho seja executado no computador remoto.
Portanto, você pode usar um comando local **Stop-Job** para interromper o trabalho.

O primeiro comando usa o cmdlet **Invoke-Command** para iniciar um trabalho de segundo plano no computador Server01.
O comando usa o parâmetro *AsJob* para executar o comando remoto como um trabalho em segundo plano.

Esse comando retorna um objeto de trabalho, que é o mesmo objeto de trabalho retornado pelo cmdlet **Start-Job** .
O comando salva o objeto de trabalho na variável $j.

O segundo comando usa um operador de pipeline para enviar o trabalho na variável $j para Stop-Job.
O comando usa o parâmetro *PassThru* para instruir **Stop-Job** a retornar um objeto de trabalho.
A exibição do objeto de trabalho confirma que o estado do trabalho foi interrompido.

Para obter mais informações sobre trabalhos remotos em segundo plano, consulte about_Remote_Jobs.

## PARAMETERS

### -Filter

Especifica uma tabela de hash de condições.
Esse cmdlet interrompe os trabalhos que atendem a todas as condições.
Insira uma tabela de hash na qual as chaves são propriedades do trabalho e os valores são valores de propriedade do trabalho.

Este parâmetro funciona somente em tipos de trabalho personalizados, como os de fluxo de trabalho e os trabalhos agendados.
Ele não funciona em trabalhos em segundo plano padrão, como aqueles criados usando o cmdlet **Start-Job** .
Para obter informações sobre o suporte para este parâmetro, consulte o tópico da Ajuda para o tipo de trabalho em questão.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: FilterParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Id

Especifica as IDs de trabalhos que este cmdlet interrompe.
O padrão é todos os trabalhos na sessão atual.

A ID é um inteiro que identifica exclusivamente o trabalho na sessão atual.
É mais fácil lembrar e digitar do que a ID da instância, mas só é exclusiva na sessão atual.
Você pode digitar uma ou mais IDs, separadas por vírgulas.
Para localizar a ID de um trabalho, digite `Get-Job` .

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId

Especifica as IDs de instância dos trabalhos que este cmdlet interrompe.
O padrão é obter todos os trabalhos.

Uma ID de instância é um GUID que identifica exclusivamente o trabalho no computador.
Para localizar a ID da instância de um trabalho, use Get-Job.

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Trabalho

Especifica os trabalhos que este cmdlet interrompe.
Insira uma variável que contenha os trabalhos ou um comando que os obtenha.
Você também pode usar um operador de pipeline para enviar trabalhos para o cmdlet **Stop-Job** .
Por padrão, **Stop-Job** exclui todos os trabalhos que foram iniciados na sessão atual.

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name

Especifica nomes amigáveis de trabalhos que este cmdlet interrompe.
Digite os nomes de trabalho em uma lista separada por vírgulas ou use caracteres curinga (*) para inserir um padrão de nome de trabalho.
Por padrão, **Stop-Job** interrompe todos os trabalhos criados na sessão atual.

Como não há garantia de que o nome amigável seja exclusivo, use os parâmetros *WhatIf* e *Confirm* ao parar trabalhos por nome.

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Estado

Especifica um estado de trabalho.
Este cmdlet interrompe apenas os trabalhos no estado especificado.
Os valores aceitáveis para esse parâmetro são:

- NotStarted
- Executando
- Concluído
- Falhou
- Parado
- Bloqueado
- Suspenso
- Desconectado
- Suspensão
- Parando

Para obter mais informações sobre os Estados de trabalho, consulte [Enumeração JobState](https://msdn.microsoft.com/library/system.management.automation.jobstate) na biblioteca MSDN.

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
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

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Management. Automation. RemotingJob

É possível canalizar um objeto de trabalho para esse cmdlet.

## SAÍDAS

### Nenhum, System. Management. Automation. PSRemotingJob

Esse cmdlet retorna um objeto de trabalho, se você especificar o parâmetro *PassThru* .
Caso contrário, este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Get-Job](Get-Job.md)

[Invoke-Command](Invoke-Command.md)

[Receive-Job](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Resume-Job](Resume-Job.md)

[Start-Job](Start-Job.md)

[Suspend-Job](Suspend-Job.md)

[Wait-Job](Wait-Job.md)

[about_Job_Details](About/about_Job_Details.md)

[about_Remote_Jobs](About/about_Remote_Jobs.md)

[about_Remote_Variables](About/about_Remote_Variables.md)

[about_Jobs](About/about_Jobs.md)

[about_Scopes](About/about_scopes.md)
