---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/add-content?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Content
ms.openlocfilehash: e31e792a60cd09d35ecc67263f107584857efe7d
ms.sourcegitcommit: bf07cffb2a66dec94bf3576e197090f958701f18
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "97693038"
---
# Add-Content

## SINOPSE
Adiciona conteúdo aos itens especificados, como a adição de palavras a um arquivo.

## SYNTAX

### Caminho (padrão)

```
Add-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

### LiteralPath

```
Add-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

## DESCRIPTION

O `Add-Content` cmdlet acrescenta o conteúdo a um item ou arquivo especificado. Você pode especificar o conteúdo, digitando-o no comando ou especificando um objeto que contém o conteúdo.

Se você precisar criar arquivos ou diretórios para os exemplos a seguir, consulte [New-Item](New-Item.md).

## EXEMPLOS

### Exemplo 1: adicionar uma cadeia de caracteres a todos os arquivos de texto com uma exceção

Este exemplo acrescenta um valor a arquivos de texto no diretório atual, mas exclui arquivos com base no nome do arquivo.

```powershell
Add-Content -Path .\*.txt -Exclude help* -Value 'End of file'
```

O parâmetro **path** especifica todos os `.txt` arquivos no diretório atual, mas o parâmetro **Exclude** ignora os nomes de arquivo que correspondem ao padrão especificado. O parâmetro **Value** especifica a cadeia de caracteres de texto que é gravada nos arquivos.

### Exemplo 2: adicionar uma data ao final dos arquivos especificados

Este exemplo acrescenta a data a arquivos no diretório atual e exibe a data no console do PowerShell.

```powershell
Add-Content -Path .\DateTimeFile1.log, .\DateTimeFile2.log -Value (Get-Date) -PassThru
Get-Content -Path .\DateTimeFile1.log
```

```Output
Tuesday, May 14, 2019 8:24:27 AM
Tuesday, May 14, 2019 8:24:27 AM
5/14/2019 8:24:27 AM
```

O `Add-Content` cmdlet cria dois novos arquivos no diretório atual. O parâmetro **Value** contém a saída do `Get-Date` cmdlet. O parâmetro **PassThru** gera o conteúdo adicionado ao pipeline.
Como não há nenhum outro cmdlet para receber a saída, ele é exibido no console do PowerShell.
O `Get-Content` cmdlet exibe o arquivo atualizado, `DateTimeFile1.log` .

### Exemplo 3: Adicionar o conteúdo de um arquivo especificado a outro arquivo

Este exemplo obtém o conteúdo de um arquivo e armazena o conteúdo em uma variável. A variável é usada para acrescentar o conteúdo a outro arquivo.

```powershell
$From = Get-Content -Path .\CopyFromFile.txt
Add-Content -Path .\CopyToFile.txt -Value $From
Get-Content -Path .\CopyToFile.txt
```

- O `Get-Content` cmdlet obtém o conteúdo de `CopyFromFile.txt` e armazena o conteúdo na `$From` variável.
- O `Add-Content` cmdlet atualiza o `CopyToFile.txt` arquivo usando o conteúdo da `$From` variável.
- O `Get-Content` cmdlet exibe CopyToFile.txt.

### Exemplo 4: Adicionar o conteúdo de um arquivo especificado a outro arquivo usando o pipeline

Este exemplo obtém o conteúdo de um arquivo e o canaliza para o `Add-Content` cmdlet.

```powershell
Get-Content -Path .\CopyFromFile.txt | Add-Content -Path .\CopyToFile.txt
Get-Content -Path .\CopyToFile.txt
```

O `Get-Content` cmdlet obtém o conteúdo de `CopyFromFile.txt` . Os resultados são canalizados para o `Add-Content` cmdlet, que atualiza o `CopyToFile.txt` .
O último `Get-Content` cmdlet é exibido `CopyToFile.txt` .

### Exemplo 5: criar um novo arquivo e copiar o conteúdo

Este exemplo cria um novo arquivo e copia o conteúdo de um arquivo existente no novo arquivo.

```powershell
Add-Content -Path .\NewFile.txt -Value (Get-Content -Path .\CopyFromFile.txt)
Get-Content -Path .\NewFile.txt
```

- O `Add-Content` cmdlet usa os parâmetros **Path** e **Value** para criar um novo arquivo no diretório atual.
- O `Get-Content` cmdlet obtém o conteúdo de um arquivo existente `CopyFromFile.txt` e o passa para o parâmetro **Value** . Os parênteses em volta do `Get-Content` cmdlet garantem que o comando seja concluído antes do `Add-Content` início do comando.
- O `Get-Content` cmdlet exibe o conteúdo do novo arquivo, `NewFile.txt` .

### Exemplo 6: adicionar conteúdo a um arquivo somente leitura

Esse comando adiciona um valor ao arquivo, mesmo que o atributo de arquivo **IsReadOnly** esteja definido como **true**.
As etapas para criar um arquivo somente leitura são incluídas no exemplo.

```powershell
New-Item -Path .\IsReadOnlyTextFile.txt -ItemType File
Set-ItemProperty -Path .\IsReadOnlyTextFile.txt -Name IsReadOnly -Value $True
Get-ChildItem -Path .\IsReadOnlyTextFile.txt
Add-Content -Path .\IsReadOnlyTextFile.txt -Value 'Add value to read-only text file' -Force
Get-Content -Path .\IsReadOnlyTextFile.txt
```

```Output
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-ar--         1/28/2019     13:35              0 IsReadOnlyTextFile.txt
```

- O `New-Item` cmdlet usa os parâmetros **Path** e **ItemType** para criar o arquivo `IsReadOnlyTextFile.txt` no diretório atual.
- O `Set-ItemProperty` cmdlet usa os parâmetros **Name** e **Value** para alterar a propriedade **IsReadOnly** do arquivo para true.
- O `Get-ChildItem` cmdlet mostra que o arquivo está vazio (0) e tem o atributo somente leitura ( `r` ).
- O `Add-Content` cmdlet usa o parâmetro **Path** para especificar o arquivo. O parâmetro **Value** inclui a cadeia de caracteres de texto a ser acrescentada ao arquivo. O parâmetro **Force** grava o texto no arquivo somente leitura.
- O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o conteúdo do arquivo.

Para remover o atributo somente leitura, use o `Set-ItemProperty` comando com o parâmetro de **valor** definido como `False` .

### Exemplo 7: usar filtros com Add-Content

Você pode especificar um filtro para o `Add-Content` cmdlet. Ao usar filtros para qualificar o parâmetro de **caminho** , você precisa incluir um asterisco à direita ( `*` ) para indicar o conteúdo do caminho.

O comando a seguir adiciona a palavra "Done" do conteúdo de todos os `*.txt` arquivos no `C:\Temp` diretório.

```powershell
Add-Content -Path C:\Temp\* -Filter *.txt -Value "Done"
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

Especifica o tipo de codificação para o arquivo de destino. O valor padrão é `utf8BOM`.

A codificação é um parâmetro dinâmico que o provedor FileSystem adiciona ao `Add-Content` cmdlet. Esse parâmetro funciona somente em unidades de sistema de arquivos.

Os valores aceitáveis para esse parâmetro são os seguintes:

- `ascii`: Usa a codificação para o conjunto de caracteres ASCII (7 bits).
- `bigendianunicode`: Codifica no formato UTF-16 usando a ordem de bytes big-endian.
- `oem`: Usa a codificação padrão para MS-DOS e programas de console.
- `unicode`: Codifica no formato UTF-16 usando a ordem de byte little-endian.
- `utf7`: Codifica em formato UTF-7.
- `utf8`: Codifica em formato UTF-8.
- `utf8BOM`: Codifica em formato UTF-8 com marca de ordem de byte (BOM)
- `utf8NoBOM`: Codifica em formato UTF-8 sem marca de ordem de byte (BOM)
- `utf32`: Codifica no formato UTF-32.

A partir do PowerShell 6,2, o parâmetro de **codificação** também permite IDs numéricas de páginas de código registradas (como `-Encoding 1251` ) ou nomes de cadeia de caracteres de páginas de código registradas (como `-Encoding "windows-1251"` ). Para obter mais informações, consulte a documentação do .NET para [Encoding. CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

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

Substitui o atributo somente leitura, permitindo adicionar conteúdo a um arquivo somente leitura. Por exemplo, o **Force** substituirá o atributo somente leitura ou criar diretórios para concluir um caminho de arquivo, mas não tentará alterar permissões de arquivo.

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

Indica que esse cmdlet não adiciona uma nova linha ou retorno de carro ao conteúdo.

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

Retorna um objeto que representa o conteúdo adicionado. Por padrão, este cmdlet não gera saída.

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

Especifica o caminho para os itens que recebem conteúdo adicional.
Caracteres curinga são permitidos.
Os caminhos devem ser caminhos para itens, não para contêineres.
Por exemplo, você deve especificar um caminho para um ou mais arquivos, não um caminho para um diretório.
Se você especificar vários caminhos, use vírgulas para separá-los.

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

**Stream** é um parâmetro dinâmico que o provedor FileSystem adiciona `Add-Content` . Esse parâmetro funciona somente em unidades de sistema de arquivos.

Você pode usar o `Add-Content` cmdlet para alterar o conteúdo de qualquer fluxo de dados alternativo, como `Zone.Identifier` . No entanto, não recomendamos isso como uma maneira de eliminar verificações de segurança que bloqueiam arquivos baixados da Internet. Se você verificar se um arquivo baixado é seguro, use o `Unblock-File` cmdlet.

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

Especifica o conteúdo a ser adicionado. Digite uma cadeia de caracteres entre aspas, como **esses dados são somente para uso interno** ou especifique um objeto que contenha conteúdo, como o objeto **DateTime** que `Get-Date` gera.

Você não pode especificar o conteúdo de um arquivo digitando seu caminho, pois o caminho é apenas uma cadeia de caracteres.
Você pode usar um `Get-Content` comando para obter o conteúdo e passá-lo para o parâmetro **Value** .

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

### System. Object, System. Management. Automation. PSCredential

Você pode canalizar valores, caminhos ou credenciais para `Set-Content` .

## SAÍDAS

### Nenhum ou System.String

Quando você usa o parâmetro **PassThru** , o `Add-Content` gera um objeto **System. String** que representa o conteúdo. Caso contrário, este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

- Quando você canaliza um objeto para `Add-Content` , o objeto é convertido em uma cadeia de caracteres antes de ser adicionado ao item. O tipo de objeto determina o formato de cadeia de caracteres, mas o formato pode ser diferente da exibição padrão do objeto. Para controlar o formato da cadeia de caracteres, use os parâmetros de formatação do cmdlet de envio.
- Você também pode consultar `Add-Content` por seu alias interno, `ac` . Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).
- O `Add-Content` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor. Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` . Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## LINKS RELACIONADOS

[about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[Clear-Content](Clear-Content.md)

[Get-Content](Get-Content.md)

[Get-Item](Get-Item.md)

[New-Item](New-Item.md)

[Set-Content](Set-Content.md)
