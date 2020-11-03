---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/29/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-string?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-String
ms.openlocfilehash: 16dc25e3468eaf3126b3286cfd71bfea9627c015
ms.sourcegitcommit: c8d1ffeab215e74e87ea1b0af8cd606c1a6a80ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2020
ms.locfileid: "93195366"
---
# Out-String

## SINOPSE
Gera objetos de entrada como cadeias de caracteres.

## SYNTAX

### NoNewLineFormatting (padrão)

```
Out-String [-Width <Int32>] [-NoNewline] [-InputObject <PSObject>] [<CommonParameters>]
```

### StreamFormatting

```
Out-String [-Stream] [-Width <Int32>] [-InputObject <PSObject>] [<CommonParameters>]
```

## DESCRIPTION

O `Out-String` cmdlet converte objetos de entrada em cadeias de caracteres. Por padrão, `Out-String` o acumula as cadeias de caracteres e as retorna como uma única cadeia de caracteres, mas você pode usar o parâmetro **Stream** para direcionar `Out-String` para retornar uma linha de cada vez ou criar e matriz de cadeias de caracteres. Esse cmdlet permite pesquisar e manipular a saída da cadeia de caracteres como faria em shells tradicionais quando a manipulação de objetos for menos conveniente.

## EXEMPLOS

### Exemplo 1: obter a cultura atual e converter os dados em cadeias de caracteres

Este exemplo obtém as configurações regionais para o usuário atual e converte os dados do objeto em cadeias de caracteres.

```powershell
$C = Get-Culture | Select-Object -Property *
Out-String -InputObject $C -Width 100
```

```Output
Parent                         : en
LCID                           : 1033
KeyboardLayoutId               : 1033
Name                           : en-US
IetfLanguageTag                : en-US
DisplayName                    : English (United States)
NativeName                     : English (United States)
EnglishName                    : English (United States)
TwoLetterISOLanguageName       : en
ThreeLetterISOLanguageName     : eng
ThreeLetterWindowsLanguageName : ENU
CompareInfo                    : CompareInfo - en-US
TextInfo                       : TextInfo - en-US
IsNeutralCulture               : False
CultureTypes                   : SpecificCultures, InstalledWin32Cultures, FrameworkCultures
NumberFormat                   : System.Globalization.NumberFormatInfo
DateTimeFormat                 : System.Globalization.DateTimeFormatInfo
Calendar                       : System.Globalization.GregorianCalendar
OptionalCalendars              : {System.Globalization.GregorianCalendar,
                                 System.Globalization.GregorianCalendar}
UseUserOverride                : True
IsReadOnly                     : False
```

A `$C` variável armazena um **Selected.System. Objeto Globalization. CultureInfo** . O objeto é o resultado do `Get-Culture` envio da saída para baixo do pipeline para `Select-Object` . O parâmetro **Property** usa um curinga asterisco ( `*` ) para especificar que todas as propriedades estão contidas no objeto.

`Out-String` usa o parâmetro **InputObject** para especificar o objeto **CultureInfo** armazenado na `$C` variável. Os objetos no `$C` são convertidos em uma cadeia de caracteres.

> [!NOTE]
> Para exibir a `Out-String` matriz, armazene a saída em uma variável e use um índice de matriz para exibir os elementos. Para obter mais informações sobre o índice de matriz, consulte [about_Arrays](../microsoft.powershell.core/about/about_arrays.md).
>
> `$str = Out-String -InputObject $C -Width 100`

### Exemplo 2: trabalhando com objetos

Este exemplo demonstra a diferença entre trabalhar com objetos e trabalhar com cadeias de caracteres. O comando exibe um alias que inclui o texto **GCM** , o alias para `Get-Command` .

```powershell
Get-Alias | Out-String -Stream | Select-String -Pattern "gcm"
```

```Output
Alias           gcm -> Get-Command
```

`Get-Alias` Obtém os objetos **System. Management. Automation. AliasInfo** , um para cada alias e envia os objetos por meio do pipeline. `Out-String` usa o parâmetro **Stream** para converter cada objeto em uma cadeia de caracteres, em vez de concatenar todos os objetos em uma única cadeia de caracteres. Os objetos **System. String** são enviados pelo pipeline e `Select-String` usam o parâmetro **Pattern** para localizar correspondências para o texto **GCM** .

> [!NOTE]
> Se você omitir o parâmetro de **fluxo** , o comando exibirá todos os aliases, pois `Select-String` localiza o texto **GCM** na cadeia de caracteres única que `Out-String` retorna.

### Exemplo 3: Use o parâmetro Width para evitar truncamento.

Embora a maior parte da saída `Out-String` seja encapsulada na próxima linha, há cenários em que a saída é truncada pelo sistema de formatação antes de ser passada para `Out-String` . Você pode evitar o truncamento usando o parâmetro **Width** .

```powershell
PS> @{TestKey = ('x' * 200)} | Out-String
Name                           Value
----                           -----
TestKey                        xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx...

PS> @{TestKey = ('x' * 200)} | Out-String -Width 250

Name                           Value
----                           -----
TestKey                        xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

## PARAMETERS

### -InputObject

Especifica os objetos a serem gravados em uma cadeia de caracteres. Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.

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

### -Nonovat

Remove todas as novas linhas da saída geradas pelo formatador do PowerShell. Novas linhas que fazem parte dos objetos de cadeia de caracteres são preservadas.

Esse parâmetro foi introduzido no PowerShell 6,0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NoNewLineFormatting
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Fluxo

Indica que o cmdlet envia uma cadeia de caracteres separada para cada linha de um objeto de entrada. Por padrão, as cadeias de caracteres para cada objeto são acumuladas e enviadas como uma única cadeia de caracteres.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: StreamFormatting
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Largura

Especifica o número de caracteres em cada linha de saída. Quaisquer caracteres adicionais são encapsulados na próxima linha ou truncados, dependendo do cmdlet do formatador usado. O parâmetro **Width** aplica-se somente a objetos que estão sendo formatados. Se você omitir esse parâmetro, a largura será determinada pelas características do programa host. Em janelas de terminal (console), a largura da janela atual é usada como o valor padrão. O console do PowerShell Windows tem como padrão uma largura de 80 caracteres na instalação.

```yaml
Type: System.Int32
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

Você pode enviar objetos pelo pipeline para o `Out-String` .

## SAÍDAS

### System.String

`Out-String` Retorna a cadeia de caracteres que ele cria do objeto de entrada.

## OBSERVAÇÕES

Os cmdlets que contêm o `Out` verbo não formatam objetos. Os `Out` cmdlets enviam objetos para o formatador para o destino de exibição especificado.

## LINKS RELACIONADOS

[about_Formatting](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md)

[Out-Default](../Microsoft.PowerShell.Core/Out-Default.md)

[Out-File](Out-File.md)

[Out-Host](../Microsoft.PowerShell.Core/Out-Host.md)

[Out-Null](../Microsoft.PowerShell.Core/Out-Null.md)

[Out-GridView](Out-GridView.md)

[Out-Printer](Out-Printer.md)

