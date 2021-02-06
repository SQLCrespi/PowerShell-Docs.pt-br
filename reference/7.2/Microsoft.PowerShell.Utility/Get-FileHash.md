---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-filehash?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-FileHash
ms.openlocfilehash: 0b31409d1da56979887e606b76ddf20532b188c1
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598833"
---
# Get-FileHash

## SINOPSE
Calcula o valor de hash para um arquivo utilizando um algoritmo de hash especificado.

## SYNTAX

### Caminho (padrão)

```
Get-FileHash [-Path] <String[]> [[-Algorithm] <String>] [<CommonParameters>]
```

### LiteralPath

```
Get-FileHash [-LiteralPath] <String[]> [[-Algorithm] <String>] [<CommonParameters>]
```

### StreamParameterSet

```
Get-FileHash [-InputStream] <Stream> [[-Algorithm] <String>] [<CommonParameters>]
```

## DESCRIPTION

O `Get-FileHash` cmdlet computa o valor de hash para um arquivo usando um algoritmo de hash especificado.
Um valor de hash é um valor exclusivo que corresponde ao conteúdo do arquivo. Em vez de identificar o conteúdo de um arquivo por seu nome, extensão ou outra designação, um hash atribui um valor exclusivo para o conteúdo de um arquivo. Extensões e nomes de arquivo podem ser alterados sem alterar o conteúdo do arquivo e sem alterar o valor de hash. Da mesma forma, o conteúdo do arquivo pode ser alterado sem alterar o nome ou a extensão. No entanto, até mesmo um único caractere no conteúdo de um arquivo altera o valor de hash do arquivo.

A finalidade dos valores de hash é fornecer uma maneira de proteger criptograficamente para verificar se o conteúdo de um arquivo não foi alterado. Embora alguns algoritmos de hash, incluindo MD5 e SHA1, não sejam mais considerados seguros contra ataques, o objetivo de um algoritmo de hash seguro é tornar impossível alterar o conteúdo de um arquivo, seja por acidente ou por tentativa mal-intencionada ou não autorizada, e manter o mesmo valor de hash. Também é possível utilizar os valores de hash para determinar se dois arquivos diferentes têm exatamente o mesmo conteúdo. Se os valores de hash de dois arquivos forem idênticos, o conteúdo dos arquivos também é idêntico.

Por padrão, o `Get-FileHash` cmdlet usa o algoritmo SHA256, embora qualquer algoritmo de hash compatível com o sistema operacional de destino possa ser usado.

## EXEMPLOS

### Exemplo 1: calcular o valor de hash para um arquivo

Este exemplo usa o `Get-FileHash` cmdlet para calcular o valor de hash para o `/etc/apt/sources.list` arquivo. O algoritmo de hash usado é o padrão, **SHA256**. A saída é canalizada para o `Format-List` cmdlet para formatar a saída como uma lista.

```powershell
Get-FileHash /etc/apt/sources.list | Format-List
```

```Output
Algorithm : SHA256
Hash      : 3CBCFDDEC145E3382D592266BE193E5BE53443138EE6AB6CA09FF20DF609E268
Path      : /etc/apt/sources.list
```

### Exemplo 2: calcular o valor de hash para um arquivo ISO

Este exemplo usa o `Get-FileHash` cmdlet e o algoritmo **Sha384** para calcular o valor de hash para um arquivo ISO que um administrador baixou da Internet. A saída é canalizada para o `Format-List` cmdlet para formatar a saída como uma lista.

```powershell
Get-FileHash C:\Users\user1\Downloads\Contoso8_1_ENT.iso -Algorithm SHA384 | Format-List
```

```Output
Algorithm : SHA384
Hash      : 20AB1C2EE19FC96A7C66E33917D191A24E3CE9DAC99DB7C786ACCE31E559144FEAFC695C58E508E2EBBC9D3C96F21FA3
Path      : C:\Users\user1\Downloads\Contoso8_1_ENT.iso
```

### Exemplo 3: calcular o valor de hash de um fluxo

Para este exemplo, obtemos o uso do **System .net. WebClient** para baixar um pacote da [página de versão do PowerShell](https://github.com/PowerShell/PowerShell/releases/tag/v6.2.4). A página versão também documenta o hash SHA256 de cada arquivo de pacote. Podemos comparar o valor de hash publicado com o que calculamos com `Get-FileHash` .

```powershell
$wc = [System.Net.WebClient]::new()
$pkgurl = 'https://github.com/PowerShell/PowerShell/releases/download/v6.2.4/powershell_6.2.4-1.debian.9_amd64.deb'
$publishedHash = '8E28E54D601F0751922DE24632C1E716B4684876255CF82304A9B19E89A9CCAC'
$FileHash = Get-FileHash -InputStream ($wc.OpenRead($pkgurl))
$FileHash.Hash -eq $publishedHash
```

```Output
True
```

### Exemplo 4: calcular o hash de uma cadeia de caracteres

O PowerShell não fornece um cmdlet para computar o hash de uma cadeia de caracteres. No entanto, você pode gravar uma cadeia de caracteres em um fluxo e usar o parâmetro **InputStream** de `Get-FileHash` para obter o valor de hash.

```powershell
$stringAsStream = [System.IO.MemoryStream]::new()
$writer = [System.IO.StreamWriter]::new($stringAsStream)
$writer.write("Hello world")
$writer.Flush()
$stringAsStream.Position = 0
Get-FileHash -InputStream $stringAsStream | Select-Object Hash
```

```Output
Hash
----
64EC88CA00B268E5BA1A35678A1B5316D212F4F366B2477232534A8AECA37F3C
```

## PARAMETERS

### -Algoritmo

Especifica a função de hash criptográfico a ser usada para calcular o valor de hash do conteúdo do arquivo ou fluxo especificado. Uma função de hash criptográfico tem a propriedade de que é impraticável encontrar dois arquivos diferentes com o mesmo valor de hash. As funções de hash são utilizadas com assinaturas digitais e integridade dos dados. Os valores aceitáveis para esse parâmetro são:

- SHA1
- SHA256
- SHA384
- SHA512
- MD5

Se nenhum valor for especificado, ou se o parâmetro for omitido, o valor padrão é SHA256.

Por motivos de segurança, MD5 e SHA1, que não são considerados seguros, devem ser utilizados somente para validação de alteração simples e não devem ser utilizados para gerar valores de hash para arquivos que exigem proteção contra ataque ou violação.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: SHA1, SHA256, SHA384, SHA512, MD5

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputStream

Especifica o fluxo de entrada.

```yaml
Type: System.IO.Stream
Parameter Sets: StreamParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LiteralPath

Especifica o caminho para um arquivo. Ao contrário do parâmetro **Path**, o valor do parâmetro **LiteralPath** é usado exatamente como foi digitado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres de escape, coloque o caminho entre aspas. As aspas simples instruem o PowerShell a não interpretar caracteres como sequências de escape.

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Especifica o caminho para um ou mais arquivos como uma matriz. Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

É possível canalizar uma cadeia de caracteres para o `Get-FileHash` cmdlet que contém um caminho para um ou mais arquivos.

## SAÍDAS

### Microsoft. PowerShell. Utility. FileHash

`Get-FileHash` Retorna um objeto que representa o caminho para o arquivo especificado, o valor do hash computado e o algoritmo usado para computar o hash.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Format-List](Format-List.md)

