---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 02/18/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/foreach-object?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ForEach-Object
ms.openlocfilehash: c8b674a895bb323b734f018e5e8654cfec4d0045
ms.sourcegitcommit: 1dfd5554b70c7e8f4e3df19e29c384a9c0a4b227
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2021
ms.locfileid: "101685584"
---
# ForEach-Object

## Sinopse
Executa uma operação em cada item de uma coleção de objetos de entrada.

## Sintaxe

### ScriptBlockset (padrão)

```
ForEach-Object [-InputObject <PSObject>] [-Begin <ScriptBlock>] [-Process] <ScriptBlock[]>
 [-End <ScriptBlock>] [-RemainingScripts <ScriptBlock[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### PropertyAndMethodSet

```
ForEach-Object [-InputObject <PSObject>] [-MemberName] <String> [-ArgumentList <Object[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ParallelParameterSet

```
ForEach-Object -Parallel <scriptblock> [-InputObject <PSObject>] [-ThrottleLimit <int>]
[-UseNewRunspace] [-TimeoutSeconds <int>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Descrição

O `ForEach-Object` cmdlet executa uma operação em cada item em uma coleção de objetos de entrada. Os objetos de entrada podem ser canalizados para o cmdlet ou especificados usando o parâmetro **InputObject** .

A partir do Windows PowerShell 3,0, há duas maneiras diferentes de construir um `ForEach-Object` comando.

- **Bloco de script**. Você pode usar um bloco de script para especificar a operação. No bloco de script, use a `$_` variável para representar o objeto atual. O bloco de script é o valor do parâmetro **Process**. O bloco de script pode conter qualquer script do PowerShell.

  Por exemplo, o comando a seguir obtém o valor da propriedade **ProcessName** de cada processo no computador.

  `Get-Process | ForEach-Object {$_.ProcessName}`

  `ForEach-Object` dá suporte `begin` aos `process` blocos, e `end` conforme descrito em [about_Functions](about/about_functions.md#piping-objects-to-functions).

  > [!NOTE]
  > Os blocos de script são executados no escopo do chamador. Portanto, os blocos têm acesso a variáveis nesse escopo e podem criar novas variáveis que persistem nesse escopo após a conclusão do cmdlet.

- **Instrução de operação**. Você também pode escrever uma instrução de operação, que é muito mais parecida com a linguagem natural. Você pode usar a instrução de operação para especificar um valor de propriedade ou chamar um método. Instruções de operação foram introduzidas no Windows PowerShell 3.0.

  Por exemplo, o comando a seguir também obtém o valor da propriedade **ProcessName** de cada processo no computador.

  `Get-Process | ForEach-Object ProcessName`

- **Bloco de script em execução paralela**. A partir do PowerShell 7,0, um terceiro conjunto de parâmetros está disponível e executa cada bloco de script em paralelo. O parâmetro **ThrottleLimit** limita o número de scripts paralelos em execução por vez. Como antes, use a `$_` variável para representar o objeto de entrada atual no bloco de script. Use a `$using:` palavra-chave para passar referências de variáveis para o script em execução.

  No PowerShell 7, um novo runspace é criado para cada iteração de loop a fim de garantir o isolamento máximo.
  Isso pode ser um grande desempenho e um maior impacto de recursos se o trabalho que você está fazendo for pequeno em comparação com a criação de novos Runspaces ou se houver muitas iterações executando um trabalho significativo. A partir do PowerShell 7,1, os Runspaces de um pool de runspace são reutilizados por padrão. O tamanho do pool de runspace é especificado pelo parâmetro **ThrottleLimit** . O tamanho do pool de runspace padrão é 5. Você ainda pode criar um novo runspace para cada iteração usando a opção **UseNewRunspace**

  Por padrão, os scriptblocks paralelos usam o diretório de trabalho atual do chamador que iniciou as tarefas paralelas.

  Os erros de não finalização são gravados no fluxo de erros do cmdlet conforme eles ocorrem em scriptblocks em execução paralela. Como a ordem de execução do scriptblock Parallel não pode ser determinada, a ordem na qual os erros aparecem no fluxo de erro é aleatória. Da mesma forma, as mensagens gravadas em outros fluxos de dados, como aviso, detalhado ou informações, são gravadas nesses fluxos de dados em uma ordem indeterminada.

  Erros de encerramento, como exceções, encerram a instância paralela individual dos scriptblocks em que ocorrem. Um erro de encerramento em um scriptblock pode não causar o encerramento do `Foreach-Object` cmdlet. Os outros scriptblocks, em execução em paralelo, continuam a ser executados, a menos que também encontrem um erro de encerramento. O erro de encerramento é gravado no fluxo de dados de erro como um **ErrorRecord** com um **FullyQualifiedErrorId** de `PSTaskException` .
  Os erros de encerramento podem ser convertidos em erros de não encerramento usando blocos try/catch ou Trap do PowerShell.

## Exemplos

### Exemplo 1: dividir inteiros em uma matriz

Este exemplo usa uma matriz de três inteiros e divide cada um deles por 1024.

```powershell
30000, 56798, 12432 | ForEach-Object -Process {$_/1024}
```

```Output
29.296875
55.466796875
12.140625
```

### Exemplo 2: obter o comprimento de todos os arquivos em um diretório

Este exemplo processa os arquivos e diretórios no diretório de instalação do PowerShell `$PSHOME` .

```powershell
Get-ChildItem $PSHOME |
  ForEach-Object -Process {if (!$_.PSIsContainer) {$_.Name; $_.Length / 1024; " " }}
```

Se o objeto não for um diretório, o bloco de script obterá o nome do arquivo, dividirá o valor de sua propriedade **Length** por 1024 e adicionará um espaço ("") para separá-lo da próxima entrada. O cmdlet usa a propriedade **PSISContainer** para determinar se um objeto é um diretório.

### Exemplo 3: operar nos eventos do sistema mais recentes

Este exemplo grava os 1000 eventos mais recentes do log de eventos do sistema em um arquivo de texto. A hora atual é exibida antes e depois do processamento dos eventos.

```powershell
$Events = Get-EventLog -LogName System -Newest 1000
$events | ForEach-Object -Begin {Get-Date} -Process {Out-File -FilePath Events.txt -Append -InputObject $_.Message} -End {Get-Date}
```

`Get-EventLog` Obtém os 1000 eventos mais recentes do log de eventos do sistema e os armazena na `$Events` variável. `$Events` é então canalizado para o `ForEach-Object` cmdlet. O parâmetro **Begin** exibe a data e hora atuais. Em seguida, o parâmetro **process** usa o `Out-File` cmdlet para criar um arquivo de texto chamado events.txt e armazena a propriedade Message de cada um dos eventos nesse arquivo. Por fim, o parâmetro **End** é usado para exibir a data e hora após todo o processamento ter sido concluído.

### Exemplo 4: alterar o valor de uma chave do registro

Este exemplo altera o valor da entrada do registro **RemotePath** em todas as subchaves sob a `HKCU:\Network` chave para texto em maiúsculas.

```powershell
Get-ItemProperty -Path HKCU:\Network\* |
  ForEach-Object {Set-ItemProperty -Path $_.PSPath -Name RemotePath -Value $_.RemotePath.ToUpper();}
```

Você pode usar esse formato para alterar a forma ou o conteúdo de um valor de entrada de registro.

Cada subchave na chave de **rede** representa uma unidade de rede mapeada que se reconecta no logon. A entrada **RemotePath** contém o caminho UNC da unidade conectada. Por exemplo, se você mapear a unidade E: para `\\Server\Share` , uma subchave **e** será criada em `HKCU:\Network` com o valor do registro **RemotePath** definido como `\\Server\Share` .

O comando usa o `Get-ItemProperty` cmdlet para obter todas as subchaves da chave de **rede** e o `Set-ItemProperty` cmdlet para alterar o valor da entrada do registro **RemotePath** em cada chave.
No `Set-ItemProperty` comando, o caminho é o valor da propriedade **PSPath** da chave do registro. Essa é uma propriedade do objeto Microsoft .NET Framework que representa a chave do registro, não uma entrada do registro. O comando usa o método **ToUpper ()** do valor **RemotePath** , que é uma cadeia de caracteres (REG_SZ).

Como o `Set-ItemProperty` está alterando a propriedade de cada chave, o `ForEach-Object` cmdlet é necessário para acessar a propriedade.

### Exemplo 5: usar a $Null variável automática

Este exemplo mostra o efeito de canalizar a `$Null` variável automática para o `ForEach-Object` cmdlet.

```powershell
1, 2, $null, 4 | ForEach-Object {"Hello"}
```

```Output
Hello
Hello
Hello
Hello
```

Como o PowerShell trata nulo como um espaço reservado explícito, o `ForEach-Object` cmdlet gera um valor para `$Null` , assim como faz para outros objetos que você canaliza para ele.

### Exemplo 6: obter valores de propriedade

Este exemplo obtém o valor da propriedade **path** de todos os módulos do PowerShell instalados usando o parâmetro **MemberName** do `ForEach-Object` cmdlet.

```powershell
Get-Module -ListAvailable | ForEach-Object -MemberName Path
Get-Module -ListAvailable | Foreach Path
```

O segundo comando é equivalente ao primeiro. Ele usa o `Foreach` alias do `ForEach-Object` cmdlet e omite o nome do parâmetro **MemberName** , que é opcional.

O `ForEach-Object` cmdlet é útil para obter valores de propriedade, pois Obtém o valor sem alterar o tipo, diferentemente dos cmdlets **Format** ou do `Select-Object` cmdlet, que alteram o tipo de valor da propriedade.

### Exemplo 7: dividir nomes de módulo em nomes de componentes

Este exemplo mostra três maneiras de dividir dois nomes de módulo separados por ponto em seus nomes de componentes.

```powershell
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | ForEach-Object {$_.Split(".")}
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | ForEach-Object -MemberName Split -ArgumentList "."
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | Foreach Split "."
```

```Output
Microsoft
PowerShell
Core
Microsoft
PowerShell
Host
```

Os comandos chamam o método de cadeias de caracteres **Split**. Os três comandos usam uma sintaxe diferente, mas são equivalentes e intercambiáveis.

O primeiro comando usa a sintaxe tradicional, que inclui um bloco de script e o operador de objeto atual `$_` . Ele usa a sintaxe de ponto para especificar o método e parênteses para incluir o argumento delimitador.

O segundo comando usa o parâmetro **MemberName** para especificar o método **Split** e o parâmetro **ArgumentName** para identificar o ponto (".") como o delimitador de divisão.

O terceiro comando usa o alias **foreach** do `ForEach-Object` cmdlet e omite os nomes dos parâmetros **MemberName** e **ArgumentList** , que são opcionais.

### Exemplo 8: usando ForEach-Object com dois blocos de script

Neste exemplo, passamos dois blocos de script de posição. Todos os blocos de script são associados ao parâmetro de **processo** . No entanto, eles são tratados como se tivessem sido passados para os parâmetros **begin** e **process** .

```powershell
1..2 | ForEach-Object { 'begin' } { 'process' }
```

```Output
begin
process
process
```

### Exemplo 9: usando ForEach-Object com mais de dois blocos de script

Neste exemplo, passamos dois blocos de script de posição. Todos os blocos de script são associados ao parâmetro de **processo** . No entanto, eles são tratados como se tivessem sido passados para os parâmetros **begin**, **process** e **end** .

```powershell
1..2 | ForEach-Object { 'begin' } { 'process A' }  { 'process B' }  { 'end' }
```

```Output
begin
process A
process B
process A
process B
end
```

> [!NOTE]
> O primeiro bloco de script é sempre mapeado para o `begin` bloco, o último bloco é mapeado para o `end` bloco e os blocos no between são todos mapeados para o `process` bloco.

### Exemplo 10: executar vários blocos de script para cada item de pipeline

Conforme mostrado no exemplo anterior, vários blocos de script passados usando o parâmetro **process** são mapeados para os parâmetros **begin** e **end** . Para evitar esse mapeamento, você deve fornecer valores explícitos para os parâmetros de **início** e **término** .

```powershell
1..2 | ForEach-Object -Begin $null -Process { 'one' }, { 'two' }, { 'three' } -End $null
```

```Output
one
two
three
one
two
three
```

### Exemplo 11: executar script lento em lotes paralelos

Este exemplo executa um bloco de script simples que avalia uma cadeia de caracteres e é suspenso por um segundo.

```powershell
$Message = "Output:"

1..8 | ForEach-Object -Parallel {
    "$using:Message $_"
    Start-Sleep 1
} -ThrottleLimit 4
```

```Output
Output: 1
Output: 2
Output: 3
Output: 4
Output: 5
Output: 6
Output: 7
Output: 8
```

O valor do parâmetro **ThrottleLimit** é definido como 4 para que a entrada seja processada em lotes de quatro.
A `$using:` palavra-chave é usada para passar a `$Message` variável em cada bloco de script paralelo.

### Exemplo 12: recuperar entradas de log em paralelo

Este exemplo recupera 50.000 entradas de log de 5 logs do sistema em uma máquina local do Windows.

```powershell
$logNames = 'Security','Application','System','Windows PowerShell','Microsoft-Windows-Store/Operational'

$logEntries = $logNames | ForEach-Object -Parallel {
    Get-WinEvent -LogName $_ -MaxEvents 10000
} -ThrottleLimit 5

$logEntries.Count
```

```Output
50000
```

O parâmetro **Parallel** especifica o bloco de script que é executado em paralelo para cada nome de log de entrada. O parâmetro **ThrottleLimit** garante que todos os cinco blocos de script sejam executados ao mesmo tempo.

### Exemplo 13: executado em paralelo como um trabalho

Este exemplo executa um bloco de script simples em paralelo, criando dois trabalhos em segundo plano por vez.

```powershell
$job = 1..10 | ForEach-Object -Parallel {
    "Output: $_"
    Start-Sleep 1
} -ThrottleLimit 2 -AsJob

$job | Receive-Job -Wait
```

```Output
Output: 1
Output: 2
Output: 3
Output: 4
Output: 5
Output: 6
Output: 7
Output: 8
Output: 9
Output: 10
```

a `$job` variável recebe o objeto de trabalho que coleta dados de saída e monitora o estado de execução.
O objeto de trabalho é canalizado para `Receive-Job` com o parâmetro de opção **Wait** . E isso transmite a saída para o console, assim como se `ForEach-Object -Parallel` fosse executado sem **AsJob**.

### Exemplo 14: usando referências de variável de thread seguro

Este exemplo invoca blocos de script em paralelo para coletar objetos de processo nomeados exclusivamente.

```powershell
$threadSafeDictionary = [System.Collections.Concurrent.ConcurrentDictionary[string,object]]::new()
Get-Process | ForEach-Object -Parallel {
    $dict = $using:threadSafeDictionary
    $dict.TryAdd($_.ProcessName, $_)
}

$threadSafeDictionary["pwsh"]
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     82    82.87     130.85      15.55    2808   2 pwsh
```

Uma única instância de um objeto **ConcurrentDictionary** é passada para cada bloco de script para coletar os objetos. Como o **ConcurrentDictionary** é thread-safe, é seguro ser modificado por cada script paralelo. Um objeto sem thread-safe, como **System. Collections. Generic. Dictionary**, não seria seguro para uso aqui.

> [!NOTE]
> Este exemplo é um uso muito ineficiente do parâmetro **paralelo** . O script simplesmente adiciona o objeto de entrada a um objeto de dicionário simultâneo. É trivial e não vale a pena a sobrecarga de invocar cada script em um thread separado. Executar `ForEach-Object` normalmente sem o comutador **paralelo** é muito mais eficiente e mais rápido. Este exemplo destina-se apenas a demonstrar como usar variáveis de thread seguro.

### Exemplo 15: gravando erros com execução paralela

Este exemplo grava no fluxo de erros em paralelo, em que a ordem dos erros gravados é aleatória.

```powershell
1..3 | ForEach-Object -Parallel {
    Write-Error "Error: $_"
}
```

```Output
Write-Error: Error: 1
Write-Error: Error: 3
Write-Error: Error: 2
```

### Exemplo 16: finalizando erros em execução paralela

Este exemplo demonstra um erro de encerramento em um scriptblock em execução paralela.

```powershell
1..5 | ForEach-Object -Parallel {
    if ($_ -eq 3)
    {
        throw "Terminating Error: $_"
    }

    Write-Output "Output: $_"
}
```

```Output
Exception: Terminating Error: 3
Output: 1
Output: 4
Output: 2
Output: 5
```

`Output: 3` Nunca é gravado porque o scriptblock paralelo dessa iteração foi encerrado.

### Exemplo 17: passando variáveis no ScriptBlockset de script paralelo aninhado

Você pode criar uma variável fora de um `Foreach-Object -Parallel` scriptblock com escopo e usá-la dentro do scriptblock com a `$using` palavra-chave.

```powershell
$test1 = 'TestA'
1..2 | Foreach-Object -Parallel {
    $using:test1
}
```

```Output
TestA
TestA
```

```powershell
# You CANNOT create a variable inside a scoped scriptblock
# to be used in a nested foreach parallel scriptblock.
$test1 = 'TestA'
1..2 | Foreach-Object -Parallel {
    $using:test1
    $test2 = 'TestB'
    1..2 | Foreach-Object -Parallel {
        $using:test2
    }
}
```

```Output
Line |
   2 |  1..2 | Foreach-Object -Parallel {
     |         ~~~~~~~~~~~~~~~~~~~~~~~~~~
     | The value of the using variable '$using:test2' cannot be retrieved because it has not been set in the local session.
```

O scriptblock aninhado não pode acessar a `$test2` variável e um erro é gerado.

## Parâmetros

### -ArgumentList

Especifica uma matriz de argumentos para uma chamada de método. Para obter mais informações sobre o comportamento de **ArgumentList**, consulte [about_Splatting](about/about_Splatting.md#splatting-with-arrays).

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Object[]
Parameter Sets: PropertyAndMethodSet
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Início

Especifica um bloco de script que é executado antes desse cmdlet processar qualquer objeto de entrada. Esse bloco de script só é executado uma vez para o pipeline inteiro. Para obter mais informações sobre o `begin` bloco, consulte [about_Functions](about/about_functions.md#piping-objects-to-functions).

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Fim

Especifica um bloco de script que é executado depois que esse cmdlet processa todos os objetos de entrada. Esse bloco de script só é executado uma vez para o pipeline inteiro. Para obter mais informações sobre o `end` bloco, consulte [about_Functions](about/about_functions.md#piping-objects-to-functions).

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Especifica os objetos de entrada. `ForEach-Object` executa o bloco de script ou a instrução de operação em cada objeto de entrada. Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.

Quando você usa o parâmetro **InputObject** com `ForEach-Object` , em vez de direcionar os resultados de comando para `ForEach-Object` , o valor **InputObject** é tratado como um único objeto. Isso é verdadeiro mesmo se o valor for uma coleção que é o resultado de um comando, como `-InputObject (Get-Process)` .
Como **InputObject** não pode retornar propriedades individuais de uma matriz ou coleção de objetos, recomendamos que, se você usar `ForEach-Object` o para executar operações em uma coleção de objetos para os objetos que têm valores específicos nas propriedades definidas, use `ForEach-Object` no pipeline, conforme mostrado nos exemplos neste tópico.

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

### -MemberName

Especifica a propriedade a ser obtida ou o método a ser chamado.

Caracteres curinga são permitidos, mas só funcionam se a cadeia de caracteres resultante for resolvida para um valor exclusivo.
Por exemplo, se você executar `Get-Process | ForEach -MemberName *Name` , o padrão curinga corresponde a mais de um membro causando a falha do comando.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: PropertyAndMethodSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Processo

Especifica a operação que é executada em cada objeto de entrada. Esse bloco de script é executado para cada objeto no pipeline. Para obter mais informações sobre o `process` bloco, consulte [about_Functions](about/about_functions.md#piping-objects-to-functions).

Quando você fornece vários blocos de script para o parâmetro **process** , o primeiro bloco de script é sempre mapeado para o `begin` bloco. Se houver apenas dois blocos de script, o segundo bloco será mapeado para o `process` bloco. Se houver três ou mais blocos de script, o primeiro bloco de script será sempre mapeado para o `begin` bloco, o último bloco será mapeado para o `end` bloco e os blocos no between serão todos mapeados para o `process` bloco.

```yaml
Type: System.Management.Automation.ScriptBlock[]
Parameter Sets: ScriptBlockSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemainingScripts

Especifica todos os blocos de script que não são usados pelo parâmetro **process** .

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.ScriptBlock[]
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Parallel

Especifica o bloco de script a ser usado para processamento paralelo de objetos de entrada. Insira um bloco de script que descreve a operação.

Esse parâmetro foi introduzido no PowerShell 7,0.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ParallelParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Especifica o número de blocos de script em paralelo. Os objetos de entrada são bloqueados até que a contagem de blocos de script em execução fique abaixo do **ThrottleLimit**. O valor padrão é `5`.

Esse parâmetro foi introduzido no PowerShell 7,0.

```yaml
Type: System.Int32
Parameter Sets: ParallelParameterSet
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeoutSeconds

Especifica o número de segundos de espera para que todas as entradas sejam processadas em paralelo. Após o tempo limite especificado, todos os scripts em execução serão interrompidos. E todos os objetos de entrada restantes a serem processados serão ignorados. O valor padrão de `0` desabilita o tempo limite e `ForEach-Object -Parallel` pode ser executado indefinidamente. Digitar <kbd>Ctrl</kbd> + <kbd>C</kbd> na linha de comando interrompe um comando em execução `ForEach-Object -Parallel` . Esse parâmetro não pode ser usado junto com o parâmetro **AsJob** .

Esse parâmetro foi introduzido no PowerShell 7,0.

```yaml
Type: System.Int32
Parameter Sets: ParallelParameterSet
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseNewRunspace

Faz com que a invocação paralela crie um novo runspace para cada iteração de loop em vez de reutilizar os Runspaces do pool de runspace.

Esse parâmetro foi introduzido no PowerShell 7,1

```yml
Type: SwitchParameter
Parameter Sets: ParallelParameterSet
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob

Faz com que a invocação paralela seja executada como um trabalho do PowerShell. Um único objeto de trabalho é retornado em vez da saída dos blocos de script em execução. O objeto de trabalho contém trabalhos filho para cada bloco de script paralelo que é executado. O objeto de trabalho pode ser usado por todos os cmdlets de trabalho do PowerShell para monitorar o estado de execução e recuperar dados.

Esse parâmetro foi introduzido no PowerShell 7,0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ParallelParameterSet
Aliases:

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

## Entradas

### System. Management. Automation. PSObject

É possível canalizar qualquer objeto para esse cmdlet.

## outputs

### System. Management. Automation. PSObject

Esse cmdlet retorna objetos que são determinados pela entrada.

## Observações

- O `ForEach-Object` cmdlet funciona de forma muito parecida com a instrução **foreach** , exceto que não é possível canalizar a entrada para uma instrução **foreach** . Para obter mais informações sobre a instrução **foreach** , consulte [about_Foreach](./About/about_Foreach.md).

- A partir do PowerShell 4,0, `Where` e os `ForEach` métodos foram adicionados para uso com coleções. Você pode ler mais sobre esses novos métodos aqui [about_arrays](./About/about_Arrays.md)

- O `ForEach-Object -Parallel` conjunto de parâmetros usa a API interna do PowerShell para executar cada bloco de script. Isso é significativamente mais sobrecarga do que executar `ForEach-Object` normalmente com processamento sequencial. É importante usar **Parallel** em que a sobrecarga de execução em paralelo é pequena em comparação com o trabalho que o bloco de script executa. Por exemplo: 

  - Computação de scripts intensivos em máquinas com vários núcleos
  - Scripts que gastam tempo aguardando resultados ou realizando operações de arquivo

  O uso do parâmetro **Parallel** pode fazer com que os scripts sejam executados muito mais lentamente do que o normal. Especialmente se os scripts paralelos forem triviais. Experimente em **paralelo** para descobrir onde ele pode ser benéfico.

  > [!IMPORTANT]
  > O `ForEach-Object -Parallel` conjunto de parâmetros executa blocos de script em paralelo em threads de processo separados. A `$using:` palavra-chave permite passar referências de variáveis do thread de invocação de cmdlet para cada thread de bloco de script em execução. Como os blocos de script são executados em threads diferentes, as variáveis de objeto passadas por referência devem ser usadas com segurança. Geralmente, é seguro ler de objetos referenciados que não são alterados. Mas se o estado do objeto estiver sendo modificado, você deverá usar objetos de thread seguro, como .NET **System. Collection. tipos simultâneos** (consulte o exemplo 11).

## Links relacionados

[Compare-Object](../Microsoft.PowerShell.Utility/Compare-Object.md)

[Where-Object](Where-Object.md)

[Group-Object](../Microsoft.PowerShell.Utility/Group-Object.md)

[Measure-Object](../Microsoft.PowerShell.Utility/Measure-Object.md)

[New-Object](../Microsoft.PowerShell.Utility/New-Object.md)

[Select-Object](../Microsoft.PowerShell.Utility/Select-Object.md)

[Sort-Object](../Microsoft.PowerShell.Utility/Sort-Object.md)

[Tee-Object](../Microsoft.PowerShell.Utility/Tee-Object.md)
