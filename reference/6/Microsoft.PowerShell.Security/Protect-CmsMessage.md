---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 02/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/protect-cmsmessage?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Protect-CmsMessage
ms.openlocfilehash: d148a9d1013de20885cd9914f283b85a2a7acd3f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194539"
---
# <span data-ttu-id="8b62f-103">Protect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="8b62f-103">Protect-CmsMessage</span></span>

## <span data-ttu-id="8b62f-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="8b62f-104">SYNOPSIS</span></span>
<span data-ttu-id="8b62f-105">Criptografa o conteúdo usando o formato de sintaxe da mensagem criptográfica.</span><span class="sxs-lookup"><span data-stu-id="8b62f-105">Encrypts content by using the Cryptographic Message Syntax format.</span></span>

## <span data-ttu-id="8b62f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8b62f-106">SYNTAX</span></span>

### <span data-ttu-id="8b62f-107">ByContent (padrão)</span><span class="sxs-lookup"><span data-stu-id="8b62f-107">ByContent (Default)</span></span>

```
Protect-CmsMessage [-To] <CmsMessageRecipient[]> [-Content] <PSObject> [[-OutFile] <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="8b62f-108">ByPath</span><span class="sxs-lookup"><span data-stu-id="8b62f-108">ByPath</span></span>

```
Protect-CmsMessage [-To] <CmsMessageRecipient[]> [-Path] <String> [[-OutFile] <String>] [<CommonParameters>]
```

### <span data-ttu-id="8b62f-109">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="8b62f-109">ByLiteralPath</span></span>

```
Protect-CmsMessage [-To] <CmsMessageRecipient[]> [-LiteralPath] <String> [[-OutFile] <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="8b62f-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8b62f-110">DESCRIPTION</span></span>

<span data-ttu-id="8b62f-111">O `Protect-CmsMessage` cmdlet criptografa o conteúdo usando o formato CMS (sintaxe de mensagem criptografada).</span><span class="sxs-lookup"><span data-stu-id="8b62f-111">The `Protect-CmsMessage` cmdlet encrypts content by using the Cryptographic Message Syntax (CMS) format.</span></span>

<span data-ttu-id="8b62f-112">Os cmdlets do CMS dão suporte à criptografia e descriptografia de conteúdo usando o formato IETF, conforme documentado por [RFC5652](https://tools.ietf.org/html/rfc5652.html).</span><span class="sxs-lookup"><span data-stu-id="8b62f-112">The CMS cmdlets support encryption and decryption of content using the IETF format as documented by [RFC5652](https://tools.ietf.org/html/rfc5652.html).</span></span>

<span data-ttu-id="8b62f-113">O padrão de criptografia do CMS usa criptografia de chave pública, em que as chaves usadas para criptografar conteúdo (a chave pública) e as chaves usadas para descriptografar conteúdo (a chave privada) são separadas.</span><span class="sxs-lookup"><span data-stu-id="8b62f-113">The CMS encryption standard uses public key cryptography, where the keys used to encrypt content (the public key) and the keys used to decrypt content (the private key) are separate.</span></span> <span data-ttu-id="8b62f-114">Sua chave pública pode ser compartilhada amplamente e não contém dados confidenciais.</span><span class="sxs-lookup"><span data-stu-id="8b62f-114">Your public key can be shared widely, and is not sensitive data.</span></span> <span data-ttu-id="8b62f-115">Se algum conteúdo for criptografado com essa chave pública, somente sua chave privada poderá descriptografá-lo.</span><span class="sxs-lookup"><span data-stu-id="8b62f-115">If any content is encrypted with this public key, only your private key can decrypt it.</span></span> <span data-ttu-id="8b62f-116">Para obter mais informações, consulte [Criptografia por chave pública](https://en.wikipedia.org/wiki/Public-key_cryptography).</span><span class="sxs-lookup"><span data-stu-id="8b62f-116">For more information, see [Public-key cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).</span></span>

<span data-ttu-id="8b62f-117">Antes de poder executar o `Protect-CmsMessage` cmdlet, você deve ter um certificado de criptografia configurado.</span><span class="sxs-lookup"><span data-stu-id="8b62f-117">Before you can run the `Protect-CmsMessage` cmdlet, you must have an encryption certificate set up.</span></span>
<span data-ttu-id="8b62f-118">Para ser reconhecido no PowerShell, os certificados de criptografia exigem uma ID de[EKU](/windows/desktop/SecCrypto/eku)(uso estendido de chave) exclusiva para identificá-los como certificados de criptografia de dados (como as IDs para assinatura de código e email criptografado).</span><span class="sxs-lookup"><span data-stu-id="8b62f-118">To be recognized in PowerShell, encryption certificates require a unique extended key usage ([EKU](/windows/desktop/SecCrypto/eku)) ID to identify them as data encryption certificates (such as the IDs for Code Signing and Encrypted Mail).</span></span> <span data-ttu-id="8b62f-119">Para obter um exemplo de um certificado que funcionaria para criptografia de documentos, consulte o exemplo 1 neste tópico.</span><span class="sxs-lookup"><span data-stu-id="8b62f-119">For an example of a certificate that would work for document encryption, see Example 1 in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="8b62f-120">Esse cmdlet só está disponível no Windows.</span><span class="sxs-lookup"><span data-stu-id="8b62f-120">This cmdlet is only available on Windows.</span></span>

## <span data-ttu-id="8b62f-121">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="8b62f-121">EXAMPLES</span></span>

### <span data-ttu-id="8b62f-122">Exemplo 1: criar um certificado para criptografar conteúdo</span><span class="sxs-lookup"><span data-stu-id="8b62f-122">Example 1: Create a certificate for encrypting content</span></span>

<span data-ttu-id="8b62f-123">Antes de poder executar o `Protect-CmsMessage` cmdlet, você deve criar um certificado de criptografia.</span><span class="sxs-lookup"><span data-stu-id="8b62f-123">Before you can run the `Protect-CmsMessage` cmdlet, you must create an encryption certificate.</span></span> <span data-ttu-id="8b62f-124">Usando o texto a seguir, altere o nome na linha de assunto para seu nome, email ou outro identificador e salve o certificado em um arquivo (como `DocumentEncryption.inf` , conforme mostrado neste exemplo).</span><span class="sxs-lookup"><span data-stu-id="8b62f-124">Using the following text, change the name in the Subject line to your name, email, or other identifier, and save the certificate in a file (such as `DocumentEncryption.inf`, as shown in this example).</span></span>

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

### <span data-ttu-id="8b62f-125">Exemplo 2: criptografar uma mensagem enviada por email</span><span class="sxs-lookup"><span data-stu-id="8b62f-125">Example 2: Encrypt a message sent by email</span></span>

```powershell
$Protected = "Hello World" | Protect-CmsMessage -To "*youralias@emailaddress.com*"
```

<span data-ttu-id="8b62f-126">No exemplo a seguir, você criptografa uma mensagem, "Olá, Mundo", ao canalizar para o `Protect-CmsMessage` cmdlet e, em seguida, salva a mensagem criptografada em uma variável.</span><span class="sxs-lookup"><span data-stu-id="8b62f-126">In the following example, you encrypt a message, "Hello World", by piping it to the `Protect-CmsMessage` cmdlet, and then save the encrypted message in a variable.</span></span> <span data-ttu-id="8b62f-127">O parâmetro **to** usa o valor da linha de assunto no certificado.</span><span class="sxs-lookup"><span data-stu-id="8b62f-127">The **To** parameter uses the value of the Subject line in the certificate.</span></span>

### <span data-ttu-id="8b62f-128">Exemplo 3: exibir certificados de criptografia de documento</span><span class="sxs-lookup"><span data-stu-id="8b62f-128">Example 3: View document encryption certificates</span></span>

```
PS C:\> cd Cert:\CurrentUser\My
PS Cert:\CurrentUser\My> Get-ChildItem -DocumentEncryptionCert
```

<span data-ttu-id="8b62f-129">Para exibir certificados de criptografia de documento no provedor de certificado, você pode adicionar o parâmetro dinâmico **DocumentEncryptionCert** de [Get-ChildItem](../Microsoft.PowerShell.Management/Get-ChildItem.md), disponível somente quando o provedor de certificado é carregado.</span><span class="sxs-lookup"><span data-stu-id="8b62f-129">To view document encryption certificates in the certificate provider, you can add the **DocumentEncryptionCert** dynamic parameter of [Get-ChildItem](../Microsoft.PowerShell.Management/Get-ChildItem.md), available only when the certificate provider is loaded.</span></span>

## <span data-ttu-id="8b62f-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8b62f-130">PARAMETERS</span></span>

### <span data-ttu-id="8b62f-131">-Conteúdo</span><span class="sxs-lookup"><span data-stu-id="8b62f-131">-Content</span></span>

<span data-ttu-id="8b62f-132">Especifica um **PSObject** que contém o conteúdo que você deseja criptografar.</span><span class="sxs-lookup"><span data-stu-id="8b62f-132">Specifies a **PSObject** that contains content that you want to encrypt.</span></span> <span data-ttu-id="8b62f-133">Por exemplo, você pode criptografar o conteúdo de uma mensagem de evento e, em seguida, usar a variável que contém a mensagem ( `$Event` , neste exemplo) como o valor do parâmetro de **conteúdo** : `$event = Get-WinEvent -ProviderName "PowerShell" -MaxEvents 1` .</span><span class="sxs-lookup"><span data-stu-id="8b62f-133">For example, you can encrypt the content of an event message, and then use the variable containing the message (`$Event`, in this example) as the value of the **Content** parameter: `$event = Get-WinEvent -ProviderName "PowerShell" -MaxEvents 1`.</span></span> <span data-ttu-id="8b62f-134">Você também pode usar o `Get-Content` cmdlet para obter o conteúdo de um arquivo, como um documento do Microsoft Word, e salvar o conteúdo em uma variável que você usa como o valor do parâmetro de **conteúdo** .</span><span class="sxs-lookup"><span data-stu-id="8b62f-134">You can also use the `Get-Content` cmdlet to get the contents of a file, such as a Microsoft Word document, and save the content in a variable that you use as the value of the **Content** parameter.</span></span>

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

### <span data-ttu-id="8b62f-135">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="8b62f-135">-LiteralPath</span></span>

<span data-ttu-id="8b62f-136">Especifica o caminho para o conteúdo que você deseja criptografar.</span><span class="sxs-lookup"><span data-stu-id="8b62f-136">Specifies the path to content that you want to encrypt.</span></span> <span data-ttu-id="8b62f-137">Ao contrário de **Path** , o valor de **LiteralPath** é usado exatamente como digitado.</span><span class="sxs-lookup"><span data-stu-id="8b62f-137">Unlike **Path** , the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="8b62f-138">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="8b62f-138">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="8b62f-139">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="8b62f-139">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="8b62f-140">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="8b62f-140">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="8b62f-141">-Outfile</span><span class="sxs-lookup"><span data-stu-id="8b62f-141">-OutFile</span></span>

<span data-ttu-id="8b62f-142">Especifica o caminho e o nome de arquivo de um arquivo para o qual você deseja enviar o conteúdo criptografado.</span><span class="sxs-lookup"><span data-stu-id="8b62f-142">Specifies the path and file name of a file to which you want to send the encrypted content.</span></span>

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

### <span data-ttu-id="8b62f-143">-Path</span><span class="sxs-lookup"><span data-stu-id="8b62f-143">-Path</span></span>

<span data-ttu-id="8b62f-144">Especifica o caminho para o conteúdo que você deseja criptografar.</span><span class="sxs-lookup"><span data-stu-id="8b62f-144">Specifies the path to content that you want to encrypt.</span></span>

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

### <span data-ttu-id="8b62f-145">-Para</span><span class="sxs-lookup"><span data-stu-id="8b62f-145">-To</span></span>

<span data-ttu-id="8b62f-146">Especifica um ou mais destinatários de mensagens CMS, identificados em qualquer um dos seguintes formatos:</span><span class="sxs-lookup"><span data-stu-id="8b62f-146">Specifies one or more CMS message recipients, identified in any of the following formats:</span></span>

- <span data-ttu-id="8b62f-147">Um certificado real (como recuperado do provedor de certificado).</span><span class="sxs-lookup"><span data-stu-id="8b62f-147">An actual certificate (as retrieved from the certificate provider).</span></span>
- <span data-ttu-id="8b62f-148">Caminho para o arquivo que contém o certificado.</span><span class="sxs-lookup"><span data-stu-id="8b62f-148">Path to the file containing the certificate.</span></span>
- <span data-ttu-id="8b62f-149">Caminho para um diretório que contém o certificado.</span><span class="sxs-lookup"><span data-stu-id="8b62f-149">Path to a directory containing the certificate.</span></span>
- <span data-ttu-id="8b62f-150">Impressão digital do certificado (usada para examinar o repositório de certificados).</span><span class="sxs-lookup"><span data-stu-id="8b62f-150">Thumbprint of the certificate (used to look in the certificate store).</span></span>
- <span data-ttu-id="8b62f-151">Nome da entidade do certificado (usado para examinar o repositório de certificados).</span><span class="sxs-lookup"><span data-stu-id="8b62f-151">Subject name of the certificate (used to look in the certificate store).</span></span>

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

### <span data-ttu-id="8b62f-152">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8b62f-152">CommonParameters</span></span>

<span data-ttu-id="8b62f-153">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="8b62f-153">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="8b62f-154">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="8b62f-154">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="8b62f-155">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="8b62f-155">INPUTS</span></span>

## <span data-ttu-id="8b62f-156">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="8b62f-156">OUTPUTS</span></span>

## <span data-ttu-id="8b62f-157">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="8b62f-157">NOTES</span></span>

## <span data-ttu-id="8b62f-158">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="8b62f-158">RELATED LINKS</span></span>

[<span data-ttu-id="8b62f-159">about_Providers</span><span class="sxs-lookup"><span data-stu-id="8b62f-159">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="8b62f-160">Get-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="8b62f-160">Get-CmsMessage</span></span>](Get-CmsMessage.md)

[<span data-ttu-id="8b62f-161">Unprotect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="8b62f-161">Unprotect-CmsMessage</span></span>](Unprotect-CmsMessage.md)
