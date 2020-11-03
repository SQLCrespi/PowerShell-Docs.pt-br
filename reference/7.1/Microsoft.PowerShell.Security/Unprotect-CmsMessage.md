---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 02/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/unprotect-cmsmessage?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unprotect-CmsMessage
ms.openlocfilehash: eaabf4e45a9441a479059513a428f2d87430dd2a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194664"
---
# Unprotect-CmsMessage

## SINOPSE
Descriptografa o conteúdo que foi criptografado usando o formato de sintaxe da mensagem criptográfica.

## SYNTAX

### ByWinEvent (padrão)

```
Unprotect-CmsMessage [-EventLogRecord] <PSObject> [-IncludeContext] [[-To] <CmsMessageRecipient[]>]
 [<CommonParameters>]
```

### ByContent

```
Unprotect-CmsMessage [-Content] <String> [-IncludeContext] [[-To] <CmsMessageRecipient[]>] [<CommonParameters>]
```

### ByPath

```
Unprotect-CmsMessage [-Path] <String> [-IncludeContext] [[-To] <CmsMessageRecipient[]>] [<CommonParameters>]
```

### ByLiteralPath

```
Unprotect-CmsMessage [-LiteralPath] <String> [-IncludeContext] [[-To] <CmsMessageRecipient[]>]
 [<CommonParameters>]
```

## DESCRIPTION

O `Unprotect-CmsMessage` cmdlet descriptografa o conteúdo que foi criptografado usando o formato CMS (sintaxe de mensagem criptografada).

Os cmdlets do CMS dão suporte à criptografia e descriptografia de conteúdo usando o formato padrão da IETF para proteger as mensagens criptograficamente, conforme documentado por [RFC5652](https://tools.ietf.org/html/rfc5652).

O padrão de criptografia do CMS usa criptografia de chave pública, em que as chaves usadas para criptografar conteúdo (a chave pública) e as chaves usadas para descriptografar conteúdo (a chave privada) são separadas. Sua chave pública pode ser compartilhada amplamente e não contém dados confidenciais. Se algum conteúdo for criptografado com essa chave pública, somente sua chave privada poderá descriptografá-lo. Para obter mais informações, consulte [Criptografia por chave pública](https://en.wikipedia.org/wiki/Public-key_cryptography).

`Unprotect-CmsMessage` descriptografa o conteúdo que foi criptografado no formato CMS. Você pode executar este cmdlet para descriptografar o conteúdo que você criptografou executando o `Protect-CmsMessage` cmdlet. Você pode especificar o conteúdo que deseja descriptografar como uma cadeia de caracteres, pelo número da ID de registro do log de eventos de criptografia ou por caminho para o conteúdo criptografado. O `Unprotect-CmsMessage` cmdlet retorna o conteúdo descriptografado.

O suporte para Linux e macOS foi adicionado no PowerShell 7,1.

## EXEMPLOS

### Exemplo 1: descriptografar uma mensagem

No exemplo a seguir, você descriptografa o conteúdo que está localizado no caminho literal `C:\Users\Test\Documents\PowerShell` . Para o valor do parâmetro obrigatório **para** , este exemplo usa a impressão digital do certificado que foi usado para executar a criptografia. A mensagem descriptografada, "Experimente o comando interromper tudo", é o resultado.

```powershell
$parameters = @{
  LiteralPath = "C:\Users\Test\Documents\PowerShell\Future_Plans.txt"
  To = '0f 8j b1 ab e0 ce 35 1d 67 d2 f2 6f a2 d2 00 cl 22 z9 m9 85'
}
Unprotect-CmsMessage -LiteralPath @parameters
```

```Output
Try the new Break All command
```

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
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -EventLogRecord

Especifica uma ID de registro de log de eventos que representa uma operação de criptografia de CMS.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByWinEvent
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IncludeContext

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

### -LiteralPath

Especifica o caminho para o conteúdo criptografado que você deseja descriptografar. Ao contrário de **Path** , o valor de **LiteralPath** é usado exatamente como digitado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres de escape, coloque-o entre aspas simples. Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases:

Required: True
Position: 0
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
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Para

Especifica um ou mais destinatários de mensagens CMS, identificados em qualquer um dos seguintes formatos:

- Um certificado real (como recuperado do provedor de certificado).
- Caminho para o arquivo que contém o certificado.
- Caminho para um diretório que contém o certificado.
- Impressão digital do certificado (usada para examinar o repositório de certificados).
- Nome da entidade do certificado (usado para examinar o repositório de certificados).

```yaml
Type: System.Management.Automation.CmsMessageRecipient[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Diagnostics. Eventing. Reader. EventLogRecord ou System. String

É possível canalizar um objeto que contém conteúdo criptografado para o `Unprotect-CmsMessage` .

## SAÍDAS

### System.String

A mensagem não criptografada.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[Get-CmsMessage](Get-CmsMessage.md)

[Protect-CmsMessage](Protect-CmsMessage.md)

