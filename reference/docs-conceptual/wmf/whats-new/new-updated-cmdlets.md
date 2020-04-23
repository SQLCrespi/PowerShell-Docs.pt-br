---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
title: Cmdlets novos e atualizados
ms.openlocfilehash: ffd5db2d4fc9bf8f67ef5e352633ad3209f72c87
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "71147586"
---
# <a name="new-and-updated-cmdlets"></a><span data-ttu-id="3f3ef-103">Cmdlets novos e atualizados</span><span class="sxs-lookup"><span data-stu-id="3f3ef-103">New and updated cmdlets</span></span>

<span data-ttu-id="3f3ef-104">Adicionamos cmdlets novos e atualizados de acordo com os comentários da comunidade.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-104">We have added new and updated existing cmdlets based on feedback from the community.</span></span>

## <a name="archive-cmdlets"></a><span data-ttu-id="3f3ef-105">Cmdlets Archive</span><span class="sxs-lookup"><span data-stu-id="3f3ef-105">Archive cmdlets</span></span>

<span data-ttu-id="3f3ef-106">Dois novos cmdlets, `Compress-Archive` e `Expand-Archive`, permitem compactar e expandir arquivos ZIP.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-106">Two new cmdlets, `Compress-Archive` and `Expand-Archive`, let you compress and expand ZIP files.</span></span>

<span data-ttu-id="3f3ef-107">Saiba mais na documentação do módulo [Microsoft.Powershell.Archive](/powershell/module/microsoft.powershell.archive/).</span><span class="sxs-lookup"><span data-stu-id="3f3ef-107">For more information, see the [Microsoft.Powershell.Archive](/powershell/module/microsoft.powershell.archive/) module documentation.</span></span>

## <a name="catalog-cmdlets"></a><span data-ttu-id="3f3ef-108">Cmdlets de Catálogo</span><span class="sxs-lookup"><span data-stu-id="3f3ef-108">Catalog Cmdlets</span></span>

<span data-ttu-id="3f3ef-109">Dois novos cmdlets foram adicionados ao módulo Microsoft.PowerShell.Security.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-109">Two new cmdlets have been added in the Microsoft.PowerShell.Security module.</span></span>

- [<span data-ttu-id="3f3ef-110">New-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="3f3ef-110">New-FileCatalog</span></span>](/powershell/module/microsoft.powershell.security/New-FileCatalog)
- [<span data-ttu-id="3f3ef-111">Test-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="3f3ef-111">Test-FileCatalog</span></span>](/powershell/module/microsoft.powershell.security/Test-FileCatalog)

<span data-ttu-id="3f3ef-112">Eles geram e validam os arquivos de catálogo do Windows.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-112">These generate and validate Windows catalog files.</span></span>

## <a name="clipboard-cmdlets"></a><span data-ttu-id="3f3ef-113">Área de transferência de Cmdlets</span><span class="sxs-lookup"><span data-stu-id="3f3ef-113">Clipboard cmdlets</span></span>

<span data-ttu-id="3f3ef-114">`Get-Clipboard` e `Set-Clipboard` facilitam a transferência do conteúdo de e para uma sessão do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-114">`Get-Clipboard` and `Set-Clipboard` make it easier for you to transfer content to and from a Windows PowerShell session.</span></span> <span data-ttu-id="3f3ef-115">Os cmdlets Clipboard dão suporte a imagens, arquivos de áudio, listas de arquivo e texto.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-115">The Clipboard cmdlets support images, audio files, file lists, and text.</span></span>

<span data-ttu-id="3f3ef-116">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="3f3ef-116">For more information, see:</span></span>

- [<span data-ttu-id="3f3ef-117">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="3f3ef-117">Get-Clipboard</span></span>](/powershell/module/Microsoft.PowerShell.Management/Get-Clipboard)
- [<span data-ttu-id="3f3ef-118">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="3f3ef-118">Set-Clipboard</span></span>](/powershell/module/Microsoft.PowerShell.Management/Set-Clipboard)

## <a name="cryptographic-message-syntax-cms-cmdlets"></a><span data-ttu-id="3f3ef-119">Cmdlets da CMS (Sintaxe de Mensagem Criptografada)</span><span class="sxs-lookup"><span data-stu-id="3f3ef-119">Cryptographic Message Syntax (CMS) cmdlets</span></span>

<span data-ttu-id="3f3ef-120">Os cmdlets da Sintaxe de Mensagem Criptografada dão suporte à criptografia e descriptografia de conteúdo usando o formato padrão da IETF para proteger as mensagens criptograficamente, conforme documentado pelo [RFC5652](https://tools.ietf.org/html/rfc5652.html).</span><span class="sxs-lookup"><span data-stu-id="3f3ef-120">The Cryptographic Message Syntax cmdlets support encryption and decryption of content using the IETF standard format for cryptographically protecting messages as documented by [RFC5652](https://tools.ietf.org/html/rfc5652.html).</span></span>

<span data-ttu-id="3f3ef-121">O padrão de criptografia CMS implementa a criptografia por chave pública, em que a chave usada para criptografar o conteúdo (a *chave pública*) e a chave usada para descriptografá-lo (a *chave privada*) são separadas.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-121">The CMS encryption standard implements public key cryptography, where the key used to encrypt content (the *public key*) and the key used to decrypt content (the *private key*) are separate.</span></span>

<span data-ttu-id="3f3ef-122">Sua chave pública pode ser compartilhada amplamente e não contém dados confidenciais.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-122">Your public key can be shared widely and is not sensitive data.</span></span> <span data-ttu-id="3f3ef-123">Se algum conteúdo for criptografado com essa chave pública, somente sua chave privada poderá descriptografá-lo.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-123">Any content encrypted with the public key can only be decrypted using the private key.</span></span> <span data-ttu-id="3f3ef-124">Para obter mais informações, consulte [Criptografia por chave pública](https://en.wikipedia.org/wiki/Public-key_cryptography).</span><span class="sxs-lookup"><span data-stu-id="3f3ef-124">For more information, see [Public-key cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).</span></span>

<span data-ttu-id="3f3ef-125">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="3f3ef-125">For more information see:</span></span>

- [<span data-ttu-id="3f3ef-126">Get-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="3f3ef-126">Get-CmsMessage</span></span>](/powershell/module/Microsoft.PowerShell.Security/Get-CmsMessage)
- [<span data-ttu-id="3f3ef-127">Protect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="3f3ef-127">Protect-CmsMessage</span></span>](/powershell/module/Microsoft.PowerShell.Security/Protect-CmsMessage)
- [<span data-ttu-id="3f3ef-128">Unprotect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="3f3ef-128">Unprotect-CmsMessage</span></span>](/powershell/module/Microsoft.PowerShell.Security/unprotect-CmsMessage)

<span data-ttu-id="3f3ef-129">Os certificados exigem um EKU (identificador exclusivo de uso de chave), como “Assinatura de Código” ou “Mensagens Criptografadas”, para identificá-los como certificados de criptografia de dados no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-129">Certificates require a unique key usage identifier (EKU), such as 'Code Signing' or 'Encrypted Mail', to identify them as data encryption certificates in PowerShell.</span></span> <span data-ttu-id="3f3ef-130">Para exibir certificados de criptografia de documento no provedor de certificados, é possível usar o parâmetro dinâmico **DocumentEncryptionCert** de `Get-ChildItem`:</span><span class="sxs-lookup"><span data-stu-id="3f3ef-130">To view document encryption certificates in the certificate provider, you can use the **DocumentEncryptionCert** dynamic parameter of `Get-ChildItem`:</span></span>

```powershell
Get-ChildItem Cert:\CurrentUser -DocumentEncryptionCert -Recurse
```

## <a name="extract-and-parse-structured-objects-from-string-content"></a><span data-ttu-id="3f3ef-131">Extrair e analisar objetos estruturados do conteúdo da cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="3f3ef-131">Extract and parse structured objects from string content</span></span>

### <a name="convertfrom-string"></a><span data-ttu-id="3f3ef-132">ConvertFrom-String</span><span class="sxs-lookup"><span data-stu-id="3f3ef-132">ConvertFrom-String</span></span>

<span data-ttu-id="3f3ef-133">O novo cmdlet `ConvertFrom-String` oferece suporte a dois modos:</span><span class="sxs-lookup"><span data-stu-id="3f3ef-133">The new `ConvertFrom-String` cmdlet supports two modes:</span></span>

- <span data-ttu-id="3f3ef-134">Análise básica delimitada</span><span class="sxs-lookup"><span data-stu-id="3f3ef-134">Basic delimited parsing</span></span>
- <span data-ttu-id="3f3ef-135">Análise orientada por exemplo gerada automaticamente</span><span class="sxs-lookup"><span data-stu-id="3f3ef-135">Auto generated example-driven parsing</span></span>

<span data-ttu-id="3f3ef-136">A análise delimitada, por padrão, divide a entrada no espaço em branco e atribui nomes de propriedade aos grupos resultantes.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-136">Delimited parsing, by default, splits the input at white space, and assigns property names to the resulting groups.</span></span>

<span data-ttu-id="3f3ef-137">O parâmetro **UpdateTemplate** salva os resultados do algoritmo de aprendizado em um comentário no arquivo de modelo.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-137">The **UpdateTemplate** parameter saves the results of the learning algorithm into a comment in the template file.</span></span> <span data-ttu-id="3f3ef-138">Isso faz com que o processo de aprendizado (a etapa mais lenta) seja de custo único.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-138">This makes the learning process (the slowest stage) a one-time cost.</span></span> <span data-ttu-id="3f3ef-139">A execução de `ConvertFrom-String` com um modelo que contém o algoritmo de aprendizado codificado agora é quase instantânea.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-139">Running `ConvertFrom-String` with a template that contains the encoded learning algorithm is now nearly instantaneous.</span></span>

<span data-ttu-id="3f3ef-140">Saiba mais em [ConvertFrom-String](/powershell/module/Microsoft.PowerShell.Utility/ConvertFrom-String).</span><span class="sxs-lookup"><span data-stu-id="3f3ef-140">For more information, see [ConvertFrom-String](/powershell/module/Microsoft.PowerShell.Utility/ConvertFrom-String).</span></span>

### <a name="convert-string"></a><span data-ttu-id="3f3ef-141">Convert-String</span><span class="sxs-lookup"><span data-stu-id="3f3ef-141">Convert-String</span></span>

<span data-ttu-id="3f3ef-142">`Convert-String` permite que você forneça exemplos da aparência que deseja para o texto antes e depois.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-142">`Convert-String` allows you to provide before and after examples of how you want text to look.</span></span> <span data-ttu-id="3f3ef-143">O cmdlet formata o texto automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-143">The cmdlet formats your text automatically.</span></span>

<span data-ttu-id="3f3ef-144">Saiba mais em [Convert-String](/powershell/module/Microsoft.PowerShell.Utility/Convert-String).</span><span class="sxs-lookup"><span data-stu-id="3f3ef-144">For more information, see [Convert-String](/powershell/module/Microsoft.PowerShell.Utility/Convert-String).</span></span>

## <a name="updates-to-fileinfo-object"></a><span data-ttu-id="3f3ef-145">Atualizações ao objeto FileInfo</span><span class="sxs-lookup"><span data-stu-id="3f3ef-145">Updates to FileInfo object</span></span>

<span data-ttu-id="3f3ef-146">Informações de versão de arquivo podem ser confusas, especialmente nos casos em que foi aplicado patch ao arquivo.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-146">File version information can be misleading, especially in cases where the file was patched.</span></span> <span data-ttu-id="3f3ef-147">O WMF 5.0 adiciona novas propriedades de script **FileVersionRaw** e **ProductVersionRaw** a objetos **FileInfo**.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-147">WMF 5.0 adds new **FileVersionRaw** and **ProductVersionRaw** script properties to **FileInfo** objects.</span></span>
<span data-ttu-id="3f3ef-148">Aqui estão as propriedades conforme exibidas para powershell.exe (supondo que $pid é a ID do processo do PowerShell):</span><span class="sxs-lookup"><span data-stu-id="3f3ef-148">Here are the properties as displayed for powershell.exe (assuming $pid is the ID of the PowerShell process):</span></span>

```powershell
Get-Process -Id $pid -FileVersionInfo | Format-List *version*
```

```Output
FileVersionRaw    : 10.0.17763.1
ProductVersionRaw : 10.0.17763.1
FileVersion       : 10.0.17763.1 (WinBuild.160101.0800)
ProductVersion    : 10.0.17763.1
```

## <a name="format-hex"></a><span data-ttu-id="3f3ef-149">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="3f3ef-149">Format-Hex</span></span>

<span data-ttu-id="3f3ef-150">`Format-Hex` permite exibir texto ou dados binários em formato hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-150">`Format-Hex` lets you view text or binary data in hexadecimal format.</span></span>

<span data-ttu-id="3f3ef-151">Saiba mais em [Format-Hex](/powershell/module/microsoft.powershell.utility/format-hex).</span><span class="sxs-lookup"><span data-stu-id="3f3ef-151">For more information, see [Format-Hex](/powershell/module/microsoft.powershell.utility/format-hex).</span></span>

## <a name="get-childitem-has--depth-parameter"></a><span data-ttu-id="3f3ef-152">Get-ChildItem contém o parâmetro -Depth</span><span class="sxs-lookup"><span data-stu-id="3f3ef-152">Get-ChildItem has -Depth parameter</span></span>

<span data-ttu-id="3f3ef-153">`Get-ChildItem` agora tem um parâmetro **Depth** que é usado com **Recurse** para limitar a recursão:</span><span class="sxs-lookup"><span data-stu-id="3f3ef-153">`Get-ChildItem` now has a **Depth** parameter for use with **Recurse** to limit the recursion:</span></span>

## <a name="modules-support-for-declaring-version-ranges-1-etc"></a><span data-ttu-id="3f3ef-154">Suporte aos módulos para declaração dos intervalos de versão (1.\*, etc.)</span><span class="sxs-lookup"><span data-stu-id="3f3ef-154">Modules support for declaring version ranges (1.\*, etc)</span></span>

<span data-ttu-id="3f3ef-155">Agora é possível combinar **MinimumVersion** e **MaximumVersion** para importar o módulo dentro de um intervalo específico.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-155">You can now combine **MinimumVersion** and **MaximumVersion** to import module within specific range.</span></span> <span data-ttu-id="3f3ef-156">O parâmetro também oferece suporte a caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-156">The parameters also support wildcards.</span></span>

```powershell
Import-Module psreadline -Verbose -MinimumVersion 1.0 -MaximumVersion 1.2.*
```

```Output
VERBOSE: Loading module from path 'C:\Program Files\WindowsPowerShell\Modules\psreadline\1.1\psreadline.psd1'.
VERBOSE: Importing cmdlet 'Get-PSReadlineKeyHandler'.
VERBOSE: Importing cmdlet 'Get-PSReadlineOption'.
VERBOSE: Importing cmdlet 'Remove-PSReadlineKeyHandler'.
VERBOSE: Importing cmdlet 'Set-PSReadlineKeyHandler'.
VERBOSE: Importing cmdlet 'Set-PSReadlineOption'.
VERBOSE: Importing function 'PSConsoleHostReadline'.
```

## <a name="new-guid"></a><span data-ttu-id="3f3ef-157">New-Guid</span><span class="sxs-lookup"><span data-stu-id="3f3ef-157">New-Guid</span></span>

<span data-ttu-id="3f3ef-158">Existem muitos cenários para os quais você precisa de um identificador exclusivo.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-158">There are many scenarios where youneed for unique identifier.</span></span> <span data-ttu-id="3f3ef-159">O cmdlet `New-GUID` fornece uma maneira simples de criar um novo GUID.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-159">The `New-GUID` cmdlet provides a simple way to create a new GUID.</span></span>

```powershell
New-Guid
```

```Output
Guid
----
e19d6ea5-3cc2-4db9-8095-0cdaed5a703d
```

## <a name="nonewline-parameter"></a><span data-ttu-id="3f3ef-160">Parâmetro NoNewLine</span><span class="sxs-lookup"><span data-stu-id="3f3ef-160">NoNewLine parameter</span></span>

<span data-ttu-id="3f3ef-161">`Out-File`, `Add-Content` e `Set-Content` agora têm uma nova opção **NoNewline** que simplesmente omite uma nova linha após a saída.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-161">`Out-File`, `Add-Content`, and `Set-Content` now have a new **NoNewline** switch which omits a new line after the output.</span></span> <span data-ttu-id="3f3ef-162">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3f3ef-162">For example:</span></span>

```powershell
"This is " | Out-File -FilePath Example.txt -NoNewline
"a single " | Add-Content -Path Example.txt -NoNewline
"sentence." | Add-Content -Path Example.txt -NoNewline
Get-Content .\Example.txt
```

```Output
This is a single sentence.
```

<span data-ttu-id="3f3ef-163">Sem **NoNewline** especificado, cada fragmento ficaria em uma linha separada:</span><span class="sxs-lookup"><span data-stu-id="3f3ef-163">Without **NoNewline** specified, each fragment would be on a separate line:</span></span>

```powershell
"This is " | Out-File -FilePath Example.txt
"a single " | Add-Content -Path Example.txt
"sentence." | Add-Content -Path Example.txt
Get-Content .\Example.txt
```

```Output
This is
a single
sentence.
```

## <a name="interact-with-symbolic-links-using-improved-item-cmdlets"></a><span data-ttu-id="3f3ef-164">Interagir com Links simbólicos usando cmdlets Item aprimorados</span><span class="sxs-lookup"><span data-stu-id="3f3ef-164">Interact with Symbolic links using improved Item cmdlets</span></span>

<span data-ttu-id="3f3ef-165">Para dar suporte a links simbólicos, o cmdlet Item e alguns cmdlets relacionados foram estendidos.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-165">The Item cmdlet and a few related cmdlets have been extended to support symbolic links.</span></span>

### <a name="symbolic-link-files"></a><span data-ttu-id="3f3ef-166">Arquivos de link simbólico</span><span class="sxs-lookup"><span data-stu-id="3f3ef-166">Symbolic link files</span></span>

<span data-ttu-id="3f3ef-167">Neste exemplo, podemos criar um novo arquivo de link simbólico chamado MySymLinkFile.txt em C:\Temp que se vincula a $pshome\profile.ps1.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-167">In this example, we create a new symbolic link file named MySymLinkFile.txt in C:\Temp which links to $pshome\profile.ps1.</span></span> <span data-ttu-id="3f3ef-168">Todos os três exemplos produzem o mesmo resultado.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-168">All three examples produce the same result.</span></span>

```powershell
New-Item -ItemType SymbolicLink -Path C:\Temp -Name MySymLinkFile.txt -Value $pshome\profile.ps1
New-Item -ItemType SymbolicLink -Path C:\Temp\MySymLinkFile.txt -Value $pshome\profile.ps1
New-Item -ItemType SymbolicLink -Name C:\Temp\MySymLinkFile.txt -Value $pshome\profile.ps1
```

### <a name="symbolic-link-directories"></a><span data-ttu-id="3f3ef-169">Diretórios de link simbólico</span><span class="sxs-lookup"><span data-stu-id="3f3ef-169">Symbolic link directories</span></span>

<span data-ttu-id="3f3ef-170">Neste exemplo, podemos criar um novo diretório de link simbólico chamado MySymLinkDir em C:\Temp que se vincula à pasta $pshome.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-170">In this example, we create a new symbolic link directory named MySymLinkDir in C:\Temp which links to the $pshome folder.</span></span> <span data-ttu-id="3f3ef-171">Todos os três exemplos produzem o mesmo resultado.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-171">All three examples produce the same result.</span></span>

```powershell
New-Item -ItemType SymbolicLink -Path C:\Temp -Name MySymLinkDir -Value $pshome
New-Item -ItemType SymbolicLink -Path C:\Temp\MySymLinkDir -Value $pshome
New-Item -ItemType SymbolicLink -Name C:\Temp\MySymLinkDir -Value $pshome
```

### <a name="hard-links"></a><span data-ttu-id="3f3ef-172">Links físicos</span><span class="sxs-lookup"><span data-stu-id="3f3ef-172">Hard links</span></span>

<span data-ttu-id="3f3ef-173">As mesmas combinações de **Path** e **Name** permitidas conforme descrito acima.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-173">The same combinations of **Path** and **Name** allowed as described above.</span></span>

```powershell
New-Item -ItemType HardLink -Path C:\Temp -Name MyHardLinkFile.txt -Value $pshome\profile.ps1
```

### <a name="directory-junctions"></a><span data-ttu-id="3f3ef-174">Junções de diretório</span><span class="sxs-lookup"><span data-stu-id="3f3ef-174">Directory junctions</span></span>

<span data-ttu-id="3f3ef-175">As mesmas combinações de **Path** e **Name** permitidas conforme descrito acima.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-175">The same combinations of **Path** and **Name** allowed as described above.</span></span>

```powershell
New-Item -ItemType Junction -Path C:\Temp\MyJunctionDir -Value $pshome
```

### <a name="get-childitem"></a><span data-ttu-id="3f3ef-176">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="3f3ef-176">Get-ChildItem</span></span>

<span data-ttu-id="3f3ef-177">`Get-ChildItem` agora exibe um "l" na propriedade **Mode** para indicar um link simbólico de arquivo ou diretório.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-177">`Get-ChildItem` now displays an 'l' in the **Mode** property to indicate a symbolic link file or directory.</span></span>

```powershell
Get-ChildItem C:\Temp | sort LastWriteTime -Descending

Directory: C:\Temp

Mode       LastWriteTime Length Name
----       ------------- ------ ----
-a---- 6/13/2014 3:00 PM     16 File.txt
d----- 6/13/2014 3:00 PM        Directory
-a---l 6/13/2014 3:21 PM      0 MySymLinkFile.txt
d----l 6/13/2014 3:22 PM        MySymLinkDir
-a---l 6/13/2014 3:23 PM  23304 MyHardLinkFile.txt
d----l 6/13/2014 3:24 PM        MyJunctionDir
```

### <a name="remove-item"></a><span data-ttu-id="3f3ef-178">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="3f3ef-178">Remove-Item</span></span>

<span data-ttu-id="3f3ef-179">Remover links simbólicos funciona como a remoção de qualquer outro tipo de item.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-179">Removing symbolic links works like removing any other item type.</span></span>

```powershell
Remove-Item C:\Temp\MySymLinkFile.txt
Remove-Item C:\Temp\MySymLinkDir
```

<span data-ttu-id="3f3ef-180">Use o parâmetro **Force** para remover os arquivos no diretório de destino e o link simbólico.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-180">Use the **Force** parameter to remove the files in the target directory and the symbolic link.</span></span>

```powershell
Remove-Item C:\Temp\MySymLinkDir -Force
```

## <a name="new-temporaryfile"></a><span data-ttu-id="3f3ef-181">New-TemporaryFile</span><span class="sxs-lookup"><span data-stu-id="3f3ef-181">New-TemporaryFile</span></span>

<span data-ttu-id="3f3ef-182">Às vezes, em seus scripts, é necessário criar um arquivo temporário.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-182">Sometimes in your scripts, you must create a temporary file.</span></span> <span data-ttu-id="3f3ef-183">Isso já pode ser feito com o cmdlet `New-TemporaryFile`:</span><span class="sxs-lookup"><span data-stu-id="3f3ef-183">You can now do this with the `New-TemporaryFile` cmdlet:</span></span>

```powershell
$tempFile = New-TemporaryFile
$tempFile.FullName
```

```Output
C:\Users\user1\AppData\Local\Temp\tmp375.tmp
```

## <a name="network-switch-management-with-powershell"></a><span data-ttu-id="3f3ef-184">Gerenciamento de comutador de rede com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f3ef-184">Network Switch Management with PowerShell</span></span>

<span data-ttu-id="3f3ef-185">Os cmdlets Network Switch, introduzidos no WMF 5.0, permitem aplicar a configuração do comutador, da VLAN (LAN virtual) e a configuração básica de porta do comutador de rede da Camada 2 a comutadores de rede certificados com o logotipo do Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-185">The Network Switch cmdlets, introduced in WMF 5.0, enable you to apply switch, virtual LAN (VLAN), and basic Layer 2 network switch port configuration to Windows Server 2012 R2 logo-certified network switches.</span></span> <span data-ttu-id="3f3ef-186">Com esses cmdlets, é possível executar:</span><span class="sxs-lookup"><span data-stu-id="3f3ef-186">Using these cmdlets you can perform:</span></span>

- <span data-ttu-id="3f3ef-187">Configuração do comutador global, como:</span><span class="sxs-lookup"><span data-stu-id="3f3ef-187">Global switch configuration, such as:</span></span>
  - <span data-ttu-id="3f3ef-188">Definir nome do host</span><span class="sxs-lookup"><span data-stu-id="3f3ef-188">Set host name</span></span>
  - <span data-ttu-id="3f3ef-189">Definir faixa do comutador</span><span class="sxs-lookup"><span data-stu-id="3f3ef-189">Set switch banner</span></span>
  - <span data-ttu-id="3f3ef-190">Persistir a configuração</span><span class="sxs-lookup"><span data-stu-id="3f3ef-190">Persist configuration</span></span>
  - <span data-ttu-id="3f3ef-191">Habilitar ou desabilitar um recurso</span><span class="sxs-lookup"><span data-stu-id="3f3ef-191">Enable or disable feature</span></span>

- <span data-ttu-id="3f3ef-192">Configuração de VLAN:</span><span class="sxs-lookup"><span data-stu-id="3f3ef-192">VLAN configuration:</span></span>
  - <span data-ttu-id="3f3ef-193">Criar ou remover uma VLAN</span><span class="sxs-lookup"><span data-stu-id="3f3ef-193">Create or remove VLAN</span></span>
  - <span data-ttu-id="3f3ef-194">Habilitar ou desabilitar uma VLAN</span><span class="sxs-lookup"><span data-stu-id="3f3ef-194">Enable or disable VLAN</span></span>
  - <span data-ttu-id="3f3ef-195">Enumerar uma VLAN</span><span class="sxs-lookup"><span data-stu-id="3f3ef-195">Enumerate VLAN</span></span>
  - <span data-ttu-id="3f3ef-196">Definir o nome amigável de uma VLAN</span><span class="sxs-lookup"><span data-stu-id="3f3ef-196">Set friendly name to a VLAN</span></span>

- <span data-ttu-id="3f3ef-197">Configuração de porta da Camada 2:</span><span class="sxs-lookup"><span data-stu-id="3f3ef-197">Layer 2 port configuration:</span></span>
  - <span data-ttu-id="3f3ef-198">Enumerar portas</span><span class="sxs-lookup"><span data-stu-id="3f3ef-198">Enumerate ports</span></span>
  - <span data-ttu-id="3f3ef-199">Habilitar ou desabilitar portas</span><span class="sxs-lookup"><span data-stu-id="3f3ef-199">Enable or disable ports</span></span>
  - <span data-ttu-id="3f3ef-200">Definir modos e propriedades de porta</span><span class="sxs-lookup"><span data-stu-id="3f3ef-200">Set port modes and properties</span></span>
  - <span data-ttu-id="3f3ef-201">Adicionar ou associar a VLAN ao Tronco ou Acesso na porta</span><span class="sxs-lookup"><span data-stu-id="3f3ef-201">Add or associate VLAN to Trunk or Access on the port</span></span>

<span data-ttu-id="3f3ef-202">Saiba mais na documentação do [NetworkSwitchManager](/powershell/module/networkswitchmanager/).</span><span class="sxs-lookup"><span data-stu-id="3f3ef-202">For more information, see the [NetworkSwitchManager](/powershell/module/networkswitchmanager/) documentation.</span></span>

## <a name="generate-powershell-cmdlets-based-on-an-odata-endpoint-with-odatautils"></a><span data-ttu-id="3f3ef-203">Gerar cmdlets do PowerShell com base em um ponto de extremidade OData com ODataUtils</span><span class="sxs-lookup"><span data-stu-id="3f3ef-203">Generate PowerShell cmdlets based on an OData endpoint with ODataUtils</span></span>

<span data-ttu-id="3f3ef-204">O módulo ODataUtils permite gerar cmdlets do PowerShell a partir de pontos de extremidade REST que oferecem suporte a OData.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-204">The ODataUtils module allows generation of PowerShell cmdlets from REST endpoints that support OData.</span></span> <span data-ttu-id="3f3ef-205">O módulo Microsoft.PowerShell.ODataUtils contém os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="3f3ef-205">The Microsoft.PowerShell.ODataUtils module includes the following features:</span></span>

- <span data-ttu-id="3f3ef-206">Informações adicionais do canal do ponto de extremidade do lado do servidor para o do lado do cliente.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-206">Channel additional information from server-side endpoint to client side.</span></span>
- <span data-ttu-id="3f3ef-207">Suporte à paginação do lado do cliente</span><span class="sxs-lookup"><span data-stu-id="3f3ef-207">Client-side paging support</span></span>
- <span data-ttu-id="3f3ef-208">Filtragem do lado do servidor usando o parâmetro -Select</span><span class="sxs-lookup"><span data-stu-id="3f3ef-208">Server-side filtering by using the -Select parameter</span></span>
- <span data-ttu-id="3f3ef-209">Suporte para cabeçalhos de solicitação da Web</span><span class="sxs-lookup"><span data-stu-id="3f3ef-209">Support for web request headers</span></span>

<span data-ttu-id="3f3ef-210">Os cmdlets de proxy gerados pelo cmdlet `Export-ODataEndPointProxy` fornecem mais informações do ponto de extremidade OData no lado do servidor no fluxo **Information**.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-210">The proxy cmdlets generated by the `Export-ODataEndPointProxy` cmdlet provide additional information from the server-side OData endpoint on the **Information** stream.</span></span>

```powershell
Import-Module Microsoft.PowerShell.ODataUtils -Force
$generatedProxyModuleDir = Join-Path -Path $env:SystemDrive -ChildPath 'ODataDemoProxy'
$uri = "http://services.odata.org/V3/(S(fhleiief23wrm5a5nhf542q5))/OData/OData.svc/"
Export-ODataEndpointProxy -Uri $uri -OutputModule $generatedProxyModuleDir -Force -AllowUnSecureConnection -Verbose -AllowClobber
```

<span data-ttu-id="3f3ef-211">No exemplo a seguir, recuperamos o produto principal e capturamos a saída na variável `$infoStream`.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-211">In the following example, we are retrieving top product and capturing the output in the `$infoStream` variable.</span></span>

<span data-ttu-id="3f3ef-212">Se especificarmos o parâmetro **IncludeTotalResponseCount**, obteremos a contagem total de todos os registros de **Product** disponíveis no servidor.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-212">By specifying **IncludeTotalResponseCount** parameter, we get the total count of all the **Product** records available on the server.</span></span>

```powershell
Import-Module $generatedProxyModuleDir -Force
$product = Get-Product -Top 1 -AllowUnsecureConnection -AllowAdditionalData -IncludeTotalResponseCount -InformationVariable infoStream
$additionalInfo = $infoStream.GetEnumerator() | % MessageData
$additionalInfo['odata.count']
```

<span data-ttu-id="3f3ef-213">É possível obter os registros do servidor em lotes usando o suporte à paginação do lado do cliente.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-213">You can get the records from the server in batches using client-side paging support.</span></span> <span data-ttu-id="3f3ef-214">Isso é útil quando é necessário obter uma grande quantidade de dados do servidor pela rede.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-214">This is useful when you must get a large amount of data from the server over the network.</span></span>

```powershell
$skipCount = 0
$batchSize = 3
while($skipCount -le $additionalInfo['odata.count'])
{
  Get-Product -AllowUnsecureConnection -AllowAdditionalData -Top $batchSize -Skip $skipCount
  $skipCount += $batchSize
}
```

<span data-ttu-id="3f3ef-215">Os cmdlets do proxy gerados oferecem suporte ao parâmetro **Select** que pode ser usado como um filtro para receber apenas as propriedades de registro de que o cliente precisa.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-215">The generated proxy cmdlets support the **Select** parameter that is used as a filter to receive only the record properties that the client needs.</span></span> <span data-ttu-id="3f3ef-216">A filtragem ocorre no servidor e isso reduz a quantidade de dados transferidos pela rede.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-216">The filtering occurs on the server, which reduces the amount of data that is transferred over the network.</span></span>

```powershell
Get-Product -Top 2 -AllowUnsecureConnection -AllowAdditionalData -Select Name
```

<span data-ttu-id="3f3ef-217">O cmdlet `Export-ODataEndpointProxy` e os cmdlets do proxy gerados por ele agora oferecem suporte ao parâmetro **Headers**.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-217">The `Export-ODataEndpointProxy` cmdlet, and the proxy cmdlets generated by it, now support the **Headers** parameter.</span></span> <span data-ttu-id="3f3ef-218">O cabeçalho pode ser usado para canalizar informações adicionais esperadas pelo ponto de extremidade OData.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-218">The header can be used to channel additional information expected by the OData endpoint.</span></span>

<span data-ttu-id="3f3ef-219">No exemplo a seguir, uma tabela de hash que contém uma chave de Assinatura é fornecida ao parâmetro **Headers**.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-219">In the following example, a hash table containing a Subscription key is provided to the **Headers** parameter.</span></span> <span data-ttu-id="3f3ef-220">Isso é um exemplo típico de serviços que esperam uma chave de Assinatura para autenticação.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-220">This is a typical example for services that are expecting a Subscription key for authentication.</span></span>

```powershell
Export-ODataEndpointProxy -Uri $endPointUri -OutputModule $generatedProxyModuleDir -Force -AllowUnSecureConnection -Verbose -Headers @{'subscription-key'='XXXX'}
```
