---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/join-string?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Join-String
ms.openlocfilehash: 34af5c0f4df5f280233ce96132473ed28ae99ee9
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "103195289"
---
# Join-String

## SINOPSE
Combina objetos do pipeline em uma única cadeia de caracteres.

## SYNTAX

### Padrão (padrão)

```
Join-String [[-Property] <PSPropertyExpression>] [[-Separator] <String>] [-OutputPrefix <String>]
 [-OutputSuffix <String>] [-UseCulture] [-InputObject <PSObject[]>] [<CommonParameters>]
```

### SingleQuote

```
Join-String [[-Property] <PSPropertyExpression>] [[-Separator] <String>] [-OutputPrefix <String>]
 [-OutputSuffix <String>] [-SingleQuote] [-UseCulture] [-InputObject <PSObject[]>]
 [<CommonParameters>]
```

### DoubleQuote

```
Join-String [[-Property] <PSPropertyExpression>] [[-Separator] <String>] [-OutputPrefix <String>]
 [-OutputSuffix <String>] [-DoubleQuote] [-UseCulture] [-InputObject <PSObject[]>]
 [<CommonParameters>]
```

### Formatar

```
Join-String [[-Property] <PSPropertyExpression>] [[-Separator] <String>] [-OutputPrefix <String>]
 [-OutputSuffix <String>] [-FormatString <String>] [-UseCulture] [-InputObject <PSObject[]>]
 [<CommonParameters>]
```

## DESCRIPTION

O `Join-String` cmdlet une ou combina texto de objetos de pipeline em uma única cadeia de caracteres.

Se nenhum parâmetro for especificado, os objetos de pipeline serão convertidos em uma cadeia de caracteres e Unidos com o separador padrão `$OFS` .

Ao especificar um nome de propriedade, o valor da propriedade é convertido em uma cadeia de caracteres e Unido a uma cadeia de caracteres.

Em vez de um nome de propriedade, um bloco de script pode ser usado. O resultado do bloco de script é convertido em uma cadeia de caracteres antes de ser associado para formar o resultado. Ele pode combinar o texto da propriedade de um objeto ou o resultado do objeto que foi convertido em uma cadeia de caracteres.

Esse cmdlet foi introduzido no PowerShell 6,2.

## EXEMPLOS

### Exemplo 1: unir nomes de diretório

<!-- markdownlint-disable MD038 -->
Este exemplo une nomes de diretório, encapsula a saída entre aspas duplas e separa os nomes de diretório com uma vírgula e um espaço ( `, ` ). A saída é um objeto de cadeia de caracteres.

```powershell
Get-ChildItem -Directory C:\ | Join-String -Property Name -DoubleQuote -Separator ', '
```

```Output
"PerfLogs", "Program Files", "Program Files (x86)", "Users", "Windows"
```

`Get-ChildItem` usa o parâmetro **Directory** para obter todos os nomes de diretório para a `C:\` unidade.
Os objetos são enviados ao pipeline para `Join-String` . O parâmetro **Property** especifica os nomes de diretório. O parâmetro **DoubleQuote** encapsula os nomes de diretório com aspas duplas.
O parâmetro **Separator** especifica a utilização de uma vírgula e um espaço ( `, ` ) para separar os nomes de diretório.

Os `Get-ChildItem` objetos são **System. IO. DirectoryInfo** e `Join-String` converte os objetos em **System. String**.

### Exemplo 2: usar uma subcadeia de caracteres de propriedade para unir nomes de diretório

Este exemplo usa um método substring para obter as primeiras quatro letras de nomes de diretório, encapsula a saída em aspas simples e separa os nomes de diretório com um ponto-e-vírgula ( `;` ).

```powershell
Get-ChildItem -Directory C:\ | Join-String -Property {$_.Name.SubString(0,4)} -SingleQuote -Separator ';'
```

```Output
'Perf';'Prog';'Prog';'User';'Wind'
```

`Get-ChildItem` usa o parâmetro **Directory** para obter todos os nomes de diretório para a `C:\` unidade.
Os objetos são enviados ao pipeline para `Join-String` .

O bloco de script de parâmetro de **Propriedade** usa variável automática ( `$_` ) para especificar a subcadeia de caracteres de propriedade de **nome** de cada objeto. A subcadeia de caracteres Obtém as primeiras quatro letras de cada nome de diretório. A subcadeia de caracteres especifica as posições de início e término do caractere. O parâmetro **SingleQuote** encapsula os nomes de diretório com marcas de aspas simples. O parâmetro **Separator** especifica o uso de um ponto e vírgula ( `;` ) para separar os nomes de diretório.

Para obter mais informações sobre variáveis automáticas e subcadeias de caracteres, consulte [about_Automatic_Variables](../microsoft.powershell.core/about/about_automatic_variables.md) e [substring](/dotnet/api/system.string.substring).

### Exemplo 3: exibir a saída de junção em uma linha separada

Este exemplo une nomes de serviço a cada serviço em uma linha separada e recuado por uma guia.

```powershell
Get-Service -Name se* | Join-String -Property Name -Separator "`r`n`t" -OutputPrefix "Services:`n`t"
```

```Output
Services:
    seclogon
    SecurityHealthService
    SEMgrSvc
    SENS
    Sense
    SensorDataService
    SensorService
    SensrSvc
    SessionEnv
```

`Get-Service` usa o parâmetro **Name** com para especificar serviços que começam com `se*` . O asterisco ( `*` ) é um curinga para qualquer caractere.

Os objetos são enviados ao pipeline para o `Join-String` que usa o parâmetro **Property** para especificar os nomes de serviço. O parâmetro **Separator** especifica três caracteres especiais que representam um retorno de carro ( `` `r `` ), nova linha ( `` `n `` ) e tabulação ( `` `t `` ). O **OutputPrefix** insere um rótulo **Serviços:** com uma nova linha e uma guia antes da primeira linha de saída.

Para obter mais informações sobre caracteres especiais, consulte [about_special_characters](..//microsoft.powershell.core/about/about_special_characters.md).

### Exemplo 4: criar uma definição de classe a partir de um objeto

Este exemplo gera uma definição de classe do PowerShell usando um objeto existente como modelo.

Este exemplo de código usa nivelamento para reduzir o tamanho da linha e melhorar a legibilidade. Para obter mais informações, consulte [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).

```powershell
$obj = [pscustomobject] @{Name = "Joe"; Age = 42}
$parms = @{
  Property = "Name"
  FormatString = '  ${0}'
  OutputPrefix = "class {`n"
  OutputSuffix = "`n}`n"
  Separator = "`n"
}
$obj.PSObject.Properties | Join-String @parms
```

```Output
class {
  $Name
  $Age
}
```

## PARAMETERS

### -DoubleQuote

Encapsula o valor da cadeia de caracteres de cada objeto de pipeline em aspas duplas.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DoubleQuote
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -FormatString

Uma cadeia de caracteres de formato que especifica como cada item deve ser formatado.

```yaml
Type: System.String
Parameter Sets: Format
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Especifica o texto a ser Unido. Insira uma variável que contenha o texto ou digite um comando ou uma expressão que obtenha os objetos para ingressar em cadeias de caracteres.

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -OutputPrefix

Texto que é inserido antes da cadeia de caracteres de saída. A cadeia de caracteres pode conter caracteres especiais, como retorno de carro ( `` `r `` ), nova linha ( `` `n `` ) e tabulação ( `` `t `` ).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: op

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputSuffix

O texto que é anexado à cadeia de caracteres de saída. A cadeia de caracteres pode conter caracteres especiais, como retorno de carro ( `` `r `` ), nova linha ( `` `n `` ) e tabulação ( `` `t `` ).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: os

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Propriedade

O nome de uma propriedade ou uma expressão de propriedade que projetará o objeto de pipeline em texto.

```yaml
Type: Microsoft.PowerShell.Commands.PSPropertyExpression
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Separador

Texto ou caracteres como uma vírgula ou ponto e vírgula que é inserido entre o texto de cada objeto de pipeline.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SingleQuote

Encapsula o valor da cadeia de caracteres de cada objeto de pipeline entre aspas simples.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SingleQuote
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseCulture

Usa o separador de lista para a cultura atual como o delimitador de item. Para localizar o separador de lista para uma cultura, use o seguinte comando: `(Get-Culture).TextInfo.ListSeparator` .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Management. Automation. PSObject

## SAÍDAS

### System.String

## OBSERVAÇÕES

## LINKS RELACIONADOS

[about_Automatic_Variables](../microsoft.powershell.core/about/about_automatic_variables.md)

[about_Special_Characters](..//microsoft.powershell.core/about/about_special_characters.md)

[Subcadeia](/dotnet/api/system.string.substring)

