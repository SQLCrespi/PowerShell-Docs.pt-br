---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-psbreakpoint?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSBreakpoint
ms.openlocfilehash: ae3dbbd062171a0185308bc120c1baf31a352c92
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93193009"
---
# Get-PSBreakpoint

## SINOPSE
Obtém os pontos de interrupção definidos na sessão atual.

## SYNTAX

### Script (padrão)

```
Get-PSBreakpoint [-Script <String[]>] [<CommonParameters>]
```

### Variável

```
Get-PSBreakpoint [-Script <String[]>] -Variable <String[]> [<CommonParameters>]
```

### Comando

```
Get-PSBreakpoint [-Script <String[]>] -Command <String[]> [<CommonParameters>]
```

### Tipo

```
Get-PSBreakpoint [-Script <String[]>] [-Type] <BreakpointType[]> [<CommonParameters>]
```

### ID

```
Get-PSBreakpoint [-Id] <Int32[]> [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Get-PSBreakpoint** Obtém os pontos de interrupção definidos na sessão atual.
Você pode usar os parâmetros do cmdlet para obter pontos de interrupção específicos.

Um ponto de interrupção é um ponto em um comando ou script onde a execução é interrompida temporariamente para que você possa examinar as instruções.
O **Get-PSBreakpoint** é um dos vários cmdlets projetados para depurar scripts e comandos do PowerShell. Para obter mais informações sobre o depurador do PowerShell, consulte about_Debuggers.

## EXEMPLOS

### Exemplo 1: obter todos os pontos de interrupção para todos os scripts e funções

```
PS C:\> Get-PSBreakpoint
```

Este comando obtém todos os pontos de interrupção definidos em todos os scripts e funções presentes na sessão atual.

### Exemplo 2: obter pontos de interrupção por ID

```
PS C:\> Get-PSBreakpoint -Id 2
Function   :
IncrementAction     :
Enabled    :
TrueHitCount   : 0
Id         : 2
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

Esse comando obtém o ponto de interrupção com o identificador 2.

### Exemplo 3: direcionar uma ID para Get-PSBreakpoint

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Command "Increment"
PS C:\> $B.Id | Get-PSBreakpoint
```

Esses comandos mostram como obter um ponto de interrupção ao canalizar uma ID de ponto de interrupção para **Get-PSBreakpoint** .

O primeiro comando usa o cmdlet Set-PSBreakpoint para criar um ponto de interrupção na função Increment, no script Sample.ps1. Ele salva o objeto de ponto de interrupção na variável $B.

O segundo comando usa o operador ponto (.) para obter a propriedade ID do objeto Breakpoint na variável $B. Ele usa um operador de pipeline (|) para enviar a ID para o cmdlet **Get-PSBreakpoint** .

Como resultado, **Get-PSBreakpoint** Obtém o ponto de interrupção com a ID especificada.

### Exemplo 4: obter pontos de interrupção em arquivos de script especificados

```
PS C:\> Get-PSBreakpoint -Script "Sample.ps1, SupportScript.ps1"
```

Este comando obtém todos os pontos de interrupção contidos nos arquivos Sample.ps1 e SupportScript.ps1.

Esse comando não obtém outros pontos de interrupção que podem ser definidos em outros scripts ou em funções na sessão.

### Exemplo 5: obter pontos de interrupção nos cmdlets especificados

```
PS C:\> Get-PSBreakpoint -Command "Read-Host, Write-Host" -Script "Sample.ps1"
```

Este comando obtém todos os pontos de interrupção de comando que estão definidos em comandos de Read-Host ou Write-Host contidos no arquivo Sample.ps1.

### Exemplo 6: obter pontos de interrupção de comando em um arquivo especificado

```
PS C:\> Get-PSBreakpoint -Type Command -Script "Sample.ps1"
```

Este comando obtém todos os pontos de interrupção do comando contidos no arquivo Sample.ps1.

### Exemplo 7: obter pontos de interrupção por variável

```
PS C:\> Get-PSBreakpoint -Variable "Index, Swap"
```

Esse comando obtém os pontos de interrupção que são definidos no $Index e $Swap variáveis na sessão atual.

### Exemplo 8: obter todos os pontos de interrupção de linha e variável em um arquivo

```
PS C:\> Get-PSBreakpoint -Type Line, Variable -Script "Sample.ps1"
```

Este comando obtém todos os pontos de interrupção variáveis e de linha contidos no script Sample.ps1.

## PARAMETERS

### -Command

Especifica uma matriz de pontos de interrupção de comando que são definidos nos nomes de comando especificados.
Insira os nomes de comando, como, por exemplo, o nome de um cmdlet ou função.

```yaml
Type: System.String[]
Parameter Sets: Command
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Especifica as IDs de ponto de interrupção que esse cmdlet obtém.
Digite os identificadores em uma lista separada por vírgulas.
Você também pode canalizar IDs de ponto de interrupção para **Get-PSBreakpoint** .

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Script

Especifica uma matriz de scripts que contém os pontos de interrupção.
Insira o caminho (opcional) e os nomes de um ou mais arquivos de script.
Se você omitir o caminho, o local padrão a considerar é o diretório atual.

```yaml
Type: System.String[]
Parameter Sets: Script, Variable, Command, Type
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Type

Especifica uma matriz de tipos de ponto de interrupção que esse cmdlet obtém.
Insira um ou mais tipos.
Os valores aceitáveis para esse parâmetro são:

- Linha
- Comando
- Variável

Você também pode canalizar tipos de ponto de interrupção para **Get-PSBreakpoint** .

```yaml
Type: Microsoft.PowerShell.Commands.BreakpointType[]
Parameter Sets: Type
Aliases:
Accepted values: Line, Variable, Command

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Variable

Especifica uma matriz de pontos de interrupção de variável que são definidos nos nomes de variável especificados.
Digite os nomes de variáveis sem cifrões.

```yaml
Type: System.String[]
Parameter Sets: Variable
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Int32, Microsoft. PowerShell. Commands. Breakpointtype

Você pode canalizar IDs de ponto de interrupção e tipos de ponto de quebra para **Get-PSBreakpoint** .

## SAÍDAS

### System. Management. Automation. Breakpoint

**Get-PSBreakpoint** retorna objetos que representam os pontos de interrupção na sessão.

## OBSERVAÇÕES

* Você pode usar **Get-PSBreakpoint** ou seu alias, "GBP".

## LINKS RELACIONADOS

[Disable-PSBreakpoint](Disable-PSBreakpoint.md)

[Enable-PSBreakpoint](Enable-PSBreakpoint.md)

[Get-PSCallStack](Get-PSCallStack.md)

[Remove-PSBreakpoint](Remove-PSBreakpoint.md)

[Set-PSBreakpoint](Set-PSBreakpoint.md)
