---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 02/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/unprotect-cmsmessage?view=powershell-7.x&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unprotect-CmsMessage
ms.openlocfilehash: 394e8c1b18d7ba0f4b65e1681faffe795592b97d
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347662"
---
# <span data-ttu-id="1bb0d-103">Unprotect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="1bb0d-103">Unprotect-CmsMessage</span></span>

## <span data-ttu-id="1bb0d-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="1bb0d-104">SYNOPSIS</span></span>
<span data-ttu-id="1bb0d-105">Descriptografa o conteúdo que foi criptografado usando o formato de sintaxe da mensagem criptográfica.</span><span class="sxs-lookup"><span data-stu-id="1bb0d-105">Decrypts content that has been encrypted by using the Cryptographic Message Syntax format.</span></span>

## <span data-ttu-id="1bb0d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1bb0d-106">SYNTAX</span></span>

### <span data-ttu-id="1bb0d-107">ByWinEvent (padrão)</span><span class="sxs-lookup"><span data-stu-id="1bb0d-107">ByWinEvent (Default)</span></span>

```
Unprotect-CmsMessage [-EventLogRecord] <PSObject> [-IncludeContext] [[-To] <CmsMessageRecipient[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="1bb0d-108">ByContent</span><span class="sxs-lookup"><span data-stu-id="1bb0d-108">ByContent</span></span>

```
Unprotect-CmsMessage [-Content] <String> [-IncludeContext] [[-To] <CmsMessageRecipient[]>] [<CommonParameters>]
```

### <span data-ttu-id="1bb0d-109">ByPath</span><span class="sxs-lookup"><span data-stu-id="1bb0d-109">ByPath</span></span>

```
Unprotect-CmsMessage [-Path] <String> [-IncludeContext] [[-To] <CmsMessageRecipient[]>] [<CommonParameters>]
```

### <span data-ttu-id="1bb0d-110">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="1bb0d-110">ByLiteralPath</span></span>

```
Unprotect-CmsMessage [-LiteralPath] <String> [-IncludeContext] [[-To] <CmsMessageRecipient[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="1bb0d-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1bb0d-111">DESCRIPTION</span></span>

<span data-ttu-id="1bb0d-112">O `Unprotect-CmsMessage` cmdlet descriptografa o conteúdo que foi criptografado usando o formato CMS (sintaxe de mensagem criptografada).</span><span class="sxs-lookup"><span data-stu-id="1bb0d-112">The `Unprotect-CmsMessage` cmdlet decrypts content that has been encrypted by using the Cryptographic Message Syntax (CMS) format.</span></span>

<span data-ttu-id="1bb0d-113">Os cmdlets do CMS dão suporte à criptografia e descriptografia de conteúdo usando o formato padrão da IETF para proteger as mensagens criptograficamente, conforme documentado por [RFC5652](https://tools.ietf.org/html/rfc5652).</span><span class="sxs-lookup"><span data-stu-id="1bb0d-113">The CMS cmdlets support encryption and decryption of content using the IETF standard format for cryptographically protecting messages, as documented by [RFC5652](https://tools.ietf.org/html/rfc5652).</span></span>

<span data-ttu-id="1bb0d-114">O padrão de criptografia do CMS usa criptografia de chave pública, em que as chaves usadas para criptografar conteúdo (a chave pública) e as chaves usadas para descriptografar conteúdo (a chave privada) são separadas.</span><span class="sxs-lookup"><span data-stu-id="1bb0d-114">The CMS encryption standard uses public key cryptography, where the keys used to encrypt content (the public key) and the keys used to decrypt content (the private key) are separate.</span></span> <span data-ttu-id="1bb0d-115">Sua chave pública pode ser compartilhada amplamente e não contém dados confidenciais.</span><span class="sxs-lookup"><span data-stu-id="1bb0d-115">Your public key can be shared widely, and is not sensitive data.</span></span> <span data-ttu-id="1bb0d-116">Se algum conteúdo for criptografado com essa chave pública, somente sua chave privada poderá descriptografá-lo.</span><span class="sxs-lookup"><span data-stu-id="1bb0d-116">If any content is encrypted with this public key, only your private key can decrypt it.</span></span> <span data-ttu-id="1bb0d-117">Para obter mais informações, consulte [Criptografia por chave pública](https://en.wikipedia.org/wiki/Public-key_cryptography).</span><span class="sxs-lookup"><span data-stu-id="1bb0d-117">For more information, see [Public-key cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).</span></span>

<span data-ttu-id="1bb0d-118">`Unprotect-CmsMessage` descriptografa o conteúdo que foi criptografado no formato CMS.</span><span class="sxs-lookup"><span data-stu-id="1bb0d-118">`Unprotect-CmsMessage` decrypts content that has been encrypted in CMS format.</span></span> <span data-ttu-id="1bb0d-119">Você pode executar este cmdlet para descriptografar o conteúdo que você criptografou executando o `Protect-CmsMessage` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1bb0d-119">You can run this cmdlet to decrypt content that you have encrypted by running the `Protect-CmsMessage` cmdlet.</span></span> <span data-ttu-id="1bb0d-120">Você pode especificar o conteúdo que deseja descriptografar como uma cadeia de caracteres, pelo número da ID de registro do log de eventos de criptografia ou por caminho para o conteúdo criptografado.</span><span class="sxs-lookup"><span data-stu-id="1bb0d-120">You can specify content that you want to decrypt as a string, by the encryption event log record ID number, or by path to the encrypted content.</span></span> <span data-ttu-id="1bb0d-121">O `Unprotect-CmsMessage` cmdlet retorna o conteúdo descriptografado.</span><span class="sxs-lookup"><span data-stu-id="1bb0d-121">The `Unprotect-CmsMessage` cmdlet returns the decrypted content.</span></span>

> [!NOTE]
> <span data-ttu-id="1bb0d-122">Esse cmdlet só está disponível no Windows.</span><span class="sxs-lookup"><span data-stu-id="1bb0d-122">This cmdlet is only available on Windows.</span></span>

## <span data-ttu-id="1bb0d-123">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="1bb0d-123">EXAMPLES</span></span>

### <span data-ttu-id="1bb0d-124">Exemplo 1: descriptografar uma mensagem</span><span class="sxs-lookup"><span data-stu-id="1bb0d-124">Example 1: Decrypt a message</span></span>

<span data-ttu-id="1bb0d-125">No exemplo a seguir, você descriptografa o conteúdo que está localizado no caminho literal `C:\Users\Test\Documents\PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="1bb0d-125">In the following example, you decrypt content that is located at the literal path `C:\Users\Test\Documents\PowerShell`.</span></span> <span data-ttu-id="1bb0d-126">Para o valor do parâmetro obrigatório **para** , este exemplo usa a impressão digital do certificado que foi usado para executar a criptografia.</span><span class="sxs-lookup"><span data-stu-id="1bb0d-126">For the value of the required **To** parameter, this example uses the thumbprint of the certificate that was used to perform the encryption.</span></span> <span data-ttu-id="1bb0d-127">A mensagem descriptografada, "Experimente o comando interromper tudo", é o resultado.</span><span class="sxs-lookup"><span data-stu-id="1bb0d-127">The decrypted message, "Try the new Break All command," is the result.</span></span>

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

## <span data-ttu-id="1bb0d-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1bb0d-128">PARAMETERS</span></span>

### <span data-ttu-id="1bb0d-129">-Conteúdo</span><span class="sxs-lookup"><span data-stu-id="1bb0d-129">-Content</span></span>

<span data-ttu-id="1bb0d-130">Especifica uma cadeia de caracteres criptografada ou uma variável que contém uma cadeia de caracteres criptografada.</span><span class="sxs-lookup"><span data-stu-id="1bb0d-130">Specifies an encrypted string, or a variable containing an encrypted string.</span></span>

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

### <span data-ttu-id="1bb0d-131">-EventLogRecord</span><span class="sxs-lookup"><span data-stu-id="1bb0d-131">-EventLogRecord</span></span>

<span data-ttu-id="1bb0d-132">Especifica uma ID de registro de log de eventos que representa uma operação de criptografia de CMS.</span><span class="sxs-lookup"><span data-stu-id="1bb0d-132">Specifies an event log record ID that represents a CMS encryption operation.</span></span>

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

### <span data-ttu-id="1bb0d-133">-IncludeContext</span><span class="sxs-lookup"><span data-stu-id="1bb0d-133">-IncludeContext</span></span>

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

### <span data-ttu-id="1bb0d-134">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="1bb0d-134">-LiteralPath</span></span>

<span data-ttu-id="1bb0d-135">Especifica o caminho para o conteúdo criptografado que você deseja descriptografar.</span><span class="sxs-lookup"><span data-stu-id="1bb0d-135">Specifies the path to encrypted content that you want to decrypt.</span></span> <span data-ttu-id="1bb0d-136">Ao contrário de **Path** , o valor de **LiteralPath** é usado exatamente como digitado.</span><span class="sxs-lookup"><span data-stu-id="1bb0d-136">Unlike **Path** , the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="1bb0d-137">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="1bb0d-137">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="1bb0d-138">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="1bb0d-138">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="1bb0d-139">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="1bb0d-139">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="1bb0d-140">-Path</span><span class="sxs-lookup"><span data-stu-id="1bb0d-140">-Path</span></span>

<span data-ttu-id="1bb0d-141">Especifica o caminho para o conteúdo criptografado que você deseja descriptografar.</span><span class="sxs-lookup"><span data-stu-id="1bb0d-141">Specifies the path to encrypted content that you want to decrypt.</span></span>

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

### <span data-ttu-id="1bb0d-142">-Para</span><span class="sxs-lookup"><span data-stu-id="1bb0d-142">-To</span></span>

<span data-ttu-id="1bb0d-143">Especifica um ou mais destinatários de mensagens CMS, identificados em qualquer um dos seguintes formatos:</span><span class="sxs-lookup"><span data-stu-id="1bb0d-143">Specifies one or more CMS message recipients, identified in any of the following formats:</span></span>

- <span data-ttu-id="1bb0d-144">Um certificado real (como recuperado do provedor de certificado).</span><span class="sxs-lookup"><span data-stu-id="1bb0d-144">An actual certificate (as retrieved from the certificate provider).</span></span>
- <span data-ttu-id="1bb0d-145">Caminho para o arquivo que contém o certificado.</span><span class="sxs-lookup"><span data-stu-id="1bb0d-145">Path to the a file containing the certificate.</span></span>
- <span data-ttu-id="1bb0d-146">Caminho para um diretório que contém o certificado.</span><span class="sxs-lookup"><span data-stu-id="1bb0d-146">Path to a directory containing the certificate.</span></span>
- <span data-ttu-id="1bb0d-147">Impressão digital do certificado (usada para examinar o repositório de certificados).</span><span class="sxs-lookup"><span data-stu-id="1bb0d-147">Thumbprint of the certificate (used to look in the certificate store).</span></span>
- <span data-ttu-id="1bb0d-148">Nome da entidade do certificado (usado para examinar o repositório de certificados).</span><span class="sxs-lookup"><span data-stu-id="1bb0d-148">Subject name of the certificate (used to look in the certificate store).</span></span>

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

### <span data-ttu-id="1bb0d-149">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1bb0d-149">CommonParameters</span></span>

<span data-ttu-id="1bb0d-150">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1bb0d-150">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1bb0d-151">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1bb0d-151">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1bb0d-152">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="1bb0d-152">INPUTS</span></span>

### <span data-ttu-id="1bb0d-153">System. Diagnostics. Eventing. Reader. EventLogRecord ou System. String</span><span class="sxs-lookup"><span data-stu-id="1bb0d-153">System.Diagnostics.Eventing.Reader.EventLogRecord or System.String</span></span>

<span data-ttu-id="1bb0d-154">É possível canalizar um objeto que contém conteúdo criptografado para o `Unprotect-CmsMessage` .</span><span class="sxs-lookup"><span data-stu-id="1bb0d-154">You can pipe an object containing encrypted content to `Unprotect-CmsMessage`.</span></span>

## <span data-ttu-id="1bb0d-155">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="1bb0d-155">OUTPUTS</span></span>

### <span data-ttu-id="1bb0d-156">System.String</span><span class="sxs-lookup"><span data-stu-id="1bb0d-156">System.String</span></span>

<span data-ttu-id="1bb0d-157">A mensagem não criptografada.</span><span class="sxs-lookup"><span data-stu-id="1bb0d-157">The unencrypted message.</span></span>

## <span data-ttu-id="1bb0d-158">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="1bb0d-158">NOTES</span></span>

<span data-ttu-id="1bb0d-159">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="1bb0d-159">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="1bb0d-160">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="1bb0d-160">RELATED LINKS</span></span>

[<span data-ttu-id="1bb0d-161">about_Providers</span><span class="sxs-lookup"><span data-stu-id="1bb0d-161">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="1bb0d-162">Get-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="1bb0d-162">Get-CmsMessage</span></span>](Get-CmsMessage.md)

[<span data-ttu-id="1bb0d-163">Protect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="1bb0d-163">Protect-CmsMessage</span></span>](Protect-CmsMessage.md)
