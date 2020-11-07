---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 02/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/protect-cmsmessage?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Protect-CmsMessage
ms.openlocfilehash: 4a181c68527c7b9d3a698ec31bbcadbe36762376
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347220"
---
# Protect-CmsMessage

## SINOPSE
Criptografa o conteúdo usando o formato de sintaxe da mensagem criptográfica.

## SYNTAX

### ByContent (padrão)

```
Protect-CmsMessage [-To] <CmsMessageRecipient[]> [-Content] <PSObject> [[-OutFile] <String>]
 [<CommonParameters>]
```

### ByPath

```
Protect-CmsMessage [-To] <CmsMessageRecipient[]> [-Path] <String> [[-OutFile] <String>] [<CommonParameters>]
```

### ByLiteralPath

```
Protect-CmsMessage [-To] <CmsMessageRecipient[]> [-LiteralPath] <String> [[-OutFile] <String>]
 [<CommonParameters>]
```

## DESCRIPTION

O `Protect-CmsMessage` cmdlet criptografa o conteúdo usando o formato CMS (sintaxe de mensagem criptografada).

Os cmdlets do CMS dão suporte à criptografia e descriptografia de conteúdo usando o formato IETF, conforme documentado por [RFC5652](https://tools.ietf.org/html/rfc5652.html).

O padrão de criptografia do CMS usa criptografia de chave pública, em que as chaves usadas para criptografar conteúdo (a chave pública) e as chaves usadas para descriptografar conteúdo (a chave privada) são separadas. Sua chave pública pode ser compartilhada amplamente e não contém dados confidenciais. Se algum conteúdo for criptografado com essa chave pública, somente sua chave privada poderá descriptografá-lo. Para obter mais informações, consulte [Criptografia por chave pública](https://en.wikipedia.org/wiki/Public-key_cryptography).

Antes de poder executar o `Protect-CmsMessage` cmdlet, você deve ter um certificado de criptografia configurado.
Para ser reconhecido no PowerShell, os certificados de criptografia exigem uma ID de[EKU](/windows/desktop/SecCrypto/eku)(uso estendido de chave) exclusiva para identificá-los como certificados de criptografia de dados (como as IDs para assinatura de código e email criptografado). Para obter um exemplo de um certificado que funcionaria para criptografia de documentos, consulte o exemplo 1 neste tópico.

O suporte para Linux e macOS foi adicionado no PowerShell 7,1.

## EXEMPLOS

### Exemplo 1: criar um certificado para criptografar conteúdo

Antes de poder executar o `Protect-CmsMessage` cmdlet, você deve criar um certificado de criptografia. Usando o texto a seguir, altere o nome na linha de assunto para seu nome, email ou outro identificador e salve o certificado em um arquivo (como `DocumentEncryption.inf` , conforme mostrado neste exemplo).

```powershell
# Create .INF file for certreq
{[Version]
Signature = "$Windows NT$"

[Strings]
szOID_ENHANCED_KEY_USAGE = "2.5.29.37"
szOID_DOCUMENT_ENCRYPTION = "1.3.6.1.4.1.311.80.1"

[NewRequest]
Subject = "cn=youralias@emailaddress.com"
MachineKeySet = false
KeyLength = 2048
KeySpec = AT_KEYEXCHANGE
HashAlgorithm = Sha1
Exportable = true
RequestType = Cert
KeyUsage = "CERT_KEY_ENCIPHERMENT_KEY_USAGE | CERT_DATA_ENCIPHERMENT_KEY_USAGE"
ValidityPeriod = "Years"
ValidityPeriodUnits = "1000"

[Extensions]
%szOID_ENHANCED_KEY_USAGE% = "{text}%szOID_DOCUMENT_ENCRYPTION%"
} | Out-File -FilePath DocumentEncryption.inf

# After you have created your certificate file, run the following command to add
# the certificate file to the certificate store. Now you are ready to encrypt and
# decrypt content with the next two examples.
certreq.exe -new DocumentEncryption.inf DocumentEncryption.cer
```

### Exemplo 2: criptografar uma mensagem enviada por email

```powershell
$Protected = "Hello World" | Protect-CmsMessage -To "*youralias@emailaddress.com*"
```

No exemplo a seguir, você criptografa uma mensagem, "Olá, Mundo", ao canalizar para o `Protect-CmsMessage` cmdlet e, em seguida, salva a mensagem criptografada em uma variável. O parâmetro **to** usa o valor da linha de assunto no certificado.

### Exemplo 3: exibir certificados de criptografia de documento

```
PS C:\> cd Cert:\CurrentUser\My
PS Cert:\CurrentUser\My> Get-ChildItem -DocumentEncryptionCert
```

Para exibir certificados de criptografia de documento no provedor de certificado, você pode adicionar o parâmetro dinâmico **DocumentEncryptionCert** de [Get-ChildItem](../Microsoft.PowerShell.Management/Get-ChildItem.md), disponível somente quando o provedor de certificado é carregado.

## PARAMETERS

### -Conteúdo

Especifica um **PSObject** que contém o conteúdo que você deseja criptografar. Por exemplo, você pode criptografar o conteúdo de uma mensagem de evento e, em seguida, usar a variável que contém a mensagem ( `$Event` , neste exemplo) como o valor do parâmetro de **conteúdo** : `$event = Get-WinEvent -ProviderName "PowerShell" -MaxEvents 1` . Você também pode usar o `Get-Content` cmdlet para obter o conteúdo de um arquivo, como um documento do Microsoft Word, e salvar o conteúdo em uma variável que você usa como o valor do parâmetro de **conteúdo** .

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByContent
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LiteralPath

Especifica o caminho para o conteúdo que você deseja criptografar. Ao contrário de **Path** , o valor de **LiteralPath** é usado exatamente como digitado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres de escape, coloque-o entre aspas simples. Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

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

### -Outfile

Especifica o caminho e o nome de arquivo de um arquivo para o qual você deseja enviar o conteúdo criptografado.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Especifica o caminho para o conteúdo que você deseja criptografar.

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

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` . Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

## SAÍDAS

## OBSERVAÇÕES

## LINKS RELACIONADOS

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[Get-CmsMessage](Get-CmsMessage.md)

[Unprotect-CmsMessage](Unprotect-CmsMessage.md)
