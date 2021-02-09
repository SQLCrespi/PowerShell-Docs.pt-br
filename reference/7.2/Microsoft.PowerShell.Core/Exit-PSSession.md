---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 02/08/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pssession?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSSession
ms.openlocfilehash: b1827929c53560cb261cd7b3ba1e5bd407c25700
ms.sourcegitcommit: 3a1d80e27438976101f216b8c3d623c61b868db8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "99975083"
---
# Exit-PSSession

## Sinopse
Encerra uma sessão interativa com um computador remoto.

## SYNTAX

```
Exit-PSSession [<CommonParameters>]
```

## Descrição

O `Exit-PSSession` cmdlet encerra as sessões interativas que você iniciou usando o `Enter-PSSession` cmdlet.

Você também pode usar a `exit` palavra-chave para encerrar uma sessão interativa. O efeito é o mesmo que usar `Exit-PSSession` .

## Exemplos

### Exemplo 1: Iniciar e parar uma sessão interativa

```powershell
PS> Enter-PSSession -ComputerName Server01
Server01\PS> Exit-PSSession
PS>
```

Esses comandos iniciam e param uma sessão interativa com o computador remoto Server01.

### Exemplo 2: Iniciar e parar uma sessão interativa usando um objeto PSSession

```powershell
PS> $s = New-PSSession -ComputerName Server01
PS> Enter-PSSession -Session $s
Server01\PS> Exit-PSSession
PS> $s
Id Name            ComputerName    State    ConfigurationName
-- ----            ------------    -----    -----------------
1  Session1        Server01        Opened   Microsoft.PowerShell
```

Esses comandos iniciam e param uma sessão interativa com o computador Server01 que usa uma sessão do PowerShell (**PSSession**).

Como a sessão interativa foi iniciada usando uma sessão do PowerShell, a **PSSession** ainda está disponível quando a sessão interativa termina. Se você usar o parâmetro _ComputerName_ , o `Enter-PSSession` criará uma sessão temporária que será fechada quando a sessão interativa terminar.

O primeiro comando usa o `New-PSSession` cmdlet para criar uma **PSSession** no computador Server01. O comando salva a **PSSession** na `$s` variável.

O segundo comando usa `Enter-PSSession` para iniciar uma sessão interativa usando a **PSSession** em `$s` .

O terceiro comando usa `Exit-PSSession` para interromper a sessão interativa.

O comando final exibe a **PSSession** na `$s` variável. A propriedade **State** mostra que **PSSession** ainda está aberto e disponível para uso.

### Exemplo 3: usar a palavra-chave EXIT para interromper uma sessão

```powershell
PS> Enter-PSSession -ComputerName Server01
Server01\PS> exit
PS>
```

Este exemplo usa a `exit` palavra-chave para interromper uma sessão interativa iniciada usando `Enter-PSSession` . A `exit` palavra-chave tem o mesmo efeito que usar `Exit-PSSession` .

## Parâmetros

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Entradas

### Nenhum

Não é possível transferir objetos para esse cmdlet.

## Saídas

### Nenhum

Este cmdlet não retorna nenhuma saída.

## Observações

Esse cmdlet usa apenas os parâmetros comuns.

## LINKS RELACIONADOS

[Connect-PSSession](Connect-PSSession.md)

[Disconnect-PSSession](Disconnect-PSSession.md)

[Enter-PSSession](Enter-PSSession.md)

[Get-PSSession](Get-PSSession.md)

[Invoke-Command](Invoke-Command.md)

[New-PSSession](New-PSSession.md)

[Receive-PSSession](Receive-PSSession.md)

[Remove-PSSession](Remove-PSSession.md)
