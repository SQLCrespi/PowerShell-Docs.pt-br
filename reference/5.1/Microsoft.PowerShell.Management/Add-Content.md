---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/add-content?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Content
ms.openlocfilehash: 903c4eb784c1bb86b66766c7dfb563f586545dc1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194219"
---
# Add-Content

## SINOPSE
Adiciona conteúdo aos itens especificados, como a adição de palavras a um arquivo.

## SYNTAX

### Caminho (padrão)

```
Add-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [-NoNewline] [-Encoding <FileSystemCmdletProviderEncoding>]
 [-Stream <string>] [<CommonParameters>]
```

### LiteralPath

```
Add-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [-NoNewline] [-Encoding <FileSystemCmdletProviderEncoding>]
 [-Stream <string>] [<CommonParameters>]
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

O `Add-Content` cmdlet usa o parâmetro **Path** para especificar todos os arquivos. txt no diretório atual. O parâmetro **Exclude** ignora nomes de arquivo que correspondem ao padrão especificado. O parâmetro **Value** especifica a cadeia de caracteres de texto que é gravada nos arquivos.

Use [Get-Content](Get-Content.md) para exibir o conteúdo desses arquivos.

### Exemplo 2: adicionar uma data ao final dos arquivos especificados

Este exemplo acrescenta a data a arquivos no diretório atual e exibe a data no console do PowerShell.

```powershell
Add-Content -Path .\DateTimeFile1.log, .\DateTimeFile2.log -Value (Get-Date) -PassThru
Get-Content -Path .\DateTimeFile1.log
```

O `Add-Content` cmdlet usa os parâmetros **Path** e **Value** para criar dois novos arquivos no diretório atual. O parâmetro **Value** especifica o `Get-Date` cmdlet para obter a data e passa a data para `Add-Content` . O `Add-Content` cmdlet grava a data em cada arquivo. O parâmetro **PassThru** passa um objeto que representa o objeto Date. Como não há nenhum outro cmdlet para receber o objeto passado, ele é exibido no console do PowerShell. O `Get-Content` cmdlet exibe o arquivo atualizado, DateTimeFile1. log.

### Exemplo 3: Adicionar o conteúdo de um arquivo especificado a outro arquivo

Este exemplo obtém o conteúdo de um arquivo e acrescenta esse conteúdo a outro arquivo.

```powershell
Add-Content -Path .\CopyToFile.txt -Value (Get-Content -Path .\CopyFromFile.txt)
Get-Content -Path .\CopyToFile.txt
```

O `Add-Content` cmdlet usa o parâmetro **Path** para especificar o novo arquivo no diretório atual, CopyToFile.txt. O parâmetro **Value** usa o `Get-Content` cmdlet para obter o conteúdo do arquivo, CopyFromFile.txt. Os parênteses em volta do `Get-Content` cmdlet garantem que o comando seja concluído antes do `Add-Content` início do comando. O parâmetro de **valor** é passado para `Add-Content` . O `Add-Content` cmdlet acrescenta os dados ao arquivo de CopyToFile.txt. O `Get-Content` cmdlet exibe o arquivo atualizado, CopyToFile.txt.

### Exemplo 4: usar uma variável para adicionar o conteúdo de um arquivo especificado a outro arquivo

Este exemplo obtém o conteúdo de um arquivo e armazena o conteúdo em uma variável. A variável é usada para acrescentar o conteúdo a outro arquivo.

```powershell
$From = Get-Content -Path .\CopyFromFile.txt
Add-Content -Path .\CopyToFile.txt -Value $From
Get-Content -Path .\CopyToFile.txt
```

O `Get-Content` cmdlet obtém o conteúdo de CopyFromFile.txt e armazena o conteúdo na `$From` variável. O `Add-Content` cmdlet usa o parâmetro **Path** para especificar o arquivo de CopyToFile.txt no diretório atual. O parâmetro **Value** usa a `$From` variável e passa o conteúdo para `Add-Content` . O `Add-Content` cmdlet atualiza o arquivo de CopyToFile.txt. O `Get-Content` cmdlet exibe CopyToFile.txt.

### Exemplo 5: criar um novo arquivo e copiar o conteúdo

Este exemplo cria um novo arquivo e copia o conteúdo de um arquivo existente no novo arquivo.

```powershell
Add-Content -Path .\NewFile.txt -Value (Get-Content -Path .\CopyFromFile.txt)
Get-Content -Path .\NewFile.txt
```

O `Add-Content` cmdlet usa os parâmetros **Path** e **Value** para criar um novo arquivo no diretório atual. O parâmetro **Value** usa o `Get-Content` cmdlet para obter o conteúdo de um arquivo existente, CopyFromFile.txt. Os parênteses em volta do `Get-Content` cmdlet garantem que o comando seja concluído antes do `Add-Content` início do comando. O parâmetro **Value** passa o conteúdo para o `Add-Content` qual atualiza o arquivo de NewFile.txt. O `Get-Content` cmdlet exibe o conteúdo do novo arquivo, NewFile.txt.

### Exemplo 6: adicionar conteúdo a um arquivo somente leitura

Esse comando adiciona o valor ao arquivo, mesmo que o atributo de arquivo **IsReadOnly** esteja definido como true.
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
-ar---        1/28/2019     13:35              0 IsReadOnlyTextFile.txt
```

O `New-Item` cmdlet usa os parâmetros **Path** e **ItemType** para criar o arquivo IsReadOnlyTextFile.txt no diretório atual. O `Set-ItemProperty` cmdlet usa os parâmetros **Name** e **Value** para alterar a propriedade **IsReadOnly** do arquivo para true. O `Get-ChildItem` cmdlet mostra que o arquivo está vazio (0) e tem o atributo somente leitura ( `r` ). O `Add-Content` cmdlet usa o parâmetro **Path** para especificar o arquivo. O parâmetro **Value** inclui a cadeia de caracteres de texto a ser acrescentada ao arquivo. O parâmetro **Force** grava o texto no arquivo somente leitura. O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o conteúdo do arquivo.

Para remover o atributo somente leitura, use o `Set-ItemProperty` comando com o parâmetro de **valor** definido como `False` .

## PARAMETERS

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

### -Credential

Especifica uma conta de usuário que tem permissão para executar esta ação. O padrão é o usuário atual.

Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet. Se você digitar um nome de usuário, uma senha será solicitada.

> [!WARNING]
> Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.

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

Especifica o tipo de codificação para o arquivo de destino. O valor padrão é `Default`.

Os valores aceitáveis para esse parâmetro são os seguintes:

- `Ascii` Usa conjunto de caracteres ASCII (7 bits).
- `BigEndianUnicode` Usa UTF-16 com a ordem de bytes big-endian.
- `BigEndianUTF32` Usa UTF-32 com a ordem de byte big-endian.
- `Byte` Codifica um conjunto de caracteres em uma sequência de bytes.
- `Default` Usa a codificação que corresponde à página de código ativa do sistema (geralmente ANSI).
- `Oem` Usa a codificação que corresponde à página de código OEM atual do sistema.
- `String` Mesmo que **Unicode** .
- `Unicode` Usa UTF-16 com a ordem de byte little-endian.
- `Unknown` Mesmo que **Unicode** .
- `UTF7` Usa UTF-7.
- `UTF8` Usa UTF-8.
- `UTF32` Usa UTF-32 com a ordem de byte little-endian.

A codificação é um parâmetro dinâmico que o provedor FileSystem adiciona ao `Add-Content` cmdlet. Esse parâmetro funciona somente em unidades de sistema de arquivos.

```yaml
Type: Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, Byte, Default, OEM, String, Unicode, Unknown, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### -Excluir

Omite os itens especificados. O valor deste parâmetro qualifica o parâmetro **Path** . Insira um elemento ou padrão de caminho, como **\* . txt** . Caracteres curinga são permitidos.

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

Especifica um filtro no formato ou linguagem do provedor. O valor deste parâmetro qualifica o parâmetro **Path** . A sintaxe do filtro, incluindo o uso de caracteres curingas, depende do provedor. Os **filtros** são mais eficientes do que outros parâmetros porque o provedor aplica filtros quando objetos são recuperados. Caso contrário, o PowerShell processará filtros depois que os objetos forem recuperados.

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

Adiciona apenas os itens especificados. O valor deste parâmetro qualifica o parâmetro **Path** . Insira um elemento ou padrão de caminho, como **\* . txt** . Caracteres curinga são permitidos.

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

Especifica o caminho para os itens que recebem conteúdo adicional. Ao contrário de **Path** , o valor de **LiteralPath** é usado exatamente como digitado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres de escape, coloque-o entre aspas simples. Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

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

Especifica o caminho para os itens que recebem conteúdo adicional. Caracteres curinga são permitidos. Se você especificar vários caminhos, use vírgulas para separá-los.

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

Especifica um fluxo de dados alternativo para o conteúdo. Se o fluxo não existir, esse cmdlet o criará. Não há suporte para caracteres curinga.

**Stream** é um parâmetro dinâmico que o provedor FileSystem adiciona `Add-Content` . Esse parâmetro funciona somente em unidades de sistema de arquivos.

Você pode usar o `Add-Content` cmdlet para alterar o conteúdo do fluxo de dados de **zona. identificador** alternativo. No entanto, não recomendamos isso como uma maneira de eliminar verificações de segurança que bloqueiam arquivos baixados da Internet. Se você verificar se um arquivo baixado é seguro, use o `Unblock-File` cmdlet.

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

### -UseTransaction

Inclui o comando na transação ativa. Este parâmetro é válido somente quando uma transação está em andamento. Para obter mais informações, consulte [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
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

Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` . Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Object, System. Management. Automation. PSCredential

Você pode canalizar valores, caminhos ou credenciais para `Set-Content` .

## SAÍDAS

### Nenhum ou System.String

Quando você usa o parâmetro **PassThru** , o `Add-Content` gera um objeto **System. String** que representa o conteúdo. Caso contrário, este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

Quando você canaliza um objeto para `Add-Content` , o objeto é convertido em uma cadeia de caracteres antes de ser adicionado ao item. O tipo de objeto determina o formato de cadeia de caracteres, mas o formato pode ser diferente da exibição padrão do objeto. Para controlar o formato da cadeia de caracteres, use os parâmetros de formatação do cmdlet de envio.

Você também pode consultar `Add-Content` por seu alias interno, `ac` . Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

O `Add-Content` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor. Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` . Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## LINKS RELACIONADOS

[about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)

[Clear-Content](Clear-Content.md)

[Get-Content](Get-Content.md)

[Get-Item](Get-Item.md)

[New-Item](New-Item.md)

[Set-Content](Set-Content.md)
