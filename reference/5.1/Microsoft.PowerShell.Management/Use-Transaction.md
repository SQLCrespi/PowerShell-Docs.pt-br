---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/use-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Use-Transaction
ms.openlocfilehash: db8423aef6dc4b25c4ddd13f9b29b774463c6a6c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193905"
---
# Use-Transaction

## SINOPSE
Adiciona o bloco de script à transação ativa.

## SYNTAX

```
Use-Transaction [-TransactedScript] <ScriptBlock> [-UseTransaction] [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Use-Transaction** adiciona um bloco de script a uma transação ativa.
Isso permite que você faça scripts transacionados usando objetos da estrutura de Microsoft .NET habilitados para transação.
O bloco de script pode conter somente objetos de transações habilitadas do .NET Framework., como instâncias da classe Microsoft.PowerShell.Commands.Management.TransactedString.

O parâmetro *UseTransaction* , que é opcional para a maioria dos cmdlets, é necessário quando você usa esse cmdlet.

**Use-Transaction** é um de um conjunto de cmdlets que dão suporte ao recurso de transações no Windows PowerShell.
Para obter mais informações, consulte about_Transactions.

## EXEMPLOS

### Exemplo 1: script usando um objeto habilitado para transação

```
PS C:\> Start-Transaction
PS C:\> $transactedString = New-Object Microsoft.PowerShell.Commands.Management.TransactedString
PS C:\> $transactedString.Append("Hello")
PS C:\> Use-Transaction -TransactedScript { $transactedString.Append(", World") } -UseTransaction
PS C:\> $transactedString.ToString()
Hello
PS C:\> Use-Transaction -TransactedScript { $transactedString.ToString() } -UseTransaction
Hello, World
PS C:\> Complete-Transaction
PS C:\> $transactedString.ToString()
Hello, World
```

Este exemplo mostra como usar o **Use-Transaction** para script em relação a um objeto de .NET Framework habilitado para transação.
Nesse caso, o objeto é um objeto **transacionated** .

O primeiro comando utiliza o cmdlet Start-Transaction para iniciar uma transação.

O segundo comando usa o comando New-Object para criar um objeto **transacionated** .
Ele armazena o objeto na variável $TransactedString.

O terceiro e o quarto comandos usam o método **Append** do objeto **transacionastring** para adicionar texto ao valor de $TransactedString.
Um comando faz parte da transação.
O outro comando não é.

O terceiro comando usa o método **Append** da cadeia de caracteres transacionada para adicionar Hello ao valor de $TransactedString.
Como o comando não é parte da transação, a alteração será aplicada imediatamente.

O quarto comando usa **Use-Transaction** para adicionar texto à cadeia de caracteres na transação.
O comando usa o método **Append** para adicionar ", World" ao valor de $TransactedString.
O comando é colocado entre chaves ( {} ) para torná-lo um bloco de script.
O parâmetro *UseTransaction* é necessário neste comando.

O quinto e o sexto comandos usam o método **ToString** do objeto **transacionastring** para exibir o valor de **transacionated** como uma cadeia de caracteres.
Novamente, um comando faz parte da transação.
A outra transação não é.

O quinto comando usa o método **ToString** para exibir o valor atual da variável $TransactedString.
Por não fazer parte da transação, ele exibe apenas o estado atual da cadeia de caracteres.

O sexto comando usa **Use-Transaction** para executar o mesmo comando na transação.
Como o comando faz parte da transação, ele exibe o valor atual da cadeia de caracteres na transação, assim como uma visualização das alterações de transação.

O sétimo comando utiliza o cmdlet Complete-Transaction para confirmar a transação.

O comando final usa o método **ToString** para exibir o valor resultante da variável como uma cadeia de caracteres.

### Exemplo 2: reverter uma transação

```
PS C:\> Start-Transaction
PS C:\> $transactedString = New-Object Microsoft.PowerShell.Commands.Management.TransactedString
PS C:\> $transactedString.Append("Hello")
PS C:\> Use-Transaction -TransactedScript { $transactedString.Append(", World") } -UseTransaction
PS C:\> Undo-Transaction
PS C:\> $transactedString.ToString()
Hello
```

Este exemplo mostra o efeito de reverter uma transação que inclui comandos **de transação de uso** .
Como todos os comandos em uma transação, quando a transação for revertida, as alterações realizadas são descartadas e os dados não são alterados.

O primeiro comando usa **Start-Transaction** para iniciar uma transação.

O segundo comando usa **New-Object** para criar um objeto **transacionated** .
Ele armazena o objeto na variável $TransactedString.

O terceiro comando, que não faz parte da transação, usa o método **Append** para adicionar "Hello" ao valor de $TransactedString.

O quarto comando usa **Use-Transaction** para executar outro comando que usa o método **Append** na transação.
O comando usa o método **Append** para adicionar ", World" ao valor de $TransactedString.

O quinto comando utiliza o cmdlet Undo-Transaction para reverter a transação.
Como resultado, todos os comandos executados na transação são revertidos.

O comando final usa o método **ToString** para exibir o valor resultante de $TransactedString como uma cadeia de caracteres.
Os resultados mostram que apenas as alterações feitas fora da transação foram aplicadas ao objeto.

## PARAMETERS

### -TransactedScript
Especifica o bloco de script que é executado na transação.
Insira qualquer bloco de script válido entre chaves ({}).
Este parâmetro é necessário.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseTransaction
Inclui o comando na transação ativa.
Este parâmetro é válido somente quando uma transação está em andamento.
Para obter mais informações, consulte about_transactions.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum
Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### PSObject
Esse cmdlet retorna o resultado da transação.

## OBSERVAÇÕES

* O parâmetro *UseTransaction* inclui o comando na transação ativa. Como o cmdlet **Use-Transaction** é sempre usado em transações, esse parâmetro é necessário para fazer com que qualquer comando **Use-Transaction** seja efetivo.

*

## LINKS RELACIONADOS

[Complete-Transaction](Complete-Transaction.md)

[Get-Transaction](Get-Transaction.md)

[Start-Transaction](Start-Transaction.md)

[Undo-Transaction](Undo-Transaction.md)
