---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/wait-job?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Job
ms.openlocfilehash: 560202531a992b9db8ba5d5ebc957f96750f1feb
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94389242"
---
# Wait-Job

## SINOPSE
Suprime o prompt de comando até que um ou todos os trabalhos em segundo plano do PowerShell em execução na sessão sejam concluídos.

## SYNTAX

### SessionIdParameterSet (padrão)

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Id] <Int32[]> [<CommonParameters>]
```

### JobParameterSet

```
Wait-Job [-Job] <Job[]> [-Any] [-Timeout <Int32>] [-Force] [<CommonParameters>]
```

### NameParameterSet

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Name] <String[]> [<CommonParameters>]
```

### InstanceIdParameterSet

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### StateParameterSet

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-State] <JobState> [<CommonParameters>]
```

### FilterParameterSet

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Filter] <Hashtable> [<CommonParameters>]
```

## DESCRIPTION

O `Wait-Job` cmdlet aguarda a conclusão dos trabalhos em segundo plano do PowerShell antes de exibir o prompt de comando. Você pode aguardar até que qualquer trabalho em segundo plano seja concluído, ou até que todos os trabalhos em segundo plano sejam concluídos, e pode definir um tempo de espera máximo para o trabalho.

Quando os comandos no trabalho forem concluídos, `Wait-Job` o exibirá o prompt de comando e retornará um objeto de trabalho para que você possa redirecioná-lo a outro comando.

Você pode usar `Wait-Job` o cmdlet para aguardar trabalhos em segundo plano, como aqueles que foram iniciados usando o `Start-Job` cmdlet ou o parâmetro **AsJob** do `Invoke-Command` cmdlet. Para obter mais informações sobre trabalhos em segundo plano do Windows PowerShell, consulte [about_Jobs](./about/about_Jobs.md).

A partir do Windows PowerShell 3,0, o `Wait-Job` cmdlet também aguarda tipos de trabalhos personalizados, como trabalhos de fluxo de trabalho e instâncias de trabalhos agendados. Para permitir `Wait-Job` que o aguarde trabalhos de um tipo específico, importe o módulo que dá suporte ao tipo de trabalho personalizado na sessão antes de executar o `Get-Job` cmdlet, seja usando o `Import-Module` cmdlet ou obtendo um cmdlet no módulo. Para obter informações sobre um tipo específico de trabalho personalizado, consulte a documentação do recurso de tipo de trabalho personalizado.

## EXEMPLOS

### Exemplo 1: aguardar todos os trabalhos

```powershell
Get-Job | Wait-Job
```

Esse comando espera que todos os trabalhos em segundo plano em execução na sessão sejam concluídos.

### Exemplo 2: aguardar os trabalhos iniciados em computadores remotos usando Start-Job

```powershell
$s = New-PSSession Server01, Server02, Server03
Invoke-Command -Session $s -ScriptBlock {Start-Job -Name Date1 -ScriptBlock {Get-Date}}
$done = Invoke-Command -Session $s -Command {Wait-Job -Name Date1}
$done.Count
```

```Output
3
```

Este exemplo mostra como usar o `Wait-Job` cmdlet com trabalhos iniciados em computadores remotos usando o `Start-Job` cmdlet. Os `Start-Job` `Wait-Job` comandos e são enviados para o computador remoto usando o `Invoke-Command` cmdlet.

Este exemplo usa `Wait-Job` para determinar se um `Get-Date` comando executado como um trabalho em segundo plano em três computadores diferentes foi concluído.

O primeiro comando cria uma sessão do Windows PowerShell ( **PSSession** ) em cada um dos três computadores remotos e os armazena na `$s` variável.

O segundo comando usa `Invoke-Command` para ser executado `Start-Job` em cada uma das três sessões no `$s` .
Todos os trabalhos são nomeados Data1.

O terceiro comando usa `Invoke-Command` para executar `Wait-Job` . Esse comando espera que os trabalhos data1 em cada computador sejam concluídos. Ele armazena a coleção resultante (matriz) de objetos de trabalho na `$done` variável.

O quarto comando usa a propriedade **Count** da matriz de objetos de trabalho na `$done` variável para determinar quantos dos trabalhos foram concluídos.

### Exemplo 3: determinar quando o primeiro trabalho em segundo plano é concluído

```powershell
$s = New-PSSession (Get-Content Machines.txt)
$c = 'Get-EventLog -LogName System | where {$_.EntryType -eq "error" --and $_.Source -eq "LSASRV"} | Out-File Errors.txt'
Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {$Using:c}
Invoke-Command -Session $s -ScriptBlock {Wait-Job -Any}
```

Este exemplo usa o parâmetro **any** de `Wait-Job` para determinar quando o primeiro dos muitos trabalhos em segundo plano em execução na sessão atual são concluídos. Ele também mostra como usar o `Wait-Job` cmdlet para aguardar a conclusão de trabalhos remotos.

O primeiro comando cria uma **PSSession** em cada um dos computadores listados no arquivo de Machines.txt e armazena os objetos **PSSession** na `$s` variável. O comando usa o `Get-Content` cmdlet para obter o conteúdo do arquivo. O `Get-Content` comando é colocado entre parênteses para garantir que ele seja executado antes do `New-PSSession` comando.

O segundo comando armazena uma `Get-EventLog` cadeia de caracteres de comando, entre aspas, na `$c` variável.

O terceiro comando usa o `Invoke-Command` cmdlet para executar `Start-Job` em cada uma das sessões no `$s` .
O `Start-Job` comando inicia um trabalho em segundo plano que executa o `Get-EventLog` comando na `$c` variável.

O comando usa o modificador de escopo de **uso** para indicar que a `$c` variável foi definida no computador local. O modificador de escopo **Using** foi introduzido no Windows PowerShell 3.0. Para obter mais informações sobre o modificador de escopo de **uso** , consulte [about_Remote_Variables](./about/about_Remote_Variables.md).

O quarto comando usa `Invoke-Command` para executar um `Wait-Job` comando nas sessões. Ele usa o parâmetro **any** para aguardar até que o primeiro trabalho nos computadores remotos seja concluído.

### Exemplo 4: definir um tempo de espera para trabalhos em computadores remotos

```powershell
$s = New-PSSession Server01, Server02, Server03
$jobs = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {Get-Date}}
$done = Invoke-Command -Session $s -ScriptBlock {Wait-Job -Timeout 30}
```

Este exemplo mostra como usar o parâmetro **Timeout** de `Wait-Job` para definir um tempo de espera máximo para os trabalhos em execução em computadores remotos.

O primeiro comando cria uma **PSSession** em cada um dos três computadores remotos (Server01, Server02 e Server03) e, em seguida, armazena os objetos **PSSession** na `$s` variável.

O segundo comando usa `Invoke-Command` para ser executado `Start-Job` em cada um dos objetos **PSSession** no `$s` . Ele armazena os objetos de trabalho resultantes na `$jobs` variável.

O terceiro comando usa `Invoke-Command` para ser executado `Wait-Job` em cada uma das sessões no `$s` . O `Wait-Job` comando determina se todos os comandos foram concluídos dentro de 30 segundos. Ele usa o parâmetro **Timeout** com um valor de 30 para estabelecer o tempo de espera máximo e, em seguida, armazena os resultados do comando na `$done` variável.

Nesse caso, após 30 segundos, apenas o comando no computador Server02 foi concluído. `Wait-Job` termina a espera, exibe o prompt de comando e retorna o objeto que representa o trabalho que foi concluído.

A `$done` variável contém um objeto de trabalho que representa o trabalho executado em Server02.

### Exemplo 5: Aguarde até que um dos vários trabalhos seja concluído

```powershell
Wait-Job -id 1,2,5 -Any
```

Esse comando identifica três trabalhos por suas IDs e aguarda até que qualquer um deles seja concluído.
O prompt de comando retorna quando o primeiro trabalho é concluído.

### Exemplo 6: aguardar um período e permitir que o trabalho continue em segundo plano

```powershell
Wait-Job -Name "DailyLog" -Timeout 120
```

Esse comando aguarda 120 segundos (dois minutos) para que o trabalho de DailyLog seja concluído. Se o trabalho não for concluído nos próximos dois minutos, o prompt de comando retornará de qualquer forma e o trabalho continuará a ser executado em segundo plano.

### Exemplo 7: aguardar um trabalho por nome

```powershell
Wait-Job -Name "Job3"
```

Esse comando usa o nome do trabalho para identificar o trabalho a ser aguardado.

### Exemplo 8: aguardar trabalhos no computador local iniciados com Start-Job

```powershell
$j = Start-Job -ScriptBlock {Get-ChildItem *.ps1| where {$_lastwritetime -gt ((Get-Date) - (New-TimeSpan -Days 7))}}
$j | Wait-Job
```

Este exemplo mostra como usar o `Wait-Job` cmdlet com trabalhos iniciados no computador local usando o `Start-Job` .

Esses comandos iniciam um trabalho que obtém os arquivos de script do Windows PowerShell que foram adicionados ou atualizados na última semana.

O primeiro comando usa `Start-Job` para iniciar um trabalho em segundo plano no computador local. O trabalho executa um `Get-ChildItem` comando que obtém todos os arquivos que têm uma extensão de nome de arquivo. ps1 que foram adicionados ou atualizados na última semana.

O terceiro comando usa `Wait-Job` para aguardar até que o trabalho seja concluído. Quando o trabalho for concluído, o comando exibirá o objeto de trabalho, que contém informações sobre o trabalho.

### Exemplo 9: aguardar trabalhos iniciados em computadores remotos usando Invoke-Command

```powershell
$s = New-PSSession Server01, Server02, Server03
$j = Invoke-Command -Session $s -ScriptBlock {Get-Process} -AsJob
$j | Wait-Job
```

Este exemplo mostra como usar `Wait-Job` com trabalhos iniciados em computadores remotos usando o parâmetro **AsJob** de `Invoke-Command` . Ao usar **AsJob** , o trabalho é criado no computador local e os resultados são retornados automaticamente para o computador local, mesmo que o trabalho seja executado nos computadores remotos.

Este exemplo usa `Wait-Job` para determinar se um `Get-Process` comando em execução nas sessões em três computadores remotos está concluído.

O primeiro comando cria objetos **PSSession** em três computadores e os armazena na `$s` variável.

O segundo comando usa `Invoke-Command` para ser executado `Get-Process` em cada uma das três sessões no `$s` .
O comando usa o parâmetro **AsJob** para executar o comando de forma assíncrona como um trabalho em segundo plano. O comando retorna um objeto de trabalho, assim como os trabalhos iniciados usando o `Start-Job` , e o objeto de trabalho é armazenado na `$j` variável.

O terceiro comando usa um operador de pipeline ( `|` ) para enviar o objeto de trabalho `$j` para o `Wait-Job` cmdlet. Um `Invoke-Command` comando não é necessário nesse caso, porque o trabalho reside no computador local.

### Exemplo 10: aguardar um trabalho que tenha uma ID

```powershell
Get-Job
```

```Output
Id   Name     State      HasMoreData     Location             Command
--   ----     -----      -----------     --------             -------
1    Job1     Completed  True            localhost,Server01.. get-service
4    Job4     Completed  True            localhost            dir | where
```

```powershell
Wait-Job -Id 1
```

Este comando aguarda o trabalho com um valor de ID de 1.

## PARAMETERS

### -Qualquer

Indica que esse cmdlet exibe o prompt de comando e retorna o objeto de trabalho, quando qualquer trabalho é concluído. Por padrão, o `Wait-Job` aguarda até que todos os trabalhos especificados sejam concluídos antes de exibir o prompt.

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

### -Filter

Especifica uma tabela de hash de condições. Esse cmdlet aguarda trabalhos que atendem a todas as condições na tabela de hash. Insira uma tabela de hash na qual as chaves são propriedades do trabalho e os valores são valores de propriedade do trabalho.

Este parâmetro funciona somente em tipos de trabalho personalizados, como os de fluxo de trabalho e os trabalhos agendados. Ele não funciona em trabalhos em segundo plano padrão, como aqueles criados usando o `Start-Job` cmdlet. Para obter informações sobre o suporte para este parâmetro, consulte o tópico da Ajuda para o tipo de trabalho em questão.

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

### -Force

Indica que esse cmdlet continua aguardando trabalhos no estado suspenso ou desconectado. Por padrão, `Wait-Job` retorna ou termina a espera, quando os trabalhos estão em um dos seguintes Estados:

- Concluído
- Falhou
- Parado
- Suspenso
- Desconectado

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

### -Id

Especifica uma matriz de IDs de trabalhos para os quais esse cmdlet espera.

A ID é um inteiro que identifica exclusivamente o trabalho na sessão atual. É mais fácil lembrar e digitar do que a ID da instância, mas só é exclusiva na sessão atual. Você pode digitar uma ou mais IDs, separadas por vírgulas. Para localizar a ID de um trabalho, digite `Get-Job` .

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

Especifica uma matriz de IDs de instância dos trabalhos para os quais esse cmdlet espera. O padrão é obter todos os trabalhos.

Uma ID de instância é um GUID que identifica exclusivamente o trabalho no computador. Para localizar a ID de instância de um trabalho, use `Get-Job` .

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

Especifica os trabalhos para os quais esse cmdlet espera. Insira uma variável que contém os objetos de trabalho ou um comando que obtém os objetos de trabalho. Você também pode usar um operador de pipeline para enviar objetos de trabalho para o `Wait-Job` cmdlet. Por padrão, o `Wait-Job` aguarda todos os trabalhos criados na sessão atual.

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

Especifica nomes amigáveis de trabalhos para os quais esse cmdlet espera.

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Estado

Especifica um estado de trabalho. Esse cmdlet aguarda apenas os trabalhos no estado especificado. Os valores aceitáveis para esse parâmetro são:

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

Para obter mais informações sobre os Estados de trabalho, consulte [Enumeração JobState](/dotnet/api/system.management.automation.jobstate).

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tempo limite

Especifica o tempo de espera máximo para cada trabalho em segundo plano, em segundos. O valor padrão,-1, indica que o cmdlet aguarda até que o trabalho seja concluído. O tempo começa quando você envia o `Wait-Job` comando, não o `Start-Job` comando.

Se esse tempo for excedido, a espera termina, e o comando prompt retorna, mesmo se o trabalho ainda está em execução. O comando não exibe nenhuma mensagem de erro.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Management. Automation. RemotingJob

É possível canalizar um objeto de trabalho para esse cmdlet.

## SAÍDAS

### System. Management. Automation. PSRemotingJob

Esse cmdlet retorna objetos de trabalho que representam os trabalhos concluídos. Se a espera terminar porque o valor do parâmetro **Timeout** é excedido, o não `Wait-Job` retorna nenhum objeto.

## OBSERVAÇÕES

Por padrão, `Wait-Job` retorna ou termina a espera, quando os trabalhos estão em um dos seguintes Estados:

- Concluído
- Falhou
- Parado
- Suspenso
- Desconectado para direcionar `Wait-Job` para continuar aguardando trabalhos suspensos e desconectados, use o parâmetro **Force** .

## LINKS RELACIONADOS

[Get-Job](Get-Job.md)

[Invoke-Command](Invoke-Command.md)

[Receive-Job](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job](Stop-Job.md)
