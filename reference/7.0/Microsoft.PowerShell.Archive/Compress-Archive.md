---
external help file: Microsoft.PowerShell.Archive-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Archive
ms.date: 02/20/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.archive/compress-archive?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Compress-Archive
ms.openlocfilehash: 1d5379b22cbc9f501d8fdf50da76d82f1122897b
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93193069"
---
# Compress-Archive

## SINOPSE
Cria um arquivo morto compactado, ou compactado, de arquivos e diretórios especificados.

## SYNTAX

### Caminho (padrão)

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### PathWithUpdate

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>] -Update
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### PathWithForce

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>] -Force
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### LiteralPathWithUpdate

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 -Update [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### LiteralPathWithForce

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 -Force [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### LiteralPath

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Compress-Archive` cmdlet cria um arquivo morto compactado, ou zipado, de um ou mais arquivos ou diretórios especificados. Um arquivo compacta vários arquivos, com compactação opcional, em um único arquivos zipados para distribuição e armazenamento mais fáceis. Um arquivo morto pode ser compactado usando o algoritmo de compactação especificado pelo parâmetro **CompressionLevel** .

O `Compress-Archive` cmdlet usa o arquivo de API Microsoft .NET [System.IO.Compression.Zip](/dotnet/api/system.io.compression.ziparchive) para compactar arquivos.
O tamanho máximo do arquivo é 2 GB, pois há uma limitação da API subjacente.

Alguns exemplos usam nivelamento para reduzir o tamanho da linha dos exemplos de código. Para obter mais informações, consulte [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).

## EXEMPLOS

### Exemplo 1: compactar arquivos para criar um arquivo morto

Este exemplo compacta arquivos de diretórios diferentes e cria um arquivo morto. Um caractere curinga é usado para obter todos os arquivos com uma extensão de arquivo específica. Não há nenhuma estrutura de diretório no arquivo morto porque o **caminho** especifica apenas nomes de arquivo.

```powershell
$compress = @{
  Path = "C:\Reference\Draftdoc.docx", "C:\Reference\Images\*.vsd"
  CompressionLevel = "Fastest"
  DestinationPath = "C:\Archives\Draft.Zip"
}
Compress-Archive @compress
```

O parâmetro **path** aceita nomes de arquivo e nomes de arquivo específicos com curingas, `*.vsd` . O **caminho** usa uma lista separada por vírgulas para obter arquivos de diretórios diferentes. O nível de compactação é **mais rápido** para reduzir o tempo de processamento. O parâmetro **DestinationPath** especifica o local para o `Draft.zip` arquivo. O `Draft.zip` arquivo contém `Draftdoc.docx` e todos os arquivos com uma `.vsd` extensão.

### Exemplo 2: compactar arquivos usando um LiteralPath

Este exemplo compacta arquivos nomeados específicos e cria um novo arquivo morto. Não há nenhuma estrutura de diretório no arquivo morto porque o **caminho** especifica apenas nomes de arquivo.

```powershell
$compress = @{
LiteralPath= "C:\Reference\Draft Doc.docx", "C:\Reference\Images\diagram2.vsd"
CompressionLevel = "Fastest"
DestinationPath = "C:\Archives\Draft.Zip"
}
Compress-Archive @compress
```

O caminho absoluto e os nomes de arquivo são usados porque o parâmetro **LiteralPath** não aceita curingas. O **caminho** usa uma lista separada por vírgulas para obter arquivos de diretórios diferentes. O nível de compactação é **mais rápido** para reduzir o tempo de processamento. O parâmetro **DestinationPath** especifica o local para o `Draft.zip` arquivo. O `Draft.zip` arquivo contém apenas `Draftdoc.docx` e `diagram2.vsd` .

### Exemplo 3: compactar um diretório que inclui o diretório raiz

Este exemplo compacta um diretório e cria um arquivo morto que **inclui** o diretório raiz e todos os seus arquivos e subdiretórios. O arquivo morto tem uma estrutura de diretório porque o **caminho** especifica um diretório raiz.

```powershell
Compress-Archive -Path C:\Reference -DestinationPath C:\Archives\Draft.zip
```

`Compress-Archive` usa o parâmetro **path** para especificar o diretório raiz, `C:\Reference` . O parâmetro **DestinationPath** especifica o local para o arquivo morto. O `Draft.zip` arquivo morto inclui o `Reference` diretório raiz e todos os seus arquivos e subdiretórios.

### Exemplo 4: compactar um diretório que exclui o diretório raiz

Este exemplo compacta um diretório e cria um arquivo morto que **exclui** o diretório raiz porque o **caminho** usa um curinga asterisco ( `*` ). O arquivo contém uma estrutura de diretório que contém os arquivos e subdiretórios do diretório raiz.

```powershell
Compress-Archive -Path C:\Reference\* -DestinationPath C:\Archives\Draft.zip
```

`Compress-Archive` usa o parâmetro **path** para especificar o diretório raiz, `C:\Reference` com um curinga asterisco ( `*` ). O parâmetro **DestinationPath** especifica o local para o arquivo morto. O `Draft.zip` arquivo contém os arquivos e subdiretórios do diretório raiz. O `Reference` diretório raiz é excluído do arquivo morto.

### Exemplo 5: compactar apenas os arquivos em um diretório raiz

Este exemplo compacta apenas os arquivos em um diretório raiz e cria um arquivo morto. Não há nenhuma estrutura de diretório no arquivo porque apenas os arquivos são compactados.

```powershell
Compress-Archive -Path C:\Reference\*.* -DestinationPath C:\Archives\Draft.zip
```

`Compress-Archive` usa o parâmetro **path** para especificar o diretório raiz, `C:\Reference` com um curinga **asterisco-ponto-asterisco** ( `*.*` ). O parâmetro **DestinationPath** especifica o local para o arquivo morto. O `Draft.zip` arquivo morto contém apenas os `Reference` arquivos do diretório raiz e o diretório raiz é excluído.

### Exemplo 6: usar o pipeline para arquivar arquivos

Este exemplo envia arquivos para baixo do pipeline para criar um arquivo morto. Não há nenhuma estrutura de diretório no arquivo morto porque o **caminho** especifica apenas nomes de arquivo.

```powershell
Get-ChildItem -Path C:\Reference\Afile.txt, C:\Reference\Images\Bfile.txt |
  Compress-Archive -DestinationPath C:\Archives\PipelineFiles.zip
```

`Get-ChildItem` usa o parâmetro **path** para especificar dois arquivos de diretórios diferentes. Cada arquivo é representado por um objeto **FileInfo** e é enviado ao pipeline para `Compress-Archive` .
Os dois arquivos especificados são arquivados no `PipelineFiles.zip` .

### Exemplo 7: usar o pipeline para arquivar um diretório

Este exemplo envia um diretório para baixo do pipeline para criar um arquivo morto. Os arquivos são enviados como objetos **FileInfo** e diretórios como objetos **DirectoryInfo** . A estrutura de diretório do arquivo morto não inclui o diretório raiz, mas seus arquivos e subdiretórios estão incluídos no arquivo morto.

```powershell
Get-ChildItem -Path C:\LogFiles | Compress-Archive -DestinationPath C:\Archives\PipelineDir.zip
```

`Get-ChildItem` usa o parâmetro **path** para especificar o `C:\LogFiles` diretório raiz. Cada objeto **FileInfo** e **DirectoryInfo** é enviado pelo pipeline.

`Compress-Archive` Adiciona cada objeto ao `PipelineDir.zip` arquivo morto. O parâmetro **path** não foi especificado porque os objetos de pipeline são recebidos na posição de parâmetro 0.

### Exemplo 8: como a recursão pode afetar os arquivos mortos

Este exemplo mostra como a recursão pode duplicar arquivos em seu arquivo morto. Por exemplo, se você usar `Get-ChildItem` com o parâmetro **recurse** . Como processos de recursão, cada objeto **FileInfo** e **DirectoryInfo** é enviado pelo pipeline e adicionado ao arquivo morto.

```powershell
Get-ChildItem -Path C:\TestLog -Recurse |
  Compress-Archive -DestinationPath C:\Archives\PipelineRecurse.zip
```

O `C:\TestLog` diretório não contém nenhum arquivo. Ele contém um subdiretório chamado `testsub` que contém o `testlog.txt` arquivo.

`Get-ChildItem` usa o parâmetro **path** para especificar o diretório raiz, `C:\TestLog` . O parâmetro **recurse** processa os arquivos e diretórios. Um objeto **DirectoryInfo** é criado para `testsub` e um objeto **FileInfo** `testlog.txt` .

Cada objeto é enviado ao pipeline para `Compress-Archive` . O **DestinationPath** especifica o local para o arquivo morto. O parâmetro **path** não foi especificado porque os objetos de pipeline são recebidos na posição de parâmetro 0.

O resumo a seguir descreve o `PipelineRecurse.zip` conteúdo do arquivo morto que contém um arquivo duplicado:

- O objeto **DirectoryInfo** cria o `testsub` diretório e contém o `testlog.txt` arquivo, que reflete a estrutura do diretório original.
- O objeto **FileInfo** cria uma duplicata `testlog.txt` na raiz do arquivo. O arquivo duplicado é criado porque a recursão enviou um objeto de arquivo para `Compress-Archive` . Esse comportamento é esperado porque cada objeto enviado pelo pipeline é adicionado ao arquivo morto.

### Exemplo 9: atualizar um arquivo morto existente

Este exemplo atualiza um arquivo morto existente, `Draft.Zip` , no `C:\Archives` diretório. Neste exemplo, o arquivo morto existente contém o diretório raiz e seus arquivos e subdiretórios.

```powershell
Compress-Archive -Path C:\Reference -Update -DestinationPath C:\Archives\Draft.Zip
```

O comando é atualizado `Draft.Zip` com versões mais recentes de arquivos existentes no `C:\Reference` diretório e em seus subdiretórios. E novos arquivos que foram adicionados ao `C:\Reference` ou seus subdiretórios estão incluídos no `Draft.Zip` arquivo atualizado.

## PARAMETERS

### -CompressionLevel

Especifica a quantidade de compactação a ser aplicada quando você estiver criando o arquivo morto. A compactação mais rápida requer menos tempo para criar o arquivo, mas pode resultar em tamanhos de arquivo maiores.

Se esse parâmetro não for especificado, o comando usará o valor padrão, **ideal** .

Estes são os valores aceitáveis para esse parâmetro:

- **Mais rápido** . Use o método de compactação mais rápido disponível para reduzir o tempo de processamento. A compactação mais rápida pode resultar em tamanhos de arquivo maiores.
- **NoCompression** . Não compacta os arquivos de origem.
- **Ideal** . O tempo de processamento depende do tamanho do arquivo.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Optimal, NoCompression, Fastest

Required: False
Position: Named
Default value: Optimal
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

### -DestinationPath

Esse parâmetro é necessário e especifica o caminho para o arquivo de saída de arquivamento. O **DestinationPath** deve incluir o nome do arquivo compactado e o caminho absoluto ou relativo para o arquivo compactado.

Se o nome do arquivo em **DestinationPath** não tiver uma `.zip` extensão de nome de arquivo, o cmdlet adicionará a `.zip` extensão de nome de arquivo.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Força o comando a ser executado sem solicitar a confirmação do usuário.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PathWithForce, LiteralPathWithForce
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -LiteralPath

Especifica o caminho ou caminhos para os arquivos que você deseja adicionar ao arquivo compactado de arquivamento. Ao contrário do parâmetro **path** , o valor de **LiteralPath** é usado exatamente como é digitado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres de escape, coloque cada caractere de escape entre aspas simples, para instruir o PowerShell a não interpretar nenhum caractere como sequências de escape.
Para especificar vários caminhos e incluir arquivos em vários locais em seu arquivo compactado de saída, use vírgulas para separar os caminhos.

```yaml
Type: System.String[]
Parameter Sets: LiteralPathWithUpdate, LiteralPathWithForce, LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Faz com que o cmdlet gere um objeto de arquivo que representa o arquivo morto criado.

Esse parâmetro foi introduzido no PowerShell 6,0.

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

### -Path

Especifica o caminho ou caminhos para os arquivos que você deseja adicionar ao arquivo compactado de arquivamento. Para especificar vários caminhos e incluir arquivos em vários locais, use vírgulas para separar os caminhos.

Esse parâmetro aceita caracteres curinga. Os caracteres curinga permitem que você adicione todos os arquivos em um diretório ao arquivo morto.

O uso de caracteres curinga com um diretório raiz afeta o conteúdo do arquivo:

- Para criar um arquivo que **inclui** o diretório raiz e todos os seus arquivos e subdiretórios, especifique o diretório raiz no **caminho** sem curingas. Por exemplo: `-Path C:\Reference`
- Para criar um arquivo que **exclua** o diretório raiz, mas zips todos os seus arquivos e subdiretórios, use o curinga asterisco ( `*` ). Por exemplo: `-Path C:\Reference\*`
- Para criar um arquivo morto que só zips os arquivos no diretório raiz, use o curinga **Star-dot-Star** ( `*.*` ). Os subdiretórios da raiz não estão incluídos no arquivo morto. Por exemplo: `-Path C:\Reference\*.*`

```yaml
Type: System.String[]
Parameter Sets: Path, PathWithUpdate, PathWithForce
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Atualização

Atualiza o arquivo especificado substituindo versões de arquivo mais antigas no arquivo morto por versões de arquivo mais recentes que têm os mesmos nomes. Você também pode adicionar esse parâmetro para adicionar arquivos a um arquivo existente.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PathWithUpdate, LiteralPathWithUpdate
Aliases:

Required: True
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

### System.String

É possível canalizar uma cadeia de caracteres que contém um caminho para um ou mais arquivos.

## SAÍDAS

### System. IO. FileInfo

O cmdlet retorna apenas um objeto **FileInfo** quando você usa o parâmetro **PassThru** .

## OBSERVAÇÕES

Usar recursão e enviar objetos por meio do pipeline pode duplicar arquivos em seu arquivo morto. Por exemplo, se você usar `Get-ChildItem` com o parâmetro **recurse** , cada objeto **FileInfo** e **DirectoryInfo** enviado pelo pipeline será adicionado ao arquivo morto.

A [especificação do arquivo zip](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) não especifica uma maneira padrão de codificar nomes de arquivos que contenham caracteres não ASCII. O `Compress-Archive` cmdlet usa a codificação UTF-8. Outras ferramentas de arquivo ZIP podem usar um esquema de codificação diferente. Ao extrair arquivos com nomes de arquivo não armazenados usando a codificação UTF-8, `Expand-Archive` o usa o valor bruto encontrado no arquivamento. Isso pode resultar em um nome de arquivo diferente do nome de arquivo de origem armazenado no arquivo morto.

## LINKS RELACIONADOS

[Expand-Archive](Expand-Archive.md)

[Get-ChildItem](../Microsoft.PowerShell.Management/Get-ChildItem.md)
