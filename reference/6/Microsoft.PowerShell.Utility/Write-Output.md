---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-output?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Output
ms.openlocfilehash: 75b046ea6b11be3e4d87ed9db3e011a1f00d6ef5
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "93196389"
---
# Write-Output

## SINOPSE
Envia os objetos especificados para o próximo comando no pipeline. Se o comando for o último no pipeline, os objetos serão exibidos no console.

## SYNTAX

```
Write-Output [-InputObject] <PSObject[]> [-NoEnumerate] [<CommonParameters>]
```

## DESCRIPTION

O `Write-Output` cmdlet envia o objeto especificado para baixo no pipeline para o próximo comando.
Se o comando for o último no pipeline, o objeto é exibido no console.

`Write-Output` envia objetos para baixo do pipeline primário, também conhecido como "fluxo de saída" ou "pipeline de sucesso". Para enviar objetos de erro pelo pipeline de erro, use Write-Error.

Esse cmdlet é usado normalmente em scripts para exibir cadeias de caracteres e outros objetos no console. Um dos aliases internos do `Write-Output` é `echo` e semelhante a outros shells que usam `echo` , o comportamento padrão é exibir a saída no final de um pipeline. No PowerShell, geralmente não é necessário usar o cmdlet em instâncias em que a saída é exibida por padrão. Por exemplo, `Get-Process | Write-Output` é equivalente a `Get-Process`. Ou, `echo "Home directory: $HOME"` pode ser escrito, `"Home directory: $HOME"` .

Por padrão, o `Write-Output` enumera por meio de coleções fornecidas para o cmdlet. No entanto, `Write-Output` também pode ser usado para passar as coleções para o pipeline como um único objeto com o parâmetro **noenumerate** .

## EXEMPLOS

### Exemplo 1: obter objetos e gravá-los no console

```powershell
$P = Get-Process
Write-Output $P
```

O primeiro comando obtém os processos em execução no computador e os armazena na `$P` variável.

O segundo e o terceiro comandos exibem os objetos de processo no `$P` console do.

### Exemplo 2: passar a saída para outro cmdlet

```powershell
Write-Output "test output" | Get-Member
```

Esse comando canaliza a cadeia de caracteres de "saída de teste" para o `Get-Member` cmdlet, que exibe os membros da classe **System. String** , demonstrando que a cadeia de caracteres foi passada ao longo do pipeline.

### Exemplo 3: suprimir enumeração na saída

```powershell
Write-Output 1,2,3 | Measure-Object
```

```Output
Count    : 3
...
```

```powershell
Write-Output 1,2,3 -NoEnumerate | Measure-Object
```

```Output
Count    : 1
...
```

Esse comando adiciona o parâmetro **Noenumerate** para tratar uma coleção ou matriz como um único objeto por meio do pipeline.

## PARAMETERS

### -InputObject

Especifica os objetos para envio pelo pipeline. Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Noenumerate

Por padrão, o `Write-Output` cmdlet sempre enumera sua saída. O parâmetro **Noenumerate** suprime o comportamento padrão e impede a `Write-Output` enumeração da saída. O parâmetro **Noenumerate** não terá nenhum efeito se o comando for encapsulado entre parênteses, porque os parênteses forçam a enumeração. Por exemplo, `(Write-Output 1,2,3)` o ainda enumera a matriz.

> [!NOTE]
> Essa opção funciona apenas corretamente com o PowerShell Core 6,2 e mais recente. Em versões mais antigas do PowerShell Core, a coleção ainda é enumerada mesmo com o uso dessa opção.

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Management. Automation. PSObject

Você pode canalizar objetos para `Write-Output` .

## SAÍDAS

### System. Management. Automation. PSObject

`Write-Output` Retorna os objetos que são enviados como entrada.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[about_Output_Streams](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[Tee-Object](Tee-Object.md)

[Write-Debug](Write-Debug.md)

[Erro de gravação](Write-Error.md)

[Write-Host](Write-Host.md)

[Write-Information](Write-Information.md)

[Write-Progress](Write-Progress.md)

[Write-Verbose](Write-Verbose.md)

[Write-Warning](Write-Warning.md)
