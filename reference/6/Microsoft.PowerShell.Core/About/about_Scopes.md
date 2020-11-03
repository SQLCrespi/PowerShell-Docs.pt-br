---
description: Explica o conceito de escopo no PowerShell e mostra como definir e alterar o escopo dos elementos.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 03/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_scopes?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_scopes
ms.openlocfilehash: 3e165867be5887ae15890f795531b5a3048c4550
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195635"
---
# <a name="about-scopes"></a>Sobre escopos

## <a name="short-description"></a>Descrição breve
Explica o conceito de escopo no PowerShell e mostra como definir e alterar o escopo dos elementos.

## <a name="long-description"></a>Descrição longa

O PowerShell protege o acesso a variáveis, aliases, funções e unidades do PowerShell (PSDrive) limitando o local em que eles podem ser lidos e alterados. O PowerShell usa regras de escopo para garantir que você não altere inadvertidamente um item que não deva ser alterado.

A seguir estão as regras básicas de escopo:

- Os escopos podem ser aninhados. Um escopo externo é conhecido como escopo pai. Todos os escopos aninhados são escopos filho desse pai.

- Um item é visível no escopo no qual ele foi criado e em qualquer escopo filho, a menos que você o torne explicitamente privado. Você pode inserir variáveis, aliases, funções ou unidades do PowerShell em um ou mais escopos.

- Um item que você criou em um escopo pode ser alterado somente no escopo no qual ele foi criado, a menos que você especifique explicitamente um escopo diferente.

Se você criar um item em um escopo e o item compartilhar seu nome com um item em um escopo diferente, o item original poderá estar oculto no novo item, mas ele não será substituído ou alterado.

## <a name="powershell-scopes"></a>Escopos do PowerShell

O PowerShell dá suporte aos seguintes escopos:

- Global: o escopo que está em vigor quando o PowerShell é iniciado. Variáveis e funções que estão presentes quando o PowerShell é iniciado foram criadas no escopo global, como variáveis automáticas e variáveis de preferência. As variáveis, os aliases e as funções nos perfis do PowerShell também são criados no escopo global.

- Local: o escopo atual. O escopo local pode ser o escopo global ou qualquer outro escopo.

- Script: o escopo que é criado enquanto um arquivo de script é executado. Somente os comandos no script são executados no escopo do script. Para os comandos em um script, o escopo do script é o escopo local.

> [!NOTE]
> **Privado** não é um escopo. É uma [opção](#private-option) que altera a visibilidade de um item fora do escopo onde o item é definido.

## <a name="parent-and-child-scopes"></a>Escopos pai e filho

Você pode criar um novo escopo executando um script ou uma função, criando uma sessão ou iniciando uma nova instância do PowerShell. Quando você cria um novo escopo, o resultado é um escopo pai (o escopo original) e um escopo filho (o escopo que você criou).

No PowerShell, todos os escopos são escopos filho do escopo global, mas você pode criar muitos escopos e muitos escopos recursivos.

A menos que você explicitamente torne os itens particulares, os itens no escopo pai estão disponíveis para o escopo filho. No entanto, os itens que você cria e alteram no escopo filho não afetam o escopo pai, a menos que você especifique explicitamente o escopo ao criar os itens.

## <a name="inheritance"></a>Herança

Um escopo filho não herda as variáveis, aliases e funções do escopo pai. A menos que um item seja privado, o escopo filho pode exibir os itens no escopo pai. E ele pode alterar os itens especificando explicitamente o escopo pai, mas os itens não fazem parte do escopo filho.

No entanto, um escopo filho é criado com um conjunto de itens. Normalmente, inclui todos os aliases que têm a opção de **escopo** . Essa opção será discutida posteriormente neste artigo. Ele inclui todas as variáveis que têm a opção de **escopo** , além de algumas variáveis automáticas.

Para localizar os itens em um escopo específico, use o parâmetro scope de `Get-Variable` ou `Get-Alias` .

Por exemplo, para obter todas as variáveis no escopo local, digite:

```powershell
Get-Variable -Scope local
```

Para obter todas as variáveis no escopo global, digite:

```powershell
Get-Variable -Scope global
```

## <a name="scope-modifiers"></a>Modificadores de escopo

Uma variável, alias ou nome de função pode incluir qualquer um dos seguintes modificadores de escopo opcionais:

- `global:` -Especifica que o nome existe no escopo **global** .
- `local:` -Especifica que o nome existe no escopo **local** . O escopo atual é sempre o escopo **local** .
- `private:` -Especifica que o nome é **privado** e visível somente para o escopo atual.
- `script:` -Especifica que o nome existe no escopo do **script** .
  Escopo de **script** é o escopo do arquivo de script ancestral mais próximo ou **global** se não houver nenhum arquivo de script ancestral mais próximo.
- `using:` -Usado para acessar variáveis definidas em outro escopo durante a execução de scripts por meio de cmdlets como `Start-Job` e `Invoke-Command` .
- `workflow:` -Especifica que o nome existe em um fluxo de trabalho. Observação: não há suporte para fluxos de trabalho no PowerShell Core.
- `<variable-namespace>` -Um modificador criado por um provedor PSDrive do PowerShell.
  Por exemplo:

  |  Namespace  |                    Descrição                     |
  | ----------- | -------------------------------------------------- |
  | `Alias:`    | Aliases definidos no escopo atual               |
  | `Env:`      | Variáveis de ambiente definidas no escopo atual |
  | `Function:` | Funções definidas no escopo atual             |
  | `Variable:` | Variáveis definidas no escopo atual             |

O escopo padrão para scripts é o escopo do script. O escopo padrão para funções e aliases é o escopo local, mesmo se eles forem definidos em um script.

### <a name="using-scope-modifiers"></a>Usando modificadores de escopo

Para especificar o escopo de uma nova variável, alias ou função, use um modificador de escopo.

A sintaxe para um modificador de escopo em uma variável é:

```
$[<scope-modifier>:]<name> = <value>
```

A sintaxe para um modificador de escopo em uma função é:

```
function [<scope-modifier>:]<name> {<function-body>}
```

O comando a seguir, que não usa um modificador de escopo, cria uma variável no escopo atual ou **local** :

```powershell
$a = "one"
```

Para criar a mesma variável no escopo **global** , use o `global:` modificador de escopo:

```powershell
$global:a = "one"
```

Para criar a mesma variável no escopo do **script** , use o `script:` modificador de escopo:

```powershell
$script:a = "one"
```

Você também pode usar um modificador de escopo com funções. A definição de função a seguir cria uma função no escopo **global** :

```powershell
function global:Hello {
  Write-Host "Hello, World"
}
```

Você também pode usar modificadores de escopo para se referir a uma variável em um escopo diferente.
O comando a seguir refere-se à `$test` variável, primeiro no escopo local e, em seguida, no escopo global:

```powershell
$test
$global:test
```

### <a name="the-using-scope-modifier"></a>O `Using:` modificador de escopo

Using é um modificador de escopo especial que identifica uma variável local em um comando remoto. Sem um modificador, o PowerShell espera que as variáveis em comandos remotos sejam definidas na sessão remota.

O `Using` modificador de escopo é introduzido no PowerShell 3,0.

Para qualquer script ou comando que é executado fora da sessão, você precisa do `Using` modificador de escopo para inserir valores de variáveis do escopo da sessão de chamada, para que o código fora da sessão possa acessá-los. O `Using` modificador de escopo tem suporte nos seguintes contextos:

- Comandos executados remotamente, iniciados com `Invoke-Command` o uso dos parâmetros **ComputerName** , **hostname** , **SSHConnection** ou **Session** (sessão remota)
- Trabalhos em segundo plano, iniciados com `Start-Job` (sessão fora do processo)
- Trabalhos de thread iniciados via `Start-ThreadJob` (sessão de thread separada)

Dependendo do contexto, os valores de variáveis inseridos são cópias independentes dos dados no escopo do chamador ou referências a ele. Em sessões remotas e fora do processo, elas são sempre cópias independentes.

Para obter mais informações, consulte [about_Remote_Variables](about_Remote_Variables.md).

Em sessões de thread, elas são passadas por referência. Isso significa que é possível modificar variáveis de escopo de chamada em um thread diferente. Para modificar com segurança as variáveis exige a sincronização de threads.

Para obter mais informações, consulte:

- [Start-ThreadJob](xref:ThreadJob.Start-ThreadJob)

#### <a name="serialization-of-variable-values"></a>Serialização de valores de variáveis

Comandos executados remotamente e trabalhos em segundo plano são executados fora do processo.
Sessões fora do processo usam serialização e desserialização baseadas em XML para tornar os valores das variáveis disponíveis nos limites do processo. O processo de serialização converte objetos em um **PSObject** que contém as propriedades dos objetos originais, mas não seus métodos.

Para um conjunto limitado de tipos, a desserialização rehydrates objetos de volta para o tipo original. O objeto de resalimentação é uma cópia da instância do objeto original.
Ele tem as propriedades e os métodos do tipo. Para tipos simples, como **System. Version** , a cópia é exata. Para tipos complexos, a cópia é imperfeita. Por exemplo, os objetos de certificado resalimentados não incluem a chave privada.

Instâncias de todos os outros tipos são instâncias de **PSObject** . A propriedade **PSTypeNames** contém o nome do tipo original prefixado com **desserializado** , por exemplo, **Deserialized.System. Data. DataTable**

### <a name="the-allscope-option"></a>A opção de escopo

Variáveis e aliases têm uma propriedade **Option** que pode assumir um valor de **escopo** . Os itens que têm a propriedade de **escopo** se tornam parte de qualquer escopo filho que você criar, embora eles não sejam herdados retroativamente por escopos pai.

Um item que tem a propriedade de **escopo** é visível no escopo filho e faz parte desse escopo. As alterações no item em qualquer escopo afetam todos os escopos nos quais a variável é definida.

### <a name="managing-scope"></a>Gerenciando escopo

Vários cmdlets têm um parâmetro de **escopo** que permite obter ou definir (criar e alterar) itens em um escopo específico. Use o seguinte comando para localizar todos os cmdlets em sua sessão que têm um parâmetro de **escopo** :

```powershell
Get-Help * -Parameter scope
```

Para localizar as variáveis que são visíveis em um escopo específico, use o `Scope` parâmetro de `Get-Variable` . As variáveis visíveis incluem variáveis globais, variáveis no escopo pai e variáveis no escopo atual.

Por exemplo, o comando a seguir obtém as variáveis que são visíveis no escopo local:

```powershell
Get-Variable -Scope local
```

Para criar uma variável em um escopo específico, use um modificador de escopo ou o parâmetro de **escopo** de `Set-Variable` . O comando a seguir cria uma variável no escopo global:

```powershell
New-Variable -Scope global -Name a -Value "One"
```

Você também pode usar o parâmetro de escopo dos `New-Alias` `Set-Alias` `Get-Alias` cmdlets, ou para especificar o escopo. O comando a seguir cria um alias no escopo global:

```powershell
New-Alias -Scope global -Name np -Value Notepad.exe
```

Para obter as funções em um escopo específico, use o `Get-Item` cmdlet quando estiver no escopo. O `Get-Item` cmdlet não tem um parâmetro de **escopo** .

> [!NOTE]
> Para os cmdlets que usam o parâmetro de **escopo** , você também pode se referir a escopos por número. O número descreve a posição relativa de um escopo para outro. O escopo 0 representa o escopo atual, ou local. O escopo 1 indica o escopo pai imediato. Escopo 2 indica o pai do escopo pai e assim por diante. Os escopos numerados serão úteis se você tiver criado muitos escopos recursivos.

### <a name="using-dot-source-notation-with-scope"></a>Usando a notação de origem de ponto com escopo

Scripts e funções seguem todas as regras de escopo. Você os cria em um escopo específico e eles afetam somente esse escopo, a menos que você use um parâmetro de cmdlet ou um modificador de escopo para alterar esse escopo.

Mas, você pode adicionar um script ou função ao escopo atual usando a notação de origem de ponto. Em seguida, quando um script é executado no escopo atual, todas as funções, aliases e variáveis que o script cria estão disponíveis no escopo atual.

Para adicionar uma função ao escopo atual, digite um ponto (.) e um espaço antes do caminho e do nome da função na chamada de função.

Por exemplo, para executar o script Sample.ps1 do diretório C:\Scripts no escopo do script (o padrão para scripts), use o seguinte comando:

```powershell
c:\scripts\sample.ps1
```

Para executar o script de Sample.ps1 no escopo local, use o seguinte comando:

```powershell
. c:\scripts.sample.ps1
```

Quando você usa o operador de chamada (&) para executar uma função ou script, ele não é adicionado ao escopo atual. O exemplo a seguir usa o operador Call:

```powershell
& c:\scripts.sample.ps1
```

Você pode ler mais sobre o operador de chamada em [about_Operators](about_operators.md).

Quaisquer aliases, funções ou variáveis que o script de Sample.ps1 cria não estão disponíveis no escopo atual.

## <a name="restricting-without-scope"></a>Restringindo sem escopo

Alguns conceitos do PowerShell são semelhantes ao escopo ou a interação com o escopo. Esses conceitos podem ser confundidos com o escopo ou o comportamento do escopo.

As sessões, os módulos e os prompts aninhados são ambientes independentes, mas não são escopos filho do escopo global na sessão.

### <a name="sessions"></a>Sessões

Uma sessão é um ambiente no qual o PowerShell é executado. Quando você cria uma sessão em um computador remoto, o PowerShell estabelece uma conexão persistente com o computador remoto. A conexão persistente permite que você use a sessão para vários comandos relacionados.

Como uma sessão é um ambiente contido, ela tem seu próprio escopo, mas uma sessão não é um escopo filho da sessão na qual foi criada. A sessão começa com seu próprio escopo global. Esse escopo é independente do escopo global da sessão. Você pode criar escopos filho na sessão. Por exemplo, você pode executar um script para criar um escopo filho em uma sessão.

### <a name="modules"></a>Módulos

Você pode usar um módulo do PowerShell para compartilhar e entregar ferramentas do PowerShell. Um módulo é uma unidade que pode conter cmdlets, scripts, funções, variáveis, aliases e outros itens úteis. A menos que definido explicitamente, os itens em um módulo não são acessíveis fora do módulo. Portanto, você pode adicionar o módulo à sua sessão e usar os itens públicos sem se preocupar que os outros itens podem substituir os cmdlets, scripts, funções e outros itens em sua sessão.

Por padrão, os módulos são carregados no nível superior do _estado de sessão_ atual, não no _escopo_ atual. O estado da sessão atual pode ser um estado de sessão de módulo ou o estado de sessão global. A adição de um módulo a uma sessão não altera o escopo. Se você estiver no escopo global, os módulos serão carregados no estado de sessão global. Todas as exportações são colocadas nas tabelas globais.
Se você carregar Module2 de _dentro_ de Module1, Module2 será carregado no estado de sessão de Module1 não o estado de sessão global. Todas as exportações de Module2 são colocadas na parte superior do estado de sessão do Module1. Se você usar `Import-Module -Scope local` , as exportações serão colocadas no objeto de escopo atual, e não no nível superior. Se você estiver _em um módulo_ e usar `Import-Module -Scope global` (ou `Import-Module -Global` ) para carregar outro módulo, esse módulo e as exportações serão carregados no estado de sessão global em vez do estado de sessão local do módulo. Esse recurso foi criado para gravar o módulo que manipula módulos. O módulo **WindowsCompatibility** faz isso para importar módulos de proxy para o estado de sessão global.

Dentro do estado da sessão, os módulos têm seu próprio escopo. Considere o seguinte módulo `C:\temp\mod1.psm1` :

```powershell
$a = "Hello"

function foo {
    "`$a = $a"
    "`$global:a = $global:a"
}
```

Agora, criamos uma variável global `$a` , atribuimos a ela um valor e chamamos a função **foo** .

```powershell
$a = "Goodbye"
foo
```

O módulo declara a variável `$a` no escopo do módulo e, em seguida, a função **foo** gera o valor da variável em ambos os escopos.

```Output
$a = Hello
$global:a = Goodbye
```

### <a name="nested-prompts"></a>Prompts aninhados

Os prompts aninhados não têm seu próprio escopo. Quando você insere um prompt aninhado, o prompt aninhado é um subconjunto do ambiente. Mas, você permanece dentro do escopo local.

Os scripts têm seu próprio escopo. Se você estiver depurando um script e chegar a um ponto de interrupção no script, insira o escopo do script.

### <a name="private-option"></a>Opção particular

Aliases e variáveis têm uma propriedade **Option** que pode ter um valor de **Private** . Os itens que têm a opção **particular** podem ser exibidos e alterados no escopo no qual eles são criados, mas não podem ser exibidos ou alterados fora desse escopo.

Por exemplo, se você criar uma variável que tenha uma opção particular no escopo global e, em seguida, executar um script, `Get-Variable` os comandos no script não exibirão a variável particular. Usar o modificador de escopo global nessa instância não exibe a variável particular.

Você pode usar o parâmetro Option dos `New-Variable` `Set-Variable` `New-Alias` cmdlets,, e `Set-Alias` para definir o valor da propriedade Option como Private.

### <a name="visibility"></a>Visibilidade

A propriedade **Visibility** de uma variável ou alias determina se você pode ver o item fora do contêiner, no qual ele foi criado. Um contêiner pode ser um módulo, um script ou um snap-in. A visibilidade é projetada para contêineres da mesma maneira que o valor **particular** da propriedade **Option** é projetado para escopos.

A propriedade **Visibility** usa os valores **público** e **privado** . Os itens que têm visibilidade privada podem ser exibidos e alterados somente no contêiner no qual eles foram criados. Se o contêiner for adicionado ou importado, os itens que têm visibilidade privada não poderão ser exibidos ou alterados.

Como a visibilidade é projetada para contêineres, ela funciona de forma diferente em um escopo.

- Se você criar um item que tenha visibilidade privada no escopo global, não poderá exibir nem alterar o item em nenhum escopo.
- Se você tentar exibir ou alterar o valor de uma variável que tem visibilidade privada, o PowerShell retornará uma mensagem de erro.

Você pode usar os `New-Variable` `Set-Variable` cmdlets e para criar uma variável que tenha visibilidade privada.

## <a name="examples"></a>Exemplos

### <a name="example-1-change-a-variable-value-only-in-a-script"></a>Exemplo 1: alterar um valor de variável somente em um script

O comando a seguir altera o valor da `$ConfirmPreference` variável em um script. A alteração não afeta o escopo global.

Primeiro, para exibir o valor da `$ConfirmPreference` variável no escopo local, use o seguinte comando:

```
PS>  $ConfirmPreference
High
```

Crie um script de Scope.ps1 que contenha os seguintes comandos:

```powershell
$ConfirmPreference = "Low"
"The value of `$ConfirmPreference is $ConfirmPreference."
```

Execute o script. O script altera o valor da `$ConfirmPreference` variável e, em seguida, relata seu valor no escopo do script. A saída deve se parecer com a seguinte saída:

```output
The value of $ConfirmPreference is Low.
```

Em seguida, teste o valor atual da `$ConfirmPreference` variável no escopo atual.

```
PS>  $ConfirmPreference
High
```

Este exemplo mostra que as alterações no valor de uma variável no escopo do script não afetam o valor da variável no escopo pai.

### <a name="example-2-view-a-variable-value-in-different-scopes"></a>Exemplo 2: exibir um valor de variável em escopos diferentes

Você pode usar modificadores de escopo para exibir o valor de uma variável no escopo local e em um escopo pai.

Primeiro, defina uma `$test` variável no escopo global.

```powershell
$test = "Global"
```

Em seguida, crie um script de Sample.ps1 que define a `$test` variável. No script, use um modificador de escopo para se referir às versões global ou local da `$test` variável.

Em Sample.ps1:

```powershell
$test = "Local"
"The local value of `$test is $test."
"The global value of `$test is $global:test."
```

Quando você executa Sample.ps1, a saída deve se parecer com a seguinte saída:

```output
The local value of $test is Local.
The global value of $test is Global.
```

Quando o script for concluído, somente o valor global de `$test` será definido na sessão.

```
PS>  $test
Global
```

### <a name="example-3-change-the-value-of-a-variable-in-a-parent-scope"></a>Exemplo 3: alterar o valor de uma variável em um escopo pai

A menos que você proteja um item usando a opção particular ou outro método, você pode exibir e alterar o valor de uma variável em um escopo pai.

Primeiro, defina uma `$test` variável no escopo global.

```powershell
$test = "Global"
```

Em seguida, crie um script de Sample.ps1 que define a `$test` variável. No script, use um modificador de escopo para se referir às versões global ou local da `$test` variável.

Em Sample.ps1:

```powershell
$global:test = "Local"
"The global value of `$test is $global:test."
```

Quando o script for concluído, o valor global de `$test` será alterado.

```
PS>  $test
Local
```

### <a name="example-4-creating-a-private-variable"></a>Exemplo 4: criando uma variável privada

Uma variável particular é uma variável que tem uma propriedade **Option** que tem um valor de *Private* . As variáveis *privadas* são herdadas pelo escopo filho, mas só podem ser exibidas ou alteradas no escopo no qual foram criadas.

O comando a seguir cria uma variável privada chamada `$ptest` no escopo local.

```powershell
New-Variable -Name ptest -Value 1 -Option private
```

Você pode exibir e alterar o valor de `$ptest` no escopo local.

```
PS>  $ptest
1

PS>  $ptest = 2
PS>  $ptest
2
```

Em seguida, crie um script de Sample.ps1 que contenha os comandos a seguir. O comando tenta exibir e alterar o valor de `$ptest` .

Em Sample.ps1:

```powershell
"The value of `$Ptest is $Ptest."
"The value of `$Ptest is $global:Ptest."
```

A `$ptest` variável não está visível no escopo do script, a saída está vazia.

```powershell
"The value of $Ptest is ."
"The value of $Ptest is ."
```

### <a name="example-5-using-a-local-variable-in-a-remote-command"></a>Exemplo 5: usando uma variável local em um comando remoto

Para variáveis em um comando remoto criado na sessão local, use o `Using` modificador de escopo. O PowerShell pressupõe que as variáveis em comandos remotos foram criadas na sessão remota.

A sintaxe do é:

```
$Using:<VariableName>
```

Por exemplo, os comandos a seguir criam uma `$Cred` variável na sessão local e, em seguida, usam a `$Cred` variável em um comando remoto:

```powershell
$Cred = Get-Credential
Invoke-Command $s {Remove-Item .\Test*.ps1 -Credential $Using:Cred}
```

O escopo de uso foi introduzido no PowerShell 3,0. No PowerShell 2,0, para indicar que uma variável foi criada na sessão local, use o seguinte formato de comando.

```powershell
$Cred = Get-Credential
Invoke-Command $s {
  param($c)
  Remove-Item .\Test*.ps1 -Credential $c
} -ArgumentList $Cred
```

## <a name="see-also"></a>Confira também

[about_Variables](about_Variables.md)

[about_Environment_Variables](about_Environment_Variables.md)

[about_Functions](about_Functions.md)

[about_Script_Blocks](about_Script_Blocks.md)

[Start-ThreadJob](/powershell/module/ThreadJob/Start-ThreadJob)
