---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-clixml?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Clixml
ms.openlocfilehash: 916b0ca30240002949b947b857b257214ea9ca1a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194503"
---
# Export-Clixml

## SINOPSE
Cria uma representação baseada em XML de um objeto ou objetos e armazena-a em um arquivo.

## SYNTAX

### ByPath (padrão)

```
Export-Clixml [-Path] <String> -InputObject <PSObject> [-Depth <Int32>] [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByLiteralPath

```
Export-Clixml -LiteralPath <String> -InputObject <PSObject> [-Depth <Int32>] [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Export-Clixml` cmdlet cria uma representação baseada em XML Common Language Infrastructure (CLI) de um objeto ou objetos e a armazena em um arquivo. Você pode usar o `Import-Clixml` cmdlet para recriar o objeto salvo com base no conteúdo desse arquivo.
Para obter mais informações sobre a CLI, consulte [independência de idioma](/dotnet/standard/language-independence).

Esse cmdlet é semelhante a `ConvertTo-Xml` , exceto pelo fato de `Export-Clixml` armazenar o XML resultante em um arquivo. `ConvertTo-XML` Retorna o XML, para que você possa continuar a processá-lo no PowerShell.

Um uso valioso do `Export-Clixml` em computadores com Windows é exportar credenciais e proteger cadeias de caracteres com segurança como XML. Para obter um exemplo, consulte o exemplo 3.

## EXEMPLOS

### Exemplo 1: exportar uma cadeia de caracteres para um arquivo XML

Este exemplo cria um arquivo XML que armazena no diretório atual, uma representação da cadeia de caracteres que **é um teste** .

```powershell
"This is a test" | Export-Clixml -Path .\sample.xml
```

A cadeia de caracteres **é um teste** que é enviado pelo pipeline. `Export-Clixml` usa o parâmetro **path** para criar um arquivo XML chamado `sample.xml` no diretório atual.

### Exemplo 2: exportar um objeto para um arquivo XML

Este exemplo mostra como exportar um objeto para um arquivo XML e, em seguida, criar um objeto importando o XML do arquivo.

```powershell
Get-Acl C:\test.txt | Export-Clixml -Path .\FileACL.xml
$fileacl = Import-Clixml -Path .\FileACL.xml
```

O `Get-Acl` cmdlet obtém o descritor de segurança do `Test.txt` arquivo. Ele envia o objeto para baixo no pipeline para o qual passar o descritor de segurança `Export-Clixml` . A representação baseada em XML do objeto é armazenada em um arquivo chamado `FileACL.xml` .

O `Import-Clixml` cmdlet cria um objeto do XML no `FileACL.xml` arquivo. Em seguida, ele salva o objeto na `$fileacl` variável.

### Exemplo 3: criptografar um objeto de credencial exportado no Windows

Neste exemplo, dada uma credencial que você armazenou na `$Credential` variável executando o `Get-Credential` cmdlet, você pode executar o `Export-Clixml` cmdlet para salvar a credencial no disco.

> [!IMPORTANT]
> `Export-Clixml` o só exporta credenciais criptografadas no Windows. Em sistemas operacionais não Windows, como macOS e Linux, as credenciais são exportadas como um texto simples armazenado como uma matriz de caracteres Unicode. Isso fornece alguma ofuscação, mas não fornece criptografia.

```powershell
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential | Export-Clixml $Credxmlpath
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential = Import-Clixml $Credxmlpath
```

O `Export-Clixml` cmdlet criptografa objetos de credencial usando a [API de proteção de dados](/previous-versions/windows/apps/hh464970(v=win.10))do Windows. A criptografia garante que apenas sua conta de usuário somente no computador possa descriptografar o conteúdo do objeto de credencial.
O arquivo exportado `CLIXML` não pode ser usado em um computador diferente ou por um usuário diferente.

No exemplo, o arquivo no qual a credencial é armazenada é representado por `TestScript.ps1.credential` . Substitua **TestScript** pelo nome do script com o qual você está carregando a credencial.

Você envia o objeto de credencial para baixo do pipeline para o `Export-Clixml` , e salva-o no caminho, `$Credxmlpath` , que você especificou no primeiro comando.

Para importar a credencial automaticamente para o script, execute os dois comandos finais. Execute `Import-Clixml` para importar o objeto de credencial protegido para o script. Essa importação elimina o risco de expor senhas de texto sem formatação em seu script.

### Exemplo 4: exportando um objeto de credencial no Linux ou no macOS

Neste exemplo, criamos um **PSCredential** na `$Credential` variável usando o `Get-Credential` cmdlet. Em seguida, usamos `Export-Clixml` para salvar a credencial no disco.

> [!IMPORTANT]
> `Export-Clixml` o só exporta credenciais criptografadas no Windows. Em sistemas operacionais não Windows, como macOS e Linux, as credenciais são exportadas como um texto simples armazenado como uma matriz de caracteres Unicode. Isso fornece alguma ofuscação, mas não fornece criptografia.

```powershell
PS> $Credential = Get-Credential

PowerShell credential request
Enter your credentials.
User: User1
Password for user User1: ********

PS> $Credential | Export-Clixml ./cred2.xml
PS> Get-Content ./cred2.xml

...
    <Props>
      <S N="UserName">User1</S>
      <SS N="Password">700061007300730077006f0072006400</SS>
    </Props>
...

PS> 'password' | Format-Hex -Encoding unicode

                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
0000000000000000 70 00 61 00 73 00 73 00 77 00 6F 00 72 00 64 00 p a s s w o r d
```

A saída de `Get-Content` neste exemplo foi truncada para se concentrar nas informações de credenciais no arquivo XML. Observe que o valor de texto sem formatação da senha é armazenado no arquivo XML como uma matriz de caracteres Unicode como comprovado pelo `Format-Hex` . Portanto, o valor é codificado, mas não criptografado.

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

### -Profundidade

Especifica quantos níveis de objetos contidos estão incluídos na representação XML. O valor padrão é `2`.

O valor padrão pode ser substituído para o tipo de objeto nos `Types.ps1xml` arquivos. Para obter mais informações, consulte [about_Types.ps1XML](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 2
Accept pipeline input: False
Accept wildcard characters: False
```

### -Codificação

Especifica o tipo de codificação para o arquivo de destino. O valor padrão é `utf8NoBOM`.

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

### -Force

Força o comando a ser executado sem solicitar a confirmação do usuário.

Faz com que o cmdlet limpe o atributo somente leitura do arquivo de saída, se necessário. O cmdlet tentará redefinir o atributo somente leitura quando o comando for concluído.

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

### -InputObject

Especifica o objeto a ser convertido. Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos. Você também pode canalizar objetos para `Export-Clixml` .

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LiteralPath

Especifica o caminho para o arquivo onde a representação XML do objeto será armazenada. Ao contrário do **caminho** , o valor do parâmetro **LiteralPath** é usado exatamente como é digitado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres de escape, coloque-o entre aspas simples. Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoClobber

Indica que o cmdlet não substitui o conteúdo de um arquivo existente. Por padrão, se um arquivo existir no caminho especificado, `Export-Clixml` o substituirá o arquivo sem aviso.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Especifica o caminho para o arquivo onde a representação XML do objeto será armazenada.

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
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

Você pode canalizar qualquer objeto para `Export-Clixml` .

## SAÍDAS

### System. IO. FileInfo

`Export-Clixml` Cria um arquivo que contém o XML.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[ConvertTo-Html](ConvertTo-Html.md)

[ConvertTo-Xml](ConvertTo-Xml.md)

[Export-Csv](Export-Csv.md)

[Import-Clixml](Import-Clixml.md)

[Join-Path](../Microsoft.PowerShell.Management/Join-Path.md)

[Armazenar credenciais com segurança no disco](https://powershellcookbook.com/recipe/PukO/securely-store-credentials-on-disk)

[Usar o PowerShell para passar credenciais para sistemas herdados](https://devblogs.microsoft.com/scripting/use-powershell-to-pass-credentials-to-legacy-systems/)

[Windows.Security.Cryptography.DataProtection](/uwp/api/windows.security.cryptography.dataprotection)
