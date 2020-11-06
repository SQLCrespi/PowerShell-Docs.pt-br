---
title: The Help System (O Sistema de Ajuda)
description: Dominar o sistema de ajuda é o segredo para ser bem-sucedido com o PowerShell.
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: 98876cf324b367fd5bb3c3462cb90ea6d7c7d5b9
ms.sourcegitcommit: 0942a6de384f4a1c624e89b1889434a30d22f4d6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2020
ms.locfileid: "93143306"
---
# <a name="chapter-2---the-help-system"></a>Capítulo 2 – O sistema de ajuda

Dois grupos de profissionais de TI receberam um teste escrito sem acesso a um computador para determinar o nível de habilidade com o PowerShell. Os iniciantes em PowerShell foram colocados em um grupo e os especialistas, em outro.
Com base nos resultados do teste, não parece haver muita diferença no nível de habilidade entre os dois grupos. Os dois grupos receberam um segundo teste semelhante ao primeiro. Desta vez, eles receberam acesso a um computador com o PowerShell que não tinha conexão com a Internet. Os resultados do segundo teste mostraram uma grande diferença no nível de habilidade entre os dois grupos. Os especialistas nem sempre sabem as respostas, mas sabem como encontrá-las.

Qual foi a diferença nos resultados do primeiro e do segundo teste entre esses dois grupos?

As diferenças observadas nesses dois testes foram o que os especialistas não memorizam como usar milhares de comandos no PowerShell. Eles aprendem muito bem a usar o sistema de ajuda no PowerShell.
Isso lhes permite encontrar os comandos necessários quando necessário e como usar esses comandos depois de encontrá-los.

Ouvi dizer Jeffrey Snover, o inventor do PowerShell, contou uma história semelhante várias vezes.

Dominar o sistema de ajuda é o segredo para ser bem-sucedido com o PowerShell.

## <a name="discoverability"></a>Detectabilidade

Os comandos compilados no PowerShell são chamados de cmdlets. O cmdlet é pronunciado "command-let" (não CMD-Let). Os nomes de cmdlets têm a forma de comandos "verbo-substantivo" no singular para torná-los facilmente detectáveis. Por exemplo, o cmdlet para determinar quais processos estão sendo executados é `Get-Process` e o cmdlet para recuperar uma lista de serviços e seus status é `Get-Service`. Há outros tipos de comandos no PowerShell, como aliases e funções, que serão abordados posteriormente neste livro. O termo comando do PowerShell é um termo genérico que geralmente é usado para fazer referência a qualquer tipo de comando no PowerShell, independentemente de ser ou não um cmdlet, uma função ou um alias.

## <a name="the-three-core-cmdlets-in-powershell"></a>Os três cmdlets principais no PowerShell

- `Get-Command`
- `Get-Help`
- `Get-Member` (abordado no capítulo 3)

Uma pergunta que costumam me fazer é como você descobrirá quais são os comandos no PowerShell? Tanto `Get-Command` quanto `Get-Help` podem ser usados para determinar os comandos.

## <a name="get-help"></a>Get-Help

`Get-Help` é um comando multipropósito. `Get-Help` ajuda você a aprender a usar comandos quando encontrá-los. `Get-Help` também pode ser usado para ajudar a localizar comandos, mas de um modo diferente e mais indireto em comparação com `Get-Command`.

Quando `Get-Help` é usado para localizar comandos, ele primeiro pesquisa correspondências curinga de nomes de comando com base na entrada fornecida. Se não encontrar uma correspondência, ele pesquisará os tópicos da ajuda em si e, se nenhuma correspondência for encontrada, um erro será retornado. Ao contrário da crença popular, `Get-Help` pode ser usado para encontrar comandos que não têm tópicos de ajuda.

A primeira coisa que você precisa saber sobre o sistema de ajuda no PowerShell é como usar o cmdlet `Get-Help`. O comando a seguir é usado para exibir o tópico da ajuda para `Get-Help`.

```powershell
Get-Help -Name Get-Help
```

```Output
Do you want to run Update-Help?
The Update-Help cmdlet downloads the most current Help files for Windows PowerShell
modules, and installs them on your computer. For more information about the Update-Help
cmdlet, see http://go.microsoft.com/fwlink/?LinkId=210614.
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

Do PowerShell versão 3 em diante, a ajuda do PowerShell não é fornecida com o sistema operacional. Na primeira vez em que `Get-Help` for executado para um comando, a mensagem anterior será exibida. Se a função `help` ou o alias de `man` for usado em vez do cmdlet `Get-Help`, você não receberá esse prompt.

Responder Sim pressionando <kbd>Y</kbd> executa o cmdlet `Update-Help`, que requer acesso à Internet por padrão. `Y` pode ser especificado em letras maiúsculas ou minúsculas.

Depois que a ajuda for baixada e a atualização for concluída, o tópico da ajuda será retornado para o comando especificado:

```powershell
Get-Help -Name Get-Help
```

Reserve um tempo para executar esse exemplo em seu computador, examinar a saída e anotar como as informações são agrupadas:

- NAME
- SINOPSE
- SYNTAX
- DESCRIPTION
- LINKS RELACIONADOS
- COMENTÁRIOS

Como você pode ver, os tópicos da ajuda podem conter uma enorme quantidade de informações e isso não é nem o tópico inteiro da ajuda.

Embora não seja específico do PowerShell, um parâmetro é um modo de fornecer entrada para um comando. `Get-Help` tem muitos parâmetros que podem ser especificados para retornar todo o tópico da ajuda ou um subconjunto dele.

A seção de sintaxe do tópico da ajuda mostrada no conjunto de resultados anterior lista todos os parâmetros para `Get-Help`. À primeira vista, parece que os mesmos parâmetros estão listados seis vezes diferentes. Cada um desses blocos diferentes na seção de sintaxe é um conjunto de parâmetros. Isso significa que o cmdlet `Get-Help` tem seis conjuntos de parâmetros diferentes. Se você examinar mais de perto, verá que pelo menos um parâmetro é diferente em cada um dos conjuntos de parâmetros.

Os conjuntos de parâmetros são mutuamente exclusivos. Quando um parâmetro exclusivo que só existe em um dos conjuntos de parâmetros é usado, somente os parâmetros contidos nesse conjunto de parâmetros podem ser usados. Por exemplo, os parâmetros **Full** e **Detailed** não podiam ser especificados ao mesmo tempo porque estavam em conjuntos de parâmetros diferentes.

Cada um dos seguintes parâmetros está em conjuntos de parâmetros diferentes:

- Completo
- Detalhado
- Exemplos
- Online
- Parâmetro
- ShowWindow

Toda a sintaxe criptografada, como colchetes quadrados e angulares na seção de sintaxe, significa algo, mas isso será abordado no apêndice A deste livro. Embora seja importante, alguém que é novo no PowerShell e não o utiliza todos os dias costuma ter dificuldade para se lembrar de qual é a sintaxe criptografada.

Para obter mais informações para entender melhor a sintaxe criptografada, confira o [Apêndice A][].

Para iniciantes, há um modo mais fácil de descobrir as mesmas informações, exceto em linguagem simples.

Quando o parâmetro **Completo** de `Get-Help` é especificado, todo o tópico da ajuda é retornado.

```powershell
Get-Help -Name Get-Help -Full
```

Reserve um tempo para executar esse exemplo em seu computador, examinar a saída e anotar como as informações são agrupadas:

- NAME
- SINOPSE
- SYNTAX
- DESCRIPTION
- PARAMETERS
- ENTRADAS
- SAÍDAS
- OBSERVAÇÕES
- EXEMPLOS
- LINKS RELACIONADOS

Observe que usar o parâmetro **Completo** retornou várias seções adicionais, uma das quais é a seção de parâmetros que fornece mais informações do que a seção de sintaxe criptografada.

O parâmetro **Completo** é um parâmetro de opção. Um parâmetro que não exige um valor é chamado de parâmetro de opção. Quando um parâmetro de opção é especificado, o valor é true; quando ele não é especificado, o valor é false.

Se você trabalhou com este capítulo no console do PowerShell, observou que o comando anterior exibe o tópico de ajuda completo para `Get-Help` mostrado por na tela sem lhe dar a oportunidade de lê-lo. Há um modo melhor.

`Help` é uma função que canaliza `Get-Help` para uma função chamada `more`, que é um wrapper para o arquivo executável `more.com` no Windows. No console do PowerShell, `help` fornece uma página de ajuda de cada vez. No ISE, funciona da mesma maneira que `Get-Help`. Minha recomendação é usar a função `help`, em vez do cmdlet `Get-Help`, uma vez que fornece uma experiência melhor e é menor para digitar.

No entanto, digitar menos nem sempre é algo bom. Se você pretende salvar seus comandos como um script ou compartilhá-los com outra pessoa, use nomes de cmdlet e parâmetro completos. Os nomes completos são autodocumentados, o que os torna mais fáceis de entender. Pense na próxima pessoa que precisará ler e entender seus comandos. Ela pode ser você. Seus colegas de trabalho e você mesmo no futuro agradecerão.

Tente executar os seguintes comandos no console do PowerShell em seu computador do ambiente de laboratório do Windows 10.

```powershell
Get-Help -Name Get-Help -Full
help -Name Get-Help -Full
help Get-Help -Full
```

Você observou alguma diferença na saída dos comandos listados anteriormente quando os executava em seu computador do ambiente de laboratório do Windows 10?

Não há diferenças que não as duas últimas opções retornarem os resultados uma página por vez.
A <kbd>barra de espaços</kbd> é usada para exibir a próxima página de conteúdo ao usar a função `Help` e <kbd>Ctrl</kbd>+<kbd>C</kbd> cancela os comandos que estão em execução no console do PowerShell.

O primeiro exemplo usa o cmdlet `Get-Help`; o segundo usa a função `Help`; e o terceiro omite o parâmetro **Name** ao usar a função `Help`. **Name** é um parâmetro posicional e está sendo usado posicionalmente neste exemplo. Isso significa que o valor pode ser especificado sem especificar o nome do parâmetro, desde que o próprio valor seja especificado na posição correta. Como eu sabia em qual posição especificar o valor? Lendo a ajuda conforme mostrado no exemplo a seguir.

```powershell
help Get-Help -Parameter Name
```

```Output
-Name <String>
    Gets help about the specified command or concept. Enter the name of a cmdlet, function,
    provider, script, or workflow, such as Get-Member, a conceptual article name, such as
    about_Objects, or an alias, such as ls. Wildcard characters are permitted in cmdlet and
    provider names, but you can't use wildcard characters to find the names of function help and
    script help articles.

    To get help for a script that isn't located in a path that's listed in the $env:Path
    environment variable, type the script's path and file name.

    If you enter the exact name of a help article, Get-Help displays the article contents.

    If you enter a word or word pattern that appears in several help article titles, Get-Help
    displays a list of the matching titles.

    If you enter a word that doesn't match any help article titles, Get-Help displays a list of
    articles that include that word in their contents.

    The names of conceptual articles, such as about_Objects, must be entered in English, even in
    non-English versions of PowerShell.

    Required?                    false
    Position?                    0
    Default value                None
    Accept pipeline input?       True (ByPropertyName)
    Accept wildcard characters?  true
```

Observe que, no exemplo anterior, o parâmetro **Parameter** foi usado com a função Ajuda para retornar apenas informações do tópico da ajuda para o parâmetro **Name**. Isso é muito mais conciso do que tentar examinar manualmente o que às vezes parece um tópico de ajuda de centenas de páginas.

Com base nesses resultados, você pode ver que o parâmetro **Name** é posicional e deve ser especificado na posição zero (a primeira posição) quando usado de acordo com a posição. A ordem em que os parâmetros são especificados não importa se o nome do parâmetro está especificado.

Outra informação importante é que o parâmetro **Name** espera que o tipo de dados de seu valor seja uma cadeia de caracteres única, que é denotada por `<String>`. Se ele aceitar várias cadeias de caracteres, o tipo de dados será listado como `<String[]>`.

Às vezes, você simplesmente não quer exibir o tópico inteiro da ajuda para um comando. Há vários outros parâmetros, além de **Full** , que podem ser especificados com `Get-Help` ou `Help`. Tente executar os seguintes comandos no computador do ambiente de laboratório do Windows 10:

```powershell
Get-Help -Name Get-Command -Full
Get-Help -Name Get-Command -Detailed
Get-Help -Name Get-Command -Examples
Get-Help -Name Get-Command -Online
Get-Help -Name Get-Command -Parameter Noun
Get-Help -Name Get-Command -ShowWindow
```

Normalmente, use `help <command name>` com o parâmetro **Full** ou **Online**. Se eu estiver interessado apenas nos exemplos, usarei o parâmetro **Examples** e, se estiver interessado apenas em um parâmetro específico, usarei o parâmetro **Parameter**. O parâmetro **ShowWindow** abre o tópico da ajuda em uma janela pesquisável separada que poderá ser colocada em um monitor diferente se você tiver vários monitores. Eu evitei o parâmetro **ShowWindow** porque há um bug conhecido em que ele não exibe todo o tópico da ajuda.

Se você quiser obter ajuda em uma janela separada, minha recomendação é usar o parâmetro **Online** ou usar o parâmetro **Full** e canalizar os resultados para `Out-GridView`, conforme mostrado no exemplo a seguir.

```powershell
help Get-Command -Full | Out-GridView
```

Tanto o cmdlet `Out-GridView` quanto o parâmetro **ShowWindow** do cmdlet `Get-Help` exigem um sistema operacional com uma GUI (interface gráfica do usuário). Eles vão gerar uma mensagem de erro se você tentar usar qualquer um deles no Windows Server instalado usando a opção de instalação de núcleo do servidor (sem GUI).

Para usar `Get-Help` para localizar comandos, use o caractere curinga asterisco (`*`) com o parâmetro **Name**. Especifique um termo no qual você está procurando comandos como o valor para o parâmetro **Name** , conforme mostrado no exemplo a seguir.

```powershell
help *process*
```

```Output
Name                              Category  Module                    Synopsis
----                              --------  ------                    --------
Enter-PSHostProcess               Cmdlet    Microsoft.PowerShell.Core Connects to and ...
Exit-PSHostProcess                Cmdlet    Microsoft.PowerShell.Core Closes an intera...
Get-PSHostProcessInfo             Cmdlet    Microsoft.PowerShell.Core
Debug-Process                     Cmdlet    Microsoft.PowerShell.M... Debugs one or mo...
Get-Process                       Cmdlet    Microsoft.PowerShell.M... Gets the process...
Start-Process                     Cmdlet    Microsoft.PowerShell.M... Starts one or mo...
Stop-Process                      Cmdlet    Microsoft.PowerShell.M... Stops one or mor...
Wait-Process                      Cmdlet    Microsoft.PowerShell.M... Waits for the pr...
Get-AppvVirtualProcess            Function  AppvClient                ...
Start-AppvVirtualProcess          Function  AppvClient                ...
```

No exemplo anterior, os caracteres curinga `*` não são necessários e omiti-los produz o mesmo resultado. `Get-Help` adiciona automaticamente os caracteres curinga em segundo plano.

```powershell
help process
```

O comando anterior produz os mesmos resultados que especificar o caractere curinga `*` em cada fim do processo.

Prefiro adicioná-los, pois essa é a opção que sempre funciona de modo consistente. Caso contrário, eles serão necessários em determinados cenários e não em outros. Assim que você adicionar um caractere curinga no meio do valor, ele não será mais adicionado automaticamente em segundo plano ao valor especificado.

```powershell
help pr*cess
```

Nenhum resultado é retornado por esse comando, a menos que o caractere curinga `*` seja adicionado ao início, ao fim ou ao início e ao fim de `pr*cess`.

Se o valor especificado começar com um traço, um erro será gerado porque o PowerShell o interpretará como um nome de parâmetro e não existirá esse nome de parâmetro para o cmdlet `Get-Help`.

```powershell
help -process
```

Se você está tentando procurar comandos que terminam com `-process`, basta adicionar o caractere curinga `*` ao início do valor.

```powershell
help *-process
```

Ao procurar comandos do PowerShell com `Get-Help`, você deve ser um pouco mais vago, em vez de específico demais com o que está procurando.

Pesquisar `process` anteriormente encontrou apenas comandos que continham `process` no nome do comando e retornavam apenas esses resultados. Quando `Get-Help` é usado para pesquisar `processes`, ele não localiza nenhuma correspondência para nomes de comando, portanto, executa uma pesquisa de cada tópico da ajuda no PowerShell no seu sistema e retorna as correspondências que encontra. Isso faz com que ele retorne um número muito grande de resultados.

```powershell
Get-Help processes
```

```Output
Name                              Category  Module                    Synopsis
----                              --------  ------                    --------
Disconnect-PSSession              Cmdlet    Microsoft.PowerShell.Core Disconnects from...
Enter-PSHostProcess               Cmdlet    Microsoft.PowerShell.Core Connects to and ...
ForEach-Object                    Cmdlet    Microsoft.PowerShell.Core Performs an oper...
Get-PSSessionConfiguration        Cmdlet    Microsoft.PowerShell.Core Gets the registe...
New-PSTransportOption             Cmdlet    Microsoft.PowerShell.Core Creates an objec...
Out-Host                          Cmdlet    Microsoft.PowerShell.Core Sends output to ...
Where-Object                      Cmdlet    Microsoft.PowerShell.Core Selects objects ...
Clear-Variable                    Cmdlet    Microsoft.PowerShell.U... Deletes the valu...
Compare-Object                    Cmdlet    Microsoft.PowerShell.U... Compares two set...
Convert-String                    Cmdlet    Microsoft.PowerShell.U... Formats a string...
ConvertFrom-Csv                   Cmdlet    Microsoft.PowerShell.U... Converts object ...
ConvertTo-Html                    Cmdlet    Microsoft.PowerShell.U... Converts Microso...
ConvertTo-Xml                     Cmdlet    Microsoft.PowerShell.U... Creates an XML-b...
Debug-Runspace                    Cmdlet    Microsoft.PowerShell.U... Starts an intera...
Export-Csv                        Cmdlet    Microsoft.PowerShell.U... Converts objects...
Export-FormatData                 Cmdlet    Microsoft.PowerShell.U... Saves formatting...
Format-List                       Cmdlet    Microsoft.PowerShell.U... Formats the outp...
Format-Table                      Cmdlet    Microsoft.PowerShell.U... Formats the outp...
Get-Random                        Cmdlet    Microsoft.PowerShell.U... Gets a random nu...
Get-Unique                        Cmdlet    Microsoft.PowerShell.U... Returns unique i...
Group-Object                      Cmdlet    Microsoft.PowerShell.U... Groups objects t...
Import-Clixml                     Cmdlet    Microsoft.PowerShell.U... Imports a CLIXML...
Import-Csv                        Cmdlet    Microsoft.PowerShell.U... Creates table-li...
Measure-Object                    Cmdlet    Microsoft.PowerShell.U... Calculates the n...
Out-File                          Cmdlet    Microsoft.PowerShell.U... Sends output to ...
Out-GridView                      Cmdlet    Microsoft.PowerShell.U... Sends output to ...
Select-Object                     Cmdlet    Microsoft.PowerShell.U... Selects objects ...
Set-Variable                      Cmdlet    Microsoft.PowerShell.U... Sets the value o...
Sort-Object                       Cmdlet    Microsoft.PowerShell.U... Sorts objects by...
Tee-Object                        Cmdlet    Microsoft.PowerShell.U... Saves command ou...
Trace-Command                     Cmdlet    Microsoft.PowerShell.U... Configures and s...
Write-Output                      Cmdlet    Microsoft.PowerShell.U... Sends the specif...
Debug-Process                     Cmdlet    Microsoft.PowerShell.M... Debugs one or mo...
Get-Process                       Cmdlet    Microsoft.PowerShell.M... Gets the process...
Get-WmiObject                     Cmdlet    Microsoft.PowerShell.M... Gets instances o...
Start-Process                     Cmdlet    Microsoft.PowerShell.M... Starts one or mo...
Stop-Process                      Cmdlet    Microsoft.PowerShell.M... Stops one or mor...
Wait-Process                      Cmdlet    Microsoft.PowerShell.M... Waits for the pr...
Get-Counter                       Cmdlet    Microsoft.PowerShell.D... Gets performance...
Invoke-WSManAction                Cmdlet    Microsoft.WSMan.Manage... Invokes an actio...
Remove-WSManInstance              Cmdlet    Microsoft.WSMan.Manage... Deletes a manage...
Get-WSManInstance                 Cmdlet    Microsoft.WSMan.Manage... Displays managem...
New-WSManInstance                 Cmdlet    Microsoft.WSMan.Manage... Creates a new in...
Set-WSManInstance                 Cmdlet    Microsoft.WSMan.Manage... Modifies the man...
about_Arithmetic_Operators        HelpFile                            Describes the op...
about_Arrays                      HelpFile                            Describes arrays...
about_Debuggers                   HelpFile                            Describes the Wi...
about_Execution_Policies          HelpFile                            Describes the Wi...
about_ForEach-Parallel            HelpFile                            Describes the Fo...
about_Foreach                     HelpFile                            Describes a lang...
about_Functions                   HelpFile                            Describes how to...
about_Language_Keywords           HelpFile                            Describes the ke...
about_Methods                     HelpFile                            Describes how to...
about_Objects                     HelpFile                            Provides essenti...
about_Parallel                    HelpFile                            Describes the Pa...
about_Pipelines                   HelpFile                            Combining comman...
about_Preference_Variables        HelpFile                            Variables that c...
about_Remote                      HelpFile                            Describes how to...
about_Remote_Output               HelpFile                            Describes how to...
about_Sequence                    HelpFile                            Describes the Se...
about_Session_Configuration_Files HelpFile                            Describes sessio...
about_Variables                   HelpFile                            Describes how va...
about_Windows_PowerShell_5.0      HelpFile                            Describes new fe...
about_WQL                         HelpFile                            Describes WMI Qu...
about_WS-Management_Cmdlets       HelpFile                            Provides an over...
about_ForEach-Parallel            HelpFile                            Describes the Fo...
about_Parallel                    HelpFile                            Describes the Pa...
about_Sequence                    HelpFile                            Describes the Se...
```

Usar `Help` para pesquisar `process` retornou 10 resultados e usá-lo para pesquisar `processes` retornou 68 resultados. Se apenas um resultado for encontrado, o tópico da ajuda em si será exibido, em vez de uma lista de comandos.

```powershell
get-help *hotfix*
```

```Output
NAME
    Get-HotFix

SYNOPSIS
    Gets the hotfixes that have been applied to the local and remote computers.


SYNTAX
    Get-HotFix [-ComputerName <String[]>] [-Credential <PSCredential>] [-Description
    <String[]>] [<CommonParameters>]

    Get-HotFix [[-Id] <String[]>] [-ComputerName <String[]>] [-Credential
    <PSCredential>] [<CommonParameters>]


DESCRIPTION
    The Get-Hotfix cmdlet gets hotfixes (also called updates) that have been installed
    on either the local computer (or on specified remote computers) by Windows Update,
    Microsoft Update, or Windows Server Update Services; the cmdlet also gets hotfixes
    or updates that have been installed manually by users.


RELATED LINKS
    Online Version: http://go.microsoft.com/fwlink/?LinkId=821586
    Win32_QuickFixEngineering http://go.microsoft.com/fwlink/?LinkID=145071
    Get-ComputerRestorePoint
    Add-Content

REMARKS
    To see the examples, type: "get-help Get-HotFix -examples".
    For more information, type: "get-help Get-HotFix -detailed".
    For technical information, type: "get-help Get-HotFix -full".
    For online help, type: "get-help Get-HotFix -online"
```

Agora, para desmistificar a ideia de que `Help` no PowerShell só pode encontrar comandos que tenham tópicos de ajuda.

```powershell
help *more*
```

```Output
NAME
    more

SYNTAX
    more [[-paths] <string[]>]


ALIASES
    None


REMARKS
    None
```

Observe, no exemplo anterior, que `more` não tem um tópico de ajuda, mas o sistema `Help` no PowerShell conseguiu encontrá-lo. Ele encontrou apenas uma correspondência e retornou as informações de sintaxe básicas que você verá quando um comando não tiver um tópico da ajuda.

O PowerShell contém vários tópicos de ajuda (Sobre) conceituais. O comando a seguir pode ser usado para retornar uma lista de todos os tópicos de ajuda **Sobre** em seu sistema.

```powershell
help About_*
```

Limitar os resultados a um único tópico sobre a ajuda exibe o tópico da ajuda real, em vez de retornar uma lista.

```powershell
help about_Updatable_Help
```

O sistema de ajuda no PowerShell precisa ser atualizado para que os tópicos de ajuda **Sobre** estejam presentes. Se, por algum motivo, a atualização inicial do sistema de ajuda falhar em seu computador, os arquivos não estarão disponíveis até que o cmdlet `Update-Help` tenha sido executado com êxito.

## <a name="get-command"></a>Get-Command

`Get-Command` é projetado para ajudar você a localizar comandos. A execução do `Get-Command` sem parâmetros retorna uma lista de todos os comandos em seu sistema. O exemplo a seguir demonstra o uso do cmdlet `Get-Command` para determinar quais comandos existem para trabalhar com processos:

```powershell
Get-Command -Noun Process
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Debug-Process                                      3.1.0.0    Microsof...
Cmdlet          Get-Process                                        3.1.0.0    Microsof...
Cmdlet          Start-Process                                      3.1.0.0    Microsof...
Cmdlet          Stop-Process                                       3.1.0.0    Microsof...
Cmdlet          Wait-Process                                       3.1.0.0    Microsof...
```

Observe no exemplo anterior em que `Get-Command` foi executado, o parâmetro **Noun** é usado e `Process` é especificado como o valor para o parâmetro **Noun**. E se você não sabia como usar o cmdlet `Get-Command`? Você pode usar `Get-Help` para exibir o tópico da ajuda para `Get-Command`.

Os parâmetros **Name** , **Noun** e **Verb** aceitam curingas. O exemplo a seguir mostra os curingas que estão sendo usados com o parâmetro **Nome** :

```Output
Get-Command -Name *service*
```

```powershell
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Function        Get-NetFirewallServiceFilter                       2.0.0.0    NetSecurity
Function        Set-NetFirewallServiceFilter                       2.0.0.0    NetSecurity
Cmdlet          Get-Service                                        3.1.0.0    Microsof...
Cmdlet          New-Service                                        3.1.0.0    Microsof...
Cmdlet          New-WebServiceProxy                                3.1.0.0    Microsof...
Cmdlet          Restart-Service                                    3.1.0.0    Microsof...
Cmdlet          Resume-Service                                     3.1.0.0    Microsof...
Cmdlet          Set-Service                                        3.1.0.0    Microsof...
Cmdlet          Start-Service                                      3.1.0.0    Microsof...
Cmdlet          Stop-Service                                       3.1.0.0    Microsof...
Cmdlet          Suspend-Service                                    3.1.0.0    Microsof...
Application     AgentService.exe                                   10.0.14... C:\Windo...
Application     SensorDataService.exe                              10.0.14... C:\Windo...
Application     services.exe                                       10.0.14... C:\Windo...
Application     services.msc                                       0.0.0.0    C:\Windo...
Application     TieringEngineService.exe                           10.0.14... C:\Windo...
```

Não sou um fã do uso de curingas com o parâmetro **Name** de `Get-Command`, já que ele também retorna arquivos executáveis que não são comandos nativos do PowerShell.

Se você pretende usar caracteres curinga com o parâmetro **Name** , recomendo limitar os resultados com o parâmetro **CommandType**.

```powershell
Get-Command -Name *service* -CommandType Cmdlet, Function, Alias
```

Uma opção melhor é usar o parâmetro **Verb** ou **Noun** ou ambos, já que apenas comandos do PowerShell têm verbos e substantivos.

Encontrou algo errado com um tópico da ajuda? A boa notícia é que os tópicos de ajuda para o PowerShell foram acessados e estão disponíveis no repositório do [PowerShell-Docs][] no GitHub. Passe esse benefício adiante não apenas corrigindo as informações incorretas para você mesmo, mas para todas as outras pessoas também. Basta bifurcar o repositório de documentação do PowerShell no GitHub, atualizar o tópico da ajuda e enviar uma solicitação de pull.
Depois que a solicitação de pull for aceita, a documentação corrigida estará disponível para todos.

## <a name="updating-help"></a>Como atualizar a ajuda

A cópia local dos tópicos da ajuda do PowerShell foi atualizada anteriormente na primeira vez em que a ajuda para um comando foi solicitada. É recomendável atualizar periodicamente o sistema de ajuda, pois pode haver atualizações ao seu conteúdo de tempos em tempos. O cmdlet `Update-Help` é usado para atualizar os tópicos da ajuda.
Por padrão, ele requer acesso à Internet e que você esteja executando o PowerShell com privilégios elevados como administrador.

```powershell
Update-Help
```

```Output
Update-Help : Failed to update Help for the module(s) 'BitsTransfer' with UI culture(s)
{en-US} : The value of the HelpInfoUri key in the module manifest must resolve to a
container or root URL on a website where the help files are stored. The HelpInfoUri
'https://technet.microsoft.com/en-us/library/dd819413.aspx' does not resolve to a
container.
At line:1 char:1
+ Update-Help
+
    + CategoryInfo          : InvalidOperation: (:) [Update-Help], Exception
    + FullyQualifiedErrorId : InvalidHelpInfoUri,Microsoft.PowerShell.Commands.UpdateHel
   pCommand

Update-Help : Failed to update Help for the module(s) 'NetworkControllerDiagnostics,
StorageReplica' with UI culture(s) {en-US} : Unable to retrieve the HelpInfo XML file
for UI culture en-US. Make sure the HelpInfoUri property in the module manifest is valid
or check your network connection and then try the command again.
At line:1 char:1
+ Update-Help
+
    + CategoryInfo          : ResourceUnavailable: (:) [Update-Help], Exception
    + FullyQualifiedErrorId : UnableToRetrieveHelpInfoXml,Microsoft.PowerShell.Commands.
   UpdateHelpCommand
```

Alguns módulos retornaram erros, o que não é incomum. Se o computador não tiver acesso à Internet, você poderá usar o cmdlet `Save-Help` em outro computador que tenha acesso à Internet para primeiro salvar as informações de ajuda atualizadas em um compartilhamento de arquivo em sua rede e, em seguida, usar o parâmetro **SourcePath** de `Update-Help` para especificar esse local de rede para os tópicos da ajuda.

Considere configurar uma tarefa agendada ou adicionar alguma lógica ao script de perfil no PowerShell para atualizar periodicamente o conteúdo da ajuda em seu computador. Os scripts de perfil serão discutidos em um capítulo futuro.

## <a name="summary"></a>Resumo

Neste capítulo, você aprendeu a encontrar comandos com `Get-Help` e `Get-Command`. Você aprendeu a usar o sistema de ajuda para descobrir como usar comandos depois de encontrá-los. Você também aprendeu a atualizar o conteúdo dos tópicos da ajuda quando as atualizações estão disponíveis.

Meu desafio para você é aprender um comando do PowerShell por dia.

```powershell
Get-Command | Get-Random | Get-Help -Full
```

## <a name="review"></a>Revisão

1. O parâmetro **DisplayName** de posicional `Get-Service`?
1. Quantos conjuntos de parâmetros o cmdlet `Get-Process` tem?
1. Quais comandos do PowerShell existem para trabalhar com logs de eventos?
1. Qual é o comando do PowerShell para retornar uma lista de processos do PowerShell em execução no seu computador?
1. Como você atualiza o conteúdo da ajuda do PowerShell armazenado no computador?

## <a name="recommended-reading"></a>Leitura recomendada

Se você quer obter mais informações sobre os tópicos abordados neste capítulo, recomendo a leitura dos tópicos da Ajuda do PowerShell a seguir.

- [Get-Help][]
- [Get-Command][]
- [Update-Help][]
- [Save-Help][]
- [about_Updatable_Help][]
- [about_Command_Syntax][]

No próximo capítulo, você aprenderá sobre o cmdlet `Get-Member`, bem como objetos, propriedades e métodos.

<!-- link references -->
[Get-Help]: /powershell/module/microsoft.powershell.core/get-help
[Get-Command]: /powershell/module/microsoft.powershell.core/get-command
[Update-Help]: /powershell/module/microsoft.powershell.core/update-help
[Save-Help]: /powershell/module/microsoft.powershell.core/save-help
[about_Updatable_Help]: /powershell/module/microsoft.powershell.core/about/about_updatable_help
[about_Command_Syntax]: /powershell/module/microsoft.powershell.core/about/about_command_syntax
[PowerShell-Docs]: https://github.com/powershell/powershell
[Apêndice A]: appendix-a.md
