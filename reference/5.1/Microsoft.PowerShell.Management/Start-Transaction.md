---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Transaction
ms.openlocfilehash: 53be131f45f15e5d2053b183040dc7b3dca4a14c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193914"
---
# Start-Transaction

## SINOPSE
Inicia uma transação.

## SYNTAX

```
Start-Transaction [-Timeout <Int32>] [-Independent] [-RollbackPreference <RollbackSeverity>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Start-Transaction** inicia uma transação, que é uma série de comandos que são gerenciados como uma unidade.
Uma transação pode ser concluída ou confirmada.
Como alternativa, ele pode ser completamente desfeito ou revertido para que todos os dados alterados pela transação sejam restaurados para seu estado original.
Como os comandos em uma transação são gerenciados como uma unidade, todos os comandos são confirmados ou então revertidos.

Por padrão, se qualquer comando na transação gerar um erro, as transações serão revertidas automaticamente.
Você pode usar o parâmetro *RollbackPreference* para alterar esse comportamento.

Os cmdlets usados em uma transação devem ser criados para oferecer suporte a transações.
Os cmdlets que dão suporte a transações têm um parâmetro *UseTransaction* .
Para realizar transações em um provedor, este provedor deve oferecer suporte a transações.
O provedor de registro do Windows PowerShell no Windows Vista e versões posteriores do sistema operacional Windows dão suporte a transações.
Você também pode usar a classe **Microsoft. PowerShell. Commands. Management.** transactionstring para incluir expressões em transações em qualquer versão do sistema Windows que ofereça suporte ao Windows PowerShell.
Outros provedores do Windows PowerShell também podem oferecer suporte a transações.

Somente uma transação pode estar ativa por vez.
Se você iniciar uma nova transação independente enquanto uma transação estiver em andamento, a nova transação se tornará a transação ativa e você deverá confirmar ou reverter a nova transação antes de fazer qualquer alteração na transação original.

O cmdlet **Start-Transaction** é um de um conjunto de cmdlets que dão suporte ao recurso de transações no Windows PowerShell.
Para obter mais informações, consulte about_Transactions.

## EXEMPLOS

### Exemplo 1: Iniciar e reverter uma transação

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> New-ItemProperty "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
PS HKCU:\software> Undo-Transaction
```

Estes comandos iniciam uma transação e em seguida a revertem.
Como a transação é revertida, nenhuma alteração é feita ao registro.

### Exemplo 2: Iniciar e concluir uma transação

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> New-ItemProperty "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
PS HKCU:\software> Complete-Transaction
```

Estes comandos iniciam uma transação e em seguida a concluem.
Nenhuma alteração é feita no registro até que o comando **Complete-Transaction** seja usado.

### Exemplo 3: usar preferências de reversão diferentes

```
PS C:\> cd HKCU:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> New-Item -Path . -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> Start-Transaction -RollbackPreference never
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> New-Item -Path . -Name "ContosoCompany" -UseTransaction

# Start-Transaction (-rollbackpreference error)

PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction
New-Item : The registry key at the specified path does not exist.
At line:1 char:9
+ new-item <<<<  -Path NoPath -Name ContosoCompany -UseTransaction

PS HKCU:\software> New-Item -Path . -Name "Contoso" -UseTransaction

New-Item : Cannot use transaction. The transaction has been rolled back or has timed out.
At line:1 char:9
+ new-item <<<<  -Path . -Name ContosoCompany -UseTransaction

# Start-Transaction (-rollbackpreference never)

PS HKCU:\software> Start-Transaction -RollbackPreference never
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction

New-Item : The registry key at the specified path does not exist.
At line:1 char:9
+ new-item <<<<  -Path NoPath -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> New-Item -Path . -Name "ContosoCompany" -UseTransaction

Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   0 ContosoCompany                 {}
PS HKCU:\Software> Complete-Transaction

# Succeeds
```

Este exemplo demonstra o efeito de alterar o valor do parâmetro *RollbackPreference* .

No primeiro conjunto de comandos, **Start-Transaction** não usa *RollbackPreference* .
Como resultado, o valor padrão (erro) é usado.
Quando ocorre um erro em um comando de transação, ou seja, o caminho especificado não existe, a transação é revertida automaticamente.

No segundo conjunto de comandos, **Start-Transaction** usa *RollbackPreference* com um valor de nunca.
Como resultado, quando ocorre um erro em um comando de transação, a transação ainda está ativa e pode ser concluída com êxito.

Como a maioria das transações deve ser executada sem erros, o valor padrão de *RollbackPreference* normalmente é preferencial.

### Exemplo 4: usar este cmdlet enquanto uma transação estiver em andamento

```
PS C:\> cd HKCU:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> Start-Transaction
PS HKCU:\software> Get-Transaction
PS HKCU:\software> New-Item "ContosoCompany2" -UseTransaction
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> Complete-Transaction
PS HKCU:\Software> Get-Transaction
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                2                 Active
```

Este exemplo mostra o efeito de usar **Start-Transaction** enquanto uma transação está em andamento.
O efeito é semelhante ao de uma união à transação em andamento.

Embora esse seja um comando simplificado, esse cenário ocorre com frequência quando a transação envolve a execução de um script que inclui uma transação completa.

O primeiro comando **Start-Transaction** inicia a transação.
O primeiro comando **New-Item** faz parte da transação.

O segundo comando **Start-Transaction** adiciona um novo assinante à transação.
O comando **Get-Transaction** agora retorna uma transação com uma contagem de assinantes de 2.
O segundo comando **New-Item** faz parte da mesma transação.

Nenhuma alteração é feita no registro até que toda a transação seja concluída.
Para concluir a transação, você deve inserir dois comandos de **transação completa** , um para cada Assinante.
Se você reverter a transação a qualquer momento, toda a transação seria revertida para ambos os assinantes.

### Exemplo 5: iniciar uma transação independente enquanto uma estiver em andamento

```
PS C:\> cd HKCU:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> Start-Transaction -Independent
PS HKCU:\software> Get-Transaction
PS HKCU:\software> Undo-Transaction
PS HKCU:\software> New-ItemProperty -Path "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir contoso*
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
PS HKCU:\software> Undo-Transaction
PS HKCU:\software> New-ItemProperty -Path "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
MyKey
-----
123
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir contoso*
Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   1 MyCompany                      {MyKey}
```

Este exemplo mostra o efeito de usar o parâmetro *independente* de **Start-Transaction** para iniciar uma transação enquanto outra transação está em andamento.
Neste caso, a nova transação é revertida sem afetar a transação original.

Apesar de as transações serem logicamente independentes, porque somente uma transação pode ficar ativa por vez, você deve reverter ou confirmar a transação mais recente antes de continuar a trabalhar na transação original.

O primeiro conjunto de comandos inicia uma transação.
O comando **New-Item** faz parte da primeira transação.

No segundo conjunto de comandos, o comando **Start-Transaction** usa o parâmetro *independente* .
O comando **Get-Transaction** que segue mostra o objeto de transação para a transação ativa, que é a mais recente.
A contagem de assinantes é igual a 1, que mostra que as transações não estão relacionadas.

Quando a transação ativa é revertida usando um comando **Undo-Transaction** , a transação original torna-se ativa novamente.

O comando **New-ItemProperty** , que faz parte da transação original, termina sem erro e a transação original pode ser concluída usando o comando **Complete-Transaction** .
Como resultado, o registro é alterado.

### Exemplo 6: executar comandos que não fazem parte de uma transação

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany1" -UseTransaction
PS HKCU:\software> New-Item "ContosoCompany2"
PS HKCU:\software> New-Item "ContosoCompany3" -UseTransaction
PS HKCU:\software> dir contoso*
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir contoso*
PS HKCU:\Software> dir contoso*

Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   0 ContosoCompany2                {}

PS HKCU:\Software> Complete-Transaction
PS HKCU:\Software> dir contoso*

Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   0 ContosoCompany1                     {}
0   0 ContosoCompany2                     {}
0   0 ContosoCompany3                     {}
```

Este exemplo demonstra que comandos enviados enquanto uma transação está em andamento podem ser incluídos na transação ou podem não ser incluídos.
Somente os comandos que usam o parâmetro *UseTransaction* fazem parte da transação.

O primeiro e terceiro comandos **New-Item** usam o parâmetro *UseTransaction* .
Estes comandos fazem parte da transação.
Como o segundo comando **New-Item** não usa o parâmetro *UseTransaction* , ele não faz parte da transação.

O primeiro comando dir mostra o efeito.
O segundo comando **New-Item** é concluído imediatamente, mas o primeiro e terceiro comandos **New-Item** não são efetivos até que a transação seja confirmada.

O comando **Complete-Transaction** confirma a transação.
Como resultado, o segundo comando dir mostra que todos os novos itens são adicionados ao registro.

### Exemplo 7: reverter uma transação que não é concluída em um tempo especificado

```
PS C:\> Start-Transaction -Timeout 2

# Wait two minutes...

PS C:\> Get-Transaction
PS C:\> New-Item HKCU:\Software\ContosoCompany -UseTransaction
PS C:\> Start-Transaction -Timeout 2

# Wait two minutes...

PS C:\> > Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----------
Error                1                 RolledBack

PS C:\> New-Item HKCU:\Software\ContosoCompany -UseTransaction

New-Item : Cannot use transaction. The transaction has been rolled back or has timed out.
At line:1 char:9
+ new-item <<<<  MyCompany -UseTransaction
```

Esse comando usa o parâmetro *Timeout* de **Start-Transaction** para iniciar uma transação que deve ser concluída dentro de dois minutos.
Se a transação não for concluída quando o tempo limite expirar, ela será revertida automaticamente.

Quando o tempo limite expirar, você não será notificado, mas a propriedade **status** do objeto de transação será definida como revertida e os comandos que usam o parâmetro *UseTransaction* falharão.

## PARAMETERS

### -Independente
Indica que esse cmdlet inicia uma transação que é independente de qualquer transação em andamento.
Por padrão, se você usar **Start-Transaction** enquanto outra transação estiver em andamento, um novo assinante será adicionado à transação em andamento.
Este parâmetro tem efeito somente quando já existe uma transação em andamento na sessão.

Por padrão, se você usar **Start-Transaction** enquanto uma transação estiver em andamento, o objeto de transação existente será reutilizado e a contagem de assinantes será incrementada.
O efeito é semelhante ao de uma união à transação original.
Um comando Undo-Transaction reverte toda a transação.
Para concluir a transação, você deve inserir um comando Complete-Transaction para cada assinante.
Como a maioria das transações que estão em andamento simultaneamente são relacionadas, o padrão é suficiente para a maior parte dos usos.

Se você especificar o parâmetro *independente* , esse cmdlet criará uma nova transação que pode ser concluída ou desfeita sem afetar a transação original.
No entanto, como somente uma transação pode estar ativa por vez, você deve concluir ou reverter a nova transação antes de continuar a trabalhar com a transação original.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RollbackPreference
Especifica as condições sob as quais uma transação é revertida automaticamente.
Os valores aceitáveis para esse parâmetro são:

- Erro.
A transação é revertida automaticamente se ocorrer um erro de finalização ou de não finalização.
- TerminatingError.
Se ocorrer um erro de finalização, a transação será revertida automaticamente.
- Nunca.
A transação nunca é revertida automaticamente.

O valor padrão é Error.

```yaml
Type: System.Management.Automation.RollbackSeverity
Parameter Sets: (All)
Aliases:
Accepted values: Error, TerminatingError, Never

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tempo limite
Especifica o tempo máximo, em minutos, pelo qual a transação fica ativa.
Quando o tempo limite expira, a transação é revertida automaticamente.

Por padrão, não há tempo limite para transações iniciadas pela linha de comando.
Quando as transações são iniciadas por um script, o tempo limite padrão é de 30 minutos.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutMins

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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
Este cmdlet não gera saída.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Complete-Transaction](Complete-Transaction.md)

[Get-Transaction](Get-Transaction.md)

[Undo-Transaction](Undo-Transaction.md)

[Use-Transaction](Use-Transaction.md)
