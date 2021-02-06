---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 07/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/convertfrom-securestring?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-SecureString
ms.openlocfilehash: 9dcc79755854cc7b9f1928cfbc5d602632eca3cc
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595971"
---
# ConvertFrom-SecureString

## SINOPSE
Converte uma cadeia de caracteres segura em uma cadeia de caracteres padrão criptografada.

## SYNTAX

### Seguro (padrão)

```
ConvertFrom-SecureString [-SecureString] <SecureString> [[-SecureKey] <SecureString>] [<CommonParameters>]
```

### AsPlainText

```
ConvertFrom-SecureString [-SecureString] <SecureString> [-AsPlainText] [<CommonParameters>]
```

### Aberto

```
ConvertFrom-SecureString [-SecureString] <SecureString> [-Key <Byte[]>] [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **ConvertFrom-SecureString** converte uma cadeia de caracteres segura (**System. Security. SecureString**) em uma cadeia de caracteres criptografada padrão (**System. String**). Ao contrário de uma cadeia de caracteres segura, uma cadeia de caracteres criptografada padrão pode ser salva em um arquivo para uso posterior. A cadeia de caracteres criptografada padrão pode ser convertida de volta para o formato de cadeia de caracteres seguro usando o `ConvertTo-SecureString` cmdlet.

Se uma chave de criptografia for especificada usando os parâmetros **Key** ou **SecureKey**, o algoritmo de criptografia AES será usado. A chave especificada deve ter um comprimento de 128, 192 ou 256 bits, pois esses são os comprimentos de chave suportados pelo algoritmo de criptografia AES. Se nenhuma chave for especificada, a API de Proteção aos Dados do Windows (DPAPI) é usada para criptografar a representação de cadeia de caracteres padrão.

> [!NOTE]
> Observe que, por [dotnet](/dotnet/api/system.security.securestring?view=netcore-2.1#remarks), o conteúdo de uma SecureString não é criptografado em sistemas que não são do Windows.

## EXEMPLOS

### Exemplo 1: criar uma cadeia de caracteres segura

```powershell
$SecureString = Read-Host -AsSecureString
```

Este comando cria uma cadeia de caracteres segura de caracteres digitados no prompt de comando. Depois de inserir o comando, digite a cadeia de caracteres que você deseja armazenar como uma cadeia de caracteres segura. Um asterisco ( `*` ) é exibido para representar cada caractere que você digitar.

### Exemplo 2: converter uma cadeia de caracteres segura em uma cadeia de caracteres criptografada padrão

```powershell
$StandardString = ConvertFrom-SecureString $SecureString
```

Esse comando converte a cadeia de caracteres segura na `$SecureString` variável em uma cadeia de caracteres padrão criptografada. A cadeia de caracteres padrão criptografada resultante é armazenada na `$StandardString` variável.

### Exemplo 3: converter uma cadeia de caracteres segura em uma cadeia de caracteres criptografada padrão com uma chave de 192 bits

```powershell
$Key = (3,4,2,3,56,34,254,222,1,1,2,23,42,54,33,233,1,34,2,7,6,5,35,43)
$StandardString = ConvertFrom-SecureString $SecureString -Key $Key
```

Esses comandos usam o algoritmo criptografia AES (AES) para converter a cadeia de caracteres segura armazenada na `$SecureString` variável em uma cadeia de caracteres criptografada padrão com uma chave de 192 bits. A cadeia de caracteres padrão criptografada resultante é armazenada na `$StandardString` variável.

O primeiro comando armazena uma chave na `$Key` variável. A chave é uma matriz de 24 numerais decimais, e cada uma deve ser menor que 256 para caber em um único byte não assinado.

Como cada numeral decimal representa um único byte (8 bits), a chave tem 24 dígitos para um total de 192 bits (8 x 24). Esse é um comprimento de chave válido para o algoritmo AES.

O segundo comando usa a chave na `$Key` variável para converter a cadeia de caracteres segura em uma cadeia de caracteres padrão criptografada.

### Exemplo 4: converter uma cadeia de caracteres segura diretamente em uma cadeia de texto sem formatação

```powershell
$secureString = ConvertTo-SecureString -String 'Example' -AsPlainText
$secureString # 'System.Security.SecureString'
ConvertFrom-SecureString -SecureString $secureString -AsPlainText # 'Example'
```

## PARAMETERS

### -Astexto não criptografado

Quando definido, `ConvertFrom-SecureString` o converterá cadeias de caracteres seguras na cadeia de texto sem formatação descriptografada como saída.

Esse parâmetro foi adicionado no PowerShell 7,0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AsPlainText
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Chave

Especifica a chave de criptografia como uma matriz de bytes.

```yaml
Type: System.Byte[]
Parameter Sets: Open
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecureKey

Especifica a chave de criptografia como uma cadeia de caracteres segura. O valor da cadeia de caracteres segura é convertido em uma matriz de bytes antes de ser usado como chave.

```yaml
Type: System.Security.SecureString
Parameter Sets: Secure
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecureString

Especifica a cadeia de caracteres segura para converter uma cadeia de caracteres criptografada padrão.

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .
Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.Security.SecureString

É possível canalizar um objeto **SecureString** para ConvertFrom-SecureString.

## SAÍDAS

### System.String

ConvertFrom-SecureString retorna um objeto de cadeia de caracteres padrão.

## OBSERVAÇÕES

- Para criar uma cadeia de caracteres segura a partir de personagens que são digitados no prompt de comando, use o parâmetro **AsSecureString** do `Read-Host` cmdlet.
- Quando você usa os parâmetros **Key** ou **SecureKey** para especificar uma chave, o comprimento da chave deve estar correto. Por exemplo, uma chave de 128 bits pode ser especificada como uma matriz de bytes de 16 numerais decimais.
  Da mesma forma, chaves de 192 bits e 256 bits correspondem a matrizes de bytes de algarismos decimais 24 e 32, respectivamente.
- Alguns caracteres, como emoticons, correspondem a vários pontos de código na cadeia de caracteres que os contém. Evite usar esses caracteres, pois eles podem causar problemas e mal-entendidos incompreendidos quando usados em uma senha.

## LINKS RELACIONADOS

[ConvertTo-SecureString](ConvertTo-SecureString.md)

[Read-Host](../Microsoft.PowerShell.Utility/Read-Host.md)
