---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-unique?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Unique
ms.openlocfilehash: e6831d953008f215bac50fd2b6ec36f88256a2fb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194463"
---
# Get-Unique

## SINOPSE
Retorna itens únicos por meio de uma lista classificada.

## SYNTAX

### AsString (padrão)

```
Get-Unique [-InputObject <PSObject>] [-AsString] [<CommonParameters>]
```

### UniqueByType

```
Get-Unique [-InputObject <PSObject>] [-OnType] [<CommonParameters>]
```

## DESCRIPTION

O `Get-Unique` cmdlet compara cada item em uma lista classificada com o próximo item, elimina duplicatas e retorna apenas uma instância de cada item. A lista deve ser classificada para que o cmdlet funcione corretamente.

`Get-Unique` diferencia maiúsculas de minúsculas. Como resultado, cadeias de caracteres que diferem apenas em maiúsculas e minúsculas são consideradas como sendo exclusivas.

## EXEMPLOS

### Exemplo 1: obter palavras exclusivas em um arquivo de texto

Estes comandos localizam o número de palavras exclusivas em um arquivo de texto.

```powershell
$A = $( foreach ($line in Get-Content C:\Test1\File1.txt) {
    $line.tolower().split(" ")
  }) | Sort-Object | Get-Unique
$A.count
```

O primeiro comando obtém o conteúdo do arquivo Arquivo.txt. Ele converte cada linha de texto em letras minúsculas e, em seguida, divide cada palavra em uma linha separada por um espaço (" "). Em seguida, ele classifica a lista resultante em ordem alfabética (o padrão) e usa o `Get-Unique` cmdlet para eliminar quaisquer palavras duplicadas. Os resultados são armazenados na `$A` variável.

O segundo comando usa a propriedade **Count** da coleção de cadeias de caracteres no `$A` para determinar a quantidade de itens em `$A` .

### Exemplo 2: obter inteiros exclusivos em uma matriz

Este comando localiza os membros exclusivos do conjunto de números inteiros.

```powershell
1,1,1,1,12,23,4,5,4643,5,3,3,3,3,3,3,3 | Sort-Object | Get-Unique
```

```Output
1
3
4
5
12
23
4643
```

O primeiro comando usa uma matriz de inteiros digitados na linha de comando, canaliza-os para o `Sort-Object` cmdlet a ser classificado e, em seguida, os canaliza para `Get-Unique` , o que elimina as entradas duplicadas.

### Exemplo 3: obter tipos de objeto exclusivos em um diretório

Esse comando usa o `Get-ChildItem` cmdlet para recuperar o conteúdo do diretório local, que inclui arquivos e diretórios.

```powershell
Get-ChildItem | Sort-Object {$_.GetType()} | Get-Unique -OnType
```

O operador de pipeline (|) envia os resultados para o `Sort-Object` cmdlet. A `$_.GetType()` instrução aplica o método **GetType** a cada arquivo ou diretório. Em seguida, `Sort-Object` o classifica os itens por tipo. Outro operador de pipeline envia os resultados para `Get-Unique` . O parâmetro **OnType** direciona `Get-Unique` para retornar apenas um objeto de cada tipo.

### Exemplo 4: obter processos exclusivos

Este comando obtém os nomes dos processos em execução no computador com as duplicatas já eliminadas.

```powershell
Get-Process | Sort-Object | Select-Object processname | Get-Unique -AsString
```

O `Get-Process` comando obtém todos os processos no computador. O operador de pipeline (|) passa o resultado para `Sort-Object` , que, por padrão, classifica os processos alfabeticamente por ProcessName. Os resultados são canalizados para o `Select-Object` cmdlet, que seleciona apenas os valores da propriedade ProcessName de cada objeto. Os resultados são então canalizados para `Get-Unique` para eliminar duplicatas.

O parâmetro **AsString** diz `Get-Unique` para tratar os valores **ProcessName** como cadeias de caracteres.
Sem esse parâmetro, `Get-Unique` o trata os valores de **ProcessName** como objetos e retorna apenas uma instância do objeto, ou seja, o primeiro nome do processo na lista.

## PARAMETERS

### -AsString

Indica que este cmdlet usa os dados como uma cadeia de caracteres. Sem esse parâmetro, os dados são tratados como um objeto, portanto, quando você envia uma coleção de objetos do mesmo tipo para `Get-Unique` , como uma coleção de arquivos, ele retorna apenas um (o primeiro). Você pode usar esse parâmetro para localizar os valores exclusivos das propriedades do objeto, como os nomes de arquivo.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AsString
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Especifica a entrada para `Get-Unique` . Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.

Esse cmdlet trata a entrada enviada usando **InputObject** como uma coleção. Ele não enumera itens individuais na coleção. Como a coleção é um único item, a entrada enviada usando **InputObject** é sempre retornada inalterada.

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

### -OnType

Indica que esse cmdlet retorna apenas um objeto de cada tipo.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UniqueByType
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

É possível canalizar qualquer tipo de objeto para `Get-Unique` .

## SAÍDAS

### System. Management. Automation. PSObject

O tipo de objeto que `Get-Unique` retorna é determinado pela entrada.

## OBSERVAÇÕES

Você também pode consultar `Get-Unique` por seu alias interno, `gu` . Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

Para classificar uma lista, utilize o Sort-Object. Você também pode usar o parâmetro **exclusivo** de `Sort-Object` para localizar os itens exclusivos em uma lista.

## LINKS RELACIONADOS

[Select-Object](Select-Object.md)

[Sort-Object](Sort-Object.md)
