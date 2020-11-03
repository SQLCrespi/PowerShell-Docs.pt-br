---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-expression?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Expression
ms.openlocfilehash: f915a5741ed5c63206da3c35f5322508515bd566
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193556"
---
# Invoke-Expression

## SINOPSE
Executa comandos ou expressões no computador local.

## SYNTAX

```
Invoke-Expression [-Command] <String> [<CommonParameters>]
```

## DESCRIPTION

O `Invoke-Expression` cmdlet avalia ou executa uma cadeia de caracteres especificada como um comando e retorna os resultados da expressão ou do comando. Sem `Invoke-Expression` , uma cadeia de caracteres enviada na linha de comando é retornada (ecoada) inalterada.

As expressões são avaliadas e executadas no escopo atual. Para obter mais informações, consulte [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).

> [!CAUTION]
> Tome precauções razoáveis ao usar o `Invoke-Expression` cmdlet em scripts. Ao usar `Invoke-Expression` o para executar um comando que o usuário insere, verifique se o comando é seguro para ser executado antes de executá-lo. Em geral, é melhor criar seu script com opções predefinidas de entrada, em vez de permitir a entrada de forma livre.

## EXEMPLOS

### Exemplo 1: avaliar uma expressão

```powershell
$Command = "Get-Process"
$Command
```

```Output
Get-Process
```

```powershell
Invoke-Expression $Command
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id   ProcessName
-------  ------    -----      ----- -----   ------     --   -----------
296       4       1572       1956    20       0.53     1348   AdtAgent
270       6       1328       800     34       0.06     2396   alg
67        2       620        484     20       0.22     716    ati2evxx
1060      15      12904      11840   74       11.48    892    CcmExec
1400      33      25280      37544   223      38.44    2564   communicator
...
```

Este exemplo demonstra o uso de `Invoke-Expression` para avaliar uma expressão. Sem `Invoke-Expression` , a expressão é impressa, mas não avaliada.

O primeiro comando atribui um valor de `Get-Process` (uma cadeia de caracteres) à `$Command` variável.

O segundo comando mostra o efeito de digitar o nome da variável na linha de comando. O PowerShell ecoa a cadeia de caracteres.

O terceiro comando usa `Invoke-Expression` para avaliar a cadeia de caracteres.

### Exemplo 2: executar um script no computador local

```powershell
Invoke-Expression -Command "C:\ps-test\testscript.ps1"
"C:\ps-test\testscript.ps1" | Invoke-Expression
```

Esses comandos usam `Invoke-Expression` para executar um script, TestScript.ps1, no computador local. Os dois comandos são equivalentes. O primeiro usa o parâmetro **Command** para especificar o comando a ser executado.
O segundo usa um operador de pipeline ( `|` ) para enviar a cadeia de caracteres de comando para `Invoke-Expression` .

### Exemplo 3: executar um comando em uma variável

```powershell
$Command = 'Get-Process | where {$_.cpu -gt 1000}'
Invoke-Expression $Command
```

Este exemplo executa uma cadeia de caracteres de comando que é salva na `$Command` variável.

A cadeia de caracteres de comando é colocada entre aspas simples porque inclui uma variável, `$_` , que representa o objeto atual. Se ele fosse colocado entre aspas duplas, a `$_` variável seria substituída por seu valor antes de ser salva na `$Command` variável.

### Exemplo 4: obter e executar um exemplo de ajuda de cmdlet

```powershell
$Cmdlet_name = "Get-EventLog"
$Example_number = 1
$Example_code = (Get-Help $Cmdlet_name).examples.example[($Example_number-1)].code
Invoke-Expression $Example_code
```

Esse comando recupera e executa o primeiro exemplo no `Get-EventLog` tópico de ajuda do cmdlet.

Para executar um exemplo de um cmdlet diferente, altere o valor da `$Cmdlet_name` variável para o nome do cmdlet. E altere a `$Example_number` variável para o número de exemplo que você deseja executar. O comando falhará se o número de exemplo não for válido.

## PARAMETERS

### -Command

Especifica o comando ou expressão a executar. Digite o comando ou expressão ou insira uma variável que contenha o comando ou expressão. O parâmetro **Command** é obrigatório.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### System. String ou PSObject

É possível canalizar um objeto que representa o comando para `Invoke-Expression` .
Use a `$Input` variável automática para representar os objetos de entrada no comando.

## SAÍDAS

### PSObject

Retorna a saída gerada pelo comando invocado (o valor do parâmetro de **comando** ).

## OBSERVAÇÕES

Na maioria dos casos, você invoca expressões usando o operador de chamada do PowerShell e obtém os mesmos resultados.
O operador de chamada é um método mais seguro. Para obter mais informações, consulte [about_Operators](../microsoft.powershell.core/about/about_operators.md#call-operator-).

## LINKS RELACIONADOS

[Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)

[about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md)

