---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/debug-process?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Process
ms.openlocfilehash: 9d2b9ce8d9aa0a1e75c0af0f2ed57aca41ec7791
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192737"
---
# Debug-Process

## SINOPSE
Depura um ou mais processos em execução no computador local.

## SYNTAX

### Nome (padrão)

```
Debug-Process [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ID

```
Debug-Process [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject

```
Debug-Process -InputObject <Process[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Debug-Process** anexa um depurador a um ou mais processos em execução em um computador local.
Você pode especificar os processos por seu nome de processo ou ID de processo (PID) ou pode canalizar objetos de processo para esse cmdlet.

Esse cmdlet anexa o depurador que está atualmente registrado para o processo.
Antes de usar esse cmdlet, verifique se um depurador foi baixado e configurado corretamente.

## EXEMPLOS

### Exemplo 1: anexar um depurador a um processo no computador

```
PS C:\> Debug-Process -Name "Windows Powershell"
```

Esse comando anexa um depurador ao processo do PowerShell no computador.

### Exemplo 2: anexar um depurador a todos os processos que começam com a cadeia de caracteres especificada

```
PS C:\> Debug-Process -Name "SQL*"
```

Esse comando anexa um depurador a todos os processos que têm nomes que começam com SQL.

### Exemplo 3: anexar um depurador a vários processos

```
PS C:\> Debug-Process "Winlogon", "Explorer", "Outlook"
```

Esse comando anexa um depurador aos processos Winlogon, Explorer e Outlook.

### Exemplo 4: anexar um depurador a várias IDs de processo

```
PS C:\> Debug-Process -Id 1132, 2028
```

Esse comando anexa um depurador aos processos que têm as IDs de processo 1132 e 2028.

### Exemplo 5: usar Get-Process para obter um processo e, em seguida, anexar um depurador a ele

```
PS C:\> Get-Process "Windows PowerShell" | Debug-Process
```

Esse comando anexa um depurador aos processos do PowerShell no computador.
Ele usa o cmdlet **Get-Process** para obter os processos do PowerShell no computador e usa um operador de pipeline (|) para enviar os processos para o cmdlet **Debug-Process** .

Para especificar um processo específico do PowerShell, use o parâmetro ID de **Get-Process** .

### Exemplo 6: anexar um depurador a um processo atual no computador local

```
PS C:\> $PID | Debug-Process
```

Esse comando anexa um depurador aos processos atuais do PowerShell no computador.

O comando usa a $PID variável automática, que contém a ID de processo do processo atual do PowerShell.
Em seguida, ele usa um operador de pipeline (|) para enviar a ID do processo para o cmdlet **Debug-Process** .

Para obter mais informações sobre a $PID variável automática, consulte about_Automatic_Variables.

### Exemplo 7: anexar um depurador a um processo que usa o parâmetro InputObject

```
PS C:\> $P = Get-Process "Windows PowerShell"
PS C:\> Debug-Process -InputObject $P
```

Esse comando anexa um depurador aos processos do PowerShell no computador local.

O primeiro comando usa o cmdlet **Get-Process** para obter os processos do PowerShell no computador.
Ele salva o objeto de processo resultante na variável chamada $P.

O segundo comando usa o parâmetro *InputObject* do cmdlet **Debug-Process** para enviar o objeto de processo na variável $P.

## PARAMETERS

### -Id

Especifica os identificadores de processo dos processos a depurar.
O nome do parâmetro de *ID* é opcional.

Para localizar a ID de processo de um processo, digite `Get-Process` .

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases: PID, ProcessId

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject

Especifica os objetos de processo que representam os processos a serem depurados.
Insira uma variável que contém os objetos de processo ou um comando que obtém os objetos de processo, como o cmdlet Get-Process.
Você também pode canalizar objetos de processo para este cmdlet.

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Especifica os nomes dos processos a serem depurados.
Se houver mais de um processo com o mesmo nome, esse cmdlet anexará um depurador a todos os processos com esse nome.
O parâmetro *Name* é opcional.

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases: ProcessName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### System. Int32, System. Diagnostics. Process, System. String

É possível canalizar uma ID de processo (Int32), um objeto de processo (System. Diagnostics. Process) ou um nome de processo (cadeia de caracteres) para esse cmdlet.

## SAÍDAS

### Nenhum

Este cmdlet não gera saída.

## OBSERVAÇÕES

* Esse cmdlet usa o método AttachDebugger da classe Win32_Process da WMI (Instrumentação de Gerenciamento do Windows). Para obter mais informações sobre esse método, consulte o [método AttachDebugger](https://go.microsoft.com/fwlink/?LinkId=143640) na biblioteca MSDN.

## LINKS RELACIONADOS

[Debug-Process](Debug-Process.md)

[Get-Process](Get-Process.md)

[Start-Process](Start-Process.md)

[Stop-Process](Stop-Process.md)

[Wait-Process](Wait-Process.md)
