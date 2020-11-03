---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/tee-object?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Tee-Object
ms.openlocfilehash: fdfbb75bf95c8dc248441b6399312ed0592f62de
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193255"
---
# Tee-Object

## SINOPSE
Salva a saída do comando em um arquivo ou variável e a envia pelo pipeline.

## SYNTAX

### Arquivo (padrão)

```
Tee-Object [-InputObject <PSObject>] [-FilePath] <String> [-Append] [<CommonParameters>]
```

### Valor literal

```
Tee-Object [-InputObject <PSObject>] -LiteralPath <String> [<CommonParameters>]
```

### Variável

```
Tee-Object [-InputObject <PSObject>] -Variable <String> [<CommonParameters>]
```

## DESCRIPTION

O `Tee-Object` cmdlet redireciona a saída, ou seja, envia a saída de um comando em duas direções (como a letra T). Ele armazena a saída em um arquivo ou variável e também a envia pelo pipeline. Se `Tee-Object` for o último comando no pipeline, a saída do comando será exibida no prompt.

## EXEMPLOS

### Exemplo 1: processos de saída para um arquivo e para o console

Este exemplo obtém uma lista dos processos em execução no computador e envia o resultado para um arquivo.
Como um segundo caminho não foi especificado, os processos também são exibidos no console.

```powershell
Get-Process | Tee-Object -FilePath "C:\Test1\testfile2.txt"
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)    Id ProcessName
-------  ------    -----      ----- -----   ------    -- -----------
83       4     2300       4520    39     0.30    4032 00THotkey
272      6     1400       3944    34     0.06    3088 alg
81       3      804       3284    21     2.45     148 ApntEx
81       4     2008       5808    38     0.75    3684 Apoint
...
```

### Exemplo 2: processos de saída para uma variável e `Select-Object`

Este exemplo obtém uma lista dos processos em execução no computador, salva-os na `$proc` variável e os canaliza para `Select-Object` .

```powershell
Get-Process notepad | Tee-Object -Variable proc | Select-Object processname,handles
```

```Output
ProcessName                              Handles
-----------                              -------
notepad                                  43
notepad                                  37
notepad                                  38
notepad                                  38
```

O `Select-Object` cmdlet seleciona o **ProcessName** e **manipula** as propriedades. Observe que a `$proc` variável inclui as informações padrão retornadas por `Get-Process` .

### Exemplo 3: arquivos do sistema de saída para dois arquivos de log

Este exemplo salva uma lista de arquivos do sistema em dois arquivos de log, um arquivo cumulativo e um arquivo atual.

```powershell
Get-ChildItem -Path D: -File -System -Recurse |
  Tee-Object -FilePath "c:\test\AllSystemFiles.txt" -Append |
    Out-File c:\test\NewSystemFiles.txt
```

O comando usa o `Get-ChildItem` cmdlet para fazer uma pesquisa recursiva de arquivos do sistema na unidade D:. Um operador de pipeline (|) envia a lista para `Tee-Object` , que acrescenta a lista ao arquivo de AllSystemFiles.txt e passa a lista para baixo do pipeline para o `Out-File` cmdlet, que salva a lista no arquivo de NewSystemFiles.txt.

## PARAMETERS

### -Acrescentar

Indica que o cmdlet acrescenta a saída ao arquivo especificado. Sem esse parâmetro, o novo conteúdo substitui todo o conteúdo existente no arquivo sem aviso.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: File
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

Especifica um arquivo no qual esse cmdlet salva o objeto para caracteres curinga é permitido, mas deve ser resolvido para um único arquivo.

```yaml
Type: System.String
Parameter Sets: File
Aliases: Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -InputObject

Especifica o objeto a ser salvo e exibido. Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos. Também é possível canalizar um objeto para `Tee-Object` .

Quando você usa o parâmetro **InputObject** com `Tee-Object` , em vez de direcionar os resultados do comando para `Tee-Object` , o valor **InputObject** é tratado como um único objeto, mesmo se o valor for uma coleção.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LiteralPath

Especifica um arquivo para o qual esse cmdlet salva o objeto. Ao contrário de **FilePath** , o valor do parâmetro **LiteralPath** é usado exatamente como é digitado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres de escape, coloque-o entre aspas simples. Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

```yaml
Type: System.String
Parameter Sets: LiteralFile
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Variable

Especifica uma variável para a qual o cmdlet salva o objeto. Insira um nome de variável sem o sinal de dólar anterior ( `$` ).

```yaml
Type: System.String
Parameter Sets: Variable
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Management. Automation. PSObject

Você pode canalizar objetos para `Tee-Object` .

## SAÍDAS

### System. Management. Automation. PSObject

`Tee-Object` Retorna o objeto que é redirecionado.

## OBSERVAÇÕES

Você também pode usar o `Out-File` cmdlet ou o operador de redirecionamento, ambos salvando a saída em um arquivo, mas não o enviam pelo pipeline.

A partir do PowerShell 6, o `Tee-Object` usa a codificação UTF-8 sem bom quando grava em arquivos. Se você precisar de uma codificação diferente, use o `Out-File` cmdlet com o parâmetro **Encoding** .

## LINKS RELACIONADOS

[Compare-Object](Compare-Object.md)

[ForEach-Object](../Microsoft.PowerShell.Core/ForEach-Object.md)

[Group-Object](Group-Object.md)

[Measure-Object](Measure-Object.md)

[New-Object](New-Object.md)

[Select-Object](Select-Object.md)

[Sort-Object](Sort-Object.md)

[Where-Object](../Microsoft.PowerShell.Core/Where-Object.md)

[about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md)

