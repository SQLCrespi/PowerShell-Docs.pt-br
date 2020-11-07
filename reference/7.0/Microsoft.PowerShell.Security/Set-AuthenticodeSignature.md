---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 04/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-authenticodesignature?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AuthenticodeSignature
ms.openlocfilehash: 66ecd756eccbe60003304419da64d65b6c55dd01
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347730"
---
# <span data-ttu-id="b1973-103">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="b1973-103">Set-AuthenticodeSignature</span></span>

## <span data-ttu-id="b1973-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b1973-104">SYNOPSIS</span></span>
<span data-ttu-id="b1973-105">Adiciona uma assinatura [Authenticode](/windows-hardware/drivers/install/authenticode) a um script do PowerShell ou a outro arquivo.</span><span class="sxs-lookup"><span data-stu-id="b1973-105">Adds an [Authenticode](/windows-hardware/drivers/install/authenticode) signature to a PowerShell script or other file.</span></span>

## <span data-ttu-id="b1973-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b1973-106">SYNTAX</span></span>

### <span data-ttu-id="b1973-107">ByPath (padrão)</span><span class="sxs-lookup"><span data-stu-id="b1973-107">ByPath (Default)</span></span>

```
Set-AuthenticodeSignature [-Certificate] <X509Certificate2> [-IncludeChain <String>]
 [-TimestampServer <String>] [-HashAlgorithm <String>] [-Force] [-FilePath] <String[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b1973-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="b1973-108">ByLiteralPath</span></span>

```
Set-AuthenticodeSignature [-Certificate] <X509Certificate2> [-IncludeChain <String>]
 [-TimestampServer <String>] [-HashAlgorithm <String>] [-Force] -LiteralPath <String[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b1973-109">ByContent</span><span class="sxs-lookup"><span data-stu-id="b1973-109">ByContent</span></span>

```
Set-AuthenticodeSignature [-Certificate] <X509Certificate2> [-IncludeChain <String>]
 [-TimestampServer <String>] [-HashAlgorithm <String>] [-Force] -SourcePathOrExtension <String[]>
 -Content <Byte[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b1973-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b1973-110">DESCRIPTION</span></span>

<span data-ttu-id="b1973-111">O `Set-AuthenticodeSignature` cmdlet adiciona uma assinatura Authenticode a qualquer arquivo que dê suporte ao SIP (pacote de interface de entidade).</span><span class="sxs-lookup"><span data-stu-id="b1973-111">The `Set-AuthenticodeSignature` cmdlet adds an Authenticode signature to any file that supports Subject Interface Package (SIP).</span></span>

<span data-ttu-id="b1973-112">Em um arquivo de script do PowerShell, a assinatura assume a forma de um bloco de texto que indica o fim das instruções que são executadas no script.</span><span class="sxs-lookup"><span data-stu-id="b1973-112">In a PowerShell script file, the signature takes the form of a block of text that indicates the end of the instructions that are executed in the script.</span></span> <span data-ttu-id="b1973-113">Se houver uma assinatura no arquivo quando esse cmdlet é executado, essa assinatura será removida.</span><span class="sxs-lookup"><span data-stu-id="b1973-113">If there is a signature in the file when this cmdlet runs, that signature is removed.</span></span>

## <span data-ttu-id="b1973-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b1973-114">EXAMPLES</span></span>

### <span data-ttu-id="b1973-115">Exemplo 1-assinar um script usando um certificado do repositório de certificados local</span><span class="sxs-lookup"><span data-stu-id="b1973-115">Example 1 - Sign a script using a certificate from the local certificate store</span></span>

<span data-ttu-id="b1973-116">Esses comandos recuperam um certificado de assinatura de código do provedor de certificados do PowerShell e o usam para assinar um script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1973-116">These commands retrieve a code-signing certificate from the PowerShell certificate provider and use it to sign a PowerShell script.</span></span>

```powershell
$cert=Get-ChildItem -Path Cert:\CurrentUser\My -CodeSigningCert
Set-AuthenticodeSignature -FilePath PsTestInternet2.ps1 -Certificate $cert
```

<span data-ttu-id="b1973-117">O primeiro comando usa o `Get-ChildItem` cmdlet e o provedor de certificados do PowerShell para obter os certificados no `Cert:\CurrentUser\My` subdiretório do repositório de certificados.</span><span class="sxs-lookup"><span data-stu-id="b1973-117">The first command uses the `Get-ChildItem` cmdlet and the PowerShell certificate provider to get the certificates in the `Cert:\CurrentUser\My` subdirectory of the certificate store.</span></span> <span data-ttu-id="b1973-118">A `Cert:` unidade é a unidade exposta pelo provedor de certificado.</span><span class="sxs-lookup"><span data-stu-id="b1973-118">The `Cert:` drive is the drive exposed by the certificate provider.</span></span> <span data-ttu-id="b1973-119">O parâmetro **CodeSigningCert** , que é suportado apenas pelo provedor de certificado, limita os certificados recuperados para aqueles com autoridade de assinatura de código.</span><span class="sxs-lookup"><span data-stu-id="b1973-119">The **CodeSigningCert** parameter, which is supported only by the certificate provider, limits the certificates retrieved to those with code-signing authority.</span></span> <span data-ttu-id="b1973-120">O comando armazena o resultado na `$cert` variável.</span><span class="sxs-lookup"><span data-stu-id="b1973-120">The command stores the result in the `$cert` variable.</span></span>

<span data-ttu-id="b1973-121">O segundo comando usa o `Set-AuthenticodeSignature` cmdlet para assinar o `PSTestInternet2.ps1` script.</span><span class="sxs-lookup"><span data-stu-id="b1973-121">The second command uses the `Set-AuthenticodeSignature` cmdlet to sign the `PSTestInternet2.ps1` script.</span></span> <span data-ttu-id="b1973-122">Ele usa o parâmetro **FilePath** para especificar o nome do script e o parâmetro de **certificado** para especificar que o certificado seja armazenado na `$cert` variável.</span><span class="sxs-lookup"><span data-stu-id="b1973-122">It uses the **FilePath** parameter to specify the name of the script and the **Certificate** parameter to specify that the certificate is stored in the `$cert` variable.</span></span>

> [!NOTE]
> <span data-ttu-id="b1973-123">O uso do parâmetro **CodeSigningCert** com `Get-ChildItem` apenas retorna certificados que têm autoridade de assinatura de código e contêm uma chave privada.</span><span class="sxs-lookup"><span data-stu-id="b1973-123">Using the **CodeSigningCert** parameter with `Get-ChildItem` only returns certificates that have code-signing authority and contain a private key.</span></span> <span data-ttu-id="b1973-124">Se não houver nenhuma chave privada, os certificados não poderão ser usados para assinatura.</span><span class="sxs-lookup"><span data-stu-id="b1973-124">If there is no private key, the certificates cannot be used for signing.</span></span>

### <span data-ttu-id="b1973-125">Exemplo 2-assinar um script usando um certificado de um arquivo PFX</span><span class="sxs-lookup"><span data-stu-id="b1973-125">Example 2 - Sign a script using a certificate from a PFX file</span></span>

<span data-ttu-id="b1973-126">Esses comandos usam o `Get-PfxCertificate` cmdlet para carregar um certificado de assinatura de código.</span><span class="sxs-lookup"><span data-stu-id="b1973-126">These commands use the `Get-PfxCertificate` cmdlet to load a code signing certificate.</span></span> <span data-ttu-id="b1973-127">Em seguida, use-o para assinar um script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1973-127">Then, use it to sign a PowerShell script.</span></span>

```powershell
$cert = Get-PfxCertificate -FilePath C:\Test\Mysign.pfx
Set-AuthenticodeSignature -FilePath ServerProps.ps1 -Certificate $cert
```

<span data-ttu-id="b1973-128">O primeiro comando usa o `Get-PfxCertificate` cmdlet para carregar o certificado C:\Test\MySign.pfx na `$cert` variável.</span><span class="sxs-lookup"><span data-stu-id="b1973-128">The first command uses the `Get-PfxCertificate` cmdlet to load the C:\Test\MySign.pfx certificate into the `$cert` variable.</span></span>

<span data-ttu-id="b1973-129">O segundo comando usa `Set-AuthenticodeSignature` para assinar o script.</span><span class="sxs-lookup"><span data-stu-id="b1973-129">The second command uses `Set-AuthenticodeSignature` to sign the script.</span></span> <span data-ttu-id="b1973-130">O parâmetro **FilePath** de `Set-AuthenticodeSignature` especifica o caminho para o arquivo de script que está sendo assinado e o parâmetro **CERT** passa a `$cert` variável que contém o certificado para `Set-AuthenticodeSignature` .</span><span class="sxs-lookup"><span data-stu-id="b1973-130">The **FilePath** parameter of `Set-AuthenticodeSignature` specifies the path to the script file being signed and the **Cert** parameter passes the `$cert` variable containing the certificate to `Set-AuthenticodeSignature`.</span></span>

<span data-ttu-id="b1973-131">Se o arquivo de certificado for protegido por senha, o PowerShell solicitará a senha.</span><span class="sxs-lookup"><span data-stu-id="b1973-131">If the certificate file is password protected, PowerShell prompts you for the password.</span></span>

### <span data-ttu-id="b1973-132">Exemplo 3-adicionar uma assinatura que inclui a autoridade raiz</span><span class="sxs-lookup"><span data-stu-id="b1973-132">Example 3 - Add a signature that includes the root authority</span></span>

<span data-ttu-id="b1973-133">Este comando adiciona uma assinatura digital que inclui a autoridade raiz da cadeia de confiança e é assinado por um servidor de carimbo de hora de terceiros.</span><span class="sxs-lookup"><span data-stu-id="b1973-133">This command adds a digital signature that includes the root authority in the trust chain, and it is signed by a third-party timestamp server.</span></span>

```powershell
Set-AuthenticodeSignature -FilePath c:\scripts\Remodel.ps1 -Certificate $cert -IncludeChain All -TimestampServer "http://timestamp.fabrikam.com/scripts/timstamper.dll"
```

<span data-ttu-id="b1973-134">O comando usa o parâmetro **FilePath** para especificar o script que está sendo assinado e o parâmetro de **certificado** para especificar o certificado que é salvo na `$cert` variável.</span><span class="sxs-lookup"><span data-stu-id="b1973-134">The command uses the **FilePath** parameter to specify the script being signed and the **Certificate** parameter to specify the certificate that is saved in the `$cert` variable.</span></span> <span data-ttu-id="b1973-135">Ele usa o parâmetro **IncludeChain** para incluir todas as assinaturas na cadeia de confiança, incluindo a autoridade raiz.</span><span class="sxs-lookup"><span data-stu-id="b1973-135">It uses the **IncludeChain** parameter to include all of the signatures in the trust chain, including the root authority.</span></span> <span data-ttu-id="b1973-136">Ele também usa o parâmetro **TimeStampServer** para adicionar um carimbo de data/hora à assinatura.</span><span class="sxs-lookup"><span data-stu-id="b1973-136">It also uses the **TimeStampServer** parameter to add a timestamp to the signature.</span></span>
<span data-ttu-id="b1973-137">Isso impede que o script falhe quando o certificado expirar.</span><span class="sxs-lookup"><span data-stu-id="b1973-137">This prevents the script from failing when the certificate expires.</span></span>

## <span data-ttu-id="b1973-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b1973-138">PARAMETERS</span></span>

### <span data-ttu-id="b1973-139">-Certificado</span><span class="sxs-lookup"><span data-stu-id="b1973-139">-Certificate</span></span>

<span data-ttu-id="b1973-140">Especifica o certificado que será usado para assinar o script ou arquivo.</span><span class="sxs-lookup"><span data-stu-id="b1973-140">Specifies the certificate that will be used to sign the script or file.</span></span> <span data-ttu-id="b1973-141">Insira uma variável que armazena um objeto que representa o certificado ou uma expressão que obtém o certificado.</span><span class="sxs-lookup"><span data-stu-id="b1973-141">Enter a variable that stores an object representing the certificate or an expression that gets the certificate.</span></span>

<span data-ttu-id="b1973-142">Para localizar um certificado, use `Get-PfxCertificate` ou use o `Get-ChildItem` cmdlet na unidade do certificado `Cert:` .</span><span class="sxs-lookup"><span data-stu-id="b1973-142">To find a certificate, use `Get-PfxCertificate` or use the `Get-ChildItem` cmdlet in the Certificate `Cert:` drive.</span></span> <span data-ttu-id="b1973-143">Se o certificado não for válido ou não tiver `code-signing` autoridade, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="b1973-143">If the certificate is not valid or does not have `code-signing` authority, the command fails.</span></span>

```yaml
Type: System.Security.Cryptography.X509Certificates.X509Certificate2
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1973-144">-FilePath</span><span class="sxs-lookup"><span data-stu-id="b1973-144">-FilePath</span></span>

<span data-ttu-id="b1973-145">Especifica o caminho para um arquivo que está sendo assinado.</span><span class="sxs-lookup"><span data-stu-id="b1973-145">Specifies the path to a file that is being signed.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b1973-146">-Force</span><span class="sxs-lookup"><span data-stu-id="b1973-146">-Force</span></span>

<span data-ttu-id="b1973-147">Permite ao cmdlet anexar informações de rastreamento a um arquivo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="b1973-147">Allows the cmdlet to append a signature to a read-only file.</span></span> <span data-ttu-id="b1973-148">Mesmo usando o parâmetro **Force** , o cmdlet não pode substituir as restrições de segurança.</span><span class="sxs-lookup"><span data-stu-id="b1973-148">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1973-149">-HashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="b1973-149">-HashAlgorithm</span></span>

<span data-ttu-id="b1973-150">Especifica o algoritmo de hash que o Windows usa para calcular a assinatura digital do arquivo.</span><span class="sxs-lookup"><span data-stu-id="b1973-150">Specifies the hashing algorithm that Windows uses to compute the digital signature for the file.</span></span>

<span data-ttu-id="b1973-151">Para o PowerShell 3,0, o padrão é SHA256, que é o algoritmo de hash padrão do Windows.</span><span class="sxs-lookup"><span data-stu-id="b1973-151">For PowerShell 3.0, the default is SHA256, which is the Windows default hashing algorithm.</span></span> <span data-ttu-id="b1973-152">Para o PowerShell 2,0, o padrão é SHA1.</span><span class="sxs-lookup"><span data-stu-id="b1973-152">For PowerShell 2.0, the default is SHA1.</span></span> <span data-ttu-id="b1973-153">Arquivos assinados com um algoritmo de hash diferente poderão não ser reconhecidos em outros sistemas.</span><span class="sxs-lookup"><span data-stu-id="b1973-153">Files that are signed with a different hashing algorithm might not be recognized on other systems.</span></span> <span data-ttu-id="b1973-154">Quais algoritmos têm suporte depende da versão do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="b1973-154">Which algorithms are supported depends on the version of the operating system.</span></span>

<span data-ttu-id="b1973-155">Para obter uma lista de possíveis valores, consulte [hashalgorithmname struct](/dotnet/api/system.security.cryptography.hashalgorithmname?view=netframework-4.7.2#properties).</span><span class="sxs-lookup"><span data-stu-id="b1973-155">For a list of possible values, see [HashAlgorithmName Struct](/dotnet/api/system.security.cryptography.hashalgorithmname?view=netframework-4.7.2#properties).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: SHA256
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1973-156">-IncludeChain</span><span class="sxs-lookup"><span data-stu-id="b1973-156">-IncludeChain</span></span>

<span data-ttu-id="b1973-157">Determina quais certificados na cadeia de confiança de certificados são incluídos na assinatura digital.</span><span class="sxs-lookup"><span data-stu-id="b1973-157">Determines which certificates in the certificate trust chain are included in the digital signature.</span></span>
<span data-ttu-id="b1973-158">Não **raiz** é o padrão.</span><span class="sxs-lookup"><span data-stu-id="b1973-158">**NotRoot** is the default.</span></span>

<span data-ttu-id="b1973-159">Os valores válidos são:</span><span class="sxs-lookup"><span data-stu-id="b1973-159">Valid values are:</span></span>

- <span data-ttu-id="b1973-160">Signatário: inclui apenas o certificado do signatário.</span><span class="sxs-lookup"><span data-stu-id="b1973-160">Signer: Includes only the signer's certificate.</span></span>
- <span data-ttu-id="b1973-161">Não raiz: inclui todos os certificados na cadeia de certificados, exceto para a autoridade raiz.</span><span class="sxs-lookup"><span data-stu-id="b1973-161">NotRoot: Includes all of the certificates in the certificate chain, except for the root authority.</span></span>
- <span data-ttu-id="b1973-162">Todos: inclui todos os certificados na cadeia de certificados.</span><span class="sxs-lookup"><span data-stu-id="b1973-162">All: Includes all the certificates in the certificate chain.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: NotRoot
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1973-163">-TimestampServer</span><span class="sxs-lookup"><span data-stu-id="b1973-163">-TimestampServer</span></span>

<span data-ttu-id="b1973-164">Usa o servidor do carimbo de data e hora especificada para adicionar um carimbo de data na assinatura.</span><span class="sxs-lookup"><span data-stu-id="b1973-164">Uses the specified time stamp server to add a time stamp to the signature.</span></span> <span data-ttu-id="b1973-165">Digite a URL do servidor de carimbo de data e hora como uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="b1973-165">Type the URL of the time stamp server as a string.</span></span>

<span data-ttu-id="b1973-166">O carimbo de data e hora representa a hora exata em que o certificado foi adicionado ao arquivo.</span><span class="sxs-lookup"><span data-stu-id="b1973-166">The time stamp represents the exact time that the certificate was added to the file.</span></span> <span data-ttu-id="b1973-167">Um carimbo de data e hora impede que o script falhe se o certificado expirar, pois usuários e programas podem verificar se o certificado era válido no momento da assinatura.</span><span class="sxs-lookup"><span data-stu-id="b1973-167">A time stamp prevents the script from failing if the certificate expires because users and programs can verify that the certificate was valid at the time of signing.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1973-168">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b1973-168">-LiteralPath</span></span>

<span data-ttu-id="b1973-169">Especifica o caminho para um arquivo que está sendo assinado.</span><span class="sxs-lookup"><span data-stu-id="b1973-169">Specifies the path to a file that is being signed.</span></span> <span data-ttu-id="b1973-170">Ao contrário de **FilePath** , o valor do parâmetro **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="b1973-170">Unlike **FilePath** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="b1973-171">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="b1973-171">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="b1973-172">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="b1973-172">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="b1973-173">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="b1973-173">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b1973-174">-SourcePathOrExtension</span><span class="sxs-lookup"><span data-stu-id="b1973-174">-SourcePathOrExtension</span></span>

<span data-ttu-id="b1973-175">Caminho para o arquivo ou tipo de arquivo do conteúdo para o qual a assinatura digital é adicionada.</span><span class="sxs-lookup"><span data-stu-id="b1973-175">Path to the file or file type of the content for which the digital signature is added.</span></span> <span data-ttu-id="b1973-176">Esse parâmetro é usado com o **conteúdo** em que o conteúdo do arquivo é passado como uma matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="b1973-176">This parameter is used with **Content** where file content is passed as a byte array.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByContent
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b1973-177">-Conteúdo</span><span class="sxs-lookup"><span data-stu-id="b1973-177">-Content</span></span>

<span data-ttu-id="b1973-178">Conteúdo de um arquivo como uma matriz de bytes para a qual a assinatura digital é adicionada.</span><span class="sxs-lookup"><span data-stu-id="b1973-178">Contents of a file as a byte array for which the digital signature is added.</span></span> <span data-ttu-id="b1973-179">Esse parâmetro deve ser usado com o parâmetro **SourcePathOrExtension** .</span><span class="sxs-lookup"><span data-stu-id="b1973-179">This parameter must be used with **SourcePathOrExtension** parameter.</span></span> <span data-ttu-id="b1973-180">O conteúdo do arquivo deve estar no formato Unicode (UTF-16LE).</span><span class="sxs-lookup"><span data-stu-id="b1973-180">The contents of the file must be in Unicode (UTF-16LE) format.</span></span>

```yaml
Type: System.Byte[]
Parameter Sets: ByContent
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b1973-181">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b1973-181">-Confirm</span></span>

<span data-ttu-id="b1973-182">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b1973-182">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1973-183">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b1973-183">-WhatIf</span></span>

<span data-ttu-id="b1973-184">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="b1973-184">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="b1973-185">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="b1973-185">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1973-186">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b1973-186">CommonParameters</span></span>

<span data-ttu-id="b1973-187">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b1973-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b1973-188">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b1973-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b1973-189">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b1973-189">INPUTS</span></span>

### <span data-ttu-id="b1973-190">System.String</span><span class="sxs-lookup"><span data-stu-id="b1973-190">System.String</span></span>

<span data-ttu-id="b1973-191">É possível canalizar uma cadeia de caracteres que contém o caminho do arquivo para `Set-AuthenticodeSignature` .</span><span class="sxs-lookup"><span data-stu-id="b1973-191">You can pipe a string that contains the file path to `Set-AuthenticodeSignature`.</span></span>

## <span data-ttu-id="b1973-192">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b1973-192">OUTPUTS</span></span>

### <span data-ttu-id="b1973-193">System. Management. Automation. Signature</span><span class="sxs-lookup"><span data-stu-id="b1973-193">System.Management.Automation.Signature</span></span>

## <span data-ttu-id="b1973-194">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b1973-194">NOTES</span></span>

<span data-ttu-id="b1973-195">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="b1973-195">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="b1973-196">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b1973-196">RELATED LINKS</span></span>

[<span data-ttu-id="b1973-197">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="b1973-197">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)

[<span data-ttu-id="b1973-198">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="b1973-198">Get-ExecutionPolicy</span></span>](Get-ExecutionPolicy.md)

[<span data-ttu-id="b1973-199">Get-PfxCertificate</span><span class="sxs-lookup"><span data-stu-id="b1973-199">Get-PfxCertificate</span></span>](Get-PfxCertificate.md)

[<span data-ttu-id="b1973-200">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="b1973-200">Set-ExecutionPolicy</span></span>](Set-ExecutionPolicy.md)

[<span data-ttu-id="b1973-201">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="b1973-201">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[<span data-ttu-id="b1973-202">about_Signing</span><span class="sxs-lookup"><span data-stu-id="b1973-202">about_Signing</span></span>](../Microsoft.PowerShell.Core/About/about_Signing.md)
