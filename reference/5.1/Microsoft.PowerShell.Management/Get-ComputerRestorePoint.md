---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/13/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-computerrestorepoint?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ComputerRestorePoint
ms.openlocfilehash: 73819aafee9ed1911354daf9af23eedff0a3e14c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194186"
---
# Get-ComputerRestorePoint

## SINOPSE
Obtém os pontos de restauração no computador local.

## SYNTAX

### ID (padrão)

```
Get-ComputerRestorePoint [[-RestorePoint] <Int32[]>] [<CommonParameters>]
```

### LastStatus

```
Get-ComputerRestorePoint -LastStatus [<CommonParameters>]
```

## DESCRIPTION

O `Get-ComputerRestorePoint` cmdlet obtém os pontos de restauração do sistema do computador local. E ele pode exibir o status da tentativa mais recente de restaurar o computador.

Você pode usar as informações do `Get-ComputerRestorePoint` para selecionar um ponto de restauração. Por exemplo, use um número de sequência para identificar um ponto de restauração para o `Restore-Computer` cmdlet.

Os pontos de restauração do sistema e o `Get-ComputerRestorePoint` cmdlet têm suporte apenas em sistemas operacionais cliente, como o Windows 10, o Windows 7, o Windows Vista e o Windows XP.

## EXEMPLOS

### Exemplo 1: obter todos os pontos de restauração do sistema

Neste exemplo, `Get-ComputerRestorePoint` Obtém todos os pontos de restauração do sistema do computador local.

```powershell
Get-ComputerRestorePoint
```

```Output
CreationTime           Description                    SequenceNumber    EventType         RestorePointType
------------           -----------                    --------------    ---------         ----------------
7/30/2019 09:17:24     Windows Update                 4                 BEGIN_SYSTEM_C... 17
8/5/2019  08:15:37     Installed PowerShell 7-prev... 5                 BEGIN_SYSTEM_C... APPLICATION_INSTALL
8/7/2019  12:56:45     Installed PowerShell 6-x64     6                 BEGIN_SYSTEM_C... APPLICATION_INSTALL
```

### Exemplo 2: obter números de sequência específicos

Este exemplo obtém pontos de restauração do sistema para números de sequência específicos.

```powershell
Get-ComputerRestorePoint -RestorePoint 4, 5
```

```Output
CreationTime           Description                    SequenceNumber    EventType         RestorePointType
------------           -----------                    --------------    ---------         ----------------
7/30/2019 09:17:24     Windows Update                 4                 BEGIN_SYSTEM_C... 17
8/5/2019  08:15:37     Installed PowerShell 7-prev... 5                 BEGIN_SYSTEM_C... APPLICATION_INSTALL
```

`Get-ComputerRestorePoint` usa o parâmetro **RestorePoint** para especificar uma matriz separada por vírgulas de números de sequência.

### Exemplo 3: exibir o status de uma restauração do sistema

Este exemplo exibe o status da restauração mais recente do sistema no computador local.

```powershell
Get-ComputerRestorePoint -LastStatus
```

```Output
The last attempt to restore the computer failed.
```

`Get-ComputerRestorePoint` usa o parâmetro **LastStatus** para exibir o resultado da restauração mais recente do sistema.

### Exemplo 4: usar uma expressão para converter o CreationTime

`Get-ComputerRestorePoint` gera o **CreationTime** como uma cadeia de caracteres de data e hora Instrumentação de gerenciamento do Windows (WMI).

Neste exemplo, uma variável armazena uma expressão que converte a cadeia de caracteres **CreationTime** em um objeto **DateTime** . Para exibir as cadeias de caracteres **CreationTime** antes que elas sejam convertidas, use um comando como `((Get-ComputerRestorePoint).CreationTime)` . Para obter mais informações sobre a cadeia de caracteres de data e hora do WMI, consulte [CIM_DATETIME](/windows/win32/wmisdk/cim-datetime).

```powershell
$date = @{Label="Date"; Expression={$_.ConvertToDateTime($_.CreationTime)}}
Get-ComputerRestorePoint | Select-Object -Property SequenceNumber, $date, Description
```

```Output
SequenceNumber   Date                 Description
--------------   ----                 -----------
             4   7/30/2019 09:17:24   Windows Update
             5   8/5/2019  08:15:37   Installed PowerShell 7-preview-x64
             6   8/7/2019  12:56:45   Installed PowerShell 6-x64
```

A `$date` variável armazena uma tabela de hash com a expressão que usa o método **ConvertToDateTime** . A expressão converte o valor da propriedade **CreationTime** de uma cadeia de caracteres WMI em um objeto **DateTime** .

`Get-ComputerRestorePoint` envia os objetos do ponto de restauração do sistema para baixo no pipeline. `Select-Object` usa o parâmetro **Property** para especificar as propriedades a serem exibidas. Para cada objeto no pipeline, a expressão em `$date` converte o **CreationTime** e gera o resultado na propriedade **Date** .

### Exemplo 5: usar uma propriedade para obter um número de sequência

Este exemplo obtém um número de sequência usando a propriedade **SequenceNumber** e um índice de matriz. A saída contém apenas o número de sequência.

```powershell
((Get-ComputerRestorePoint).SequenceNumber)[-1]
```

```Output
6
```

`Get-ComputerRestorePoint` usa a propriedade **SequenceNumber** com um índice de matriz. O índice de matriz `-1` Obtém o número de sequência mais recente na matriz.

## PARAMETERS

### -LastStatus

Indica que `Get-ComputerRestorePoint` Obtém o status da operação de restauração do sistema mais recente.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LastStatus
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestorePoint

Especifica os números de sequência dos pontos de restauração do sistema. Você pode especificar um único número de sequência ou uma matriz separada por vírgulas de números de sequência.

Se o parâmetro **RestorePoint** não for especificado, o `Get-ComputerRestorePoint` retornará todos os pontos de restauração do sistema do computador local.

```yaml
Type: System.Int32[]
Parameter Sets: ID
Aliases:

Required: False
Position: 0
Default value: All restore points
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Você não pode enviar objetos pelo pipeline para o `Get-ComputerRestorePoint` .

## SAÍDAS

### System. Management. ManagementObject # root\default\SystemRestore ou String

`Get-ComputerRestorePoint` Retorna um objeto **SystemRestore** , que é uma instância da classe **SystemRestore** do Instrumentação de gerenciamento do Windows (WMI).

Quando você usa o parâmetro **LastStatus** , o `Get-ComputerRestorePoint` retorna uma cadeia de caracteres.

## OBSERVAÇÕES

Para executar um `Get-ComputerRestorePoint` comando no Windows Vista e em versões posteriores do Windows, abra o PowerShell com a opção **Executar como administrador** .

`Get-ComputerRestorePoint` usa a classe WMI **SystemRestore** .

## LINKS RELACIONADOS

[about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[about_Arrays](../Microsoft.PowerShell.Core/About/about_Arrays.md)

[Checkpoint-Computer](Checkpoint-Computer.md)

[Disable-ComputerRestore](Disable-ComputerRestore.md)

[Enable-ComputerRestore](Enable-ComputerRestore.md)

[Restart-Computer](Restart-Computer.md)

[Restore-Computer](Restore-Computer.md)

[SystemRestore](/windows/win32/sr/systemrestore)
