---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 02/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/unprotect-cmsmessage?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unprotect-CmsMessage
ms.openlocfilehash: ed1c80a70e8fc51c242be6f9369f0a0bd44cb9c8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597647"
---
# <span data-ttu-id="7e523-102">Unprotect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="7e523-102">Unprotect-CmsMessage</span></span>

## <span data-ttu-id="7e523-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="7e523-103">SYNOPSIS</span></span>
<span data-ttu-id="7e523-104">Descriptografa o conteúdo que foi criptografado usando o formato de sintaxe da mensagem criptográfica.</span><span class="sxs-lookup"><span data-stu-id="7e523-104">Decrypts content that has been encrypted by using the Cryptographic Message Syntax format.</span></span>

## <span data-ttu-id="7e523-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7e523-105">SYNTAX</span></span>

### <span data-ttu-id="7e523-106">ByWinEvent (padrão)</span><span class="sxs-lookup"><span data-stu-id="7e523-106">ByWinEvent (Default)</span></span>

```
Unprotect-CmsMessage [-EventLogRecord] <PSObject> [-IncludeContext] [[-To] <CmsMessageRecipient[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="7e523-107">ByContent</span><span class="sxs-lookup"><span data-stu-id="7e523-107">ByContent</span></span>

```
Unprotect-CmsMessage [-Content] <String> [-IncludeContext] [[-To] <CmsMessageRecipient[]>] [<CommonParameters>]
```

### <span data-ttu-id="7e523-108">ByPath</span><span class="sxs-lookup"><span data-stu-id="7e523-108">ByPath</span></span>

```
Unprotect-CmsMessage [-Path] <String> [-IncludeContext] [[-To] <CmsMessageRecipient[]>] [<CommonParameters>]
```

### <span data-ttu-id="7e523-109">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="7e523-109">ByLiteralPath</span></span>

```
Unprotect-CmsMessage [-LiteralPath] <String> [-IncludeContext] [[-To] <CmsMessageRecipient[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="7e523-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7e523-110">DESCRIPTION</span></span>

<span data-ttu-id="7e523-111">O `Unprotect-CmsMessage` cmdlet descriptografa o conteúdo que foi criptografado usando o formato CMS (sintaxe de mensagem criptografada).</span><span class="sxs-lookup"><span data-stu-id="7e523-111">The `Unprotect-CmsMessage` cmdlet decrypts content that has been encrypted by using the Cryptographic Message Syntax (CMS) format.</span></span>

<span data-ttu-id="7e523-112">Os cmdlets do CMS dão suporte à criptografia e descriptografia de conteúdo usando o formato padrão da IETF para proteger as mensagens criptograficamente, conforme documentado por [RFC5652](https://tools.ietf.org/html/rfc5652).</span><span class="sxs-lookup"><span data-stu-id="7e523-112">The CMS cmdlets support encryption and decryption of content using the IETF standard format for cryptographically protecting messages, as documented by [RFC5652](https://tools.ietf.org/html/rfc5652).</span></span>

<span data-ttu-id="7e523-113">O padrão de criptografia do CMS usa criptografia de chave pública, em que as chaves usadas para criptografar conteúdo (a chave pública) e as chaves usadas para descriptografar conteúdo (a chave privada) são separadas.</span><span class="sxs-lookup"><span data-stu-id="7e523-113">The CMS encryption standard uses public key cryptography, where the keys used to encrypt content (the public key) and the keys used to decrypt content (the private key) are separate.</span></span> <span data-ttu-id="7e523-114">Sua chave pública pode ser compartilhada amplamente e não contém dados confidenciais.</span><span class="sxs-lookup"><span data-stu-id="7e523-114">Your public key can be shared widely, and is not sensitive data.</span></span> <span data-ttu-id="7e523-115">Se algum conteúdo for criptografado com essa chave pública, somente sua chave privada poderá descriptografá-lo.</span><span class="sxs-lookup"><span data-stu-id="7e523-115">If any content is encrypted with this public key, only your private key can decrypt it.</span></span> <span data-ttu-id="7e523-116">Para obter mais informações, consulte [Criptografia por chave pública](https://en.wikipedia.org/wiki/Public-key_cryptography).</span><span class="sxs-lookup"><span data-stu-id="7e523-116">For more information, see [Public-key cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).</span></span>

<span data-ttu-id="7e523-117">`Unprotect-CmsMessage` descriptografa o conteúdo que foi criptografado no formato CMS.</span><span class="sxs-lookup"><span data-stu-id="7e523-117">`Unprotect-CmsMessage` decrypts content that has been encrypted in CMS format.</span></span> <span data-ttu-id="7e523-118">Você pode executar este cmdlet para descriptografar o conteúdo que você criptografou executando o `Protect-CmsMessage` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7e523-118">You can run this cmdlet to decrypt content that you have encrypted by running the `Protect-CmsMessage` cmdlet.</span></span> <span data-ttu-id="7e523-119">Você pode especificar o conteúdo que deseja descriptografar como uma cadeia de caracteres, pelo número da ID de registro do log de eventos de criptografia ou por caminho para o conteúdo criptografado.</span><span class="sxs-lookup"><span data-stu-id="7e523-119">You can specify content that you want to decrypt as a string, by the encryption event log record ID number, or by path to the encrypted content.</span></span> <span data-ttu-id="7e523-120">O `Unprotect-CmsMessage` cmdlet retorna o conteúdo descriptografado.</span><span class="sxs-lookup"><span data-stu-id="7e523-120">The `Unprotect-CmsMessage` cmdlet returns the decrypted content.</span></span>

<span data-ttu-id="7e523-121">O suporte para Linux e macOS foi adicionado no PowerShell 7,1.</span><span class="sxs-lookup"><span data-stu-id="7e523-121">Support for Linux and macOS was added in PowerShell 7.1.</span></span>

## <span data-ttu-id="7e523-122">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="7e523-122">EXAMPLES</span></span>

### <span data-ttu-id="7e523-123">Exemplo 1: descriptografar uma mensagem</span><span class="sxs-lookup"><span data-stu-id="7e523-123">Example 1: Decrypt a message</span></span>

<span data-ttu-id="7e523-124">No exemplo a seguir, você descriptografa o conteúdo que está localizado no caminho literal `C:\Users\Test\Documents\PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="7e523-124">In the following example, you decrypt content that is located at the literal path `C:\Users\Test\Documents\PowerShell`.</span></span> <span data-ttu-id="7e523-125">Para o valor do parâmetro obrigatório **para** , este exemplo usa a impressão digital do certificado que foi usado para executar a criptografia.</span><span class="sxs-lookup"><span data-stu-id="7e523-125">For the value of the required **To** parameter, this example uses the thumbprint of the certificate that was used to perform the encryption.</span></span> <span data-ttu-id="7e523-126">A mensagem descriptografada, "Experimente o comando interromper tudo", é o resultado.</span><span class="sxs-lookup"><span data-stu-id="7e523-126">The decrypted message, "Try the new Break All command," is the result.</span></span>

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

## <span data-ttu-id="7e523-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7e523-127">PARAMETERS</span></span>

### <span data-ttu-id="7e523-128">-Conteúdo</span><span class="sxs-lookup"><span data-stu-id="7e523-128">-Content</span></span>

<span data-ttu-id="7e523-129">Especifica uma cadeia de caracteres criptografada ou uma variável que contém uma cadeia de caracteres criptografada.</span><span class="sxs-lookup"><span data-stu-id="7e523-129">Specifies an encrypted string, or a variable containing an encrypted string.</span></span>

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

### <span data-ttu-id="7e523-130">-EventLogRecord</span><span class="sxs-lookup"><span data-stu-id="7e523-130">-EventLogRecord</span></span>

<span data-ttu-id="7e523-131">Especifica uma ID de registro de log de eventos que representa uma operação de criptografia de CMS.</span><span class="sxs-lookup"><span data-stu-id="7e523-131">Specifies an event log record ID that represents a CMS encryption operation.</span></span>

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

### <span data-ttu-id="7e523-132">-IncludeContext</span><span class="sxs-lookup"><span data-stu-id="7e523-132">-IncludeContext</span></span>

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

### <span data-ttu-id="7e523-133">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="7e523-133">-LiteralPath</span></span>

<span data-ttu-id="7e523-134">Especifica o caminho para o conteúdo criptografado que você deseja descriptografar.</span><span class="sxs-lookup"><span data-stu-id="7e523-134">Specifies the path to encrypted content that you want to decrypt.</span></span> <span data-ttu-id="7e523-135">Ao contrário de **Path**, o valor de **LiteralPath** é usado exatamente como digitado.</span><span class="sxs-lookup"><span data-stu-id="7e523-135">Unlike **Path**, the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="7e523-136">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="7e523-136">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="7e523-137">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="7e523-137">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="7e523-138">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="7e523-138">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="7e523-139">-Path</span><span class="sxs-lookup"><span data-stu-id="7e523-139">-Path</span></span>

<span data-ttu-id="7e523-140">Especifica o caminho para o conteúdo criptografado que você deseja descriptografar.</span><span class="sxs-lookup"><span data-stu-id="7e523-140">Specifies the path to encrypted content that you want to decrypt.</span></span>

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

### <span data-ttu-id="7e523-141">-Para</span><span class="sxs-lookup"><span data-stu-id="7e523-141">-To</span></span>

<span data-ttu-id="7e523-142">Especifica um ou mais destinatários de mensagens CMS, identificados em qualquer um dos seguintes formatos:</span><span class="sxs-lookup"><span data-stu-id="7e523-142">Specifies one or more CMS message recipients, identified in any of the following formats:</span></span>

- <span data-ttu-id="7e523-143">Um certificado real (como recuperado do provedor de certificado).</span><span class="sxs-lookup"><span data-stu-id="7e523-143">An actual certificate (as retrieved from the certificate provider).</span></span>
- <span data-ttu-id="7e523-144">Caminho para o arquivo que contém o certificado.</span><span class="sxs-lookup"><span data-stu-id="7e523-144">Path to the a file containing the certificate.</span></span>
- <span data-ttu-id="7e523-145">Caminho para um diretório que contém o certificado.</span><span class="sxs-lookup"><span data-stu-id="7e523-145">Path to a directory containing the certificate.</span></span>
- <span data-ttu-id="7e523-146">Impressão digital do certificado (usada para examinar o repositório de certificados).</span><span class="sxs-lookup"><span data-stu-id="7e523-146">Thumbprint of the certificate (used to look in the certificate store).</span></span>
- <span data-ttu-id="7e523-147">Nome da entidade do certificado (usado para examinar o repositório de certificados).</span><span class="sxs-lookup"><span data-stu-id="7e523-147">Subject name of the certificate (used to look in the certificate store).</span></span>

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

### <span data-ttu-id="7e523-148">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7e523-148">CommonParameters</span></span>

<span data-ttu-id="7e523-149">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7e523-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7e523-150">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7e523-150">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7e523-151">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="7e523-151">INPUTS</span></span>

### <span data-ttu-id="7e523-152">System. Diagnostics. Eventing. Reader. EventLogRecord ou System. String</span><span class="sxs-lookup"><span data-stu-id="7e523-152">System.Diagnostics.Eventing.Reader.EventLogRecord or System.String</span></span>

<span data-ttu-id="7e523-153">É possível canalizar um objeto que contém conteúdo criptografado para o `Unprotect-CmsMessage` .</span><span class="sxs-lookup"><span data-stu-id="7e523-153">You can pipe an object containing encrypted content to `Unprotect-CmsMessage`.</span></span>

## <span data-ttu-id="7e523-154">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="7e523-154">OUTPUTS</span></span>

### <span data-ttu-id="7e523-155">System.String</span><span class="sxs-lookup"><span data-stu-id="7e523-155">System.String</span></span>

<span data-ttu-id="7e523-156">A mensagem não criptografada.</span><span class="sxs-lookup"><span data-stu-id="7e523-156">The unencrypted message.</span></span>

## <span data-ttu-id="7e523-157">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="7e523-157">NOTES</span></span>

## <span data-ttu-id="7e523-158">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="7e523-158">RELATED LINKS</span></span>

[<span data-ttu-id="7e523-159">about_Providers</span><span class="sxs-lookup"><span data-stu-id="7e523-159">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="7e523-160">Get-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="7e523-160">Get-CmsMessage</span></span>](Get-CmsMessage.md)

[<span data-ttu-id="7e523-161">Protect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="7e523-161">Protect-CmsMessage</span></span>](Protect-CmsMessage.md)
