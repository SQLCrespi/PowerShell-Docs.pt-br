---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-file?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-File
ms.openlocfilehash: e3a066957ab1e6935049003f8ccf55aee8bb7c94
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595767"
---
# Out-File

## SINOPSE
Envia a saída para um arquivo.

## SYNTAX

### ByPath (padrão)

```
Out-File [-FilePath] <string> [[-Encoding] <Encoding>] [-Append] [-Force] [-NoClobber]
 [-Width <int>] [-NoNewline] [-InputObject <psobject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByLiteralPath

```
Out-File [[-Encoding] <Encoding>] -LiteralPath <string> [-Append] [-Force] [-NoClobber]
 [-Width <int>] [-NoNewline] [-InputObject <psobject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Out-File` cmdlet envia a saída para um arquivo. Ele usa implicitamente o sistema de formatação do PowerShell para gravar no arquivo. O arquivo recebe a mesma representação de exibição que o terminal. Isso significa que a saída pode não ser ideal para processamento programático, a menos que todos os objetos de entrada sejam cadeias de caracteres.
Quando você precisar especificar parâmetros para a saída, use `Out-File` em vez do operador de redirecionamento ( `>` ). Para obter mais informações sobre o redirecionamento, consulte [about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md).

## EXEMPLOS

### Exemplo 1: enviar a saída e criar um arquivo

Este exemplo mostra como enviar uma lista de processos do computador local para um arquivo. Se o arquivo não existir, o `Out-File` criará o arquivo no caminho especificado.

```powershell
Get-Process | Out-File -FilePath .\Process.txt
Get-Content -Path .\Process.txt
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     29    22.39      35.40      10.98   42764   9 Application
     53    99.04     113.96       0.00   32664   0 CcmExec
     27    96.62     112.43     113.00   17720   9 Code
```

O `Get-Process` cmdlet obtém a lista de processos em execução no computador local. Os objetos de **processo** são enviados por meio do pipeline para o `Out-File` cmdlet. `Out-File` usa o parâmetro **FilePath** e cria um arquivo no diretório atual chamado **Process.txt**. O `Get-Content` comando obtém o conteúdo do arquivo e o exibe no console do PowerShell.

### Exemplo 2: impedir que um arquivo existente seja substituído

Este exemplo impede que um arquivo existente seja substituído. Por padrão, o `Out-File` substitui os arquivos existentes.

```powershell
Get-Process | Out-File -FilePath .\Process.txt -NoClobber
```

```Output
Out-File : The file 'C:\Test\Process.txt' already exists.
At line:1 char:15
+ Get-Process | Out-File -FilePath .\Process.txt -NoClobber
+               ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
```

O `Get-Process` cmdlet obtém a lista de processos em execução no computador local. Os objetos de **processo** são enviados por meio do pipeline para o `Out-File` cmdlet. `Out-File` usa o parâmetro **FilePath** e tenta gravar em um arquivo no diretório atual chamado **Process.txt**. O parâmetro **NoClobber** impede que o arquivo seja substituído e exibe uma mensagem informando que o arquivo já existe.

### Exemplo 3: enviar a saída para um arquivo no formato ASCII

Este exemplo mostra como codificar a saída com um tipo de codificação específico.

```powershell
$Procs = Get-Process
Out-File -FilePath .\Process.txt -InputObject $Procs -Encoding ASCII -Width 50
```

O `Get-Process` cmdlet obtém a lista de processos em execução no computador local. Os objetos de **processo** são armazenados na variável, `$Procs` . `Out-File` usa o parâmetro **FilePath** e cria um arquivo no diretório atual chamado **Process.txt**. O parâmetro **InputObject** passa os objetos de processo `$Procs` para o arquivo **Process.txt**. O parâmetro **Encoding** converte a saída para o formato **ASCII** . O parâmetro **Width** limita cada linha no arquivo a 50 caracteres, de modo que alguns dados possam ser truncados.

### Exemplo 4: usar um provedor e enviar a saída para um arquivo

Este exemplo mostra como usar o `Out-File` cmdlet quando você não está em uma unidade do provedor **FileSystem** . Use o `Get-PSProvider` cmdlet para exibir os provedores em seu computador local. Para obter mais informações, consulte [about_Providers](../Microsoft.Powershell.Core/About/about_Providers.md).

```
PS> Set-Location -Path Alias:

PS> Get-Location

Path
----
Alias:\

PS> Get-ChildItem | Out-File -FilePath C:\TestDir\AliasNames.txt

PS> Get-Content -Path C:\TestDir\AliasNames.txt

CommandType     Name
-----------     ----
Alias           % -> ForEach-Object
Alias           ? -> Where-Object
Alias           ac -> Add-Content
Alias           cat -> Get-Content
```

O `Set-Location` comando usa o parâmetro **Path** para definir o local atual como o provedor de registro `Alias:` . O `Get-Location` cmdlet exibe o caminho completo para `Alias:` .
`Get-ChildItem` envia objetos pelo pipeline para o `Out-File` cmdlet. `Out-File` usa o parâmetro **FilePath** para especificar o caminho e o nome de arquivo completos para a saída, **C:\TestDir\AliasNames.txt**. O `Get-Content` cmdlet usa o parâmetro **Path** e exibe o conteúdo do arquivo no console do PowerShell.

## PARAMETERS

### -Acrescentar

Adiciona a saída ao final de um arquivo existente.

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

### -Codificação

Especifica o tipo de codificação para o arquivo de destino. O valor padrão é `utf8NoBOM`.

Os valores aceitáveis para esse parâmetro são os seguintes:

- `ascii`: Usa a codificação para o conjunto de caracteres ASCII (7 bits).
- `bigendianunicode`: Codifica no formato UTF-16 usando a ordem de bytes big-endian.
- `bigendianutf32`: Codifica em formato UTF-32 usando a ordem de byte big-endian.
- `oem`: Usa a codificação padrão para MS-DOS e programas de console.
- `unicode`: Codifica no formato UTF-16 usando a ordem de byte little-endian.
- `utf7`: Codifica em formato UTF-7.
- `utf8`: Codifica em formato UTF-8.
- `utf8BOM`: Codifica em formato UTF-8 com marca de ordem de byte (BOM)
- `utf8NoBOM`: Codifica em formato UTF-8 sem marca de ordem de byte (BOM)
- `utf32`: Codifica no formato UTF-32.

A partir do PowerShell 6,2, o parâmetro de **codificação** também permite IDs numéricas de páginas de código registradas (como `-Encoding 1251` ) ou nomes de cadeia de caracteres de páginas de código registradas (como `-Encoding "windows-1251"` ). Para obter mais informações, consulte a documentação do .NET para [Encoding. CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).

> [!NOTE]
> O **UTF-7** _ não é mais recomendado para uso. No PowerShell 7,1, um aviso será gravado se você especificar `utf7` para o parâmetro _ *Encoding**.

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: 1
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

Especifica o caminho para o arquivo de saída.

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases: Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Substitui o atributo somente leitura e sobrescreve um arquivo somente leitura existente. O parâmetro **Force** não substitui as restrições de segurança.

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

### -InputObject

Especifica os objetos a serem gravados no arquivo. Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.

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

Especifica o caminho para o arquivo de saída. O parâmetro **LiteralPath** é usado exatamente como é digitado.
Caracteres curinga não são aceitos. Se o caminho incluir caracteres de escape, coloque-o entre aspas simples. Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape. Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NoClobber

**NoClobber** impede que um arquivo existente seja substituído e exibe uma mensagem informando que o arquivo já existe. Por padrão, se um arquivo existir no caminho especificado, `Out-File` o substituirá o arquivo sem aviso.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nonovat

Especifica que o conteúdo gravado no arquivo não termina com um caractere de nova linha. As representações de cadeia de caracteres dos objetos de entrada são concatenadas para formar a saída. Nenhum espaço ou novas linhas são inseridas entre as cadeias de caracteres de saída. Nenhuma nova linha é adicionada após a última cadeia de caracteres de saída.

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

### -Largura

Especifica o número de caracteres em cada linha de saída. Quaisquer eventuais caracteres adicionais ficam truncados, não encapsulados. Se esse parâmetro não for usado, a largura será determinada pelas características do host. O padrão para o console do PowerShell é de 80 caracteres.

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

Mostra o que aconteceria se o cmdlet fosse executado. O cmdlet não é executado.

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

### System. Management. Automation. PSObject

Você pode canalizar qualquer objeto para `Out-File` .

## SAÍDAS

### Nenhum

`Out-File` não gera nenhuma saída.

## OBSERVAÇÕES

Os objetos de entrada são formatados automaticamente como seriam no terminal, mas você pode usar um `Format-*` cmdlet para controlar explicitamente a formatação da saída para o arquivo. Por exemplo, `Get-Date | Format-List | Out-File out.txt`

Para enviar a saída de um comando do PowerShell para o `Out-File` cmdlet, use o pipeline. Como alternativa, você pode armazenar dados em uma variável e usar o parâmetro **InputObject** para passar dados para o `Out-File` cmdlet.

`Out-File` salva dados em um arquivo, mas não produz nenhum objeto de saída para o pipeline.

## LINKS RELACIONADOS

[about_Providers](../Microsoft.Powershell.Core/About/about_Providers.md)

[about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[Out-Default](../Microsoft.PowerShell.Core/Out-Default.md)

[Out-Host](../Microsoft.PowerShell.Core/Out-Host.md)

[Out-Null](../Microsoft.PowerShell.Core/Out-Null.md)

[Out-String](Out-String.md)

[Tee-Object](Tee-Object.md)

