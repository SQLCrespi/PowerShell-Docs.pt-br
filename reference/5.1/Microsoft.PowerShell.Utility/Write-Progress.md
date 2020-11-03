---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-progress?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Progress
ms.openlocfilehash: 5a0c197387f67dae1830b6d9ebd4145e96383b39
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "93196411"
---
# Write-Progress

## SINOPSE
Exibe uma barra de progresso dentro de uma janela de comando do PowerShell.

## SYNTAX

```
Write-Progress [-Activity] <String> [[-Status] <String>] [[-Id] <Int32>] [-PercentComplete <Int32>]
 [-SecondsRemaining <Int32>] [-CurrentOperation <String>] [-ParentId <Int32>] [-Completed] [-SourceId <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION

O `Write-Progress` cmdlet exibe uma barra de progresso em uma janela de comando do PowerShell que descreve o status de um comando ou script em execução. Você pode selecionar os indicadores que a barra reflete e o texto que aparece acima e abaixo da barra de progresso.

## EXEMPLOS

### Exemplo 1: exibir o progresso de um loop for

```powershell
for ($i = 1; $i -le 100; $i++ )
{
    Write-Progress -Activity "Search in Progress" -Status "$i% Complete:" -PercentComplete $i;
}
```

Este comando exibe o progresso de um loop For que realiza a contagem de 1 a 100.

O `Write-Progress` cmdlet inclui um título de barra de status `Activity` , uma linha de status e a variável `$i` (o contador no loop for), que indica a conclusão relativa da tarefa.

### Exemplo 2: exibir o progresso de loops for aninhados

```powershell
for($I = 1; $I -lt 101; $I++ )
{
    Write-Progress -Activity Updating -Status 'Progress->' -PercentComplete $I -CurrentOperation OuterLoop
    for($j = 1; $j -lt 101; $j++ )
    {
        Write-Progress -Id 1 -Activity Updating -Status 'Progress' -PercentComplete $j -CurrentOperation InnerLoop
    }
}
```

```Output
Updating
Progress ->
 [ooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooo]
OuterLoop
Updating
Progress
 [oooooooooooooooooo                                                   ]
InnerLoop
```

Este exemplo exibe o progresso de dois loops aninhados For, cada um dos quais é representado por uma barra de progresso.

O `Write-Progress` comando da segunda barra de progresso inclui o parâmetro **ID** que o distingue da primeira barra de progresso.

Sem o parâmetro **ID** , as barras de progresso seriam sobrepostas umas às outras em vez de serem exibidas uma abaixo da outra.

### Exemplo 3: exibir o progresso ao procurar uma cadeia de caracteres

```powershell
# Use Get-EventLog to get the events in the System log and store them in the $Events variable.
$Events = Get-EventLog -LogName system
# Pipe the events to the ForEach-Object cmdlet.
$Events | ForEach-Object -Begin {
    # In the Begin block, use Clear-Host to clear the screen.
    Clear-Host
    # Set the $i counter variable to zero.
    $i = 0
    # Set the $out variable to a empty string.
    $out = ""
} -Process {
    # In the Process script block search the message property of each incoming object for "bios".
    if($_.message -like "*bios*")
    {
        # Append the matching message to the out variable.
        $out=$out + $_.Message
    }
    # Increment the $i counter variable which is used to create the progress bar.
    $i = $i+1
    # Use Write-Progress to output a progress bar.
    # The Activity and Status parameters create the first and second lines of the progress bar heading, respectively.
    Write-Progress -Activity "Searching Events" -Status "Progress:" -PercentComplete ($i/$Events.count*100)
} -End {
    # Display the matching messages using the out variable.
    $out
}
```

Este comando exibe o progresso de um comando para encontrar a cadeia de caracteres "bios" no log de eventos do sistema.

O valor do parâmetro **PercentComplete** é calculado dividindo-se o número de eventos que foram processados `$I` pelo número total de eventos recuperados `$Events.count` e, em seguida, multiplicando esse resultado por 100.

### Exemplo 4: exibir o progresso de cada nível de um processo aninhado

```powershell
foreach ( $i in 1..10 ) {
  Write-Progress -Id 0 "Step $i"
  foreach ( $j in 1..10 ) {
    Write-Progress -Id 1 -ParentId 0 "Step $i - Substep $j"
    foreach ( $k in 1..10 ) {
      Write-Progress -Id 2  -ParentId 1 "Step $i - Substep $j - iteration $k"; start-sleep -m 150
    }
  }
}
```

```Output
Step 1
     Processing
    Step 1 - Substep 2
         Processing
        Step 1 - Substep 2 - Iteration 3
             Processing
```

Neste exemplo, você pode usar o parâmetro **parentID** para ter uma saída recuada para mostrar relações pai/filho no andamento de cada etapa.

## PARAMETERS

### -Atividade

Especifica a primeira linha de texto no título acima da barra de status.
Esse texto descreve a atividade cujo progresso está sendo relatado.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Concluído

Indica se a barra de progresso está visível.
Se esse parâmetro for omitido, `Write-Progress` exibirá informações de progresso.

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

### -CurrentOperation

Especifica a linha de texto abaixo da barra de progresso.
Esse texto descreve a operação que está ocorrendo no momento.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Especifica um identificador que distingue cada barra de progresso das demais. Use este parâmetro quando você estiver criando mais de uma barra de progresso em um único comando. Se as barras de progresso não possuem identificadores diferentes, elas são sobrepostas em vez de exibidas em série.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParentId

Especifica a atividade pai da atividade atual.
Use o valor -1 se a atividade atual não tem nenhuma atividade pai.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PercentComplete

Especifica a porcentagem concluída de uma determinada atividade.
Use o valor -1 se a porcentagem concluída é desconhecida ou não aplicável.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecondsRemaining

Especifica o número previsto de segundos restantes até que a atividade seja concluída.
Use o valor -1 se o número de segundos restantes é desconhecido ou não aplicável.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceID

Especifica a origem do registro. Você pode usar isso no lugar da **ID** , mas não pode ser usado com outros parâmetros como **parentID** .

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Status

Especifica a segunda linha de texto no título acima da barra de status.
Esse texto descreve o estado atual da atividade.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### Nenhum

Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### Nenhum

`Write-Progress` não gera nenhuma saída.

## OBSERVAÇÕES

Se a barra de progresso não for exibida, verifique o valor da `$ProgressPreference` variável. Se o valor está definido como SilentlyContinue, a barra de progresso não é exibida. Para obter mais informações sobre as preferências do PowerShell, consulte [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).

Os parâmetros do cmdlet correspondem às propriedades da classe **System. Management. Automation. ProgressRecord** . Para obter mais informações, consulte [classe ProgressRecord](/dotnet/api/system.management.automation.progressrecord).

## LINKS RELACIONADOS

[Write-Debug](Write-Debug.md)

[Erro de gravação](Write-Error.md)

[Write-Host](Write-Host.md)

[Write-Output](Write-Output.md)

[Write-Progress](Write-Progress.md)

[Write-Verbose](Write-Verbose.md)

[Write-Warning](Write-Warning.md)
