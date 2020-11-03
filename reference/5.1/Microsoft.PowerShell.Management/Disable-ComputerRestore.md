---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/disable-computerrestore?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-ComputerRestore
ms.openlocfilehash: 941829c3caa0f6bb2f5712dda9eb7d8c36908062
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194190"
---
# Disable-ComputerRestore

## SINOPSE
Desabilita o recurso de Restauração de sistema na unidade de sistema de arquivos especificada.

## SYNTAX

```
Disable-ComputerRestore [-Drive] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Disable-ComputerRestore** desativa o recurso de restauração do sistema em uma ou mais unidades do sistema de arquivos.
Como resultado, tentativas de restaurar o computador não afetam a unidade especificada.

Para desabilitar a Restauração do sistema em uma determinada unidade, é necessário desabilitá-la primeiro ou simultaneamente na unidade do sistema.

Para ativar novamente a Restauração do sistema, use o cmdlet Enable-ComputerRestore.
Para descobrir o estado de Restauração do sistema para cada unidade, use o Rstrui.exe.

Pontos de restauração do sistema e os cmdlets ComputerRestore têm suporte apenas em sistemas operacionais de cliente, como o Windows 7, Windows Vista e Windows XP.

## EXEMPLOS

### Exemplo 1: desabilitar a restauração do sistema na unidade especificada

```
PS C:\> Disable-ComputerRestore -Drive "C:\"
```

Este comando desabilita a Restauração do sistema na unidade C:.

### Exemplo 2: desabilitar a restauração do sistema em várias unidades

```
PS C:\> Disable-ComputerRestore "C:\", "D:\"
```

Este comando desabilita a Restauração do sistema nas unidades C: e D:.
O comando usa o parâmetro *drive* , mas omite o nome do parâmetro da unidade.

## PARAMETERS

### -Unidade
Especifica as unidades do sistema de arquivos.
Insira uma ou mais letras de unidade do sistema de arquivos, cada uma seguida por dois-pontos e uma barra invertida e entre aspas, como C:\ ou D:\.
Este parâmetro é necessário.

Você não pode usar este cmdlet para desabilitar a Restauração do sistema em uma unidade de rede remota, mesmo que a unidade esteja mapeada para o computador local; você também não pode desabilitar a Restauração do sistema em unidades que não estão qualificadas para essa operação, como unidades externas.

Para desabilitar a Restauração do sistema em uma determinada unidade, é necessário desabilitá-la primeiro ou simultaneamente na unidade do sistema.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
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

* Para executar esse cmdlet no Windows Vista e em versões posteriores do Windows, abra o Windows PowerShell com a opção Executar como administrador.

  Para localizar as unidades do sistema de arquivos elegíveis para a restauração do sistema, em sistema no painel de controle, consulte a guia proteção do sistema. Para abrir essa guia no Windows PowerShell, digite `SystemPropertiesProtection` .

  Esse cmdlet usa Instrumentação de Gerenciamento do Windows a classe **SystemRestore** (WMI).

*

## LINKS RELACIONADOS

[Checkpoint-Computer](Checkpoint-Computer.md)

[Enable-ComputerRestore](Enable-ComputerRestore.md)

[Get-ComputerRestorePoint](Get-ComputerRestorePoint.md)

[Restart-Computer](Restart-Computer.md)

[Restore-Computer](Restore-Computer.md)
