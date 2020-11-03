---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/undo-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Undo-Transaction
ms.openlocfilehash: 1acb06ea7b05a2127b04a22c4c51b92cd68056f2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193901"
---
# Undo-Transaction

## SINOPSE
Reverte a transação ativa.

## SYNTAX

```
Undo-Transaction [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Undo-Transaction** reverte a transação ativa.
Quando você reverte uma transação, as alterações feitas pelos comandos na transação são descartadas e os dados são restaurados para seu formato original.

Se a transação incluir vários assinantes, um comando **Undo-Transaction** reverterá toda a transação para todos os assinantes.

Por padrão, as transações serão revertidas automaticamente se qualquer comando na transação gerar um erro.
No entanto, as transações podem ser iniciadas usando uma preferência de reversão diferente e você pode usar esse cmdlet para reverter a transação ativa a qualquer momento.

O cmdlet **Undo-Transaction** é um de um conjunto de cmdlets que dão suporte ao recurso de transações no Windows PowerShell.
Para obter mais informações, consulte about_Transactions.

## EXEMPLOS

### Exemplo 1: reverter a transação atual

```
PS C:\> Undo-Transaction
```

Esse comando reverte a transação atual, ativa.

### Exemplo 2: Iniciar e reverter uma transação

```
PS C:\> cd hkcu:\software
PS HKCU:\Software> Start-Transaction
PS HKCU:\Software> New-Item -Path "ContosoCompany" -UseTransaction
PS HKCU:\Software> Undo-Transaction
```

Este exemplo inicia uma transação e a reverte novamente.
Como resultado, nenhuma alteração é feita no registro.

### Exemplo 3: reverter uma transação para todos os assinantes

```
PS C:\> cd hkcu:\software
PS HKCU:\Software> Start-Transaction
PS HKCU:\Software> New-Item -Path "ContosoCompany" -UseTransaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----
Error                1                 Active

PS HKCU:\Software> Start-Transaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----
Error                2                 Active

PS HKCU:\Software> Undo-Transaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----
Error                0                 RolledBack
```

Este exemplo demonstra que quando qualquer assinante reverte uma transação, toda a transação é revertida para todos os assinantes.

O primeiro comando altera o local para a chave de registro HKCU:\Software.

O segundo comando inicia uma transação.

O terceiro comando usa o cmdlet New-Item para criar uma nova chave do registro.
O comando usa o parâmetro *UseTransaction* para incluir a alteração na transação.

O quarto comando usa o cmdlet Get-Transaction para obter a transação ativa.
Observe que o status está ativo e que a contagem de assinante é 1.

O quinto comando usa o comando Start-Transaction novamente.
Normalmente, iniciar uma transação enquanto outra transação está em andamento ocorre quando um script usado pela transação principal inclui sua própria transação completa.
Este exemplo é executado interativamente para que você possa examiná-lo em estágios.
Quando você executa um comando **Start-Transaction** enquanto outra transação está em andamento, os comandos se unem à transação existente como um novo assinante e a contagem de assinantes é incrementada.

O sexto comando usa o cmdlet **Get-Transaction** para obter a transação ativa.
Observe que a contagem de assinante agora é 2.

O sétimo comando usa **desfazer-transação** para reverter a transação.
Este cmdlet não retorna nenhum objeto.

O comando final é um comando **Get-Transaction** que obtém o ativo, ou nesse caso, a transação ativa mais recentemente.
Os resultados mostram que a transação é revertida e a contagem de assinante é 0, mostrando que a transação foi revertida para todos os assinantes.

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
Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### Nenhum
Este cmdlet não retorna nenhuma saída.

## OBSERVAÇÕES

* Você não pode reverter uma transação que foi confirmada.

  Você não pode reverter uma transação que não seja a transação ativa.
Para reverter uma transação diferente e independente, primeiro você deve confirmar ou reverter a transação ativa.

  Reverter a transação termina a transação.
Para usar uma transação novamente, você deve iniciar uma nova transação.

## LINKS RELACIONADOS

[Complete-Transaction](Complete-Transaction.md)

[Get-Transaction](Get-Transaction.md)

[Start-Transaction](Start-Transaction.md)

[Use-Transaction](Use-Transaction.md)
