---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/update-formatdata?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-FormatData
ms.openlocfilehash: 8e04de16aebc467360c7f9b02de6681ddc3e7ca3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194457"
---
# Update-FormatData

## SINOPSE
Atualiza os dados de formatação na sessão atual.

## SYNTAX

```
Update-FormatData [[-AppendPath] <String[]>] [-PrependPath <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

O `Update-FormatData` cmdlet recarrega os dados de formatação de arquivos de formatação na sessão atual. Esse cmdlet permite que você atualize os dados de formatação sem reiniciar o PowerShell.

Sem parâmetros, `Update-FormatData` o recarrega os arquivos de formatação que ele carregou anteriormente.
Você pode usar os parâmetros de `Update-FormatData` para adicionar novos arquivos de formatação à sessão.

Os arquivos de formatação são arquivos de texto em formato XML com a `format.ps1xml` extensão de nome de arquivo. A formatação de dados nos arquivos define a exibição de objetos do Microsoft .NET Framework presentes na sessão.

Quando o PowerShell é iniciado, ele carrega os dados de formato do código-fonte do PowerShell. No entanto, você pode criar arquivos XML de format.ps1personalizados para atualizar a formatação na sessão atual. Você pode usar `Update-FormatData` o para recarregar os dados de formatação na sessão atual sem reiniciar o PowerShell. Isso é útil para quando você adicionou ou alterou um arquivo de formatação, mas não deseja interromper a sessão.

Para obter mais informações sobre como formatar arquivos no PowerShell, consulte [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).

## EXEMPLOS

### Exemplo 1: recarregar arquivos de formatação carregados anteriormente

```powershell
Update-FormatData
```

Este comando recarrega os arquivos de formatação que havia carregado anteriormente.

### Exemplo 2: recarregar arquivos de formatação e rastreamento e arquivos de formatação de log

```powershell
Update-FormatData -AppendPath "trace.format.ps1xml, log.format.ps1xml"
```

Este comando recarrega os arquivos de formatação para a sessão, incluindo dois novos arquivos: Trace.format.ps1xml e Log.format.ps1xml.

Como o comando usa o parâmetro **AppendPath** , os dados de formatação nos novos arquivos são carregados após os dados de formatação dos arquivos internos.

O parâmetro **AppendPath** é usado porque os novos arquivos contêm dados de formatação para objetos que não são referenciados nos arquivos internos.

### Exemplo 3: editar um arquivo de formatação e recarregá-lo

```powershell
Update-FormatData -PrependPath "c:\test\NewFiles.format.ps1xml"

# Edit the NewFiles.format.ps1 file.

Update-FormatData
```

Este exemplo mostra como recarregar um arquivo formatação após você tê-lo editado.

O primeiro comando adiciona o arquivo NewFiles.format.ps1xml à sessão. Ele usa o parâmetro **PrependPath** porque o arquivo contém dados de formatação para objetos que são referenciados nos arquivos internos.

Depois de adicionar o arquivo XML de NewFiles.format.ps1e testá-lo nessas sessões, o autor editará o arquivo.

O segundo comando usa o `Update-FormatData` cmdlet para recarregar os arquivos de formatação. Como o arquivo XML de NewFiles.format.ps1foi carregado anteriormente, o `Update-FormatData` recarrega automaticamente sem usar parâmetros.

## PARAMETERS

### -AppendPath

Especifica os arquivos de formatação que esse cmdlet adiciona à sessão. Os arquivos são carregados depois que o PowerShell carrega os arquivos de formatação internos.

Ao Formatar objetos .NET, o PowerShell usa a primeira definição de formatação que encontra para cada tipo de .NET. Se você usar o parâmetro **AppendPath** , o PowerShell pesquisará os dados dos arquivos internos antes de encontrar os dados de formatação que você está adicionando.

Use este parâmetro para adicionar um arquivo que formata um objeto .NET que não é referenciado nos arquivos de formatação internos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSPath, Path

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PrependPath

Especifica os arquivos de formatação que esse cmdlet adiciona à sessão. Os arquivos são carregados antes que o PowerShell carregue os arquivos de formatação internos.

Ao Formatar objetos .NET, o PowerShell usa a primeira definição de formatação que encontra para cada tipo de .NET. Se você usar o parâmetro **PrependPath** , o PowerShell pesquisará os dados dos arquivos que você está adicionando antes de encontrar os dados de formatação dos arquivos internos.

Use este parâmetro para adicionar um arquivo que formata um objeto .NET que também é referenciado nos arquivos de formatação internos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Solicita sua confirmação antes de executar o cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Mostra o que aconteceria se o cmdlet fosse executado.
O cmdlet não é executado.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

É possível canalizar uma cadeia de caracteres que contém o caminho de acréscimo para `Update-FormatData` .

## SAÍDAS

### Nenhum

O cmdlet não retorna nenhuma saída.

## OBSERVAÇÕES

- `Update-FormatData` também atualiza os dados de formatação para comandos na sessão que foram importados dos módulos. Se o arquivo de formatação de um módulo for alterado, você poderá executar um `Update-FormatData` comando para atualizar os dados de formatação para comandos importados. Você não precisa importar o módulo novamente.

## LINKS RELACIONADOS

[Get-FormatData](Get-FormatData.md)

[Export-FormatData](Export-FormatData.md)
