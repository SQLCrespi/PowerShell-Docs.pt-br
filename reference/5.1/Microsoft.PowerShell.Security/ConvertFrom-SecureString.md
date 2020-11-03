---
external help file: Microsoft.PowerShell.Security.dll-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 04/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/convertfrom-securestring?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-SecureString
ms.openlocfilehash: 4dae7806cbec85347a8dfa01348be72061214c6c
ms.sourcegitcommit: b0488ca6557501184f20c8343b0ed5147b09e3fe
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "93194831"
---
# <span data-ttu-id="079fc-103">ConvertFrom-SecureString</span><span class="sxs-lookup"><span data-stu-id="079fc-103">ConvertFrom-SecureString</span></span>

## <span data-ttu-id="079fc-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="079fc-104">SYNOPSIS</span></span>
<span data-ttu-id="079fc-105">Converte uma cadeia de caracteres segura em uma cadeia de caracteres padrão criptografada.</span><span class="sxs-lookup"><span data-stu-id="079fc-105">Converts a secure string to an encrypted standard string.</span></span>

## <span data-ttu-id="079fc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="079fc-106">SYNTAX</span></span>

### <span data-ttu-id="079fc-107">Seguro (padrão)</span><span class="sxs-lookup"><span data-stu-id="079fc-107">Secure (Default)</span></span>

```
ConvertFrom-SecureString [-SecureString] <SecureString> [[-SecureKey] <SecureString>] [<CommonParameters>]
```

### <span data-ttu-id="079fc-108">Aberto</span><span class="sxs-lookup"><span data-stu-id="079fc-108">Open</span></span>

```
ConvertFrom-SecureString [-SecureString] <SecureString> [-Key <Byte[]>] [<CommonParameters>]
```

## <span data-ttu-id="079fc-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="079fc-109">DESCRIPTION</span></span>

<span data-ttu-id="079fc-110">O cmdlet **ConvertFrom-SecureString** converte uma cadeia de caracteres segura ( **System. Security. SecureString** ) em uma cadeia de caracteres criptografada padrão ( **System. String** ).</span><span class="sxs-lookup"><span data-stu-id="079fc-110">The **ConvertFrom-SecureString** cmdlet converts a secure string ( **System.Security.SecureString** ) into an encrypted standard string ( **System.String** ).</span></span> <span data-ttu-id="079fc-111">Ao contrário de uma cadeia de caracteres segura, uma cadeia de caracteres criptografada padrão pode ser salva em um arquivo para uso posterior.</span><span class="sxs-lookup"><span data-stu-id="079fc-111">Unlike a secure string, an encrypted standard string can be saved in a file for later use.</span></span> <span data-ttu-id="079fc-112">A cadeia de caracteres criptografada padrão pode ser convertida de volta para o formato de cadeia de caracteres seguro usando o `ConvertTo-SecureString` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="079fc-112">The encrypted standard string can be converted back to its secure string format by using the `ConvertTo-SecureString` cmdlet.</span></span>

<span data-ttu-id="079fc-113">Se uma chave de criptografia for especificada usando os parâmetros **Key** ou **SecureKey** , o algoritmo de criptografia AES será usado.</span><span class="sxs-lookup"><span data-stu-id="079fc-113">If an encryption key is specified by using the **Key** or **SecureKey** parameters, the Advanced Encryption Standard (AES) encryption algorithm is used.</span></span> <span data-ttu-id="079fc-114">A chave especificada deve ter um comprimento de 128, 192 ou 256 bits, pois esses são os comprimentos de chave suportados pelo algoritmo de criptografia AES.</span><span class="sxs-lookup"><span data-stu-id="079fc-114">The specified key must have a length of 128, 192, or 256 bits because those are the key lengths supported by the AES encryption algorithm.</span></span> <span data-ttu-id="079fc-115">Se nenhuma chave for especificada, a API de Proteção aos Dados do Windows (DPAPI) é usada para criptografar a representação de cadeia de caracteres padrão.</span><span class="sxs-lookup"><span data-stu-id="079fc-115">If no key is specified, the Windows Data Protection API (DPAPI) is used to encrypt the standard string representation.</span></span>

## <span data-ttu-id="079fc-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="079fc-116">EXAMPLES</span></span>

### <span data-ttu-id="079fc-117">Exemplo 1: criar uma cadeia de caracteres segura</span><span class="sxs-lookup"><span data-stu-id="079fc-117">Example 1: Create a secure string</span></span>

```powershell
$SecureString = Read-Host -AsSecureString
```

<span data-ttu-id="079fc-118">Este comando cria uma cadeia de caracteres segura de caracteres digitados no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="079fc-118">This command creates a secure string from characters that you type at the command prompt.</span></span> <span data-ttu-id="079fc-119">Depois de inserir o comando, digite a cadeia de caracteres que você deseja armazenar como uma cadeia de caracteres segura.</span><span class="sxs-lookup"><span data-stu-id="079fc-119">After entering the command, type the string you want to store as a secure string.</span></span> <span data-ttu-id="079fc-120">Um asterisco ( `*` ) é exibido para representar cada caractere que você digitar.</span><span class="sxs-lookup"><span data-stu-id="079fc-120">An asterisk (`*`) is displayed to represent each character that you type.</span></span>

### <span data-ttu-id="079fc-121">Exemplo 2: converter uma cadeia de caracteres segura em uma cadeia de caracteres criptografada padrão</span><span class="sxs-lookup"><span data-stu-id="079fc-121">Example 2: Convert a secure string to an encrypted standard string</span></span>

```powershell
$StandardString = ConvertFrom-SecureString $SecureString
```

<span data-ttu-id="079fc-122">Esse comando converte a cadeia de caracteres segura na `$SecureString` variável em uma cadeia de caracteres padrão criptografada.</span><span class="sxs-lookup"><span data-stu-id="079fc-122">This command converts the secure string in the `$SecureString` variable to an encrypted standard string.</span></span> <span data-ttu-id="079fc-123">A cadeia de caracteres padrão criptografada resultante é armazenada na `$StandardString` variável.</span><span class="sxs-lookup"><span data-stu-id="079fc-123">The resulting encrypted standard string is stored in the `$StandardString` variable.</span></span>

### <span data-ttu-id="079fc-124">Exemplo 3: converter uma cadeia de caracteres segura em uma cadeia de caracteres criptografada padrão com uma chave de 192 bits</span><span class="sxs-lookup"><span data-stu-id="079fc-124">Example 3: Convert a secure string to an encrypted standard string with a 192-bit key</span></span>

```powershell
$Key = (3,4,2,3,56,34,254,222,1,1,2,23,42,54,33,233,1,34,2,7,6,5,35,43)
$StandardString = ConvertFrom-SecureString $SecureString -Key $Key
```

<span data-ttu-id="079fc-125">Esses comandos usam o algoritmo criptografia AES (AES) para converter a cadeia de caracteres segura armazenada na `$SecureString` variável em uma cadeia de caracteres criptografada padrão com uma chave de 192 bits.</span><span class="sxs-lookup"><span data-stu-id="079fc-125">These commands use the Advanced Encryption Standard (AES) algorithm to convert the secure string stored in the `$SecureString` variable to an encrypted standard string with a 192-bit key.</span></span> <span data-ttu-id="079fc-126">A cadeia de caracteres padrão criptografada resultante é armazenada na `$StandardString` variável.</span><span class="sxs-lookup"><span data-stu-id="079fc-126">The resulting encrypted standard string is stored in the `$StandardString` variable.</span></span>

<span data-ttu-id="079fc-127">O primeiro comando armazena uma chave na `$Key` variável.</span><span class="sxs-lookup"><span data-stu-id="079fc-127">The first command stores a key in the `$Key` variable.</span></span> <span data-ttu-id="079fc-128">A chave é uma matriz de 24 numerais decimais, e cada uma deve ser menor que 256 para caber em um único byte não assinado.</span><span class="sxs-lookup"><span data-stu-id="079fc-128">The key is an array of 24 decimal numerals, each of which must be less than 256 to fit within a single unsigned byte.</span></span>

<span data-ttu-id="079fc-129">Como cada numeral decimal representa um único byte (8 bits), a chave tem 24 dígitos para um total de 192 bits (8 x 24).</span><span class="sxs-lookup"><span data-stu-id="079fc-129">Because each decimal numeral represents a single byte (8 bits), the key has 24 digits for a total of 192 bits (8 x 24).</span></span> <span data-ttu-id="079fc-130">Esse é um comprimento de chave válido para o algoritmo AES.</span><span class="sxs-lookup"><span data-stu-id="079fc-130">This is a valid key length for the AES algorithm.</span></span>

<span data-ttu-id="079fc-131">O segundo comando usa a chave na `$Key` variável para converter a cadeia de caracteres segura em uma cadeia de caracteres padrão criptografada.</span><span class="sxs-lookup"><span data-stu-id="079fc-131">The second command uses the key in the `$Key` variable to convert the secure string to an encrypted standard string.</span></span>

## <span data-ttu-id="079fc-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="079fc-132">PARAMETERS</span></span>

### <span data-ttu-id="079fc-133">-Chave</span><span class="sxs-lookup"><span data-stu-id="079fc-133">-Key</span></span>

<span data-ttu-id="079fc-134">Especifica a chave de criptografia como uma matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="079fc-134">Specifies the encryption key as a byte array.</span></span>

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

### <span data-ttu-id="079fc-135">-SecureKey</span><span class="sxs-lookup"><span data-stu-id="079fc-135">-SecureKey</span></span>

<span data-ttu-id="079fc-136">Especifica a chave de criptografia como uma cadeia de caracteres segura.</span><span class="sxs-lookup"><span data-stu-id="079fc-136">Specifies the encryption key as a secure string.</span></span> <span data-ttu-id="079fc-137">O valor da cadeia de caracteres segura é convertido em uma matriz de bytes antes de ser usado como chave.</span><span class="sxs-lookup"><span data-stu-id="079fc-137">The secure string value is converted to a byte array before being used as the key.</span></span>

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

### <span data-ttu-id="079fc-138">-SecureString</span><span class="sxs-lookup"><span data-stu-id="079fc-138">-SecureString</span></span>

<span data-ttu-id="079fc-139">Especifica a cadeia de caracteres segura para converter uma cadeia de caracteres criptografada padrão.</span><span class="sxs-lookup"><span data-stu-id="079fc-139">Specifies the secure string to convert to an encrypted standard string.</span></span>

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

### <span data-ttu-id="079fc-140">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="079fc-140">CommonParameters</span></span>

<span data-ttu-id="079fc-141">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="079fc-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="079fc-142">Para obter mais informações, confira about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="079fc-142">For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="079fc-143">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="079fc-143">INPUTS</span></span>

### <span data-ttu-id="079fc-144">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="079fc-144">System.Security.SecureString</span></span>

<span data-ttu-id="079fc-145">É possível canalizar um objeto **SecureString** para ConvertFrom-SecureString.</span><span class="sxs-lookup"><span data-stu-id="079fc-145">You can pipe a **SecureString** object to ConvertFrom-SecureString.</span></span>

## <span data-ttu-id="079fc-146">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="079fc-146">OUTPUTS</span></span>

### <span data-ttu-id="079fc-147">System.String</span><span class="sxs-lookup"><span data-stu-id="079fc-147">System.String</span></span>

<span data-ttu-id="079fc-148">ConvertFrom-SecureString retorna um objeto de cadeia de caracteres padrão.</span><span class="sxs-lookup"><span data-stu-id="079fc-148">ConvertFrom-SecureString returns a standard string object.</span></span>

## <span data-ttu-id="079fc-149">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="079fc-149">NOTES</span></span>

- <span data-ttu-id="079fc-150">Para criar uma cadeia de caracteres segura a partir de personagens que são digitados no prompt de comando, use o parâmetro **AsSecureString** do `Read-Host` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="079fc-150">To create a secure string from characters that are typed at the command prompt, use the **AsSecureString** parameter of the `Read-Host` cmdlet.</span></span>
- <span data-ttu-id="079fc-151">Quando você usa os parâmetros **Key** ou **SecureKey** para especificar uma chave, o comprimento da chave deve estar correto.</span><span class="sxs-lookup"><span data-stu-id="079fc-151">When you use the **Key** or **SecureKey** parameters to specify a key, the key length must be correct.</span></span> <span data-ttu-id="079fc-152">Por exemplo, uma chave de 128 bits pode ser especificada como uma matriz de bytes de 16 numerais decimais.</span><span class="sxs-lookup"><span data-stu-id="079fc-152">For example, a key of 128 bits can be specified as a byte array of 16 decimal numerals.</span></span>
  <span data-ttu-id="079fc-153">Da mesma forma, chaves de 192 bits e 256 bits correspondem a matrizes de bytes de algarismos decimais 24 e 32, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="079fc-153">Similarly, 192-bit and 256-bit keys correspond to byte arrays of 24 and 32 decimal numerals, respectively.</span></span>
- <span data-ttu-id="079fc-154">Alguns caracteres, como emoticons, correspondem a vários pontos de código na cadeia de caracteres que os contém.</span><span class="sxs-lookup"><span data-stu-id="079fc-154">Some characters, such as emoticons, correspond to several code points in the string that contains them.</span></span> <span data-ttu-id="079fc-155">Evite usar esses caracteres, pois eles podem causar problemas e mal-entendidos incompreendidos quando usados em uma senha.</span><span class="sxs-lookup"><span data-stu-id="079fc-155">Avoid using these characters because they may cause problems and misunderstandings when used in a password.</span></span>

## <span data-ttu-id="079fc-156">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="079fc-156">RELATED LINKS</span></span>

[<span data-ttu-id="079fc-157">ConvertTo-SecureString</span><span class="sxs-lookup"><span data-stu-id="079fc-157">ConvertTo-SecureString</span></span>](ConvertTo-SecureString.md)

[<span data-ttu-id="079fc-158">Read-Host</span><span class="sxs-lookup"><span data-stu-id="079fc-158">Read-Host</span></span>](../Microsoft.PowerShell.Utility/Read-Host.md)
