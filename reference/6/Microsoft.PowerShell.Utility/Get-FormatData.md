---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-formatdata?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-FormatData
ms.openlocfilehash: afc6253e112bf44ba4f92b726002003cc8b594fc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194481"
---
# Get-FormatData

## SINOPSE
Obtém os dados de formatação na sessão atual.

## SYNTAX

```
Get-FormatData [[-TypeName] <String[]>] [-PowerShellVersion <Version>] [<CommonParameters>]
```

## DESCRIPTION

O `Get-FormatData` cmdlet obtém os dados de formatação na sessão atual.

Os dados de formatação na sessão incluem a formatação de dados de `Format.ps1xml` arquivos de formatação, como aqueles no `$PSHOME` diretório, a formatação de dados para os módulos que você importa para a sessão e a formatação de dados para comandos que você importa para sua sessão usando o `Import-PSSession` cmdlet.

Você pode usar este cmdlet para examinar os dados de formatação. Em seguida, você pode usar o `Export-FormatData` cmdlet para serializar os objetos, convertê-los em XML e salvá-los em `Format.ps1xml` arquivos.

Para obter mais informações sobre como formatar arquivos no PowerShell, consulte [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).

## EXEMPLOS

### Exemplo 1: obter todos os dados de formatação

Este exemplo obtém todos os dados de formatação na sessão.

```powershell
Get-FormatData -PowerShellVersion 5.1
```

> [!IMPORTANT]
> Para garantir que as informações de formatação de tipo completas sejam retornadas, você deve sempre incluir o parâmetro **PowerShellVersion** com o valor `5.1` ao usar uma invocação local de `Get-FormatData` . Se o parâmetro e o valor forem omitidos, você não poderá obter todas as informações de tipo corretas.

### Exemplo 2: obter dados de formatação por nome de tipo

Este exemplo obtém os itens de dados de formatação cujos nomes começam com `System.Management.Automation.Cmd` .

```powershell
Get-FormatData -TypeName 'System.Management.Automation.Cmd*' -PowerShellVersion 5.1
```

### Exemplo 3: examinar um objeto de dados de formatação

Este exemplo mostra como obter um objeto de dados de formatação e examinar suas propriedades.

```powershell
$F = Get-FormatData -TypeName 'System.Management.Automation.Cmd*' -PowerShellVersion 5.1
$F
```

```Output
TypeName        FormatViewDefinition
--------        --------------------
HelpInfoShort   {help , TableControl}
```

```powershell
$F.FormatViewDefinition[0].control
```

```Output
Headers          : {System.Management.Automation.TableControlColumnHeader,
                   System.Management.Automation.TableControlColumnHeader,
                   System.Management.Automation.TableControlColumnHeader,
                   System.Management.Automation.TableControlColumnHeader}
Rows             : {System.Management.Automation.TableControlRow}
AutoSize         : False
HideTableHeaders : False
GroupBy          :
OutOfBand        : False
```

```powershell
$F.FormatViewDefinition[0].control.Headers
```

```Output
Label       Alignment Width
-----       --------- -----
CommandType Undefined    15
Name        Undefined    50
Version     Undefined    10
Source      Undefined     0
```

### Exemplo 4: obter dados de formatação e exportá-los

Este exemplo mostra como usar `Get-FormatData` e `Export-FormatData` para exportar os dados de formatação que são adicionados por um módulo.

```powershell
$A = Get-FormatData -PowerShellVersion 5.1
Import-Module bitstransfer
$B = Get-FormatData -PowerShellVersion 5.1
Compare-Object $A $B
```

```Output
InputObject                                                SideIndicator
-----------                                                -------------
Microsoft.BackgroundIntelligentTransfer.Management.BitsJob =>
```

```powershell
Get-FormatData *bits* | Export-FormatData -FilePath c:\test\bits.format.ps1xml
Get-Content c:\test\bits.format.ps1xml
```

```Output
<?xml version="1.0" encoding="utf-8"?><Configuration><ViewDefinitions>
<View><Name>Microsoft.BackgroundIntelligentTransfer.Management.BitsJob</Name>
...
```

Os primeiros quatro comandos usam os `Get-FormatData` `Import-Module` `Compare-Object` cmdlets, e para identificar o tipo de formato que o módulo **BitsTransfer** adiciona à sessão.

O quinto comando usa o `Get-FormatData` cmdlet para obter o tipo de formato que o módulo **BitsTransfer** adiciona. Ele usa um operador de pipeline ( `|` ) para enviar o objeto de tipo de formato para o `Export-FormatData` cmdlet, que o converte de volta em XML e o salva no `format.ps1xml` arquivo especificado.

O comando final mostra um trecho do `format.ps1xml` conteúdo do arquivo.

### Exemplo 5: obter dados de formatação com base na versão especificada do PowerShell

Este exemplo mostra como usar o `Get-FormatData` para obter dados de formato para uma versão especificada do **TypeName** e do PowerShell.

```powershell
Get-FormatData -TypeName 'Microsoft.Powershell.Utility.FileHash' -PowerShellVersion $PSVersionTable.PSVersion

TypeNames                               FormatViewDefinition
---------                               --------------------
{Microsoft.Powershell.Utility.FileHash} {Microsoft.Powershell.Utility.FileHash}
```

## PARAMETERS

### -PowerShellVersion

Especifique a versão do PowerShell que esse cmdlet obtém para os dados de formatação. Insira um número de dois dígitos separado por um ponto.

Esse parâmetro foi adicionado no PowerShell 5,1 para melhorar a compatibilidade quando computadores remotos que executam versões anteriores do PowerShell.

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TypeName

Especifica os nomes de tipo que esse cmdlet obtém para os dados de formatação.
Insira os nomes de tipo.
Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### System. Management. Automation. ExtendedTypeDefinition

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Export-FormatData](Export-FormatData.md)

[Update-FormatData](Update-FormatData.md)
