---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Transaction
ms.openlocfilehash: bb8e9e1f204c67207f31613181f856d3bcaf8dc3
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2020
ms.locfileid: "93192592"
---
# Get-Transaction

## SINOPSE
Obtém a transação atual (ativa).

## SYNTAX

```
Get-Transaction [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Get-Transaction** Obtém um objeto que representa a transação atual na sessão.

Esse cmdlet nunca retorna mais de um objeto, porque somente uma transação está ativa por vez.
Se você iniciar uma ou mais transações independentes (usando o parâmetro independente de Start-Transaction), a transação iniciada mais recentemente estará ativa e essa será a transação que o **Get-Transaction** retornará.

Quando todas as transações ativas tiverem sido revertidas ou confirmadas, esse cmdlet mostrará a transação que foi ativada mais recentemente na sessão.

Esse cmdlet é um de um conjunto de cmdlets que dão suporte ao recurso de transações no Windows PowerShell.
Para obter mais informações, consulte about_Transactions.

## EXEMPLOS

### Exemplo 1: obter a transação atual

```
PS C:\> Start-Transaction
PS C:\> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

Esse comando usa o cmdlet Get-Transaction para obter a transação atual.

### Exemplo 2: mostrar as propriedades e os métodos do objeto de transação

```
PS C:\> Get-Transaction | Get-Member

Name               MemberType Definition
----               ---------- ----------
Dispose            Method     System.Void Dispose(), System.Void Dispose(Boolean disposing)
Equals             Method     System.Boolean Equals(Object obj)
GetHashCode        Method     System.Int32 GetHashCode()
GetType            Method     System.Type GetType()
ToString           Method     System.String ToString()
IsCommitted        Property   System.Boolean IsCommitted {get;}
IsRolledBack       Property   System.Boolean IsRolledBack {get;}
RollbackPreference Property   System.Management.Automation.RollbackSeverity RollbackPreference {get;}
SubscriberCount    Property   System.Int32 SubscriberCount {get;set;}
```

Esse comando usa o cmdlet Get-Member para mostrar as propriedades e métodos do objeto de transação.

### Exemplo 3: mostrar os valores de propriedade de uma transação revertida

```
PS C:\> cd hklm:\software
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany -UseTransaction
HKLM:\SOFTWARE> Undo-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ----------
Error                0                 RolledBack
```

Esse comando mostra os valores de propriedade de um objeto de transação para uma transação que foi revertida.

### Exemplo 4: mostrar os valores de propriedade de uma transação confirmada

```
PS C:\> cd hklm:\software
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany -UseTransaction
HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ---------
Error                1                 Committed
```

Esse comando mostra os valores de propriedade de um objeto de transação para uma transação que foi confirmada.

### Exemplo 5: iniciar uma transação enquanto outra estiver em andamento

```
PS C:\> cd hklm:\software
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany -UseTransaction
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany2 -UseTransaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                2                 Active

HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active

HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ---------
Error                1                 Committed
```

Este exemplo mostra o efeito sobre o objeto de transação de iniciar uma transação enquanto outra transação está em andamento.
Normalmente, isso ocorre quando um script que executa uma transação inclui uma função ou chama um script que contém outra transação completa.

A menos que o segundo comando **Start-Transaction** inclua o parâmetro *independente* , **Start-Transaction** não criará uma nova transação.
Em vez disso, ele adiciona um segundo assinante à transação original.

O primeiro comando **Start-Transaction** inicia a transação.
Um comando New-Item com o parâmetro *UseTransaction* é parte da transação.

Um segundo comando **Start-Transaction** adiciona um assinante à transação.
O comando New-Item seguinte também faz parte da transação.

O primeiro comando **Get-Transaction** mostra a transação de vários assinantes.
Observe que a contagem de assinantes é 2.

O primeiro comando Complete-Transaction não confirma a transação, mas reduz a contagem de assinantes para 1.

O segundo comando **Complete-Transaction** confirma a transação.

### Exemplo 6: iniciar uma transação independente enquanto outra estiver em andamento

```
PS C:\>
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   IsRolledBack   IsCommitted
------------------   ---------------   ------------   -----------
Error                1                 False          False

HKLM:\SOFTWARE> Start-Transaction -Independent
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   IsRolledBack   IsCommitted
------------------   ---------------   ------------   -----------
Error                1                 False          False

HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction
HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction
```

Este exemplo mostra o efeito sobre o objeto de transação de iniciar uma transação independente enquanto outra transação está em andamento.

O primeiro comando **Start-Transaction** inicia a transação.
Um comando **New-Item** com o parâmetro *UseTransaction* é parte da transação.

Um segundo comando **Start-Transaction** adiciona um assinante à transação.
O próximo comando **New-Item** também faz parte da transação.

O primeiro comando **Get-Transaction** mostra a transação de vários assinantes.
Observe que a contagem de assinantes é 2.

O comando **Complete-Transaction** reduz a contagem de assinantes para 1, mas não confirma a transação.

O segundo comando **Complete-Transaction** confirma a transação.

## PARAMETERS

### CommonParameters
Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum
Não é possível transferir objetos para esse cmdlet.

## SAÍDAS

### System. Management. Automation. PSTransaction
Esse cmdlet retorna um objeto que representa a transação atual.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Complete-Transaction](Complete-Transaction.md)

[Start-Transaction](Start-Transaction.md)

[Undo-Transaction](Undo-Transaction.md)

[Use-Transaction](Use-Transaction.md)

[New-Item](New-Item.md)
