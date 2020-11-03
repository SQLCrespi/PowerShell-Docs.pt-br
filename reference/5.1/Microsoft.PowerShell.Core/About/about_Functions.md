---
description: Descreve como criar e usar funções no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 2/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions
ms.openlocfilehash: f033bc36bf67a9d01e3f238645b83df7d75c6963
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196021"
---
# <a name="about-functions"></a>Sobre o Functions

## <a name="short-description"></a>Descrição breve

Descreve como criar e usar funções no PowerShell.

## <a name="long-description"></a>Descrição longa

Uma função é uma lista de instruções do PowerShell que tem um nome que você atribui. Ao executar uma função, você digita o nome da função. As instruções na lista são executadas como se você as tivesse digitado no prompt de comando.

As funções podem ser tão simples quanto:

```powershell
function Get-PowerShellProcess { Get-Process PowerShell }
```

Uma função também pode ser tão complexa quanto um cmdlet ou um programa de aplicativo.

Como os cmdlets, as funções podem ter parâmetros. Os parâmetros podem ser nomeados, posicionais, switches ou parâmetros dinâmicos. Os parâmetros de função podem ser lidos na linha de comando ou no pipeline.

As funções podem retornar valores que podem ser exibidos, atribuídos a variáveis ou passados para outras funções ou cmdlets. Você também pode especificar um valor de retorno usando a `return` palavra-chave. A `return` palavra-chave não afeta ou elimina outra saída retornada de sua função. No entanto, a `return` palavra-chave sai da função nessa linha. Para obter mais informações, consulte [about_Return](about_Return.md).

A lista de instruções da função pode conter tipos diferentes de listas de instruções com as palavras-chave `Begin` , `Process` e `End` . Essas instruções listam a entrada do pipeline de forma diferente.

Um filtro é um tipo especial de função que usa a `Filter` palavra-chave.

As funções também podem atuar como cmdlets. Você pode criar uma função que funciona exatamente como um cmdlet sem usar a `C#` programação. Para obter mais informações, consulte [about_Functions_Advanced](about_Functions_Advanced.md).

## <a name="syntax"></a>Syntax

Veja a seguir a sintaxe de uma função:

```
function [<scope:>]<name> [([type]$parameter1[,[type]$parameter2])]
{
  param([type]$parameter1 [,[type]$parameter2])
  dynamicparam {<statement list>}
  begin {<statement list>}
  process {<statement list>}
  end {<statement list>}
}
```

Uma função inclui os seguintes itens:

- Uma `Function` palavra-chave
- Um escopo (opcional)
- Um nome que você seleciona
- Qualquer número de parâmetros nomeados (opcional)
- Um ou mais comandos do PowerShell entre chaves `{}`

Para obter mais informações sobre a `Dynamicparam` palavra-chave e os parâmetros dinâmicos em funções, consulte [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).

## <a name="simple-functions"></a>Funções simples

As funções não precisam ser complicadas para serem úteis. As funções mais simples têm o seguinte formato:

```
function <function-name> {statements}
```

Por exemplo, a função a seguir inicia o PowerShell com a opção Executar como administrador.

```powershell
function Start-PSAdmin {Start-Process PowerShell -Verb RunAs}
```

Para usar a função, digite: `Start-PSAdmin`

Para adicionar instruções à função, digite cada instrução em uma linha separada ou use um ponto-e-vírgula `;` para separar as instruções.

Por exemplo, a função a seguir localiza todos os `.jpg` arquivos nos diretórios do usuário atual que foram alterados após a data de início.

```powershell
function Get-NewPix
{
  $start = Get-Date -Month 1 -Day 1 -Year 2010
  $allpix = Get-ChildItem -Path $env:UserProfile\*.jpg -Recurse
  $allpix | Where-Object {$_.LastWriteTime -gt $Start}
}
```

Você pode criar uma caixa de ferramentas de funções pequenas úteis. Adicione essas funções ao seu perfil do PowerShell, conforme descrito em [about_Profiles](about_Profiles.md) e posteriormente neste tópico.

## <a name="function-names"></a>Nomes de função

Você pode atribuir qualquer nome a uma função, mas as funções que você compartilha com outras pessoas devem seguir as regras de nomenclatura que foram estabelecidas para todos os comandos do PowerShell.

Os nomes de funções devem consistir em um par verbo-substantivo no qual o verbo identifica a ação que a função executa e o substantivo identifica o item no qual o cmdlet executa sua ação.

As funções devem usar os verbos padrão que foram aprovados para todos os comandos do PowerShell. Esses verbos nos ajudam a manter nossos nomes de comando simples, consistentes e fáceis para os usuários entenderem.

Para obter mais informações sobre os verbos padrão do PowerShell, consulte [verbos aprovados](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands) no Microsoft docs.

## <a name="functions-with-parameters"></a>Funções com parâmetros

Você pode usar parâmetros com funções, incluindo parâmetros nomeados, parâmetros posicionais, parâmetros de switch e parâmetros dinâmicos. Para obter mais informações sobre parâmetros dinâmicos em funções, consulte [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).

### <a name="named-parameters"></a>Parâmetros nomeados

Você pode definir qualquer número de parâmetros nomeados. Você pode incluir um valor padrão para parâmetros nomeados, conforme descrito posteriormente neste tópico.

Você pode definir parâmetros dentro das chaves usando a `Param` palavra-chave, conforme mostrado na seguinte sintaxe de exemplo:

```
function <name> {
  param ([type]$parameter1[,[type]$parameter2])
  <statement list>
}
```

Você também pode definir parâmetros fora das chaves sem a `Param` palavra-chave, conforme mostrado na seguinte sintaxe de exemplo:

```powershell
function <name> [([type]$parameter1[,[type]$parameter2])] {
  <statement list>
}
```

Veja abaixo um exemplo dessa sintaxe alternativa.

```powershell
Function Add-Numbers($one, $two) {
    $one + $two
}
```

Embora o primeiro método seja preferencial, não há nenhuma diferença entre esses dois métodos.

Quando você executa a função, o valor que você fornece para um parâmetro é atribuído a uma variável que contém o nome do parâmetro. O valor dessa variável pode ser usado na função.

O exemplo a seguir é uma função chamada `Get-SmallFiles` . Essa função tem um `$Size` parâmetro. A função exibe todos os arquivos que são menores do que o valor do `$Size` parâmetro e exclui os diretórios:

```powershell
function Get-SmallFiles {
  Param($Size)
  Get-ChildItem $HOME | Where-Object {
    $_.Length -lt $Size -and !$_.PSIsContainer
  }
}
```

Na função, você pode usar a `$Size` variável, que é o nome definido para o parâmetro.

Para usar essa função, digite o seguinte comando:

```powershell
Get-SmallFiles -Size 50
```

Você também pode inserir um valor para um parâmetro nomeado sem o nome do parâmetro.
Por exemplo, o comando a seguir fornece o mesmo resultado que um comando que nomeia o parâmetro de **tamanho** :

```powershell
Get-SmallFiles 50
```

Para definir um valor padrão para um parâmetro, digite um sinal de igual e o valor após o nome do parâmetro, conforme mostrado na seguinte variação do `Get-SmallFiles` exemplo:

```powershell
function Get-SmallFiles ($Size = 100) {
  Get-ChildItem $HOME | Where-Object {
    $_.Length -lt $Size -and !$_.PSIsContainer
  }
}
```

Se você digitar `Get-SmallFiles` sem um valor, a função atribuirá 100 a `$size` . Se você fornecer um valor, a função usará esse valor.

Opcionalmente, você pode fornecer uma breve cadeia de caracteres de ajuda que descreve o valor padrão do parâmetro, adicionando o atributo **PSDefaultValue** à descrição do parâmetro e especificando a propriedade da **ajuda** de **PSDefaultValue** . Para fornecer uma cadeia de caracteres de ajuda que descreva o valor padrão (100) do parâmetro de **tamanho** na `Get-SmallFiles` função, adicione o atributo **PSDefaultValue** , conforme mostrado no exemplo a seguir.

```powershell
function Get-SmallFiles {
  param (
      [PSDefaultValue(Help = '100')]
      $Size = 100
  )
}
```

Para obter mais informações sobre a classe de atributo **PSDefaultValue** , consulte [membros de atributo PSDefaultValue](/dotnet/api/system.management.automation.psdefaultvalueattribute).

### <a name="positional-parameters"></a>Parâmetros posicionais

Um parâmetro posicional é um parâmetro sem um nome de parâmetro. O PowerShell usa a ordem de valor do parâmetro para associar cada valor de parâmetro a um parâmetro na função.

Ao usar parâmetros posicionais, digite um ou mais valores após o nome da função. Os valores de parâmetros posicionais são atribuídos à `$args` variável de matriz.
O valor que segue o nome da função é atribuído à primeira posição na `$args` matriz, `$args[0]` .

A função a seguir `Get-Extension` adiciona a `.txt` extensão de nome de arquivo a um nome de arquivo que você fornece:

```powershell
function Get-Extension {
  $name = $args[0] + ".txt"
  $name
}
```

```powershell
Get-Extension myTextFile
```

```Output
myTextFile.txt
```

### <a name="switch-parameters"></a>Parâmetros de comutação

Uma opção é um parâmetro que não requer um valor. Em vez disso, digite o nome da função seguido pelo nome do parâmetro de opção.

Para definir um parâmetro de opção, especifique o tipo `[switch]` antes do nome do parâmetro, conforme mostrado no exemplo a seguir:

```powershell
function Switch-Item {
  param ([switch]$on)
  if ($on) { "Switch on" }
  else { "Switch off" }
}
```

Quando você digita o `On` parâmetro switch após o nome da função, a função exibe "switch on". Sem o parâmetro switch, ele exibe "switch off".

```powershell
Switch-Item -on
```

```Output
Switch on
```

```powershell
Switch-Item
```

```Output
Switch off
```

Você também pode atribuir um valor **booliano** a uma opção ao executar a função, conforme mostrado no exemplo a seguir:

```powershell
Switch-Item -on:$true
```

```Output
Switch on
```

```powershell
Switch-Item -on:$false
```

```Output
Switch off
```

## <a name="using-splatting-to-represent-command-parameters"></a>Usando nivelamento para representar parâmetros de comando

Você pode usar nivelamento para representar os parâmetros de um comando. Esse recurso é introduzido no Windows PowerShell 3,0.

Use essa técnica em funções que chamam comandos na sessão. Você não precisa declarar ou enumerar os parâmetros de comando ou alterar a função quando os parâmetros de comando são alterados.

A função de exemplo a seguir chama o `Get-Command` cmdlet. O comando usa `@Args` para representar os parâmetros de `Get-Command` .

```powershell
function Get-MyCommand { Get-Command @Args }
```

Você pode usar todos os parâmetros de `Get-Command` quando chamar a `Get-MyCommand` função. Os parâmetros e os valores de parâmetro são passados para o comando usando `@Args` .

```powershell
Get-MyCommand -Name Get-ChildItem
```

```Output
CommandType     Name                ModuleName
-----------     ----                ----------
Cmdlet          Get-ChildItem       Microsoft.PowerShell.Management
```

O `@Args` recurso usa o `$Args` parâmetro Automatic, que representa os valores e parâmetros de cmdlet não declarados dos argumentos restantes.

Para obter mais informações sobre nivelamento, consulte [about_Splatting](about_Splatting.md).

## <a name="piping-objects-to-functions"></a>Direcionando objetos para funções

Qualquer função pode receber entrada do pipeline. Você pode controlar como uma função processa a entrada do pipeline usando `Begin` as `Process` `End` palavras-chave, e. A sintaxe de exemplo a seguir mostra as três palavras-chave:

```
function <name> {
  begin {<statement list>}
  process {<statement list>}
  end {<statement list>}
}
```

A `Begin` lista de instruções é executada apenas uma vez, no início da função.

> [!IMPORTANT]
> Se sua função define um `Begin` `Process` bloco, ou `End` , todo o seu código deve residir dentro desses blocos. Nenhum código será reconhecido fora dos blocos se *qualquer* um dos blocos for definido.

A `Process` lista de instruções é executada uma vez para cada objeto no pipeline.
Enquanto o `Process` bloco está em execução, cada objeto de pipeline é atribuído à `$_` variável automática, um objeto de pipeline por vez.

Depois que a função recebe todos os objetos no pipeline, a `End` lista de instruções é executada uma vez. Se nenhuma `Begin` `Process` `End` palavra-chave, ou for usada, todas as instruções serão tratadas como uma `End` lista de instruções.

A função a seguir usa a `Process` palavra-chave. A função exibe exemplos do pipeline:

```powershell
function Get-Pipeline
{
  process {"The value is: $_"}
}
```

Para demonstrar essa função, insira uma lista de números separados por vírgulas, conforme mostrado no exemplo a seguir:

```powershell
1,2,4 | Get-Pipeline
```

```Output
The value is: 1
The value is: 2
The value is: 4
```

Quando você usa uma função em um pipeline, os objetos canalizados para a função são atribuídos à `$input` variável automática. A função executa instruções com a `Begin` palavra-chave antes de qualquer objeto ser proveniente do pipeline. A função executa instruções com a `End` palavra-chave após a recebimento de todos os objetos do pipeline.

O exemplo a seguir mostra a `$input` variável automática com `Begin` e `End` palavras-chave.

```powershell
function Get-PipelineBeginEnd
{
  begin {"Begin: The input is $input"}
  end {"End:   The input is $input" }
}
```

Se essa função for executada usando o pipeline, ela exibirá os seguintes resultados:

```powershell
1,2,4 | Get-PipelineBeginEnd
```

```Output
Begin: The input is
End:   The input is 1 2 4
```

Quando a `Begin` instrução é executada, a função não tem a entrada do pipeline. A `End` instrução é executada Depois que a função tem os valores.

Se a função tiver uma `Process` palavra-chave, cada objeto no `$input` será removido de `$input` e atribuído a `$_` . O exemplo a seguir tem uma `Process` lista de instruções:

```powershell
function Get-PipelineInput
{
  process {"Processing:  $_ " }
  end {"End:   The input is: $input" }
}
```

Neste exemplo, cada objeto que é canalizado para a função é enviado para a `Process` lista de instruções. As `Process` instruções são executadas em cada objeto, um objeto por vez. A `$input` variável automática estará vazia quando a função atingir a `End` palavra-chave.

```powershell
1,2,4 | Get-PipelineInput
```

```Output
Processing:  1
Processing:  2
Processing:  4
End:   The input is:
```

Para obter mais informações, consulte [usando enumeradores](about_Automatic_Variables.md#using-enumerators)

## <a name="filters"></a>Filtros

Um filtro é um tipo de função que é executado em cada objeto no pipeline. Um filtro é semelhante a uma função com todas as suas instruções em um `Process` bloco.

A sintaxe de um filtro é a seguinte:

```
filter [<scope:>]<name> {<statement list>}
```

O filtro a seguir usa entradas de log do pipeline e, em seguida, exibe a entrada inteira ou apenas a parte da mensagem da entrada:

```powershell
filter Get-ErrorLog ([switch]$message)
{
  if ($message) { Out-Host -InputObject $_.Message }
  else { $_ }
}
```

## <a name="function-scope"></a>Escopo da função

Existe uma função no escopo no qual ela foi criada.

Se uma função fizer parte de um script, a função estará disponível para instruções dentro desse script. Por padrão, uma função em um script não está disponível no prompt de comando.

Você pode especificar o escopo de uma função. Por exemplo, a função é adicionada ao escopo global no exemplo a seguir:

```powershell
function global:Get-DependentSvs {
  Get-Service | Where-Object {$_.DependentServices}
}
```

Quando uma função está no escopo global, você pode usar a função em scripts, em funções e na linha de comando.

Normalmente, o Functions cria um escopo. Os itens criados em uma função, como variáveis, existem somente no escopo da função.

Para obter mais informações sobre o escopo no PowerShell, consulte [about_Scopes](about_Scopes.md).

## <a name="finding-and-managing-functions-using-the-function-drive"></a>Localizando e gerenciando funções usando a unidade Function:

Todas as funções e filtros no PowerShell são armazenados automaticamente na `Function:` unidade. Essa unidade é exposta pelo provedor de **funções** do PowerShell.

Ao fazer referência à `Function:` unidade, digite uma vírgula após a **função** , assim como faria ao referenciar a `C` unidade ou `D` de um computador.

O comando a seguir exibe todas as funções na sessão atual do PowerShell:

```powershell
Get-ChildItem function:
```

Os comandos na função são armazenados como um bloco de script na propriedade Definition da função. Por exemplo, para exibir os comandos na função de ajuda que vem com o PowerShell, digite:

```powershell
(Get-ChildItem function:help).Definition
```

Você também pode usar a sintaxe a seguir.

```powershell
$function:help
```

Para obter mais informações sobre a `Function:` unidade, consulte o tópico da ajuda para o provedor de **funções** . Digite `Get-Help Function`.

## <a name="reusing-functions-in-new-sessions"></a>Reutilizando funções em novas sessões

Quando você digita uma função no prompt de comando do PowerShell, a função se torna parte da sessão atual. Ele estará disponível até que a sessão termine.

Para usar sua função em todas as sessões do PowerShell, adicione a função ao seu perfil do PowerShell. Para obter mais informações sobre perfis, consulte [about_Profiles](about_Profiles.md).

Você também pode salvar sua função em um arquivo de script do PowerShell. Digite sua função em um arquivo de texto e salve o arquivo com a `.ps1` extensão de nome de arquivo.

## <a name="writing-help-for-functions"></a>Gravando ajuda para funções

O `Get-Help` cmdlet obtém ajuda para funções, bem como para cmdlets, provedores e scripts. Para obter ajuda para uma função, digite `Get-Help` seguido pelo nome da função.

Por exemplo, para obter ajuda para a `Get-MyDisks` função, digite:

```powershell
Get-Help Get-MyDisks
```

Você pode escrever ajuda para uma função usando qualquer um dos dois métodos a seguir:

- Comment-Based ajuda para o Functions

  Crie um tópico da ajuda usando palavras-chave especiais nos comentários. Para criar uma ajuda baseada em comentários para uma função, os comentários devem ser colocados no início ou no final do corpo da função ou nas linhas que antecedem a palavra-chave da função. Para obter mais informações sobre a ajuda baseada em comentários, consulte [about_Comment_Based_Help](about_Comment_Based_Help.md).

- XML-Based ajuda para o Functions

  Crie um tópico de ajuda baseado em XML, como o tipo que normalmente é criado para cmdlets. A ajuda baseada em XML é necessária se você estiver localizando tópicos de ajuda em vários idiomas.

  Para associar a função ao tópico de ajuda baseado em XML, use a `.ExternalHelp` palavra-chave de ajuda baseada em comentários. Sem essa palavra-chave, `Get-Help` não é possível localizar o tópico de ajuda da função e as chamadas para `Get-Help` para a função retornam apenas a ajuda gerada automaticamente.

  Para obter mais informações sobre a `ExternalHelp` palavra-chave, consulte [about_Comment_Based_Help](about_Comment_Based_Help.md). Para obter mais informações sobre a ajuda baseada em XML, consulte [como gravar a ajuda de cmdlet](https://go.microsoft.com/fwlink/?LinkID=123415) na biblioteca MSDN.

## <a name="see-also"></a>Confira também

[about_Automatic_Variables](about_Automatic_Variables.md)

[about_Comment_Based_Help](about_Comment_Based_Help.md)

[about_Functions_Advanced](about_Functions_Advanced.md)

[about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md)

[about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)

[about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md)

[about_Functions_OutputTypeAttribute](about_Functions_OutputTypeAttribute.md)

[about_Parameters](about_Parameters.md)

[about_Profiles](about_Profiles.md)

[about_Scopes](about_Scopes.md)

[about_Script_Blocks](about_Script_Blocks.md)

[about_Function_provider](about_Function_provider.md)
