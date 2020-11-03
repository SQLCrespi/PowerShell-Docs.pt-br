---
description: Descreve as palavras-chave na linguagem de script do PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_language_keywords?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Language_Keywords
ms.openlocfilehash: 09b0414a962cce3f9f5c90b28aa871f4c09f76e2
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195890"
---
# <a name="about-language-keywords"></a>Sobre palavras-chave de idioma

## <a name="short-description"></a>DESCRIÇÃO BREVE
Descreve as palavras-chave na linguagem de script do PowerShell.

## <a name="long-description"></a>DESCRIÇÃO LONGA

O PowerShell tem as seguintes palavras-chave de idioma. Para obter mais informações, consulte o tópico sobre para a palavra-chave e as informações que seguem a tabela.

Palavra-chave     | Referência
---         | ---
Começar       | [about_Functions](about_Functions.md), [about_Functions_Advanced](about_Functions_Advanced.md)
Falha       | [about_Break](about_Break.md), [about_Trap](about_Trap.md)
Pegar       | [about_Try_Catch_Finally](about_Try_Catch_Finally.md)
Classe       | [about_Classes](about_Classes.md)
Continuar    | [about_Continue](about_Continue.md), [about_Trap](about_Trap.md)
Dados        | [about_Data_Sections](about_Data_Sections.md)
Definir      | Reservado para uso futuro
O que fazer          | [about_Do](about_Do.md), [about_While](about_While.md)
DynamicParam| [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)
Else        | [about_If](about_If.md)
ElseIf      | [about_If](about_If.md)
End         | [about_Functions](about_Functions.md), [about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md)
Enumeração        | [about_Enum](about_Enum.md)
Fechar        | [Descrito neste tópico](#exit)
Filtrar      | [about_Functions](about_Functions.md)
Finalmente     | [about_Try_Catch_Finally](about_Try_Catch_Finally.md)
For (para)         | [about_For](about_For.md)
ForEach     | [about_ForEach](about_ForEach.md)
De        | Reservado para uso futuro
Função    | [about_Functions](about_Functions.md), [about_Functions_Advanced](about_Functions_Advanced.md)
Hidden      | [about_Hidden](about_Hidden.md)
If          | [about_If](about_If.md)
Em          | [about_ForEach](about_ForEach.md)
Param       | [about_Functions](about_Functions.md)
Processar     | [about_Functions](about_Functions.md), [about_Functions_Advanced](about_Functions_Advanced.md)
Retorno      | [about_Return](about_Return.md)
Estático      | [about_Classes](about_Classes.md)
Alternar      | [about_Switch](about_Switch.md)
Throw       | [about_Throw](about_Throw.md), [about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md)
Trap        | [about_Trap](about_Trap.md), [about_Break](about_Break.md), [about_Try_Catch_Finally](about_Try_Catch_Finally.md)
Experimente         | [about_Try_Catch_Finally](about_Try_Catch_Finally.md)
Haja       | [about_Do](about_Do.md)
Usar       | [about_Using](about_Using.md), [about_Classes](about_Classes.md)
Var         | Reservado para uso futuro
While       | [about_While](about_While.md), [about_Do](about_Do.md)

Palavras-chave de linguagem

### <a name="begin"></a>Começar

Especifica uma parte do corpo de uma função, juntamente com as `DynamicParam` `Process` `End` palavras-chave, e. A `Begin` lista de instruções é executada uma vez antes de todos os objetos serem recebidos do pipeline.

Sintaxe:

```Syntax
function <name> {
    DynamicParam {<statement list>}
    begin {<statement list>}
    process {<statement list>}
    end {<statement list>}
}
```

### <a name="break"></a>Falha

Faz com que um script saia de um loop.

Sintaxe:

```Syntax
while (<condition>) {
   <statements>
   ...

   break
   ...

   <statements>
}
```

### <a name="catch"></a>Pegar

Especifica uma lista de instruções a ser executada se ocorrer um erro na lista de instruções Try que o acompanha. Um tipo de erro requer colchetes. O segundo par de colchetes indica que o tipo de erro é opcional.

Sintaxe:

```Syntax
try {<statement list>}
catch [[<error type>]] {<statement list>}
```

### <a name="class"></a>Classe

Especifica uma nova classe no PowerShell.

Sintaxe:

```Syntax
class <class-name> {
    [[hidden] [static] <property-definition> ...]
    [<class-name>([argument-list>]) {<constructor-statement-list>} ...]
    [[hidden] [static] <method-definition> ...]
}
```

### <a name="continue"></a>Continuar

Faz com que um script pare de executar um loop e volte para a condição. Se a condição for atendida, o script iniciará o loop novamente.

Sintaxe:

```Syntax
while (<condition>) {
   <statements>
   ...

   continue
   ...

   <statements>
}
```

### <a name="data"></a>Dados

Em um script, define uma seção que isola os dados da lógica do script. Também pode incluir `If` instruções e alguns comandos limitados.

Sintaxe:

```Syntax
data <variable> [-supportedCommand <cmdlet-name>] {<permitted content>}
```

### <a name="do"></a>O que fazer

Usado com a `While` `Until` palavra-chave or como uma construção de looping. O PowerShell executa a lista de instruções pelo menos uma vez, ao contrário de um loop que usa `While` .

Sintaxe para `While`:

```Syntax
do {<statement list>} while (<condition>)
```

Sintaxe para `Until`:

```Syntax
do {<statement list>} until (<condition>)
```

### <a name="dynamicparam"></a>DynamicParam

Especifica uma parte do corpo de uma função, juntamente com as `Begin` `Process` `End` palavras-chave, e. Parâmetros dinâmicos são adicionados em tempo de execução.

Sintaxe:

```Syntax
function <name> {
   DynamicParam {<statement list>}
   begin {<statement list>}
   process {<statement list>}
   end {<statement list>}
}
```

### <a name="else"></a>Else

Usado com a `If` palavra-chave para especificar a lista de instruções padrão.

Sintaxe:

```Syntax
if (<condition>) {<statement list>}
else {<statement list>}
```

### <a name="elseif"></a>ElseIf

Usado com as `If` `Else` palavras-chave e para especificar condicionais adicionais. A `Else` palavra-chave é opcional.

Sintaxe:

```Syntax
if (<condition>) {<statement list>}
elseif (<condition>) {<statement list>}
else {<statement list>}
```

### <a name="end"></a>End

Especifica uma parte do corpo de uma função, juntamente com as `DynamicParam` `Begin` `End` palavras-chave, e. A `End` lista de instruções é executada uma vez depois que todos os objetos são recebidos do pipeline.

Sintaxe:

```Syntax
function <name> {
   DynamicParam {<statement list>}
   begin {<statement list>}
   process {<statement list>}
   end {<statement list>}
}
```

### <a name="enum"></a>Enumeração

`enum` é usado para declarar uma enumeração; um tipo distinto que consiste em um conjunto de rótulos nomeados chamado lista de enumeradores.

Sintaxe:

```Syntax
enum <enum-name> {
    <label> [= <int-value>]
    ...
}
```

### <a name="exit"></a>Fechar

Faz com que o PowerShell saia de um script ou de uma instância do PowerShell.

Sintaxe:

```Syntax
exit
exit <exitcode>
```

Quando você usa `pwsh` o com o parâmetro **File** , o `.ps1` próprio arquivo (script) deve incluir instruções para lidar com erros ou exceções que ocorrem durante a execução do script. Você só deve usar a `exit` instrução para indicar o status de pós-execução do script.

No Windows, qualquer número entre `[int]::MinValue` e `[int]::MaxValue` é permitido.

No UNIX, somente números positivos entre `[byte]::MinValue` e `[byte]::MaxValue` são permitidos. Um número negativo no intervalo de `-1` até `-255` é automaticamente convertido em um número positivo adicionando 256. Por exemplo, `-2` é transformado para `254` .

No PowerShell, a `exit` instrução define o valor da `$LASTEXITCODE` variável. No Shell de comando do Windows (cmd.exe), a instrução Exit define o valor da `%ERRORLEVEL%` variável de ambiente.

Qualquer argumento que não seja numérico ou fora do intervalo específico da plataforma é convertido para o valor de `0` .

No exemplo a seguir, o usuário define o valor da variável de nível de erro como 4 adicionando `exit 4` ao arquivo de script `test.ps1` .

```cmd
C:\scripts\test>type test.ps1
1
2
3
exit 4

C:\scripts\test>pwsh -file ./test.ps1
1
2
3

C:\scripts\test>echo %ERRORLEVEL%
4
```

Quando você executa `pwsh.exe -File <path to a script>` o e o arquivo de script termina com um `exit` comando, o código de saída é definido como o argumento numérico usado com o `exit` comando. Se o script não tiver nenhuma `exit` instrução, o código de saída sempre será `0` quando o script for concluído sem erros ou `1` quando o script for encerrado a partir de uma exceção sem tratamento.

### <a name="filter"></a>Filtrar

Especifica uma função na qual a lista de instruções é executada uma vez para cada objeto de entrada. Ele tem o mesmo efeito que uma função que contém apenas um bloco de processo.

Sintaxe:

```Syntax
filter <name> {<statement list>}
```

### <a name="finally"></a>Finalmente

Define uma lista de instruções que é executada após as instruções associadas a try e catch. Uma `Finally` lista de instruções é executada mesmo se você pressionar `CTRL+C` para sair de um script ou se usar a palavra-chave Exit no script.

Sintaxe:

```Syntax
try {<statement list>}
catch [<error type>] {<statement list>}
finally {<statement list>}
```

### <a name="for"></a>For (para)

Define um loop usando uma condição.

Sintaxe:

```Syntax
for (<initialize>; <condition>; <iterate>) { <statement list> }
```

### <a name="foreach"></a>ForEach

Define um loop usando cada membro de uma coleção.

Sintaxe:

```Syntax
ForEach (<item> in <collection>) { <statement list> }
```

### <a name="from"></a>De

Reservado para uso futuro.

### <a name="function"></a>Função

Cria uma lista de instruções nomeadas de código reutilizável. Você pode nomear o escopo ao qual uma função pertence. E você pode especificar um ou mais parâmetros nomeados usando a `Param` palavra-chave. Dentro da lista de instruções de função, você pode incluir `DynamicParam` listas de instruções,, `Begin` `Process` e `End` .

Sintaxe:

```Syntax
function [<scope:>]<name> {
   param ([type]<$pname1> [, [type]<$pname2>])
   DynamicParam {<statement list>}
   begin {<statement list>}
   process {<statement list>}
   end {<statement list>}
}
```

Você também tem a opção de definir um ou mais parâmetros fora da lista de instruções após o nome da função.

Sintaxe:

```Syntax
function [<scope:>]<name> [([type]<$pname1>, [[type]<$pname2>])] {
   DynamicParam {<statement list>}
   begin {<statement list>}
   process {<statement list>}
   end {<statement list>}
}
```

### <a name="if"></a>If

Define uma condicional.

Sintaxe:

```Syntax
if (<condition>) {<statement list>}
```

### <a name="hidden"></a>Hidden

Oculta os membros da classe dos resultados padrão do `Get-Member` cmdlet e dos resultados do IntelliSense e da conclusão da guia.

Sintaxe:

```Syntax
Hidden [data type] $member_name
```

### <a name="in"></a>Em

Usado em uma `ForEach` instrução para criar um loop que usa cada membro de uma coleção.

Sintaxe:

```Syntax
ForEach (<item> in <collection>){<statement list>}
```

### <a name="inlinescript"></a>InlineScript

Executa comandos de fluxo de trabalho em uma sessão do PowerShell compartilhada. Essa palavra-chave é válida somente em um fluxo de trabalho do PowerShell.

Sintaxe:

```Syntax
workflow <verb>-<noun>
{
   InlineScript
   {
      <Command/Expression>
      ...

   }
}
```

A `InlineScript` palavra-chave indica uma `InlineScript` atividade, que executa comandos em uma sessão padrão compartilhada (sem fluxo de trabalho). Você pode usar a `InlineScript` palavra-chave para executar comandos que, de outra forma, não são válidos em um fluxo de trabalho e para executar comandos que compartilham dados. Por padrão, os comandos em um bloco de script InlineScript são executados em um processo separado.

Para obter mais informações, consulte [executando comandos do PowerShell em um fluxo de trabalho](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj574197(v=ws.11)).

### <a name="param"></a>Param

Define os parâmetros em uma função.

Sintaxe:

```Syntax
function [<scope:>]<name> {
   param ([type]<$pname1>[, [[type]<$pname2>]])
   <statement list>
}
```

### <a name="process"></a>Processar

Especifica uma parte do corpo de uma função, juntamente com as `DynamicParam` `Begin` `End` palavras-chave, e. Quando uma `Process` lista de instruções recebe entrada do pipeline, a `Process` lista de instruções é executada uma vez para cada elemento do pipeline. Se o pipeline não fornecer nenhum objeto, a `Process` lista de instruções não será executada. Se o comando for o primeiro comando no pipeline, a `Process` lista de instruções será executada uma vez.

Sintaxe:

```Syntax
function <name> {
   DynamicParam {<statement list>}
   begin {<statement list>}
   process {<statement list>}
   end {<statement list>}
}
```

### <a name="return"></a>Retorno

Faz com que o PowerShell deixe o escopo atual, como um script ou uma função, e grava a expressão opcional na saída.

Sintaxe:

```Syntax
return [<expression>]
```

### <a name="static"></a>Estático

Especifica se a propriedade ou o método definido é comum a todas as instâncias da classe em que está definido.

Consulte `Class` para obter exemplos de uso.

### <a name="switch"></a>Alternar

Para verificar várias condições, use uma `Switch` instrução. A `Switch` instrução é equivalente a uma série de `If` instruções, mas é mais simples.

A `Switch` instrução lista cada condição e uma ação opcional. Se uma condição for obtida, a ação será executada.

Sintaxe 1:

```Syntax
switch [-regex|-wildcard|-exact][-casesensitive] ( <value> )
{
   <string>|<number>|<variable>|{ <expression> } {<statement list>}
   <string>|<number>|<variable>|{ <expression> } {<statement list>}
   ...

   default {<statement list>}
}
```

Sintaxe 2:

```Syntax
switch [-regex|-wildcard|-exact][-casesensitive] -file <filename>
{
   <string>|<number>|<variable>|{ <expression> } {<statement list>}
   <string>|<number>|<variable>|{ <expression> } {<statement list>}
   ...

   default {<statement list>}
}
```

### <a name="throw"></a>Throw

Gera um objeto como um erro.

Sintaxe:

```Syntax
throw [<object>]
```

### <a name="trap"></a>Trap

Define uma lista de instruções a ser executada se um erro for encontrado. Um tipo de erro requer colchetes. O segundo par de colchetes indica que o tipo de erro é opcional.

Sintaxe:

```Syntax
trap [[<error type>]] {<statement list>}
```

### <a name="try"></a>Experimente

Define uma lista de instruções para ser verificada quanto a erros enquanto as instruções são executadas. Se ocorrer um erro, o PowerShell continuará em execução em uma `Catch` `Finally` instrução ou. Um tipo de erro requer colchetes. O segundo par de colchetes indica que o tipo de erro é opcional.

Sintaxe:

```Syntax
try {<statement list>}
catch [[<error type>]] {<statement list>}
finally {<statement list>}
```

### <a name="until"></a>Haja

Usado em uma `Do` instrução como um constructo de loop em que a lista de instruções é executada pelo menos uma vez.

Sintaxe:

```Syntax
do {<statement list>} until (<condition>)
```

### <a name="using"></a>Usar

Permite indicar quais namespaces são usados na sessão. As classes e os membros exigem menos digitação para mencionar. Você também pode incluir classes de módulos.

#1 de sintaxe:

```Syntax
using namespace <.Net-framework-namespace>
```

#2 de sintaxe:

```Syntax
using module <module-name>
```

### <a name="while"></a>While

A `while` instrução é um constructo de loop em que a condição é testada antes que as instruções sejam executadas. Se a condição for falsa, as instruções não serão executadas.

Sintaxe da instrução:

```Syntax
while (<condition>) {
   <statements>
 }
```

Quando usado em uma `Do` instrução, `while` faz parte de um constructo de loop em que a lista de instruções é executada pelo menos uma vez.

Sintaxe do loop do:

```Syntax
do {<statement list>} while (<condition>)
```

## <a name="see-also"></a>CONSULTE TAMBÉM

- [about_Special_Characters](about_Special_Characters.md)
- [about_Wildcards](about_Wildcards.md)
