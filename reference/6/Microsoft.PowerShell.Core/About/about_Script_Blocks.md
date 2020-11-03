---
description: Define o que é um bloco de script e explica como usar blocos de script na linguagem de programação do PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_script_blocks?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Script_Blocks
ms.openlocfilehash: dc3ee050399e92506cabed370e95d03c65652953
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195634"
---
# <a name="about-script-blocks"></a>Sobre blocos de script

## <a name="short-description"></a>Descrição breve

Define o que é um bloco de script e explica como usar blocos de script na linguagem de programação do PowerShell.

## <a name="long-description"></a>Descrição longa

Na linguagem de programação do PowerShell, um bloco de script é uma coleção de instruções ou expressões que podem ser usadas como uma única unidade.
Um bloco de script pode aceitar argumentos e valores de retorno.

Sintaticamente, um bloco de script é uma lista de instruções entre chaves, conforme mostrado na seguinte sintaxe:

```
{<statement list>}
```

Um bloco de script retorna a saída de todos os comandos no bloco de script, seja como um único objeto ou como uma matriz.

Você também pode especificar um valor de retorno usando a `return` palavra-chave. A `return` palavra-chave não afeta ou elimina outra saída retornada do bloco de script. No entanto, a `return` palavra-chave sai do bloco de script nessa linha. Para obter mais informações, consulte [about_Return](about_Return.md).

Como o functions, um bloco de script pode incluir parâmetros. Use a palavra-chave param para atribuir parâmetros nomeados, conforme mostrado na sintaxe a seguir:

```
{
Param([type]$Parameter1 [,[type]$Parameter2])
<statement list>
}
```

> [!NOTE]
> Em um bloco de script, ao contrário de uma função, você não pode especificar parâmetros fora das chaves.

Como as funções, os blocos de script podem incluir as `DynamicParam` `Begin` `Process` `End` palavras-chave,, e. Para obter mais informações, consulte [about_Functions](about_Functions.md) e [about_Functions_Advanced](about_Functions_Advanced.md).

## <a name="using-script-blocks"></a>Usando blocos de script

Um bloco de script é uma instância de um tipo de estrutura Microsoft .NET `System.Management.Automation.ScriptBlock` . Os comandos podem ter valores de parâmetro de bloco de script. Por exemplo, o `Invoke-Command` cmdlet tem um `ScriptBlock` parâmetro que usa um valor de bloco de script, como mostrado neste exemplo:

```powershell
Invoke-Command -ScriptBlock { Get-Process }
```

```Output
Handles  NPM(K)    PM(K)     WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----     ----- -----   ------     -- -----------
999          28    39100     45020   262    15.88   1844 communicator
721          28    32696     36536   222    20.84   4028 explorer
...
```

`Invoke-Command` também pode executar blocos de script que têm blocos de parâmetro.
Os parâmetros são atribuídos por position usando o parâmetro **ArgumentList** .

```powershell
Invoke-Command -ScriptBlock { param($p1, $p2)
"p1: $p1"
"p2: $p2"
} -ArgumentList "First", "Second"
```

```Output
p1: First
p2: Second
```

O bloco de script no exemplo anterior usa a `param` palavra-chave para criar parâmetros `$p1` e `$p2` . A cadeia de caracteres "First" é associada ao primeiro parâmetro ( `$p1` ) e "Second" está associado a ( `$p2` ).

Para obter mais informações sobre o comportamento de **ArgumentList** , consulte [about_Splatting](about_Splatting.md#splatting-with-arrays).

Você pode usar variáveis para armazenar e executar blocos de script. O exemplo a seguir armazena um bloco de script em uma variável e o passa para `Invoke-Command` .

```powershell
$a = { Get-Service BITS }
Invoke-Command -ScriptBlock $a
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  BITS               Background Intelligent Transfer Ser...
```

O operador de chamada é outra maneira de executar blocos de script armazenados em uma variável.
Como `Invoke-Command` , o operador de chamada executa o bloco de script em um escopo filho. O operador Call pode facilitar o uso de parâmetros com seus blocos de script.

```powershell
$a ={ param($p1, $p2)
"p1: $p1"
"p2: $p2"
}
&$a -p2 "First" -p1 "Second"
```

```Output
p1: Second
p2: First
```

Você pode armazenar a saída de seus blocos de script em uma variável usando a atribuição.

```
PS>  $a = { 1 + 1}
PS>  $b = &$a
PS>  $b
2
```

```
PS>  $a = { 1 + 1}
PS>  $b = Invoke-Command $a
PS>  $b
2
```

Para obter mais informações sobre o operador de chamada, consulte [about_Operators](about_Operators.md).

## <a name="using-delay-bind-script-blocks-with-parameters"></a>Usando blocos de script de associação de atraso com parâmetros

Um parâmetro tipado que aceita entrada de pipeline ( `by Value` ) ou ( `by PropertyName` ) permite o uso de blocos de script de **ligação de atraso** no parâmetro.
No bloco de script **Delay-BIND** , você pode referenciar o objeto piped in usando a variável de pipeline `$_` .

```powershell
# Renames config.log to old_config.log
dir config.log | Rename-Item -NewName {"old_" + $_.Name}
```

Em cmdlets mais complexos, os blocos de script de ligação de atraso permitem a reutilização de um piped no objeto para popular outros parâmetros.

Observações sobre blocos de script de **Associação de atraso** como parâmetros:

- Você deve especificar explicitamente os nomes de parâmetro usados com blocos **de script de ligação atrasada** .
- O parâmetro não deve ser sem tipo, e o tipo do parâmetro não pode ser `[scriptblock]` ou `[object]` .
- Você receberá um erro se usar um bloco de script de **ligação de atraso** sem fornecer entrada de pipeline.

  ```powershell
  Rename-Item -NewName {$_.Name + ".old"}
  ```

  ```Output
  Rename-Item : Cannot evaluate parameter 'NewName' because its argument is
  specified as a script block and there is no input. A script block cannot
  be evaluated without input.
  At line:1 char:23
  +  Rename-Item -NewName {$_.Name + ".old"}
  +                       ~~~~~~~~~~~~~~~~~~
      + CategoryInfo          : MetadataError: (:) [Rename-Item],
        ParameterBindingException
      + FullyQualifiedErrorId : ScriptBlockArgumentNoInput,
        Microsoft.PowerShell.Commands.RenameItemCommand
  ```

## <a name="see-also"></a>Consulte Também

[about_Functions](about_Functions.md)

[about_Functions_Advanced](about_Functions_Advanced.md)

[about_Operators](about_Operators.md)
