---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pssession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSSession
ms.openlocfilehash: efe0e6c9287b3595988aa3ffc520ce46699cafda
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193333"
---
# Exit-PSSession

## SINOPSE
Encerra uma sessão interativa com um computador remoto.

## SYNTAX

```
Exit-PSSession [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Exit-PSSession** encerra as sessões interativas que você iniciou usando o cmdlet Enter-PSSession.

Você também pode usar a palavra-chave **Exit** para encerrar uma sessão interativa.
O efeito é o mesmo que usar **Exit-PSSession** .

## EXEMPLOS

### Exemplo 1: Iniciar e parar uma sessão interativa

```
PS C:\> Enter-PSSession -computername Server01
Server01\PS> Exit-PSSession
PS C:\>
```

Esses comandos iniciam e param uma sessão interativa com o computador remoto Server01.

### Exemplo 2: Iniciar e parar uma sessão interativa usando um objeto PSSession

```
PS C:\> $s = New-PSSession -ComputerName Server01
PS C:\> Enter-PSSession -Session $s
Server01\PS> Exit-PSSession
PS C:\> $s
Id Name            ComputerName    State    ConfigurationName
-- ----            ------------    -----    -----------------
1  Session1        Server01        Opened   Microsoft.PowerShell
```

Esses comandos iniciam e param uma sessão interativa com o computador Server01 que usa uma sessão do Windows PowerShell ( **PSSession** ).

Como a sessão interativa foi iniciada usando uma sessão do Windows PowerShell, a **PSSession** ainda está disponível quando a sessão interativa termina.
Se você usar o parâmetro *ComputerName* , **Enter-PSSession** criará uma sessão temporária que será fechada quando a sessão interativa terminar.

O primeiro comando usa o cmdlet New-PSSession para criar uma **PSSession** no computador Server01.
O comando salva a **PSSession** na variável $s.

O segundo comando usa **Enter-PSSession** para iniciar uma sessão interativa usando a **PSSession** em $s.

O terceiro comando usa **Exit-PSSession** para interromper a sessão interativa.

O comando final exibe a **PSSession** na variável $s.
A propriedade **State** mostra que **PSSession** ainda está aberto e disponível para uso.

### Exemplo 3: usar a palavra-chave EXIT para interromper uma sessão

```
PS C:\> Enter-PSSession -computername Server01
Server01\PS> exit
PS C:\>
```

Este exemplo usa a palavra-chave **Exit** para interromper uma sessão interativa iniciada usando **Enter-PSSession** .
A palavra-chave **Exit** tem o mesmo efeito que usar **Exit-PSSession** .

## PARAMETERS

### CommonParameters
Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum
Não é possível transferir objetos para esse cmdlet.

## SAÍDAS

### Nenhum
Este cmdlet não retorna nenhuma saída.

## OBSERVAÇÕES

* Esse cmdlet usa apenas os parâmetros comuns.


## LINKS RELACIONADOS

[Connect-PSSession](Connect-PSSession.md)

[Disconnect-PSSession](Disconnect-PSSession.md)

[Enter-PSSession](Enter-PSSession.md)

[Get-PSSession](Get-PSSession.md)

[Invoke-Command](Invoke-Command.md)

[New-PSSession](New-PSSession.md)

[Receive-PSSession](Receive-PSSession.md)

[Remove-PSSession](Remove-PSSession.md)
