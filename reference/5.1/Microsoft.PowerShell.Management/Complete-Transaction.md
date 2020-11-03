---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/complete-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Complete-Transaction
ms.openlocfilehash: 20fbdd86aab07dda065492eff2da4f358fb2ffca
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194205"
---
# Complete-Transaction

## SINOPSE
Confirma a transação ativa.

## SYNTAX

```
Complete-Transaction [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Complete-Transaction** confirma uma transação ativa.
Quando você confirma uma transação, os comandos nessa transação são finalizados e os dados afetados pelos comandos são alterados.

Se a transação incluir vários assinantes, para confirmar a transação, você deverá inserir um comando de **transação de conclusão** para cada comando de Start-Transaction.

O cmdlet **Complete-Transaction** é um de um conjunto de cmdlets que dão suporte ao recurso de transações no Windows PowerShell.
Para obter mais informações, consulte about_Transactions.

## EXEMPLOS

### Exemplo 1: confirmar uma transação

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item MyCompany -UseTransaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}

PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}
0   0 MyCompany                      {}
```

Este exemplo mostra o que acontece quando você usa o cmdlet **Complete-Transaction** para confirmar uma transação.

O comando **Start-Transaction** inicia a transação.
O comando New-Item usa o parâmetro *UseTransaction* para incluir o comando na transação.

O primeiro comando dir (Get-ChildItem) mostra que o novo item ainda não foi adicionado ao registro.

O comando **Complete-Transaction** confirma a transação, o que torna a alteração do registro efetiva.
Como resultado, o segundo comando dir mostra que o registro foi alterado.

### Exemplo 2: confirmar uma transação que tem mais de um assinante

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item MyCompany -UseTransaction
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
0   0 MyCompany                      {}

PS HKCU:\software> Start-Transaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount  Status
------------------   ---------------  ------
Error                2                Active

PS HKCU:\software> New-ItemProperty -Path MyCompany -Name MyKey -Value -UseTransaction

MyKey
-----
123

PS HKCU:\software> Complete-Transaction
PS HKCU:\software> Get-Transaction

RollbackPreference   SubscriberCount  Status
------------------   ---------------  ------
Error                1                Active

PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}

PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}
0   1 MyCompany                      {MyKey}
```

Este exemplo mostra como usar a **transação completa** para confirmar uma transação que tem mais de um assinante.

Para confirmar uma transação de vários assinantes, você deve inserir um comando **Complete-Transaction** para cada comando **Start-Transaction** .
Os dados são alterados somente quando o comando **Complete-Transaction** final é enviado.

Para fins de demonstração, este exemplo mostra uma série de comandos inseridos na linha de comando.
Na prática, transações provavelmente serão executadas em scripts, com a transação secundária sendo executada por uma função ou script auxiliar que é chamado pelo script principal.

Neste exemplo, um comando **Start-Transaction** inicia a transação.
Um comando **New-Item** com o parâmetro *UseTransaction* adiciona a chave MyCompany à chave de software.
Embora o cmdlet **New-Item** retorne um objeto de chave, os dados no registro ainda não foram alterados.

Um segundo comando **Start-Transaction** adiciona um segundo assinante à transação existente.
O cmdlet **Get-Transaction** confirma que a contagem de assinantes é 2.
Um comando New-ItemProperty com o parâmetro *UseTransaction* adiciona uma entrada de registro à nova chave MyCompany.
Novamente, o comando retorna um valor, mas o registro não é alterado.

O primeiro comando **Complete-Transaction** reduz a contagem de assinantes em 1.
Isso é confirmado por um comando **Get-Transaction** .
No entanto, nenhum dado é alterado, conforme evidenciado por um comando dir m * ( **Get-ChildItem** ).

O segundo comando **Complete-Transaction** confirma a transação inteira e altera os dados no registro.
Isso é confirmado por um segundo comando dir m *, que mostra as alterações.

### Exemplo 3: executar uma transação que não altera nenhum dado

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item MyCompany -UseTransaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}

PS HKCU:\software> dir m* -UseTransaction
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}
0   0 MyCompany                      {}

PS HKCU:\software> Complete-Transaction
```

Este exemplo mostra o valor do uso de get- \* Commands e outros comandos que não alteram dados, em uma transação.
Quando um get- \* Command é usado em uma transação, ele obtém os objetos que fazem parte da transação.
Isso permite a você visualizar as alterações na transação antes de confirmá-las.

Neste exemplo, uma transação é iniciada.
Um comando New-Item com o parâmetro *UseTransaction* adiciona uma nova chave ao registro como parte da transação.

Como a nova chave do registro não é adicionada ao registro até que o comando **Complete-Transaction** seja executado, um comando dir ( **Get-ChildItem** ) simples mostra o registro sem a nova chave.

No entanto, quando você adiciona o parâmetro *UseTransaction* ao comando dir, o comando se torna parte da transação e obtém os itens na transação, mesmo que eles ainda não tenham sido adicionados aos dados.

## PARAMETERS

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
Mostra o que aconteceria se o cmdlet fosse executado.
O cmdlet não é executado.

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

## ENTRADAS

### Nenhum
Não é possível transferir objetos para esse cmdlet.

## SAÍDAS

### Nenhum
Este cmdlet não gera saída.

## OBSERVAÇÕES

* Você não pode reverter uma transação que foi confirmada, nem confirmar uma transação que foi revertida.

  Você não pode reverter uma transação que não seja a transação ativa.
Para reverter uma transação diferente, primeiro você deve confirmar ou reverter a transação ativa.

  Por padrão, se qualquer parte de uma transação não pode ser confirmada, como por exemplo quando um comando na transação resulta em um erro, a transação inteira é revertida.

*

## LINKS RELACIONADOS

[Get-Transaction](Get-Transaction.md)

[Start-Transaction](Start-Transaction.md)

[Undo-Transaction](Undo-Transaction.md)

[Use-Transaction](Use-Transaction.md)

[Get-ChildItem](Get-ChildItem.md)

[New-Item](New-Item.md)

[New-ItemProperty](New-ItemProperty.md)
