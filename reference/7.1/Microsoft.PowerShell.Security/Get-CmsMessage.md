---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 02/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-cmsmessage?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CmsMessage
ms.openlocfilehash: 9a24cfc0e2312a5bb985084ffb9eb753f49cb8ea
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194712"
---
# Get-CmsMessage

## SINOPSE
Obtém o conteúdo que foi criptografado usando o formato de sintaxe da mensagem criptográfica.

## SYNTAX

### ByContent

```
Get-CmsMessage [-Content] <String> [<CommonParameters>]
```

### ByPath

```
Get-CmsMessage [-Path] <String> [<CommonParameters>]
```

### ByLiteralPath

```
Get-CmsMessage [-LiteralPath] <String> [<CommonParameters>]
```

## DESCRIPTION

O `Get-CmsMessage` cmdlet obtém o conteúdo que foi criptografado usando o formato CMS (sintaxe de mensagem criptografada).

Os cmdlets CMS dão suporte à criptografia e descriptografia de conteúdo usando o formato IETF para proteger as mensagens criptograficamente, conforme documentado por [RFC5652](https://tools.ietf.org/html/rfc5652).

O padrão de criptografia do CMS usa criptografia de chave pública, em que as chaves usadas para criptografar conteúdo (a chave pública) e as chaves usadas para descriptografar conteúdo (a chave privada) são separadas. Sua chave pública pode ser compartilhada amplamente e não contém dados confidenciais. Se algum conteúdo for criptografado com essa chave pública, somente sua chave privada poderá descriptografá-lo. Para obter mais informações, consulte [Criptografia por chave pública](https://en.wikipedia.org/wiki/Public-key_cryptography).

`Get-CmsMessage` Obtém o conteúdo que foi criptografado no formato CMS. Ele não descriptografa nem desprotege o conteúdo. Você pode executar este cmdlet para obter o conteúdo que você criptografou executando o `Protect-CmsMessage` cmdlet. Você pode especificar o conteúdo que deseja descriptografar como uma cadeia de caracteres ou por caminho para o conteúdo criptografado. É possível canalizar os resultados de `Get-CmsMessage` para `Unprotect-CmsMessage` para descriptografar o conteúdo, desde que você tenha informações sobre o certificado de criptografia do documento que foi usado para criptografar o conteúdo.

O suporte para Linux e macOS foi adicionado no PowerShell 7,1.

## EXEMPLOS

### Exemplo 1: obter conteúdo criptografado

```powershell
$Msg = Get-CmsMessage -Path "C:\Users\Test\Documents\PowerShell\Future_Plans.txt"
$Msg.Content
```

```Output
-----BEGIN CMS-----
MIIBqAYJKoZIhvcNAQcDoIIBmTCCAZUCAQAxggFQMIIBTAIBADA0MCAxHjAcBgNVBAMBFWxlZWhv
bG1AbGljcm9zb2Z0LmNvbQIQQYHsbcXnjIJCtH+OhGmc1DANBgkqhkiG9w0BAQcwAASCAQAnkFHM
proJnFy4geFGfyNmxH3yeoPvwEYzdnsoVqqDPAd8D3wao77z7OhJEXwz9GeFLnxD6djKV/tF4PxR
E27aduKSLbnxfpf/sepZ4fUkuGibnwWFrxGE3B1G26MCenHWjYQiqv+Nq32Gc97qEAERrhLv6S4R
G+2dJEnesW8A+z9QPo+DwYP5FzD0Td0ExrkswVckpLNR6j17Yaags3ltNXmbdEXekhi6Psf2MLMP
TSO79lv2L0KeXFGuPOrdzPRwCkV0vNEqTEBeDnZGrjv/5766bM3GW34FXApod9u+VSFpBnqVOCBA
DVDraA6k+xwBt66cV84AHLkh0kT02SIHMDwGCSqGSIb3DQEHATAdBglghkgBZQMEASoEEJbJaiRl
KMnBoD1dkb/FzSWAEBaL8xkFwCu0e1AtDj7nSJc=
-----END CMS-----
```

Este comando obtém o conteúdo criptografado localizado em C:\Users\Test\Documents\PowerShell\Future_Plans.txt.

### Exemplo 2: direcionar conteúdo criptografado para Unprotect-CmsMessage

```powershell
$Msg = Get-CmsMessage -Path "C:\Users\Test\Documents\PowerShell\Future_Plans.txt"
$Msg | Unprotect-CmsMessage -To "cn=youralias@emailaddress.com"
```

```Output
Try the new Break All command
```

Esse comando canaliza os resultados do `Get-CmsMessage` cmdlet do exemplo 1 para `Unprotect-CmsMessage` , para descriptografar a mensagem e lê-la em texto sem formatação. Nesse caso, o valor do parâmetro **to** é o valor da linha de assunto do certificado de criptografia. A mensagem descriptografada, "Experimente o comando interromper tudo", é o resultado.

## PARAMETERS

### -Conteúdo

Especifica uma cadeia de caracteres criptografada ou uma variável que contém uma cadeia de caracteres criptografada.

```yaml
Type: System.String
Parameter Sets: ByContent
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LiteralPath

Especifica o caminho para o conteúdo criptografado que você deseja obter. Ao contrário de **Path** , o valor de **LiteralPath** é usado exatamente como digitado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres de escape, coloque cada um entre aspas simples.
Aspas simples instruem o PowerShell a não interpretar caracteres incluídos como caracteres de escape.

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Especifica o caminho para o conteúdo criptografado que você deseja descriptografar.

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

## SAÍDAS

## OBSERVAÇÕES

## LINKS RELACIONADOS

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[Protect-CmsMessage](Protect-CmsMessage.md)

[Unprotect-CmsMessage](Unprotect-CmsMessage.md)

