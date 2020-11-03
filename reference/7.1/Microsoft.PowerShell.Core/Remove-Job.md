---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-job?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Job
ms.openlocfilehash: b65e990c8d03858705b167bd1712ab6fde305a82
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194572"
---
# Remove-Job

## SINOPSE
Exclui um trabalho em segundo plano do PowerShell.

## SYNTAX

### SessionIdParameterSet (padrão)

```
Remove-Job [-Force] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### JobParameterSet

```
Remove-Job [-Job] <Job[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### NameParameterSet

```
Remove-Job [-Force] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InstanceIdParameterSet

```
Remove-Job [-Force] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FilterParameterSet

```
Remove-Job [-Force] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### StateParameterSet

```
Remove-Job [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CommandParameterSet

```
Remove-Job [-Command <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Remove-Job` cmdlet exclui trabalhos em segundo plano do PowerShell que foram iniciados pelo `Start-Job` cmdlet ou por cmdlets como `Invoke-Command` o que dão suporte ao parâmetro **AsJob** .

Você pode usar `Remove-Job` para excluir todos os trabalhos ou excluir trabalhos selecionados. Os trabalhos são identificados por seu **nome** , **ID** , **ID de instância** , **comando** ou **estado** . Ou, um objeto de trabalho pode ser enviado ao pipeline para `Remove-Job` . Sem parâmetros ou valores de parâmetro, `Remove-Job` não tem efeito.

Como o PowerShell 3,0, `Remove-Job` o pode excluir tipos de trabalhos personalizados, como trabalhos agendados e trabalhos de fluxo de trabalho. Por exemplo, `Remove-Job` exclui o trabalho agendado, todas as instâncias do trabalho agendado no disco e os resultados de todas as instâncias de trabalho disparadas.

Se você tentar excluir um trabalho em execução, o `Remove-Job` falhará. Use o `Stop-Job` cmdlet para interromper um trabalho em execução. Ou use `Remove-Job` com o parâmetro **Force** para excluir um trabalho em execução.

Os trabalhos permanecem no cache de trabalhos globais até que você exclua o trabalho em segundo plano ou feche a sessão do PowerShell.

## EXEMPLOS

### Exemplo 1: excluir um trabalho usando seu nome

Este exemplo usa uma variável e o pipeline para excluir um trabalho por nome.

```powershell
$batch = Get-Job -Name BatchJob
$batch | Remove-Job
```

`Get-Job` usa o parâmetro **Name** para especificar o trabalho, **BatchJob** . O objeto de trabalho é armazenado na `$batch` variável. O objeto no `$batch` é enviado ao pipeline para `Remove-Job` .

Uma alternativa é usar o parâmetro **Job** , como `Remove-Job -Job $batch` .

### Exemplo 2: excluir todos os trabalhos em uma sessão

Neste exemplo, todos os trabalhos na sessão atual do PowerShell são excluídos.

```powershell
Get-job | Remove-Job
```

`Get-Job` Obtém todos os trabalhos na sessão atual do PowerShell. Os objetos de trabalho são enviados ao pipeline para o `Remove-Job` .

### Exemplo 3: excluir trabalhos não iniciados

Este exemplo exclui todos os trabalhos da sessão atual do PowerShell que não foram iniciadas.

```powershell
Remove-Job -State NotStarted
```

`Remove-Job` usa o parâmetro **State** para especificar o status do trabalho.

### Exemplo 4: excluir trabalhos usando um nome amigável

Este exemplo exclui todos os trabalhos da sessão atual com nomes amigáveis que terminam com * batch * *, incluindo os trabalhos que estão em execução.

```powershell
Remove-Job -Name *batch -Force
```

`Remove-Job` usa o parâmetro **Name** para especificar um padrão de nome de trabalho. O padrão inclui o curinga asterisco ( `*` ) para localizar todos os nomes de trabalho que terminam com o **lote** . O parâmetro **Force** exclui trabalhos que executam o.

### Exemplo 5: excluir um trabalho criado por Invoke-Command

Este exemplo remove um trabalho que foi iniciado em um computador remoto usando `Invoke-Command` com o parâmetro **AsJob** .

Como o exemplo usa o parâmetro **AsJob** , o objeto de trabalho é criado no computador local.
No entanto, o trabalho é executado em um computador remoto. Como resultado, você deve usar comandos locais para gerenciar o trabalho.

```powershell
$job = Invoke-Command -ComputerName Server01 -ScriptBlock {Get-Process} -AsJob
$job | Remove-Job
```

`Invoke-Command` executa um trabalho no computador **SERVER01** . O parâmetro **AsJob** executa o **scriptblock** como um trabalho em segundo plano. O objeto de trabalho é armazenado na `$job` variável. O `$job` objeto Variable é enviado ao pipeline para `Remove-Job` .

### Exemplo 6: excluir um trabalho que foi criado por Invoke-Command e Start-Job

Este exemplo mostra como remover um trabalho em um computador remoto que foi iniciado usando o `Invoke-Command` para executar o `Start-Job` . O objeto de trabalho é criado no computador remoto e os comandos remotos são usados para gerenciar o trabalho. Uma conexão persistente é necessária ao executar um `Start-Job` comando remoto.

```powershell
$S = New-PSSession -ComputerName Server01
Invoke-Command -Session $S -ScriptBlock {Start-Job -ScriptBlock {Get-Process} -Name MyJob}
Invoke-Command -Session $S -ScriptBlock {Remove-Job -Name MyJob}
```

`New-PSSession` Cria uma **PSSession** , uma conexão persistente, para o computador **Server01** . A conexão é salva na `$S` variável.

`Invoke-Command` conecta-se à sessão salva em `$S` . O **scriptblock** usa `Start-Job` para iniciar um trabalho remoto. O trabalho executa um `Get-Process` comando e usa o parâmetro **Name** para especificar um nome de trabalho amigável, **MyJob** .

`Invoke-Command` usa a `$S` sessão e executa o `Remove-Job` . O parâmetro **Name** especifica que o trabalho chamado **MyJob** é excluído.

### Exemplo 7: excluir um trabalho usando sua InstanceId

Este exemplo remove um trabalho com base em sua **InstanceId** .

```powershell
$job = Start-Job -ScriptBlock {Get-Process PowerShell}
$job | Format-List -Property *
Remove-Job -InstanceId ad02b942-8007-4407-87f3-d23e71955872
```

```Output
State         : Completed
HasMoreData   : True
StatusMessage :
Location      : localhost
Command       : Get-Process PowerShell
JobStateInfo  : Completed
Finished      : System.Threading.ManualResetEvent
InstanceId    : ad02b942-8007-4407-87f3-d23e71955872
Id            : 3
Name          : Job3
ChildJobs     : {Job4}
PSBeginTime   : 7/26/2019 11:36:56
PSEndTime     : 7/26/2019 11:36:57
PSJobTypeName : BackgroundJob
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
Information   : {}
```

`Start-Job` inicia um trabalho em segundo plano e o objeto de trabalho é salvo na `$job` variável.

O objeto no `$job` é enviado ao pipeline para `Format-List` . O parâmetro **Property** usa um asterisco ( `*` ) para especificar que todas as propriedades do objeto sejam exibidas em uma lista.

`Remove-Job` usa o parâmetro **InstanceId** para especificar o trabalho a ser excluído.

## PARAMETERS

### -Command

Exclui os trabalhos que incluem as palavras especificadas no comando. Você pode inserir uma matriz separada por vírgulas.

```yaml
Type: System.String[]
Parameter Sets: CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm

Solicita que você confirme antes que o `Remove-Job` seja executado.

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

### -Filter

Exclui os trabalhos que atendem a todas as condições estabelecidas na tabela de hash associada. Insira uma tabela de hash na qual as chaves são propriedades do trabalho e os valores são valores de propriedade do trabalho.

Este parâmetro funciona somente em tipos de trabalho personalizados, como os de fluxo de trabalho e os trabalhos agendados. Ele não funciona em trabalhos em segundo plano padrão, como aqueles criados usando o `Start-Job` .

Este parâmetro é introduzido no PowerShell 3.0.

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

### -Force

Exclui um trabalho mesmo que o estado do trabalho esteja **em execução** . Se o parâmetro **Force** não for especificado, o `Remove-Job` não excluirá os trabalhos em execução.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SessionIdParameterSet, JobParameterSet, InstanceIdParameterSet, NameParameterSet, FilterParameterSet
Aliases: F

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Exclui trabalhos em segundo plano com a **ID** especificada. Você pode inserir uma matriz separada por vírgulas. A **ID** do trabalho é um inteiro exclusivo que identifica um trabalho na sessão atual.

Para localizar a **ID** de um trabalho, use `Get-Job` sem parâmetros.

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

Exclui trabalhos com a **InstanceId** especificada. Você pode inserir uma matriz separada por vírgulas. Uma **InstanceId** é um GUID exclusivo que identifica um trabalho.

Para localizar a **InstanceId** de um trabalho, use `Get-Job` .

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Trabalho

Especifica os trabalhos a serem excluídos. Insira uma variável que contenha os trabalhos ou um comando que os obtenha. Você pode inserir uma matriz separada por vírgulas.

Você pode enviar objetos de trabalho para o pipeline para o `Remove-Job` .

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name

Somente exclui trabalhos com o nome amigável especificado. Caracteres curinga são permitidos. Você pode inserir uma matriz separada por vírgulas.

Nomes amigáveis para trabalhos não têm garantia de serem exclusivos, mesmo em uma sessão do PowerShell. Use os parâmetros **WhatIf** e **Confirm** ao excluir arquivos por nome.

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

### -Estado

Somente exclui trabalhos com o estado especificado. Para excluir trabalhos com um estado de **em execução** , use o parâmetro **Force** .

Valores aceitos:

- AtBreakpoint
- Bloqueado
- Concluído
- Desconectado
- Com falha
- NotStarted
- Executando
- Parado
- Parando
- Suspenso
- Suspensão

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: AtBreakpoint, Blocked, Completed, Disconnected, Failed, NotStarted, Running, Stopped, Stopping, Suspended, Suspending

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf

Mostra o que aconteceria se `Remove-Job` for executado. O cmdlet não é executado.

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

### System. Management. Automation. Job

Você pode enviar um objeto de trabalho para baixo do pipeline para `Remove-Job` .

## SAÍDAS

### Nenhum

`Remove-Job` não gera nenhuma saída.

## OBSERVAÇÕES

Um trabalho do PowerShell cria um novo processo. Quando o trabalho é concluído, o processo é encerrado. Quando `Remove-Job` é executado, o estado do trabalho é removido.

Se um trabalho parar antes da conclusão e seu processo não tiver sido encerrado, o processo será encerrado de modo forçado.

## LINKS RELACIONADOS

[about_Jobs](./About/about_Jobs.md)

[about_Job_Details](./About/about_Job_Details.md)

[about_Remote_Jobs](./About/about_Remote_Jobs.md)

[Get-Job](Get-Job.md)

[Invoke-Command](Invoke-Command.md)

[Receive-Job](Receive-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job](Stop-Job.md)

[Wait-Job](Wait-Job.md)

