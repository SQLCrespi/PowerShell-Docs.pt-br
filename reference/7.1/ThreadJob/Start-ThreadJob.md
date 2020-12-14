---
external help file: Microsoft.PowerShell.ThreadJob.dll-Help.xml
Locale: en-US
Module Name: ThreadJob
ms.date: 12/05/2020
online version: https://docs.microsoft.com/powershell/module/threadjob/start-threadjob?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-ThreadJob
ms.openlocfilehash: bced2b87c3843833414ebfd189d003e83af9718f
ms.sourcegitcommit: f9d855dd73b916559a22e337672dea3fbb11c634
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/07/2020
ms.locfileid: "96777740"
---
# Start-ThreadJob

## SINOPSE
Cria trabalhos em segundo plano semelhantes ao `Start-Job` cmdlet.

## SYNTAX

### Bloco de script

```
Start-ThreadJob [-ScriptBlock] <ScriptBlock> [-Name <String>] [-InitializationScript <ScriptBlock>]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [-ThrottleLimit <Int32>]
 [-StreamingHost <PSHost>] [<CommonParameters>]
```

### FilePath

```
Start-ThreadJob [-FilePath] <String> [-Name <String>] [-InitializationScript <ScriptBlock>]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [-ThrottleLimit <Int32>]
 [-StreamingHost <PSHost>] [<CommonParameters>]
```

## DESCRIPTION

`Start-ThreadJob` cria trabalhos em segundo plano semelhantes ao `Start-Job` cmdlet. A principal diferença é que os trabalhos criados são executados em threads separados dentro do processo local. Por padrão, os trabalhos usam o diretório de trabalho atual do chamador que iniciou o trabalho.

O cmdlet também dá suporte a um parâmetro **ThrottleLimit** para limitar o número de trabalhos em execução ao mesmo tempo. À medida que mais trabalhos são iniciados, eles são enfileirados e aguardam até que o número atual de trabalhos fique abaixo do limite de limitação.

## EXEMPLOS

### Exemplo 1-criar trabalhos em segundo plano com um limite de thread de 2

```powershell
Start-ThreadJob -ScriptBlock { 1..100 | % { sleep 1; "Output $_" } } -ThrottleLimit 2
Start-ThreadJob -ScriptBlock { 1..100 | % { sleep 1; "Output $_" } }
Start-ThreadJob -ScriptBlock { 1..100 | % { sleep 1; "Output $_" } }
Get-Job
```

```Output
Id   Name   PSJobTypeName   State        HasMoreData   Location     Command
--   ----   -------------   -----        -----------   --------     -------
1    Job1   ThreadJob       Running      True          PowerShell   1..100 | % { sleep 1;...
2    Job2   ThreadJob       Running      True          PowerShell   1..100 | % { sleep 1;...
3    Job3   ThreadJob       NotStarted   False         PowerShell   1..100 | % { sleep 1;...
```

### Exemplo 2 – comparar o desempenho de Start-Job e Start-ThreadJob

Este exemplo mostra a diferença entre `Start-Job` e `Start-ThreadJob` . Os trabalhos executam o `Start-Sleep` cmdlet por 1 segundo. Como os trabalhos são executados em paralelo, o tempo de execução total é de cerca de 1 segundo, além de qualquer tempo necessário para criar os trabalhos.

```powershell
# start five background jobs each running 1 second
Measure-Command {1..5 | % {Start-Job {Start-Sleep 1}} | Wait-Job} | Select-Object TotalSeconds
Measure-Command {1..5 | % {Start-ThreadJob {Start-Sleep 1}} | Wait-Job} | Select-Object TotalSeconds
```

```Output
TotalSeconds
------------
   5.7665849
   1.5735008
```

Depois de subtrair 1 segundo para o tempo de execução, você pode ver que `Start-Job` leva cerca de 4,8 segundos para criar cinco trabalhos. `Start-ThreadJob` é 8 vezes mais rápido, levando cerca de 0,6 segundos para criar cinco trabalhos. Os resultados podem variar em seu ambiente, mas a melhoria relativa deve ser a mesma.

### Exemplo 3-criar trabalhos usando InputObject

Neste exemplo, o bloco de script usa a `$input` variável para receber a entrada do parâmetro **InputObject** . Isso também pode ser feito por meio de objetos de tubulação `Start-ThreadJob` .

```powershell
$j = Start-ThreadJob -InputObject (Get-Process pwsh) -ScriptBlock { $input | Out-String }
$j | Wait-Job | Receive-Job
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     94   145.80     159.02      18.31   18276   1 pwsh
    101   163.30     222.05      29.00   35928   1 pwsh
```

```powershell
$j = Get-Process pwsh | Start-ThreadJob -ScriptBlock { $input | Out-String }
$j | Wait-Job | Receive-Job
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     94   145.80     159.02      18.31   18276   1 pwsh
    101   163.30     222.05      29.00   35928   1 pwsh
```

### Exemplo 4-fluxo de saída de trabalho para o host pai

Usando o parâmetro **StreamingHost** , você pode dizer a um trabalho para direcionar toda a saída do host para um host específico. Sem esse parâmetro, a saída vai para a coleção de fluxo de dados de trabalho e não aparece em um console de host até que você receba a saída do trabalho.

Para este exemplo, o host atual é passado para `Start-ThreadJob` usando a `$Host` variável automática.

```powershell
PS> Start-ThreadJob -ScriptBlock { Read-Host 'Say hello'; Write-Warning 'Warning output' } -StreamingHost $Host

Id   Name   PSJobTypeName   State         HasMoreData     Location      Command
--   ----   -------------   -----         -----------     --------      -------
7    Job7   ThreadJob       NotStarted    False           PowerShell    Read-Host 'Say hello'; �

PS> Say hello: Hello
WARNING: Warning output
PS> Receive-Job -Id 7
Hello
WARNING: Warning output
PS>
```

Observe que o prompt de `Read-Host` é exibido e você pode digitar a entrada. Em seguida, a mensagem de `Write-Warning` é exibida. O `Receive-Job` cmdlet retorna toda a saída do trabalho.

## PARAMETERS

### -ArgumentList

Especifica uma matriz de argumentos, ou valores de parâmetro, para o script que é especificado pelos parâmetros **FilePath** ou **scriptblock** .

**ArgumentList** deve ser o último parâmetro na linha de comando. Todos os valores que seguem o nome do parâmetro são valores interpretados na lista de argumentos.

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

### -FilePath

Especifica um arquivo de script para ser executado como um trabalho em segundo plano. Insira o caminho e o nome do arquivo do script. O script deve estar no computador local ou em uma pasta que o computador local possa acessar.

Quando você usa esse parâmetro, o PowerShell converte o conteúdo do arquivo de script especificado em um bloco de script e executa o bloco de script como um trabalho em segundo plano.

```yaml
Type: System.String
Parameter Sets: FilePath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InitializationScript

Especifica os comandos que são executados antes do trabalho ser iniciado. Coloque os comandos entre chaves ( `{}` ) para criar um bloco de script.

Use esse parâmetro para preparar a sessão na qual o trabalho é executado. Por exemplo, você pode usá-lo para adicionar funções e módulos à sessão.

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

### -InputObject

Especifica os objetos usados como entrada para o bloco de script. Ele também permite a entrada do pipeline. Use a `$input` variável automática no bloco de script para acessar os objetos de entrada.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Especifica um nome amigável para o novo trabalho. Você pode usar o nome para identificar o trabalho para outros cmdlets de trabalho, como o `Stop-Job` cmdlet.

O nome amigável padrão é "Job #", em que "#" é um número ordinal que é incrementado para cada trabalho.

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

### -ScriptBlock

Especifica os comandos a executar no trabalho em segundo plano. Coloque os comandos entre chaves ( `{}` ) para criar um bloco de script. Use a `$Input` variável automática para acessar o valor do parâmetro **InputObject** . Este parâmetro é necessário.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StreamingHost

Esse parâmetro fornece uma maneira segura de thread para permitir que a `Write-Host` saída vá diretamente para o objeto passado no **PSHost** . Sem ele, a `Write-Host` saída vai para a coleção de fluxo de dados de informações do trabalho e não aparece em um console de host até que os trabalhos terminem de ser executados.

```yaml
Type: System.Management.Automation.Host.PSHost
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Esse parâmetro limita o número de trabalhos em execução ao mesmo tempo. À medida que os trabalhos são iniciados, eles são enfileirados e aguardam até que um thread esteja disponível no pool de threads para executar o trabalho. O limite padrão é 5 threads.

O tamanho do pool de threads é global para a sessão do PowerShell. A especificação de um **ThrottleLimit** em uma chamada define o limite para chamadas subsequentes na mesma sessão.

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Management. Automation. PSObject

## SAÍDAS

### ThreadJob.ThreadJob

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Start-Job](../Microsoft.PowerShell.Core/Start-Job.md)

[Stop-Job](../Microsoft.PowerShell.Core/Stop-Job.md)

[Receive-Job](../Microsoft.PowerShell.Core/Receive-Job.md)
