---
description: Descreve o depurador do PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 08/06/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_debuggers?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Debuggers
ms.openlocfilehash: 6765c33e4508e19dfca7f291f8452f1bb4730747
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195863"
---
# <a name="about-debuggers"></a>Sobre os depuradores

## <a name="short-description"></a>DESCRIÇÃO BREVE
Descreve o depurador do PowerShell.

## <a name="long-description"></a>DESCRIÇÃO LONGA

A depuração é o processo de examinar um script enquanto ele está em execução para identificar e corrigir erros nas instruções do script. O depurador do PowerShell pode ajudá-lo a examinar e identificar erros e ineficiências em seus scripts, funções, comandos, configurações de DSC (configuração de estado desejado) do PowerShell ou expressões.

A partir do PowerShell 5,0, o depurador do PowerShell foi atualizado para depurar scripts, funções, comandos, configurações ou expressões que estão sendo executadas no console do ou ISE do Windows PowerShell em computadores remotos. Você pode executar `Enter-PSSession` o para iniciar uma sessão interativa do PowerShell remoto, na qual é possível definir pontos de interrupção e depurar arquivos de script e comandos no computador remoto. `Enter-PSSession` a funcionalidade foi atualizada para permitir que você se reconecte e insira uma sessão desconectada que esteja executando um script ou comando em um computador remoto. Se o script em execução atingir um ponto de interrupção, a sessão do cliente iniciará automaticamente o depurador. Se a sessão desconectada que está executando um script já tiver atingido um ponto de interrupção e for interrompida no ponto de interrupção, `Enter-PSSession` o iniciará automaticamente o depurador de linha de comando, depois que você se reconectar à sessão.

Você pode usar os recursos do depurador do PowerShell para examinar um script, função, comando ou expressão do PowerShell enquanto ele está em execução. O depurador do PowerShell inclui um conjunto de cmdlets que permitem definir pontos de interrupção, gerenciar pontos de interrupção e exibir a pilha de chamadas.

## <a name="debugger-cmdlets"></a>Cmdlets do depurador

O depurador do PowerShell inclui o seguinte conjunto de cmdlets:

- `Set-PSBreakpoint`: Define pontos de interrupção em linhas, variáveis e comandos.
- `Get-PSBreakpoint`: Obtém pontos de interrupção na sessão atual.
- `Disable-PSBreakpoint`: Desativa os pontos de interrupção na sessão atual.
- `Enable-PSBreakpoint`: Habilita novamente os pontos de interrupção na sessão atual.
- `Remove-PSBreakpoint`: Exclui pontos de interrupção da sessão atual.
- `Get-PSCallStack`: Exibe a pilha de chamadas atual.

## <a name="starting-and-stopping-the-debugger"></a>Iniciando e parando o depurador

Para iniciar o depurador, defina um ou mais pontos de interrupção. Em seguida, execute o script, comando ou função que você deseja depurar.

Quando você atinge um ponto de interrupção, a execução é interrompida e o controle é ativado para o depurador.

Para interromper o depurador, execute o script, comando ou função até que ele seja concluído. Ou digite `stop` ou `t` .

### <a name="debugger-commands"></a>Comandos do depurador

Ao usar o depurador no console do PowerShell, use os comandos a seguir para controlar a execução. No ISE do Windows PowerShell, use os comandos no menu Depurar.

Observação: para obter informações sobre como usar o depurador em outros aplicativos host, consulte a documentação do aplicativo host.

- `s`, `StepInto` : Executa a próxima instrução e, em seguida, para.

- `v`, `StepOver` : Executa a próxima instrução, mas ignora as funções e invocações. As instruções ignoradas são executadas, mas não percorridas.

- `Ctrl+Break`: (Interromper tudo no ISE) é dividido em um script em execução no console do PowerShell ou ISE do Windows PowerShell. Observe que <kbd>Ctrl</kbd> + <kbd>Break</kbd> no Windows PowerShell 2,0, 3,0 e 4,0 fecha o programa. Interromper tudo funciona em scripts locais e remotos de execução interativa.

- `o`, `StepOut` : Sai da função atual; um nível acima se estiver aninhado. Se estiver no corpo principal, ele continuará ao final ou ao próximo ponto de interrupção. As instruções ignoradas são executadas, mas não percorridas.

- `c`, `Continue` : Continua a ser executado até que o script seja concluído ou até que o próximo ponto de interrupção seja atingido. As instruções ignoradas são executadas, mas não percorridas.

- `l`, `List` : Exibe a parte do script que está em execução. Por padrão, ele exibe a linha atual, cinco linhas anteriores e 10 linhas subsequentes.
  Para continuar a listar o script, pressione ENTER.

- `l <m>`, `List` : Exibe 16 linhas do script começando com o número de linha especificado por `<m>` .

- `l <m> <n>`, `List` : Exibe `<n>` linhas do script, começando com o número de linha especificado por `<m>` .

- `q`, `Stop` , `Exit` : Interrompe a execução do script e sai do depurador. Se você estiver depurando um trabalho executando o `Debug-Job` cmdlet, o `Exit` comando desanexará o depurador e permitirá que o trabalho continue em execução.

- `k`, `Get-PsCallStack` : Exibe a pilha de chamadas atual.

- `<Enter>`: Repete o último comando se ele foi Step (s), StepOver (v) ou List (l). Caso contrário, representa uma ação de envio.

- `?`, `h` : Exibe a ajuda do comando do depurador.

Para sair do depurador, você pode usar Stop (q).

A partir do PowerShell 5,0, você pode executar o comando Exit para sair de uma sessão de depuração aninhada que você iniciou executando o `Debug-Job` ou o `Debug-Runspace` .

Usando esses comandos do depurador, você pode executar um script, parar em um ponto de preocupação, examinar os valores de variáveis e o estado do sistema e continuar executando o script até que você tenha identificado um problema.

Observação: se você entrar em uma instrução com um operador de redirecionamento, como ">", o depurador do PowerShell percorre todas as instruções restantes no script.

Exibindo os valores das variáveis de script

Enquanto estiver no depurador, você também poderá inserir comandos, exibir o valor de variáveis, usar cmdlets e executar scripts na linha de comando.

Você pode exibir o valor atual de todas as variáveis no script que está sendo depurado, exceto pelas seguintes variáveis automáticas:

```powershell
$_
$Args
$Input
$MyInvocation
$PSBoundParameters
```

Se você tentar exibir o valor de qualquer uma dessas variáveis, obterá o valor dessa variável para em um pipeline interno usado pelo depurador, não o valor da variável no script.

Para exibir o valor dessas variáveis para o script que está sendo depurado, no script, atribua o valor da variável automática a uma nova variável. Em seguida, você pode exibir o valor da nova variável.

Por exemplo,

```powershell
$scriptArgs = $Args
$scriptArgs
```

No exemplo neste tópico, o valor da `$MyInvocation` variável é reatribuído da seguinte maneira:

```powershell
$scriptname = $MyInvocation.MyCommand.Path
```

## <a name="the-debugger-environment"></a>O ambiente do depurador

Ao alcançar um ponto de interrupção, você entra no ambiente do depurador. O prompt de comando é alterado para que comece com "[DBG]:".

Para obter mais informações sobre como personalizar o prompt, consulte [about_Prompts](about_prompts.md).

Além disso, em alguns aplicativos host, como o console do PowerShell (mas não no Ambiente de Script Integrado do Windows PowerShell [ISE]), um prompt aninhado é aberto para depuração. Você pode detectar o prompt aninhado pelos caracteres de maior que repetições (ASCII 62) que aparecem no prompt de comando.

Por exemplo, o seguinte é o prompt de depuração padrão no console do PowerShell:

```
[DBG]: PS (get-location)>>>
```

Você pode encontrar o nível de aninhamento usando a `$NestedPromptLevel` variável automática.

Além disso, uma variável automática, `$PSDebugContext` , é definida no escopo local. Você pode usar a presença da `$PsDebugContext` variável para determinar se está no depurador.

Por exemplo:

```powershell
if ($PSDebugContext) {"Debugging"} else {"Not Debugging"}
```

Você pode usar o valor da `$PSDebugContext` variável em sua depuração.

```
[DBG]: PS>>> $PSDebugContext.InvocationInfo

Name   CommandLineParameters  UnboundArguments  Location
----   ---------------------  ----------------  --------
=      {}                     {}                C:\ps-test\vote.ps1 (1)
```

## <a name="debugging-and-scope"></a>Depuração e escopo

Interromper o depurador não altera o escopo no qual você está operando, mas quando você atinge um ponto de interrupção em um script, você passa para o escopo do script. O escopo do script é um filho do escopo no qual você executou o depurador.

Para localizar as variáveis e os aliases definidos no escopo do script, use o parâmetro scope dos `Get-Alias` `Get-Variable` cmdlets ou.

Por exemplo, o comando a seguir obtém as variáveis no escopo local (script):

```powershell
Get-Variable -scope 0
```

Você pode abreviar o comando como:

```powershell
gv -s 0
```

Essa é uma maneira útil de ver apenas as variáveis que você definiu no script e que você definiu durante a depuração.

Depuração na linha de comando

Ao definir um ponto de interrupção de variável ou um ponto de interrupção de comando, você pode definir o ponto de interrupção somente em um arquivo de script. No entanto, por padrão, o ponto de interrupção é definido em qualquer coisa que seja executada na sessão atual.

Por exemplo, se você definir um ponto de interrupção na `$name` variável, o depurador interromperá qualquer `$name` variável em qualquer script, comando, função, cmdlet de script ou expressão que você executar até que você desabilite ou remova o ponto de interrupção.

Isso permite que você depure seus scripts em um contexto mais realista no qual eles podem ser afetados por funções, variáveis e outros scripts na sessão e no perfil do usuário.

Os pontos de interrupção de linha são específicos para arquivos de script, portanto, eles são definidos somente em arquivos de script.

## <a name="debugging-functions"></a>Funções de depuração

Quando você define um ponto de interrupção em uma função que tem `Begin` `Process` seções, e `End` , o depurador é interrompido na primeira linha de cada seção.

Por exemplo:

```powershell
function test-cmdlet {
    begin {
        write-output "Begin"
    }
    process {
        write-output "Process"
    }
    end {
        write-output "End"
    }
}

C:\PS> Set-PSBreakpoint -command test-cmdlet

C:\PS> test-cmdlet

Begin
Entering debug mode. Use h or ? for help.

Hit Command breakpoint on 'prompt:test-cmdlet'

test-cmdlet

[DBG]: C:\PS> c
Process
Entering debug mode. Use h or ? for help.

Hit Command breakpoint on 'prompt:test-cmdlet'

test-cmdlet

[DBG]: C:\PS> c
End
Entering debug mode. Use h or ? for help.

Hit Command breakpoint on 'prompt:test-cmdlet'

test-cmdlet

# [DBG]: C:\PS>
```

## <a name="debugging-remote-scripts"></a>Depuração de scripts remotos

A partir do PowerShell 5,0, você pode executar o depurador do PowerShell em uma sessão remota, no console do ou ISE do Windows PowerShell.
`Enter-PSSession` a funcionalidade foi atualizada para permitir que você se reconecte e insira uma sessão desconectada que está sendo executada em um computador remoto e que atualmente está executando um script. Se o script em execução atingir um ponto de interrupção, a sessão do cliente iniciará automaticamente o depurador.

Veja a seguir um exemplo que mostra como isso funciona, com pontos de interrupção definidos em um script nas linhas 6, 11, 22 e 25. Observe que, no exemplo, quando o depurador é iniciado, há dois prompts de identificação: o nome do computador no qual a sessão está em execução e o prompt DBG que lhe permite saber se você está no modo de depuração.

```powershell
Enter-Pssession -Cn localhost
[localhost]: PS C:\psscripts> Set-PSBreakpoint .\ttest19.ps1 6,11,22,25

ID Script          Line     Command          Variable          Action
-- ------          ----     -------          --------          ------
0 ttest19.ps1          6
1 ttest19.ps1          11
2 ttest19.ps1          22
3 ttest19.ps1          25

[localhost]: PS C:\psscripts> .\ttest19.ps1
Hit Line breakpoint on 'C:\psscripts\ttest19.ps1:11'

At C:\psscripts\ttest19.ps1:11 char:1
+ $winRMName = "WinRM"
# + ~

[localhost]: [DBG]: PS C:\psscripts>> list

6:      1..5 | foreach { sleep 1; Write-Output "hello2day $_" }
7:  }
# 8:

9:  $count = 10
10:  $psName = "PowerShell"
11:* $winRMName = "WinRM"
12:  $myVar = 102
# 13:

14:  for ($i=0; $i -lt $count; $i++)
15:  {
16:      sleep 1
17:      Write-Output "Loop iteration is: $i"
18:      Write-Output "MyVar is $myVar"
# 19:

20:      hello2day
# 21:


[localhost]: [DBG]: PS C:\psscripts>> stepover
At C:\psscripts\ttest19.ps1:12 char:1
+ $myVar = 102
# + ~

[localhost]: [DBG]: PS C:\psscripts>> quit
[localhost]: PS C:\psscripts> Exit-PSSession
PS C:\psscripts>
```

## <a name="examples"></a>Exemplos

Esse script de teste detecta a versão do sistema operacional e exibe uma mensagem apropriada do sistema. Ele inclui uma função, uma chamada de função e uma variável.

O comando a seguir exibe o conteúdo do arquivo de script de teste:

```powershell
PS C:\PS-test>  Get-Content test.ps1

function psversion {
  "PowerShell " + $PSVersionTable.PSVersion
  if ($PSVersionTable.PSVersion.Major -lt 6) {
    "Upgrade to PowerShell 6.0!"
  }
  else {
    "Have you run a background job today (start-job)?"
  }
}

$scriptName = $MyInvocation.MyCommand.Path
psversion
"Done $scriptName."
```

Para começar, defina um ponto de interrupção em um momento de interesse no script, como uma linha, comando, variável ou função.

Comece criando um ponto de interrupção de linha na primeira linha do script de Test.ps1 no diretório atual.

```powershell
PS C:\ps-test> Set-PSBreakpoint -line 1 -script test.ps1
```

Você pode abreviar esse comando como:

```powershell
PS C:\ps-test> spb 1 -s test.ps1
```

O comando retorna um objeto de ponto de interrupção de linha ( **System. Management. Automation. LineBreakpoint** ).

```
Column     : 0
Line       : 1
Action     :
Enabled    : True
HitCount   : 0
Id         : 0
Script     : C:\ps-test\test.ps1
ScriptName : C:\ps-test\test.ps1
```

Agora, inicie o script.

```powershell
PS C:\ps-test> .\test.ps1
```

Quando o script atinge o primeiro ponto de interrupção, a mensagem de ponto de interrupção indica que o depurador está ativo. Ele descreve o ponto de interrupção e a visualização da primeira linha do script, que é uma declaração de função. O prompt de comando também é alterado para indicar que o depurador tem controle.

A linha de visualização inclui o nome do script e o número de linha do comando visualizado.

```powershell
Entering debug mode. Use h or ? for help.

Hit Line breakpoint on 'C:\ps-test\test.ps1:1'

test.ps1:1   function psversion {
# DBG>
```

Use os comandos Step para executar a primeira instrução no script e visualizar a próxima instrução. A próxima instrução usa a `$MyInvocation` variável automática para definir o valor da `$scriptName` variável como o caminho e o nome de arquivo do arquivo de script.

```powershell
DBG> s
test.ps1:11  $scriptName = $MyInvocation.MyCommand.Path
```

Neste ponto, a `$scriptName` variável não é populada, mas você pode verificar o valor da variável exibindo seu valor. Nesse caso, o valor é `$null` .

```powershell
DBG> $scriptname
# DBG>
```

Use outro comando Step para executar a instrução atual e visualizar a próxima instrução no script. A próxima instrução chama a função PsVersion.

```powershell
DBG> s
test.ps1:12  psversion
```

Neste ponto, a `$scriptName` variável é populada, mas você verifica o valor da variável exibindo seu valor. Nesse caso, o valor é definido como o caminho do script.

```powershell
DBG> $scriptName
C:\ps-test\test.ps1
```

Use outro comando Step para executar a chamada de função. Pressione ENTER ou digite "s" para a etapa.

```powershell
DBG> s
test.ps1:2       "PowerShell " + $PSVersionTable.PSVersion
```

A mensagem de depuração inclui uma visualização da instrução na função. Para executar essa instrução e visualizar a próxima instrução na função, você pode usar um `Step` comando. Mas, nesse caso, use um comando StepOut (o). Ele conclui a execução da função (a menos que ela alcance um ponto de interrupção) e etapas para a próxima instrução no script.

```powershell
DBG> o
Windows PowerShell 2.0
Have you run a background job today (start-job)?
test.ps1:13  "Done $scriptName"
```

Como estamos na última instrução do script, os comandos Step, StepOut e continue têm o mesmo efeito. Nesse caso, use o StepOut (o).

```powershell
Done C:\ps-test\test.ps1
PS C:\ps-test>
```

O comando StepOut executa o último comando. O prompt de comando padrão indica que o depurador saiu e retornou o controle para o processador de comando.

Agora, execute o depurador novamente. Primeiro, para excluir o ponto de interrupção atual, use os `Get-PsBreakpoint` `Remove-PsBreakpoint` cmdlets e. (Se você considerar que pode reutilizar o ponto de interrupção, use o `Disable-PsBreakpoint` cmdlet em vez de `Remove-PsBreakpoint` .)

```powershell
PS C:\ps-test> Get-PSBreakpoint| Remove-PSBreakpoint
```

Você pode abreviar esse comando como:

```powershell
PS C:\ps-test> gbp | rbp
```

Ou execute o comando escrevendo uma função, como a seguinte função:

```powershell
function delbr { gbp | rbp }
```

Agora, crie um ponto de interrupção na `$scriptname` variável.

```powershell
PS C:\ps-test> Set-PSBreakpoint -variable scriptname -script test.ps1
```

Você pode abreviar o comando como:

```powershell
PS C:\ps-test> sbp -v scriptname -s test.ps1
```

Agora, inicie o script. O script atinge o ponto de interrupção da variável. O modo padrão é Write, portanto a execução é interrompida logo antes da instrução que altera o valor da variável.

```powershell
PS C:\ps-test> .\test.ps1
Hit Variable breakpoint on 'C:\ps-test\test.ps1:$scriptName'
(Write access)

test.ps1:11  $scriptName = $MyInvocation.MyCommand.Path
# DBG>
```

Exibe o valor atual da `$scriptName` variável, que é `$null` .

```powershell
DBG> $scriptName
# DBG>
```

Use um ou mais comandos Step para executar a instrução que popula a variável.
Em seguida, exiba o novo valor da `$scriptName` variável.

```powershell
DBG> $scriptName
C:\ps-test\test.ps1
```powershell

Use a Step command (s) to preview the next statement in the script.

```powershell
DBG> s
test.ps1:12  psversion
```

A próxima instrução é uma chamada para a função PsVersion. Para ignorar a função, mas ainda executá-la, use um comando StepOver (v). Se você já estiver na função ao usar o StepOver, ele não será eficaz. A chamada de função é exibida, mas não é executada.

```powershell
DBG> v
Windows PowerShell 2.0
Have you run a background job today (start-job)?
test.ps1:13  "Done $scriptName"
```

O comando StepOver executa a função e visualiza a próxima instrução no script, que imprime a linha final.

Use um comando de parada (t) para sair do depurador. O prompt de comando reverte para o prompt de comando padrão.

```powershell
C:\ps-test>
```

Para excluir os pontos de interrupção, use `Get-PsBreakpoint` os `Remove-PsBreakpoint` cmdlets e.

```powershell
PS C:\ps-test> Get-PSBreakpoint| Remove-PSBreakpoint
```

Crie um novo ponto de interrupção de comando na função PsVersion.

```powershell
PS C:\ps-test> Set-PSBreakpoint -command psversion -script test.ps1
```

Você pode abreviar este comando para:

```powershell
PS C:\ps-test> sbp -c psversion -s test.ps1
```

Agora, execute o script.

```powershell
PS C:\ps-test> .\test.ps1
Hit Command breakpoint on 'C:\ps-test\test.ps1:psversion'

test.ps1:12  psversion
# DBG>
```

O script atinge o ponto de interrupção na chamada de função. Neste ponto, a função ainda não foi chamada. Isso lhe dá a oportunidade de usar o parâmetro Action do `Set-PSBreakpoint` para definir condições para a execução do ponto de interrupção ou para executar tarefas preparatórias ou de diagnóstico, como iniciar um log ou invocar um script de diagnóstico ou segurança.

Para definir uma ação, use um comando Continue (c) para sair do script e um `Remove-PsBreakpoint` comando para excluir o ponto de interrupção atual. (Os pontos de interrupção são somente leitura, portanto, você não pode adicionar uma ação ao ponto de interrupção atual.)

```powershell
DBG> c
Windows PowerShell 2.0
Have you run a background job today (start-job)?
Done C:\ps-test\test.ps1

PS C:\ps-test> Get-PSBreakpoint| Remove-PSBreakpoint
PS C:\ps-test>
```

Agora, crie um novo ponto de interrupção de comando com uma ação. O comando a seguir define um ponto de interrupção de comando com uma ação que registra o valor da `$scriptName` variável quando a função é chamada. Como a palavra-chave break não é usada na ação, a execução não é interrompida. (') É o caractere de continuação de linha.)

```powershell
PS C:\ps-test> Set-PSBreakpoint -command psversion -script test.ps1  `
-action { add-content "The value of `$scriptName is $scriptName." `
-path action.log}
```

Você também pode adicionar ações que definem condições para o ponto de interrupção. No comando a seguir, o ponto de interrupção do comando será executado somente se a política de execução estiver definida como RemoteSigned, a política mais restritiva que ainda permitirá executar scripts. (') É o caractere de continuação.)

```powershell
PS C:\ps-test> Set-PSBreakpoint -script test.ps1 -command psversion `
-action { if ((Get-ExecutionPolicy) -eq "RemoteSigned") { break }}
```

A palavra-chave break na ação direciona o depurador para executar o ponto de interrupção.
Você também pode usar a palavra-chave continue para direcionar o depurador a ser executado sem interrupção. Como a palavra-chave default é Continue, você deve especificar Break para interromper a execução.

Agora, execute o script.

```powershell
PS C:\ps-test> .\test.ps1
Hit Command breakpoint on 'C:\ps-test\test.ps1:psversion'

test.ps1:12  psversion
```

Como a política de execução é definida como **RemoteSigned** , a execução é interrompida na chamada de função.

Neste ponto, talvez você queira verificar a pilha de chamadas. Use o `Get-PsCallStack` cmdlet ou o `Get-PsCallStack` comando do depurador (k). O comando a seguir obtém a pilha de chamadas atual.

```powershell
DBG> k
2: prompt
1: .\test.ps1: $args=[]
0: prompt: $args=[]
```

Este exemplo demonstra apenas algumas das muitas maneiras de usar o depurador do PowerShell.

Para obter mais informações sobre os cmdlets do depurador, digite o seguinte comando:

```powershell
help <cmdlet-name> -full
```

Por exemplo, digite:

```powershell
help Set-PSBreakpoint -full
```

## <a name="other-debugging-features-in-powershell"></a>Outros recursos de depuração no PowerShell

Além do depurador do PowerShell, o PowerShell inclui vários outros recursos que você pode usar para depurar scripts e funções.

- O ISE do Windows PowerShell inclui um depurador gráfico interativo. Para obter mais informações, inicie ISE do Windows PowerShell e pressione F1.

- O `Set-PSDebug` cmdlet oferece recursos de depuração de script muito básicos, incluindo depuração e rastreamento.

- Use o `Set-StrictMode` cmdlet para detectar referências a variáveis não inicializadas, para referências a Propriedades inexistentes de um objeto e para a sintaxe de função que não é válida.

- Adicione instruções de diagnóstico a um script, como instruções que exibem o valor de variáveis, instruções que lêem a entrada da linha de comando ou instruções que relatam a instrução atual. Use os cmdlets que contêm o verbo de gravação para essa tarefa, como `Write-Host` , `Write-Debug` , `Write-Warning` e `Write-Verbose` .

## <a name="see-also"></a>CONSULTE TAMBÉM

- [Desabilitar-PsBreakpoint](xref:Microsoft.PowerShell.Utility.Disable-PSBreakpoint)
- [Habilitar-PsBreakpoint](xref:Microsoft.PowerShell.Utility.Enable-PSBreakpoint)
- [Get-PsBreakpoint](xref:Microsoft.PowerShell.Utility.Get-PSBreakpoint)
- [Get-PsCallStack](xref:Microsoft.PowerShell.Utility.Get-PSCallStack)
- [Remove-PsBreakpoint](xref:Microsoft.PowerShell.Utility.Remove-PSBreakpoint)
- [Set-PSBreakpoint](xref:Microsoft.PowerShell.Utility.Set-PSBreakpoint)
- [Write-Debug](xref:Microsoft.PowerShell.Utility.Write-Debug)
- [Write-Verbose](xref:Microsoft.PowerShell.Utility.Write-Verbose)

