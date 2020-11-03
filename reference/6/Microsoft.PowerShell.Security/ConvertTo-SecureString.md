---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 10/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-SecureString
ms.openlocfilehash: 71b2a36601281d148bed6742ce3f3cb78e11acf4
ms.sourcegitcommit: df80c558e9a4b89c9798f084bd04012ece15155c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2020
ms.locfileid: "93196624"
---
# <span data-ttu-id="125d3-103">ConvertTo-SecureString</span><span class="sxs-lookup"><span data-stu-id="125d3-103">ConvertTo-SecureString</span></span>

## <span data-ttu-id="125d3-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="125d3-104">SYNOPSIS</span></span>
<span data-ttu-id="125d3-105">Converte texto sem formatação ou cadeias de caracteres criptografadas para proteger cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="125d3-105">Converts plain text or encrypted strings to secure strings.</span></span>

## <span data-ttu-id="125d3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="125d3-106">SYNTAX</span></span>

### <span data-ttu-id="125d3-107">Seguro (padrão)</span><span class="sxs-lookup"><span data-stu-id="125d3-107">Secure (Default)</span></span>

```
ConvertTo-SecureString [-String] <String> [[-SecureKey] <SecureString>] [<CommonParameters>]
```

### <span data-ttu-id="125d3-108">Texto sem formatação</span><span class="sxs-lookup"><span data-stu-id="125d3-108">PlainText</span></span>

```
ConvertTo-SecureString [-String] <String> [-AsPlainText] [-Force] [<CommonParameters>]
```

### <span data-ttu-id="125d3-109">Aberto</span><span class="sxs-lookup"><span data-stu-id="125d3-109">Open</span></span>

```
ConvertTo-SecureString [-String] <String> [-Key <Byte[]>] [<CommonParameters>]
```

## <span data-ttu-id="125d3-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="125d3-110">DESCRIPTION</span></span>

<span data-ttu-id="125d3-111">O `ConvertTo-SecureString` cmdlet converte cadeias de caracteres padrão criptografadas em cadeias de caracteres seguras.</span><span class="sxs-lookup"><span data-stu-id="125d3-111">The `ConvertTo-SecureString` cmdlet converts encrypted standard strings into secure strings.</span></span> <span data-ttu-id="125d3-112">Também pode converter o texto sem formatação em cadeias de caracteres seguras.</span><span class="sxs-lookup"><span data-stu-id="125d3-112">It can also convert plain text to secure strings.</span></span> <span data-ttu-id="125d3-113">Ele é usado com `ConvertFrom-SecureString` e `Read-Host` .</span><span class="sxs-lookup"><span data-stu-id="125d3-113">It is used with `ConvertFrom-SecureString` and `Read-Host`.</span></span> <span data-ttu-id="125d3-114">A cadeia de caracteres segura criada pelo cmdlet pode ser usada com cmdlets ou funções que exigem um parâmetro do tipo **SecureString** .</span><span class="sxs-lookup"><span data-stu-id="125d3-114">The secure string created by the cmdlet can be used with cmdlets or functions that require a parameter of type **SecureString** .</span></span> <span data-ttu-id="125d3-115">A cadeia de caracteres segura pode ser convertida novamente em uma cadeia de caracteres criptografada padrão usando o `ConvertFrom-SecureString` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="125d3-115">The secure string can be converted back to an encrypted, standard string using the `ConvertFrom-SecureString` cmdlet.</span></span> <span data-ttu-id="125d3-116">Isso permite que ele seja armazenada em um arquivo para uso posterior.</span><span class="sxs-lookup"><span data-stu-id="125d3-116">This enables it to be stored in a file for later use.</span></span>

<span data-ttu-id="125d3-117">Se a cadeia de caracteres padrão que está sendo convertida tiver sido criptografada com o `ConvertFrom-SecureString` usando uma chave especificada, essa mesma chave deverá ser fornecida como o valor do parâmetro **Key** ou **SecureKey** do `ConvertTo-SecureString` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="125d3-117">If the standard string being converted was encrypted with `ConvertFrom-SecureString` using a specified key, that same key must be provided as the value of the **Key** or **SecureKey** parameter of the `ConvertTo-SecureString` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="125d3-118">Observe que, por [dotnet](/dotnet/api/system.security.securestring#remarks), o conteúdo de uma SecureString não é criptografado em sistemas que não são do Windows.</span><span class="sxs-lookup"><span data-stu-id="125d3-118">Note that per [DotNet](/dotnet/api/system.security.securestring#remarks), the contents of a SecureString are not encrypted on non-Windows systems.</span></span>

## <span data-ttu-id="125d3-119">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="125d3-119">EXAMPLES</span></span>

### <span data-ttu-id="125d3-120">Exemplo 1: converter uma cadeia de caracteres segura em uma cadeia de caracteres criptografada</span><span class="sxs-lookup"><span data-stu-id="125d3-120">Example 1: Convert a secure string to an encrypted string</span></span>

<span data-ttu-id="125d3-121">Este exemplo mostra como criar uma cadeia de caracteres segura da entrada do usuário, converter a cadeia de caracteres segura em uma cadeia de caracteres criptografada padrão e converter a cadeia de caracteres criptografada padrão novamente em uma cadeia de caracteres segura.</span><span class="sxs-lookup"><span data-stu-id="125d3-121">This example shows how to create a secure string from user input, convert the secure string to an encrypted standard string, and then convert the encrypted standard string back to a secure string.</span></span>

```powershell
PS C:\> $Secure = Read-Host -AsSecureString
PS C:\> $Secure
System.Security.SecureString
PS C:\> $Encrypted = ConvertFrom-SecureString -SecureString $Secure
PS C:\> $Encrypted
01000000d08c9ddf0115d1118c7a00c04fc297eb010000001a114d45b8dd3f4aa11ad7c0abdae98000000000
02000000000003660000a8000000100000005df63cea84bfb7d70bd6842e7efa79820000000004800000a000
000010000000f10cd0f4a99a8d5814d94e0687d7430b100000008bf11f1960158405b2779613e9352c6d1400
0000e6b7bf46a9d485ff211b9b2a2df3bd6eb67aae41
PS C:\> $Secure2 = ConvertTo-SecureString -String $Encrypted
PS C:\> $Secure2
System.Security.SecureString
```

<span data-ttu-id="125d3-122">O primeiro comando usa o parâmetro **AsSecureString** do `Read-Host` cmdlet para criar uma cadeia de caracteres segura.</span><span class="sxs-lookup"><span data-stu-id="125d3-122">The first command uses the **AsSecureString** parameter of the `Read-Host` cmdlet to create a secure string.</span></span> <span data-ttu-id="125d3-123">Depois de inserir o comando, todos os caracteres que você digitar serão convertidos em uma cadeia de caracteres segura e, em seguida, salvos na `$Secure` variável.</span><span class="sxs-lookup"><span data-stu-id="125d3-123">After you enter the command, any characters that you type are converted into a secure string and then saved in the `$Secure` variable.</span></span>

<span data-ttu-id="125d3-124">O segundo comando exibe o conteúdo da `$Secure` variável.</span><span class="sxs-lookup"><span data-stu-id="125d3-124">The second command displays the contents of the `$Secure` variable.</span></span> <span data-ttu-id="125d3-125">Como a `$Secure` variável contém uma cadeia de caracteres segura, o PowerShell exibe somente o tipo **System. Security. SecureString** .</span><span class="sxs-lookup"><span data-stu-id="125d3-125">Because the `$Secure` variable contains a secure string, PowerShell displays only the **System.Security.SecureString** type.</span></span>

<span data-ttu-id="125d3-126">O terceiro comando usa o `ConvertFrom-SecureString` cmdlet para converter a cadeia de caracteres segura na `$Secure` variável em uma cadeia de caracteres criptografada padrão.</span><span class="sxs-lookup"><span data-stu-id="125d3-126">The third command uses the `ConvertFrom-SecureString` cmdlet to convert the secure string in the `$Secure` variable into an encrypted standard string.</span></span> <span data-ttu-id="125d3-127">Ele salva o resultado na `$Encrypted` variável.</span><span class="sxs-lookup"><span data-stu-id="125d3-127">It saves the result in the `$Encrypted` variable.</span></span>

<span data-ttu-id="125d3-128">O quarto comando exibe a cadeia de caracteres criptografada no valor da `$Encrypted` variável.</span><span class="sxs-lookup"><span data-stu-id="125d3-128">The fourth command displays the encrypted string in the value of the `$Encrypted` variable.</span></span>

<span data-ttu-id="125d3-129">O quinto comando usa o `ConvertTo-SecureString` cmdlet para converter a cadeia de caracteres criptografada padrão na `$Encrypted` variável de volta em uma cadeia de caracteres segura.</span><span class="sxs-lookup"><span data-stu-id="125d3-129">The fifth command uses the `ConvertTo-SecureString` cmdlet to convert the encrypted standard string in the `$Encrypted` variable back into a secure string.</span></span> <span data-ttu-id="125d3-130">Ele salva o resultado na `$Secure2` variável.</span><span class="sxs-lookup"><span data-stu-id="125d3-130">It saves the result in the `$Secure2` variable.</span></span>
<span data-ttu-id="125d3-131">O sexto comando exibe o valor da `$Secure2` variável.</span><span class="sxs-lookup"><span data-stu-id="125d3-131">The sixth command displays the value of the `$Secure2` variable.</span></span> <span data-ttu-id="125d3-132">O tipo SecureString indica que o comando foi bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="125d3-132">The SecureString type indicates that the command was successful.</span></span>

### <span data-ttu-id="125d3-133">Exemplo 2: criar uma cadeia de caracteres segura de uma cadeia de caracteres criptografada em um arquivo</span><span class="sxs-lookup"><span data-stu-id="125d3-133">Example 2: Create a secure string from an encrypted string in a file</span></span>

<span data-ttu-id="125d3-134">Este exemplo mostra como criar uma cadeia de caracteres segura de uma cadeia de caracteres criptografada padrão que é salva em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="125d3-134">This example shows how to create a secure string from an encrypted standard string that is saved in a file.</span></span>

```powershell
$Secure = Read-Host -AsSecureString
$Encrypted = ConvertFrom-SecureString -SecureString $Secure -Key (1..16)
$Encrypted | Set-Content Encrypted.txt
$Secure2 = Get-Content Encrypted.txt | ConvertTo-SecureString -Key (1..16)
```

<span data-ttu-id="125d3-135">O primeiro comando usa o parâmetro **AsSecureString** do `Read-Host` cmdlet para criar uma cadeia de caracteres segura.</span><span class="sxs-lookup"><span data-stu-id="125d3-135">The first command uses the **AsSecureString** parameter of the `Read-Host` cmdlet to create a secure string.</span></span> <span data-ttu-id="125d3-136">Depois de inserir o comando, todos os caracteres que você digitar serão convertidos em uma cadeia de caracteres segura e, em seguida, salvos na `$Secure` variável.</span><span class="sxs-lookup"><span data-stu-id="125d3-136">After you enter the command, any characters that you type are converted into a secure string and then saved in the `$Secure` variable.</span></span>

<span data-ttu-id="125d3-137">O segundo comando usa o `ConvertFrom-SecureString` cmdlet para converter a cadeia de caracteres segura na `$Secure` variável em uma cadeia de caracteres padrão criptografada usando a chave especificada.</span><span class="sxs-lookup"><span data-stu-id="125d3-137">The second command uses the `ConvertFrom-SecureString` cmdlet to convert the secure string in the `$Secure` variable into an encrypted standard string by using the specified key.</span></span> <span data-ttu-id="125d3-138">O conteúdo é salvo na `$Encrypted` variável.</span><span class="sxs-lookup"><span data-stu-id="125d3-138">The contents are saved in the `$Encrypted` variable.</span></span>

<span data-ttu-id="125d3-139">O terceiro comando usa um operador de pipeline ( `|` ) para enviar o valor da `$Encrypted` variável para o `Set-Content` cmdlet, que salva o valor no arquivo de Encrypted.txt.</span><span class="sxs-lookup"><span data-stu-id="125d3-139">The third command uses a pipeline operator (`|`) to send the value of the `$Encrypted` variable to the `Set-Content` cmdlet, which saves the value in the Encrypted.txt file.</span></span>

<span data-ttu-id="125d3-140">O quarto comando usa o `Get-Content` cmdlet para obter a cadeia de caracteres criptografada padrão no arquivo de Encrypted.txt.</span><span class="sxs-lookup"><span data-stu-id="125d3-140">The fourth command uses the `Get-Content` cmdlet to get the encrypted standard string in the Encrypted.txt file.</span></span> <span data-ttu-id="125d3-141">O comando usa um operador de pipeline para enviar a cadeia de caracteres criptografada para o `ConvertTo-SecureString` cmdlet, que converte-o em uma cadeia de caracteres segura usando a chave especificada.</span><span class="sxs-lookup"><span data-stu-id="125d3-141">The command uses a pipeline operator to send the encrypted string to the `ConvertTo-SecureString` cmdlet, which converts it to a secure string by using the specified key.</span></span>
<span data-ttu-id="125d3-142">Os resultados são salvos na `$Secure2` variável.</span><span class="sxs-lookup"><span data-stu-id="125d3-142">The results are saved in the `$Secure2` variable.</span></span>

### <span data-ttu-id="125d3-143">Exemplo 3: converter uma cadeia de caracteres de texto sem formatação em uma cadeia de caracteres segura</span><span class="sxs-lookup"><span data-stu-id="125d3-143">Example 3: Convert a plain text string to a secure string</span></span>

<span data-ttu-id="125d3-144">Esse comando converte a cadeia de texto sem formatação `P@ssW0rD!` em uma cadeia de caracteres segura e armazena o resultado na `$Secure_String_Pwd` variável.</span><span class="sxs-lookup"><span data-stu-id="125d3-144">This command converts the plain text string `P@ssW0rD!` into a secure string and stores the result in the `$Secure_String_Pwd` variable.</span></span> <span data-ttu-id="125d3-145">Para usar o parâmetro **Astexto não criptografado** , o parâmetro **Force** também deve ser incluído no comando.</span><span class="sxs-lookup"><span data-stu-id="125d3-145">To use the **AsPlainText** parameter, the **Force** parameter must also be included in the command.</span></span>

```powershell
$Secure_String_Pwd = ConvertTo-SecureString "P@ssW0rD!" -AsPlainText -Force
```

> [!CAUTION]
> <span data-ttu-id="125d3-146">Evite usar cadeias de caracteres de texto sem formatação no script ou na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="125d3-146">You should avoid using plain text strings in script or from the command line.</span></span> <span data-ttu-id="125d3-147">O texto sem formatação pode aparecer nos logs de eventos e nos logs de histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="125d3-147">The plain text can show up in event logs and command history logs.</span></span>

## <span data-ttu-id="125d3-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="125d3-148">PARAMETERS</span></span>

### <span data-ttu-id="125d3-149">-Astexto não criptografado</span><span class="sxs-lookup"><span data-stu-id="125d3-149">-AsPlainText</span></span>

<span data-ttu-id="125d3-150">Especifica uma cadeia de caracteres de texto sem formatação para converter em uma cadeia de caracteres segura.</span><span class="sxs-lookup"><span data-stu-id="125d3-150">Specifies a plain text string to convert to a secure string.</span></span> <span data-ttu-id="125d3-151">Os cmdlets de cadeia de caracteres segura protegem texto confidencial.</span><span class="sxs-lookup"><span data-stu-id="125d3-151">The secure string cmdlets help protect confidential text.</span></span> <span data-ttu-id="125d3-152">O texto é criptografado para privacidade e é excluído da memória do computador depois que ele é usado.</span><span class="sxs-lookup"><span data-stu-id="125d3-152">The text is encrypted for privacy and is deleted from computer memory after it is used.</span></span> <span data-ttu-id="125d3-153">Se você usar esse parâmetro para fornecer texto sem formatação como entrada, o sistema não poderá proteger essa entrada dessa maneira.</span><span class="sxs-lookup"><span data-stu-id="125d3-153">If you use this parameter to provide plain text as input, the system cannot protect that input in this manner.</span></span> <span data-ttu-id="125d3-154">Para usar esse parâmetro, você também deve especificar o parâmetro **Force** .</span><span class="sxs-lookup"><span data-stu-id="125d3-154">To use this parameter, you must also specify the **Force** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PlainText
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="125d3-155">-Force</span><span class="sxs-lookup"><span data-stu-id="125d3-155">-Force</span></span>

<span data-ttu-id="125d3-156">Confirma que você entende as implicações de usar o parâmetro **Astexto não criptografado** e ainda deseja usá-lo.</span><span class="sxs-lookup"><span data-stu-id="125d3-156">Confirms that you understand the implications of using the **AsPlainText** parameter and still want to use it.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PlainText
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="125d3-157">-Chave</span><span class="sxs-lookup"><span data-stu-id="125d3-157">-Key</span></span>

<span data-ttu-id="125d3-158">Especifica a chave de criptografia usada para converter a cadeia de caracteres segura original na cadeia de caracteres padrão criptografada.</span><span class="sxs-lookup"><span data-stu-id="125d3-158">Specifies the encryption key used to convert the original secure string into the encrypted standard string.</span></span> <span data-ttu-id="125d3-159">Os comprimentos de chave válidos são 16, 24 e 32 bytes.</span><span class="sxs-lookup"><span data-stu-id="125d3-159">Valid key lengths are 16, 24 and 32 bytes.</span></span>

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

### <span data-ttu-id="125d3-160">-SecureKey</span><span class="sxs-lookup"><span data-stu-id="125d3-160">-SecureKey</span></span>

<span data-ttu-id="125d3-161">Especifica a chave de criptografia usada para converter a cadeia de caracteres segura original na cadeia de caracteres padrão criptografada.</span><span class="sxs-lookup"><span data-stu-id="125d3-161">Specifies the encryption key used to convert the original secure string into the encrypted standard string.</span></span> <span data-ttu-id="125d3-162">A chave deve ser fornecida no formato de uma cadeia de caracteres segura.</span><span class="sxs-lookup"><span data-stu-id="125d3-162">The key must be provided in the format of a secure string.</span></span> <span data-ttu-id="125d3-163">A cadeia de caracteres segura será convertida em uma matriz de bytes a ser usada como chave.</span><span class="sxs-lookup"><span data-stu-id="125d3-163">The secure string will be converted to a byte array to be used as the key.</span></span> <span data-ttu-id="125d3-164">Os comprimentos de chave segura válidos são 8, 12 e 16 pontos de código.</span><span class="sxs-lookup"><span data-stu-id="125d3-164">Valid secure key lengths are 8, 12 and 16 code points.</span></span>

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

### <span data-ttu-id="125d3-165">-Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="125d3-165">-String</span></span>

<span data-ttu-id="125d3-166">Especifica a cadeia de caracteres a ser convertida em uma cadeia de caracteres segura.</span><span class="sxs-lookup"><span data-stu-id="125d3-166">Specifies the string to convert to a secure string.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="125d3-167">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="125d3-167">CommonParameters</span></span>

<span data-ttu-id="125d3-168">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="125d3-168">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="125d3-169">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="125d3-169">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="125d3-170">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="125d3-170">INPUTS</span></span>

### <span data-ttu-id="125d3-171">System.String</span><span class="sxs-lookup"><span data-stu-id="125d3-171">System.String</span></span>

<span data-ttu-id="125d3-172">É possível canalizar uma cadeia de caracteres criptografada padrão para `ConvertTo-SecureString` .</span><span class="sxs-lookup"><span data-stu-id="125d3-172">You can pipe a standard encrypted string to `ConvertTo-SecureString`.</span></span>

## <span data-ttu-id="125d3-173">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="125d3-173">OUTPUTS</span></span>

### <span data-ttu-id="125d3-174">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="125d3-174">System.Security.SecureString</span></span>

<span data-ttu-id="125d3-175">`ConvertTo-SecureString` Retorna um objeto **SecureString** .</span><span class="sxs-lookup"><span data-stu-id="125d3-175">`ConvertTo-SecureString` returns a **SecureString** object.</span></span>

## <span data-ttu-id="125d3-176">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="125d3-176">NOTES</span></span>

<span data-ttu-id="125d3-177">Alguns caracteres, como emoticons, correspondem a vários pontos de código na cadeia de caracteres que os contém.</span><span class="sxs-lookup"><span data-stu-id="125d3-177">Some characters, such as emoticons, correspond to several code points in the string that contains them.</span></span> <span data-ttu-id="125d3-178">Evite usar esses caracteres, pois eles podem causar problemas e mal-entendidos incompreendidos quando usados em uma senha.</span><span class="sxs-lookup"><span data-stu-id="125d3-178">Avoid using these characters because they may cause problems and misunderstandings when used in a password.</span></span>

## <span data-ttu-id="125d3-179">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="125d3-179">RELATED LINKS</span></span>

[<span data-ttu-id="125d3-180">ConvertFrom-SecureString</span><span class="sxs-lookup"><span data-stu-id="125d3-180">ConvertFrom-SecureString</span></span>](ConvertFrom-SecureString.md)

[<span data-ttu-id="125d3-181">Read-Host</span><span class="sxs-lookup"><span data-stu-id="125d3-181">Read-Host</span></span>](../Microsoft.PowerShell.Utility/Read-Host.md)
