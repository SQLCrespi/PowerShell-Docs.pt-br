---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pshostprocess?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSHostProcess
ms.openlocfilehash: b7e2bf7cff84e92f4c174ef01861ee5c0a822bea
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2020
ms.locfileid: "93192651"
---
# Exit-PSHostProcess

## SINOPSE
Fecha uma sessão interativa com um processo local.

## SYNTAX

```
Exit-PSHostProcess [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Exit-PSHostProcess** fecha uma sessão interativa com um processo local que você abriu executando o cmdlet Enter-PSHostProcess. Você executa o cmdlet **Exit-PSHostProcess** de dentro do processo, quando conclui a depuração ou a solução de problemas de um script que está sendo executado dentro de um processo.

## EXEMPLOS

### Exemplo 1: sair de um processo

```
[Process:1520]: PS>  Exit-PSHostProcess
PS>
```

Neste exemplo, você esteve trabalhando em um processo ativo para depurar um script em execução em um runspace no processo, conforme descrito em Enter-PSHostProcess. Depois de digitar o comando **Exit** para sair do depurador, execute o cmdlet **Exit-PSHostProcess** para fechar sua sessão interativa com o processo.
O cmdlet fecha a sessão no processo e retorna para o prompt PS C: \\ \> .

## PARAMETERS

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

## SAÍDAS

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Enter-PSHostProcess](Enter-PSHostProcess.md)

