---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-content?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Content
ms.openlocfilehash: 0140691bc0b01fff803f0efdf81980c621e1150d
ms.sourcegitcommit: 9a8bb1b459b5939c95e1f6d9499fcb13d01a58c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/25/2020
ms.locfileid: "93195250"
---
# Get-Content

## SINOPSE
Obtém o conteúdo do item no local especificado.

## SYNTAX

### Caminho (padrão)

```
Get-Content [-ReadCount <Int64>] [-TotalCount <Int64>] [-Tail <Int32>] [-Path] <String[]>
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force] [-Credential <PSCredential>]
 [-Delimiter <String>] [-Wait] [-Raw] [-Encoding <Encoding>] [-AsByteStream] [-Stream <String>]
 [<CommonParameters>]
```

### LiteralPath

```
Get-Content [-ReadCount <Int64>] [-TotalCount <Int64>] [-Tail <Int32>] -LiteralPath <String[]>
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force] [-Credential <PSCredential>]
 [-Delimiter <String>] [-Wait] [-Raw] [-Encoding <Encoding>] [-AsByteStream] [-Stream <String>]
 [<CommonParameters>]
```

## DESCRIPTION

O `Get-Content` cmdlet obtém o conteúdo do item no local especificado pelo caminho, como o texto em um arquivo ou o conteúdo de uma função. Para arquivos, o conteúdo é lido uma linha por vez e retorna uma coleção de objetos, cada um representando uma linha de conteúdo.

A partir do PowerShell 3,0, `Get-Content` também pode obter um número especificado de linhas do início ou do fim de um item.

## EXEMPLOS

### Exemplo 1: obter o conteúdo de um arquivo de texto

Este exemplo obtém o conteúdo de um arquivo no diretório atual. O `LineNumbers.txt` arquivo contém 100 linhas no formato, **é a linha X** e é usado em vários exemplos.

```powershell
1..100 | ForEach-Object { Add-Content -Path .\LineNumbers.txt -Value "This is line $_." }
Get-Content -Path .\LineNumbers.txt
```

```Output
This is Line 1
This is Line 2
...
This is line 99.
This is line 100.
```

Os valores de matriz 1-100 são enviados pelo pipeline para o `ForEach-Object` cmdlet. `ForEach-Object` usa um bloco de script com o `Add-Content` cmdlet para criar o `LineNumbers.txt` arquivo. A variável `$_` representa os valores de matriz conforme cada objeto é enviado ao pipeline. O `Get-Content` cmdlet usa o parâmetro **Path** para especificar o `LineNumbers.txt` arquivo e exibe o conteúdo no console do PowerShell.

### Exemplo 2: limitar o número de linhas Get-Content retorna

Esse comando obtém as primeiras cinco linhas de um arquivo. O parâmetro **TotalCount** é usado para obter as primeiras cinco linhas de conteúdo. Este exemplo usa o `LineNumbers.txt` arquivo que foi criado no exemplo 1.

```powershell
Get-Content -Path .\LineNumbers.txt -TotalCount 5
```

```Output
This is Line 1
This is Line 2
This is Line 3
This is Line 4
This is Line 5
```

### Exemplo 3: obter uma linha de conteúdo específica de um arquivo de texto

Esse comando obtém um número específico de linhas de um arquivo e, em seguida, exibe apenas a última linha desse conteúdo. O parâmetro **TotalCount** Obtém as 25 primeiras linhas de conteúdo. Este exemplo usa o `LineNumbers.txt` arquivo que foi criado no exemplo 1.

```powershell
(Get-Content -Path .\LineNumbers.txt -TotalCount 25)[-1]
```

```Output
This is Line 25
```

O `Get-Content` comando é encapsulado entre parênteses para que o comando seja concluído antes de ir para a próxima etapa. `Get-Content`Retorna uma matriz de linhas, isso permite que você adicione a notação de índice após o parêntese para recuperar um número de linha específico. Nesse caso, o `[-1]` índice especifica o último índice na matriz retornada de 25 linhas recuperadas.

### Exemplo 4: obter a última linha de um arquivo de texto

Esse comando obtém a primeira linha e a última linha de conteúdo de um arquivo. Este exemplo usa o `LineNumbers.txt` arquivo que foi criado no exemplo 1.

```powershell
Get-Item -Path .\LineNumbers.txt | Get-Content -Tail 1
```

```Output
This is Line 100
```

Este exemplo usa o `Get-Item` cmdlet para demonstrar que você pode canalizar arquivos para o `Get-Content` parâmetro. O parâmetro **tail** Obtém a última linha do arquivo. Esse método é mais rápido do que recuperar todas as linhas e usar a `[-1]` notação de índice.

### Exemplo 5: obter o conteúdo de um fluxo de dados alternativo

Este exemplo descreve como usar o parâmetro **Stream** para obter o conteúdo de um fluxo de dados alternativo para arquivos armazenados em um volume NTFS do Windows. Neste exemplo, o `Set-Content` cmdlet é usado para criar conteúdo de exemplo em um arquivo chamado `Stream.txt` .

```powershell
Set-Content -Path .\Stream.txt -Value 'This is the content of the Stream.txt file'
# Specify a wildcard to the Stream parameter to display all streams of the recently created file.
Get-Item -Path .\Stream.txt -Stream *
```

```Output
PSPath        : Microsoft.PowerShell.Core\FileSystem::C:\Test\Stream.txt::$DATA
PSParentPath  : Microsoft.PowerShell.Core\FileSystem::C:\Test
PSChildName   : Stream.txt::$DATA
PSDrive       : C
PSProvider    : Microsoft.PowerShell.Core\FileSystem
PSIsContainer : False
FileName      : C:\Test\Stream.txt
Stream        : :$DATA
Length        : 44
```

```powershell
# Retrieve the content of the primary, or $DATA stream.
Get-Content -Path .\Stream.txt -Stream $DATA
```

```Output
This is the content of the Stream.txt file
```

```powershell
# Use the Stream parameter of Add-Content to create a new Stream containing sample content.
Add-Content -Path .\Stream.txt -Stream NewStream -Value 'Added a stream named NewStream to Stream.txt'
# Use Get-Item to verify the stream was created.
Get-Item -Path .\Stream.txt -Stream *
```

```Output
PSPath        : Microsoft.PowerShell.Core\FileSystem::C:\Test\Stream.txt::$DATA
PSParentPath  : Microsoft.PowerShell.Core\FileSystem::C:\Test
PSChildName   : Stream.txt::$DATA
PSDrive       : C
PSProvider    : Microsoft.PowerShell.Core\FileSystem
PSIsContainer : False
FileName      : C:\Test\Stream.txt
Stream        : :$DATA
Length        : 44

PSPath        : Microsoft.PowerShell.Core\FileSystem::C:\Test\Stream.txt:NewStream
PSParentPath  : Microsoft.PowerShell.Core\FileSystem::C:\Test
PSChildName   : Stream.txt:NewStream
PSDrive       : C
PSProvider    : Microsoft.PowerShell.Core\FileSystem
PSIsContainer : False
FileName      : C:\Test\Stream.txt
Stream        : NewStream
Length        : 46
```

```powershell
# Retrieve the content of your newly created Stream.
Get-Content -Path .\Stream.txt -Stream NewStream
```

```Output
Added a stream named NewStream to Stream.txt
```

O parâmetro **Stream** é um parâmetro dinâmico do [provedor FileSystem](../microsoft.powershell.core/about/about_filesystem_provider.md#stream-systemstring).
Por padrão `Get-Content` , o só recupera dados do fluxo principal ou do `$DATA` Stream. Os **fluxos** podem ser usados para armazenar dados ocultos, como atributos, configurações de segurança ou outros dados.

### Exemplo 6: obter conteúdo bruto

Os comandos neste exemplo obtêm o conteúdo de um arquivo como uma cadeia de caracteres, em vez de uma matriz de cadeias de caracteres. Por padrão, sem o parâmetro dinâmico **bruto** , o conteúdo é retornado como uma matriz de cadeias de caracteres delimitadas por nova linha. Este exemplo usa o `LineNumbers.txt` arquivo que foi criado no exemplo
1.

```powershell
$raw = Get-Content -Path .\LineNumbers.txt -Raw
$lines = Get-Content -Path .\LineNumbers.txt
Write-Host "Raw contains $($raw.Count) lines."
Write-Host "Lines contains $($lines.Count) lines."
```

```Output
Raw contains 1 lines.
Lines contains 100 lines.
```

### Exemplo 7: usar filtros com Get-Content

Você pode especificar um filtro para o `Get-Content` cmdlet. Ao usar filtros para qualificar o parâmetro de **caminho** , você precisa incluir um asterisco à direita ( `*` ) para indicar o conteúdo do caminho.

O comando a seguir obtém o conteúdo de todos os `*.log` arquivos no `C:\Temp` diretório.

```powershell
Get-Content -Path C:\Temp\* -Filter *.log
```

### Exemplo 8: obter o conteúdo do arquivo como uma matriz de bytes

Este exemplo demonstra como obter o conteúdo de um arquivo como um `[byte[]]` único objeto.

```powershell
$byteArray = Get-Content -Path C:\temp\test.txt -AsByteStream -Raw
Get-Member -InputObject $bytearray
```

```Output
   TypeName: System.Byte[]

Name           MemberType            Definition
----           ----------            ----------
Count          AliasProperty         Count = Length
Add            Method                int IList.Add(System.Object value)
```

O primeiro comando usa o parâmetro **AsByteStream** para obter o fluxo de bytes do arquivo.
O parâmetro **RAW** garante que os bytes sejam retornados como um `[System.Byte[]]` . Se o parâmetro **RAW** estiver ausente, o valor de retorno será um fluxo de bytes, que é interpretado pelo PowerShell como `[System.Object[]]` .

## PARAMETERS

### -Path

Especifica o caminho para um item em que `Get-Content` o Obtém o conteúdo. Caracteres curinga são permitidos. Os caminhos devem ser caminhos para itens, não para contêineres. Por exemplo, você deve especificar um caminho para um ou mais arquivos, não um caminho para um diretório.

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

### -ReadCount

Especifica quantas linhas de conteúdo são enviadas por meio do pipeline por vez. O valor padrão é 1.
Um valor de 0 (zero) envia todo o conteúdo de uma só vez.

Esse parâmetro não altera o conteúdo exibido, mas ele afeta o tempo necessário para exibir o conteúdo. Como o valor de **ReadCount** aumenta, o tempo necessário para retornar a primeira linha também aumenta, mas o tempo total para a operação diminui. Isso pode fazer uma diferença perceptível em itens grandes.

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TotalCount

Especifica o número de linhas desde o início de um arquivo ou outro item. O padrão é -1 (todas as linhas).

Você pode usar o nome do parâmetro **TotalCount** ou seus aliases, **primeiro** ou o **cabeçalho** .

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases: First, Head

Required: False
Position: Named
Default value: -1
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Parte final

Especifica o número de linhas do final de um arquivo ou outro item. Você pode usar o nome do parâmetro de **cauda** ou seu alias, **por fim** . Esse parâmetro foi introduzido no PowerShell 3,0.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: Last

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
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

### -Incluir

Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação. O valor deste parâmetro qualifica o parâmetro **Path** . Insira um elemento ou padrão de caminho, como `"*.txt"` . Caracteres curinga são permitidos. O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.

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

### -Excluir

Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.
O valor deste parâmetro qualifica o parâmetro **Path** .

Insira um elemento ou padrão de caminho, como `*.txt` .
Caracteres curinga são permitidos.

O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.

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

### -Force

**Forçar** irá substituir um atributo somente leitura ou criar diretórios para concluir um caminho de arquivo. O parâmetro **Force** não tenta alterar as permissões de arquivo ou substituir as restrições de segurança.

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
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Delimitador

Especifica o delimitador que `Get-Content` o usa para dividir o arquivo em objetos enquanto ele lê. O padrão é `\n` , o caractere de fim de linha. Ao ler um arquivo de texto, `Get-Content` retorna uma coleção de objetos String, cada um dos quais termina com um caractere de final de linha. Quando você insere um delimitador que não existe no arquivo, `Get-Content` o retorna o arquivo inteiro como um único objeto não delimitado.

Você pode usar esse parâmetro para dividir um arquivo grande em arquivos menores, especificando um separador de arquivo como o delimitador. O delimitador é preservado (não descartado) e se torna o último item em cada seção do arquivo.

O **delimitador** é um parâmetro dinâmico que o provedor **FileSystem** adiciona ao `Get-Content` cmdlet. Esse parâmetro funciona somente em unidades de sistema de arquivos.

> [!NOTE]
> Atualmente, quando o valor do parâmetro **delimitador** é uma cadeia de caracteres vazia, o não `Get-Content` retorna nada. Este é um problema conhecido. Para forçar a `Get-Content` retornar o arquivo inteiro como uma única cadeia de caracteres não delimitado. Insira um valor que não exista no arquivo.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: End-of-line character
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wait

Mantém o arquivo aberto após a saída de todas as linhas existentes. Enquanto aguarda, `Get-Content` o verifica o arquivo uma vez por segundo e gera novas linhas, se houver. Você pode interromper a **espera** pressionando **Ctrl + C** . A espera também termina se o arquivo é excluído, caso em que um erro de não finalização é relatado.

**Wait** é um parâmetro dinâmico que o provedor FileSystem adiciona ao `Get-Content` cmdlet. Esse parâmetro funciona somente em unidades de sistema de arquivos. **Wait** não pode ser combinado com **RAW** .

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

### -RAW

Ignora os caracteres de nova linha e retorna todo o conteúdo de um arquivo em uma cadeia de caracteres com as novas linhas preservadas. Por padrão, os caracteres de nova linha em um arquivo são usados como delimitadores para separar a entrada em uma matriz de cadeias de caracteres. Esse parâmetro foi introduzido no PowerShell 3,0.

**RAW** é um parâmetro dinâmico que o provedor **FileSystem** adiciona ao `Get-Content` cmdlet. esse parâmetro funciona somente em unidades do sistema de arquivos.

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

A codificação é um parâmetro dinâmico que o provedor **FileSystem** adiciona ao `Get-Content` cmdlet.
Esse parâmetro está disponível somente em unidades do sistema de arquivos.

Ao ler e gravar em arquivos binários, use o parâmetro **AsByteStream** e um valor de 0 para o parâmetro **readCount** . Um valor de **readCount** de 0 lê o arquivo inteiro em uma única operação de leitura. O valor padrão de **readCount** , 1, lê um byte em cada operação de leitura e converte cada byte em um objeto separado, o que causa erros quando você usa o `Set-Content` cmdlet para gravar os bytes em um arquivo, a menos que use o parâmetro **AsByteStream** .

A partir do PowerShell 6,2, o parâmetro de **codificação** também permite IDs numéricas de páginas de código registradas (como `-Encoding 1251` ) ou nomes de cadeia de caracteres de páginas de código registradas (como `-Encoding "windows-1251"` ). Para obter mais informações, consulte a documentação do .NET para [Encoding. CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).

> [!NOTE]
> O **UTF-7** * não é mais recomendado para uso. No PowerShell 7,1, um aviso será gravado se você especificar `utf7` para o parâmetro de **codificação** .

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

### -Fluxo

Obtém o fluxo de arquivos NTFS alternativo especificado do conteúdo do arquivo. Insira o nome do fluxo.
Não há suporte para caracteres curinga.

**Stream** é um parâmetro dinâmico que o provedor **FileSystem** adiciona ao `Get-Content` cmdlet.
Esse parâmetro funciona apenas em unidades do sistema de arquivos em sistemas Windows. Este parâmetro foi introduzido no Windows PowerShell 3.0.

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

### -AsByteStream

Especifica que o conteúdo deve ser lido como um fluxo de bytes. O parâmetro **AsByteStream** foi introduzido no Windows PowerShell 6,0.

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

### CommonParameters

Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` . Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### System.Int64, System.String[], System.Management.Automation.PSCredential

Você pode canalizar a contagem de leitura, a contagem total, os caminhos ou as credenciais para `Get-Content` .

## SAÍDAS

### System. byte, System. String

`Get-Content` Retorna cadeias de caracteres ou bytes. O tipo de saída depende do tipo de conteúdo que você especificar como entrada.

## OBSERVAÇÕES

O `Get-Content` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor. Para obter os provedores em sua sessão, use o `Get-PSProvider` cmdlet. Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## LINKS RELACIONADOS

[about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[Add-Content](Add-Content.md)

[Clear-Content](Clear-Content.md)

[ForEach-Object](../Microsoft.PowerShell.Core/ForEach-Object.md)

[Get-PSProvider](Get-PSProvider.md)

[Set-Content](Set-Content.md)

