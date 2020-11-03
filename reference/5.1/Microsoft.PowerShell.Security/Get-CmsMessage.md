---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 02/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-cmsmessage?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CmsMessage
ms.openlocfilehash: bafe666c5cb24accfc931c58cb1805e85455ab30
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193884"
---
# <span data-ttu-id="cd927-103">Get-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="cd927-103">Get-CmsMessage</span></span>

## <span data-ttu-id="cd927-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="cd927-104">SYNOPSIS</span></span>
<span data-ttu-id="cd927-105">Obtém o conteúdo que foi criptografado usando o formato de sintaxe da mensagem criptográfica.</span><span class="sxs-lookup"><span data-stu-id="cd927-105">Gets content that has been encrypted by using the Cryptographic Message Syntax format.</span></span>

## <span data-ttu-id="cd927-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cd927-106">SYNTAX</span></span>

### <span data-ttu-id="cd927-107">ByContent</span><span class="sxs-lookup"><span data-stu-id="cd927-107">ByContent</span></span>

```
Get-CmsMessage [-Content] <String> [<CommonParameters>]
```

### <span data-ttu-id="cd927-108">ByPath</span><span class="sxs-lookup"><span data-stu-id="cd927-108">ByPath</span></span>

```
Get-CmsMessage [-Path] <String> [<CommonParameters>]
```

### <span data-ttu-id="cd927-109">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="cd927-109">ByLiteralPath</span></span>

```
Get-CmsMessage [-LiteralPath] <String> [<CommonParameters>]
```

## <span data-ttu-id="cd927-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cd927-110">DESCRIPTION</span></span>

<span data-ttu-id="cd927-111">O `Get-CmsMessage` cmdlet obtém o conteúdo que foi criptografado usando o formato CMS (sintaxe de mensagem criptografada).</span><span class="sxs-lookup"><span data-stu-id="cd927-111">The `Get-CmsMessage` cmdlet gets content that has been encrypted using the Cryptographic Message Syntax (CMS) format.</span></span>

<span data-ttu-id="cd927-112">Os cmdlets CMS dão suporte à criptografia e descriptografia de conteúdo usando o formato IETF para proteger as mensagens criptograficamente, conforme documentado por [RFC5652](https://tools.ietf.org/html/rfc5652).</span><span class="sxs-lookup"><span data-stu-id="cd927-112">The CMS cmdlets support encryption and decryption of content using the IETF format for cryptographically protecting messages, as documented by [RFC5652](https://tools.ietf.org/html/rfc5652).</span></span>

<span data-ttu-id="cd927-113">O padrão de criptografia do CMS usa criptografia de chave pública, em que as chaves usadas para criptografar conteúdo (a chave pública) e as chaves usadas para descriptografar conteúdo (a chave privada) são separadas.</span><span class="sxs-lookup"><span data-stu-id="cd927-113">The CMS encryption standard uses public key cryptography, where the keys used to encrypt content (the public key) and the keys used to decrypt content (the private key) are separate.</span></span> <span data-ttu-id="cd927-114">Sua chave pública pode ser compartilhada amplamente e não contém dados confidenciais.</span><span class="sxs-lookup"><span data-stu-id="cd927-114">Your public key can be shared widely, and is not sensitive data.</span></span> <span data-ttu-id="cd927-115">Se algum conteúdo for criptografado com essa chave pública, somente sua chave privada poderá descriptografá-lo.</span><span class="sxs-lookup"><span data-stu-id="cd927-115">If any content is encrypted with this public key, only your private key can decrypt it.</span></span> <span data-ttu-id="cd927-116">Para obter mais informações, consulte [Criptografia por chave pública](https://en.wikipedia.org/wiki/Public-key_cryptography).</span><span class="sxs-lookup"><span data-stu-id="cd927-116">For more information, see [Public-key cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).</span></span>

<span data-ttu-id="cd927-117">`Get-CmsMessage` Obtém o conteúdo que foi criptografado no formato CMS.</span><span class="sxs-lookup"><span data-stu-id="cd927-117">`Get-CmsMessage` gets content that has been encrypted in CMS format.</span></span> <span data-ttu-id="cd927-118">Ele não descriptografa nem desprotege o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="cd927-118">It does not decrypt or unprotect content.</span></span> <span data-ttu-id="cd927-119">Você pode executar este cmdlet para obter o conteúdo que você criptografou executando o `Protect-CmsMessage` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="cd927-119">You can run this cmdlet to get content that you have encrypted by running the `Protect-CmsMessage` cmdlet.</span></span> <span data-ttu-id="cd927-120">Você pode especificar o conteúdo que deseja descriptografar como uma cadeia de caracteres ou por caminho para o conteúdo criptografado.</span><span class="sxs-lookup"><span data-stu-id="cd927-120">You can specify content that you want to decrypt as a string, or by path to the encrypted content.</span></span> <span data-ttu-id="cd927-121">É possível canalizar os resultados de `Get-CmsMessage` para `Unprotect-CmsMessage` para descriptografar o conteúdo, desde que você tenha informações sobre o certificado de criptografia do documento que foi usado para criptografar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="cd927-121">You can pipe the results of `Get-CmsMessage` to `Unprotect-CmsMessage` to decrypt the content, provided that you have information about the document encryption certificate that was used to encrypt the content.</span></span>

## <span data-ttu-id="cd927-122">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="cd927-122">EXAMPLES</span></span>

### <span data-ttu-id="cd927-123">Exemplo 1: obter conteúdo criptografado</span><span class="sxs-lookup"><span data-stu-id="cd927-123">Example 1: Get encrypted content</span></span>

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

<span data-ttu-id="cd927-124">Este comando obtém o conteúdo criptografado localizado em C:\Users\Test\Documents\PowerShell\Future_Plans.txt.</span><span class="sxs-lookup"><span data-stu-id="cd927-124">This command gets encrypted content located at C:\Users\Test\Documents\PowerShell\Future_Plans.txt.</span></span>

### <span data-ttu-id="cd927-125">Exemplo 2: direcionar conteúdo criptografado para Unprotect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="cd927-125">Example 2: Pipe encrypted content to Unprotect-CmsMessage</span></span>

```powershell
$Msg = Get-CmsMessage -Path "C:\Users\Test\Documents\PowerShell\Future_Plans.txt"
$Msg | Unprotect-CmsMessage -To "cn=youralias@emailaddress.com"
```

```Output
Try the new Break All command
```

<span data-ttu-id="cd927-126">Esse comando canaliza os resultados do `Get-CmsMessage` cmdlet do exemplo 1 para `Unprotect-CmsMessage` , para descriptografar a mensagem e lê-la em texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="cd927-126">This command pipes the results of the `Get-CmsMessage` cmdlet from Example 1 to `Unprotect-CmsMessage`, to decrypt the message and read it in plain text.</span></span> <span data-ttu-id="cd927-127">Nesse caso, o valor do parâmetro **to** é o valor da linha de assunto do certificado de criptografia.</span><span class="sxs-lookup"><span data-stu-id="cd927-127">In this case, the value of the **To** parameter is the value of the encrypting certificate's Subject line.</span></span> <span data-ttu-id="cd927-128">A mensagem descriptografada, "Experimente o comando interromper tudo", é o resultado.</span><span class="sxs-lookup"><span data-stu-id="cd927-128">The decrypted message, "Try the new Break All command," is the result.</span></span>

## <span data-ttu-id="cd927-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cd927-129">PARAMETERS</span></span>

### <span data-ttu-id="cd927-130">-Conteúdo</span><span class="sxs-lookup"><span data-stu-id="cd927-130">-Content</span></span>

<span data-ttu-id="cd927-131">Especifica uma cadeia de caracteres criptografada ou uma variável que contém uma cadeia de caracteres criptografada.</span><span class="sxs-lookup"><span data-stu-id="cd927-131">Specifies an encrypted string, or a variable containing an encrypted string.</span></span>

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

### <span data-ttu-id="cd927-132">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="cd927-132">-LiteralPath</span></span>

<span data-ttu-id="cd927-133">Especifica o caminho para o conteúdo criptografado que você deseja obter.</span><span class="sxs-lookup"><span data-stu-id="cd927-133">Specifies the path to encrypted content that you want to get.</span></span> <span data-ttu-id="cd927-134">Ao contrário de **Path** , o valor de **LiteralPath** é usado exatamente como digitado.</span><span class="sxs-lookup"><span data-stu-id="cd927-134">Unlike **Path** , the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="cd927-135">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="cd927-135">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="cd927-136">Se o caminho incluir caracteres de escape, coloque cada um entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="cd927-136">If the path includes escape characters, enclose each one in single quotation marks.</span></span>
<span data-ttu-id="cd927-137">Aspas simples instruem o PowerShell a não interpretar caracteres incluídos como caracteres de escape.</span><span class="sxs-lookup"><span data-stu-id="cd927-137">Single quotation marks tell PowerShell not to interpret enclosed characters as escape characters.</span></span>

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

### <span data-ttu-id="cd927-138">-Path</span><span class="sxs-lookup"><span data-stu-id="cd927-138">-Path</span></span>

<span data-ttu-id="cd927-139">Especifica o caminho para o conteúdo criptografado que você deseja descriptografar.</span><span class="sxs-lookup"><span data-stu-id="cd927-139">Specifies the path to encrypted content that you want to decrypt.</span></span>

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

### <span data-ttu-id="cd927-140">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="cd927-140">CommonParameters</span></span>

<span data-ttu-id="cd927-141">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="cd927-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cd927-142">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="cd927-142">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cd927-143">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="cd927-143">INPUTS</span></span>

## <span data-ttu-id="cd927-144">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="cd927-144">OUTPUTS</span></span>

## <span data-ttu-id="cd927-145">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="cd927-145">NOTES</span></span>

## <span data-ttu-id="cd927-146">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="cd927-146">RELATED LINKS</span></span>

[<span data-ttu-id="cd927-147">about_Providers</span><span class="sxs-lookup"><span data-stu-id="cd927-147">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="cd927-148">Protect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="cd927-148">Protect-CmsMessage</span></span>](Protect-CmsMessage.md)

[<span data-ttu-id="cd927-149">Unprotect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="cd927-149">Unprotect-CmsMessage</span></span>](Unprotect-CmsMessage.md)
