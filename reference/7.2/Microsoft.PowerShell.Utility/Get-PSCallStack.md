---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-pscallstack?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSCallStack
ms.openlocfilehash: 607e3999a1dbe9a4f22a751f11ac93ee3f9d9409
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595348"
---
# Get-PSCallStack

## SINOPSE
Exibe a pilha de chamadas atual.

## SYNTAX

```
Get-PSCallStack [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Get-PSCallStack** exibe a pilha de chamadas atual.

Embora ele seja projetado para ser usado com o depurador do PowerShell, você pode usar este cmdlet para exibir a pilha de chamadas em um script ou função fora do depurador.

Para executar um comando **Get-PSCallStack** no depurador, digite `k` ou `Get-PSCallStack` .

## EXEMPLOS

### Exemplo 1: obter a pilha de chamadas para uma função

```
PS C:\> function my-alias {
$p = $args[0]
Get-Alias | where {$_.definition -like "*$p"} | format-table definition, name -auto
}
PS C:\ps-test> Set-PSBreakpoint -Command my-alias
Command    : my-alias
Action     :
Enabled    : True
HitCount   : 0
Id         : 0
Script     : prompt PS C:\> my-alias Get-Content

Entering debug mode. Use h or ? for help.
Hit Command breakpoint on 'prompt:my-alias'
my-alias get-content
[DBG]: PS C:\ps-test> s
$p = $args[0]
DEBUG: Stepped to ':    $p = $args[0]    '
[DBG]: PS C:\ps-test> s
get-alias | Where {$_.Definition -like "*$p*"} | format-table Definition,
[DBG]: PS C:\ps-test>get-pscallstack

Name        CommandLineParameters         UnboundArguments              Location
----        ---------------------         ----------------              --------
prompt      {}                            {}                            prompt
my-alias    {}                            {get-content}                 prompt
prompt      {}                            {}                            prompt PS C:\> [DBG]: PS C:\ps-test> o
Definition  Name
----------  ----
Get-Content gc
Get-Content cat
Get-Content type
```

Esse comando usa o cmdlet **Get-PSCallStack** para exibir a pilha de chamadas para My-alias, uma função simples que obtém os aliases para um nome de cmdlet.

O primeiro comando insere a função no prompt do PowerShell.
O segundo comando usa o cmdlet Set-PSBreakpoint para definir um ponto de interrupção na função My-Alias.
O terceiro comando usa a função My-Alias para obter todos os aliases na sessão atual para o cmdlet Get-Content.

O depurador interrompe na chamada de função.
Dois comandos set-into consecutivos iniciam a execução da função linha por linha.
Em seguida, um comando **Get-PSCallStack** é usado para recuperar a pilha de chamadas.

O comando final é um comando de Step-Out (o) que sai do depurador e continua executando o script até sua conclusão.

## PARAMETERS

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Não é possível transferir objetos para esse cmdlet.

## SAÍDAS

### System. Management. Automation. CallStackFrame

**Get-PSCallStack** retorna um objeto que representa os itens na pilha de chamadas.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Disable-PSBreakpoint](Disable-PSBreakpoint.md)

[Enable-PSBreakpoint](Enable-PSBreakpoint.md)

[Format-Table](Format-Table.md)

[Get-PSBreakpoint](Get-PSBreakpoint.md)

[Remove-PSBreakpoint](Remove-PSBreakpoint.md)

[Set-PSBreakpoint](Set-PSBreakpoint.md)

