---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-content?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Content
ms.openlocfilehash: d21765541fb849aed8dc37895c167c0ea34486a3
ms.sourcegitcommit: bf07cffb2a66dec94bf3576e197090f958701f18
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "97692832"
---
# Set-Content

## SINOPSE
Grava novo conteúdo ou substitui o conteúdo existente em um arquivo.

## SYNTAX

### Caminho (padrão)

```
Set-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>]
 [-WhatIf] [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

### LiteralPath

```
Set-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>]
 [-WhatIf] [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

## DESCRIPTION

`Set-Content` é um cmdlet de processamento de cadeia de caracteres que grava novo conteúdo ou substitui o conteúdo em um arquivo. `Set-Content` Substitui o conteúdo existente e difere do `Add-Content` cmdlet que acrescenta o conteúdo a um arquivo. Para enviar conteúdo para `Set-Content` você pode usar o parâmetro **Value** na linha de comando ou enviar conteúdo por meio do pipeline.

Se você precisar criar arquivos ou diretórios para os exemplos a seguir, consulte [New-Item](New-Item.md).

## EXEMPLOS

### Exemplo 1: substituir o conteúdo de vários arquivos em um diretório

Este exemplo substitui o conteúdo de vários arquivos no diretório atual.

```powershell
Get-ChildItem -Path .\Test*.txt
```

```Output
Test1.txt
Test2.txt
Test3.txt
```

```powershell
Set-Content -Path .\Test*.txt -Value 'Hello, World'
Get-Content -Path .\Test*.txt
```

```Output
Hello, World
Hello, World
Hello, World
```

O `Get-ChildItem` cmdlet usa o parâmetro **Path** para listar arquivos **. txt** que começam com `Test*` no diretório atual. O `Set-Content` cmdlet usa o parâmetro **Path** para especificar os `Test*.txt` arquivos. O parâmetro **Value** fornece a cadeia de caracteres de texto **Olá, mundo** que substitui o conteúdo existente em cada arquivo. O `Get-Content` cmdlet usa o parâmetro **Path** para especificar os `Test*.txt` arquivos e exibe o conteúdo de cada arquivo no console do PowerShell.

### Exemplo 2: criar um novo arquivo e gravar o conteúdo

Este exemplo cria um novo arquivo e grava a data e hora atuais no arquivo.

```powershell
Set-Content -Path .\DateTime.txt -Value (Get-Date)
Get-Content -Path .\DateTime.txt
```

```Output
1/30/2019 09:55:08
```

`Set-Content` usa os parâmetros **Path** e **Value** para criar um novo arquivo chamado **DateTime.txt** no diretório atual. O parâmetro **Value** usa `Get-Date` para obter a data e a hora atuais.
`Set-Content` grava o objeto **DateTime** no arquivo como uma cadeia de caracteres. O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o conteúdo de **DateTime.txt** no console do PowerShell.

### Exemplo 3: substituir o texto em um arquivo

Esse comando substitui todas as instâncias do Word em um arquivo existente.

```powershell
Get-Content -Path .\Notice.txt
```

```Output
Warning
Replace Warning with a new word.
The word Warning was replaced.
```

```powershell
(Get-Content -Path .\Notice.txt) |
    ForEach-Object {$_ -Replace 'Warning', 'Caution'} |
        Set-Content -Path .\Notice.txt
Get-Content -Path .\Notice.txt
```

```Output
Caution
Replace Caution with a new word.
The word Caution was replaced.
```

O `Get-Content` cmdlet usa o parâmetro **Path** para especificar o arquivo de **Notice.txt** no diretório atual. O `Get-Content` comando é encapsulado com parênteses para que o comando seja concluído antes de ser enviado ao pipeline.

O conteúdo do arquivo de **Notice.txt** é enviado ao pipeline para o `ForEach-Object` cmdlet.
`ForEach-Object` usa a variável automática `$_` e substitui cada ocorrência de **Warning** por **cuidado**. Os objetos são enviados para o pipeline para o `Set-Content` cmdlet. `Set-Content` usa o parâmetro **path** para especificar o arquivo de **Notice.txt** e grava o conteúdo atualizado no arquivo.

O último `Get-Content` cmdlet exibe o conteúdo do arquivo atualizado no console do PowerShell.

### Exemplo 4: usar filtros com Set-Content

Você pode especificar um filtro para o `Set-Content` cmdlet. Ao usar filtros para qualificar o parâmetro de **caminho** , você precisa incluir um asterisco à direita ( `*` ) para indicar o conteúdo do caminho.

O comando a seguir define o conteúdo todos os `*.txt` arquivos no `C:\Temp` diretório para o **valor** vazio.

```powershell
Set-Content -Path C:\Temp\* -Filter *.txt -Value "Empty"
```

## PARAMETERS

### -AsByteStream

Especifica que o conteúdo deve ser lido como um fluxo de bytes. Esse parâmetro foi introduzido no PowerShell 6,0.

Um aviso ocorre quando você usa o parâmetro **AsByteStream** com o parâmetro **Encoding** . O parâmetro **AsByteStream** ignora qualquer codificação e a saída é retornada como um fluxo de bytes.

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

### -Credential

> [!NOTE]
> Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.
> Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Codificação

Especifica o tipo de codificação para o arquivo de destino. O valor padrão é `utf8NoBOM`.

A codificação é um parâmetro dinâmico que o provedor FileSystem adiciona `Set-Content` . Esse parâmetro funciona somente em unidades de sistema de arquivos.

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
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### -Excluir

Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação. O valor deste parâmetro qualifica o parâmetro **Path**. Insira um elemento ou padrão de caminho, como `*.txt` . Caracteres curinga são permitidos. O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Filter

Especifica um filtro para qualificar o parâmetro **path** . O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros. Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).
Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Force

Força o cmdlet a definir o conteúdo de um arquivo, mesmo se o arquivo for somente leitura. A implementação varia de provedor para provedor. Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).
O parâmetro **Force** não substitui as restrições de segurança.

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

### -Incluir

Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação. O valor deste parâmetro qualifica o parâmetro **Path**. Insira um elemento ou padrão de caminho, como `"*.txt"` . Caracteres curinga são permitidos. O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -LiteralPath

Especifica um caminho para um ou mais locais. O valor de **LiteralPath** é usado exatamente como é digitado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres de escape, coloque-o entre aspas simples. Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nonovat

As representações de cadeia de caracteres dos objetos de entrada são concatenadas para formar a saída. Nenhum espaço ou novas linhas são inseridas entre as cadeias de caracteres de saída. Nenhuma nova linha é adicionada após a última cadeia de caracteres de saída.

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

### -PassThru

Retorna um objeto que representa o conteúdo. Por padrão, este cmdlet não gera saída.

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

### -Path

Especifica o caminho do item que recebe o conteúdo.
Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Fluxo

> [!NOTE]
> Esse parâmetro só está disponível no Windows.

Especifica um fluxo de dados alternativo para o conteúdo. Se o fluxo não existir, esse cmdlet o criará. Não há suporte para caracteres curinga.

**Stream** é um parâmetro dinâmico que o provedor **FileSystem** adiciona `Set-Content` . Esse parâmetro funciona somente em unidades de sistema de arquivos.

Você pode usar o `Set-Content` cmdlet para criar ou atualizar o conteúdo de qualquer fluxo de dados alternativo, como `Zone.Identifier` . No entanto, não recomendamos isso como uma maneira de eliminar verificações de segurança que bloqueiam arquivos baixados da Internet. Se você verificar se um arquivo baixado é seguro, use o `Unblock-File` cmdlet.

Esse parâmetro foi introduzido no PowerShell 3,0.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value

Especifica o novo conteúdo para o item.

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### System.Object

É possível canalizar um objeto que contém o novo valor para o item para `Set-Content` .

## SAÍDAS

### Nenhum ou System.String

Quando você usa o parâmetro **PassThru** , o `Set-Content` gera um objeto **System. String** que representa o conteúdo. Caso contrário, este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

- Você também pode consultar `Set-Content` por seu alias interno, `sc` .
  Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).
- `Set-Content` é projetado para processamento de cadeia de caracteres. Se você canaliza objetos que não são de cadeia de caracteres para `Set-Content` , ele converte o objeto em uma cadeia de caracteres antes de gravá-lo. Para gravar objetos em arquivos, use `Out-File` .
- O `Set-Content` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor. Para listar os provedores disponíveis em sua sessão, digite `Get-PsProvider` . Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## LINKS RELACIONADOS

[about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[about_Automatic_Variables. MD](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[Add-Content](Add-Content.md)

[Clear-Content](Clear-Content.md)

[Get-ChildItem](Get-ChildItem.md)

[Get-Content](Get-Content.md)

[ForEach-Object](../Microsoft.PowerShell.Core/ForEach-Object.md)

[New-Item](New-Item.md)
