---
description: Certificado
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/about/about_certificate_provider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Provedor Certificate
ms.openlocfilehash: b3ac701f18ba57d9108a76b7c478b8514075b3ee
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195829"
---
# <a name="certificate-provider"></a><span data-ttu-id="65766-104">Provedor Certificate</span><span class="sxs-lookup"><span data-stu-id="65766-104">Certificate Provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="65766-105">Nome do provedor</span><span class="sxs-lookup"><span data-stu-id="65766-105">Provider name</span></span>

<span data-ttu-id="65766-106">Certificado</span><span class="sxs-lookup"><span data-stu-id="65766-106">Certificate</span></span>

## <a name="drives"></a><span data-ttu-id="65766-107">Unidades</span><span class="sxs-lookup"><span data-stu-id="65766-107">Drives</span></span>

`Cert:`

## <a name="capabilities"></a><span data-ttu-id="65766-108">Funcionalidades</span><span class="sxs-lookup"><span data-stu-id="65766-108">Capabilities</span></span>

<span data-ttu-id="65766-109">**ShouldProcess**</span><span class="sxs-lookup"><span data-stu-id="65766-109">**ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="65766-110">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="65766-110">Short description</span></span>

<span data-ttu-id="65766-111">Fornece acesso a repositórios de certificados X. 509 e certificados no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65766-111">Provides access to X.509 certificate stores and certificates in PowerShell.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="65766-112">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="65766-112">Detailed description</span></span>

<span data-ttu-id="65766-113">O provedor de **certificados** do PowerShell permite que você obtenha, adicione, altere, apague e exclua certificados e repositórios de certificados no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65766-113">The PowerShell **Certificate** provider lets you get, add, change, clear, and delete certificates and certificate stores in PowerShell.</span></span>

<span data-ttu-id="65766-114">A unidade de **certificado** é um namespace hierárquico que contém os repositórios de certificados e certificados em seu computador.</span><span class="sxs-lookup"><span data-stu-id="65766-114">The **Certificate** drive is a hierarchical namespace containing the certificate stores and certificates on your computer.</span></span>

<span data-ttu-id="65766-115">O provedor de **certificado** dá suporte aos seguintes cmdlets, que são abordados neste artigo.</span><span class="sxs-lookup"><span data-stu-id="65766-115">The **Certificate** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="65766-116">Get-Location</span><span class="sxs-lookup"><span data-stu-id="65766-116">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="65766-117">Set-Location</span><span class="sxs-lookup"><span data-stu-id="65766-117">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="65766-118">Get-Item</span><span class="sxs-lookup"><span data-stu-id="65766-118">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="65766-119">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="65766-119">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [<span data-ttu-id="65766-120">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="65766-120">Invoke-Item</span></span>](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [<span data-ttu-id="65766-121">Move-Item</span><span class="sxs-lookup"><span data-stu-id="65766-121">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="65766-122">New-Item</span><span class="sxs-lookup"><span data-stu-id="65766-122">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="65766-123">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="65766-123">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="65766-124">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="65766-124">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="65766-125">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="65766-125">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [<span data-ttu-id="65766-126">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="65766-126">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [<span data-ttu-id="65766-127">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="65766-127">Get-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Get-AuthenticodeSignature)
- [<span data-ttu-id="65766-128">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="65766-128">Set-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="65766-129">Tipos expostos por este provedor</span><span class="sxs-lookup"><span data-stu-id="65766-129">Types exposed by this provider</span></span>

<span data-ttu-id="65766-130">A unidade do certificado expõe os tipos a seguir.</span><span class="sxs-lookup"><span data-stu-id="65766-130">The Certificate drive exposes the following types.</span></span>

- <span data-ttu-id="65766-131">Locais de armazenamento (Microsoft. PowerShell. Commands. X509StoreLocation), que são contêineres de alto nível que agrupam os certificados para o usuário atual e para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="65766-131">Store locations (Microsoft.PowerShell.Commands.X509StoreLocation), which are high-level containers that group the certificates for the current user and for all users.</span></span> <span data-ttu-id="65766-132">Cada sistema tem um local de armazenamento CurrentUser e LocalMachine (todos os usuários).</span><span class="sxs-lookup"><span data-stu-id="65766-132">Each system has a CurrentUser and LocalMachine (all users) store location.</span></span>

- <span data-ttu-id="65766-133">Os certificados armazena (System. Security. Cryptography. X509Certificates. X509Store), que são repositórios físicos nos quais os certificados são salvos e gerenciados.</span><span class="sxs-lookup"><span data-stu-id="65766-133">Certificates stores (System.Security.Cryptography.X509Certificates.X509Store), which are physical stores in which certificates are saved and managed.</span></span>

- <span data-ttu-id="65766-134">Os certificados x. 509 **System. Security. Cryptography. X509Certificates. X509Certificate2** , cada um representando um certificado X. 509 no computador.</span><span class="sxs-lookup"><span data-stu-id="65766-134">X.509 **System.Security.Cryptography.X509Certificates.X509Certificate2** certificates, each of which represent an X.509 certificate on the computer.</span></span>
  <span data-ttu-id="65766-135">Certificados são identificados por suas impressões digitais.</span><span class="sxs-lookup"><span data-stu-id="65766-135">Certificates are identified by their thumbprints.</span></span>

## <a name="navigating-the-certificate-drive"></a><span data-ttu-id="65766-136">Navegando pela unidade de certificado</span><span class="sxs-lookup"><span data-stu-id="65766-136">Navigating the Certificate drive</span></span>

<span data-ttu-id="65766-137">O provedor de **certificado** expõe o namespace do certificado como a `Cert:` unidade no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65766-137">The **Certificate** provider exposes the certificate namespace as the `Cert:` drive in PowerShell.</span></span> <span data-ttu-id="65766-138">Esse comando usa o `Set-Location` comando para alterar o local atual para o repositório de certificados raiz no local de armazenamento LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="65766-138">This command uses the `Set-Location` command to change the current location to the Root certificate store in the LocalMachine store location.</span></span> <span data-ttu-id="65766-139">Use uma barra invertida ( \\ ) ou uma barra (/) para indicar um nível da `Cert:` unidade.</span><span class="sxs-lookup"><span data-stu-id="65766-139">Use a backslash (\\) or a forward slash (/) to indicate a level of the `Cert:` drive.</span></span>

```powershell
Set-Location Cert:
```

<span data-ttu-id="65766-140">Você também pode trabalhar com o provedor de certificado de qualquer outra unidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65766-140">You can also work with the certificate provider from any other PowerShell drive.</span></span> <span data-ttu-id="65766-141">Para fazer referência a um alias de outro local, use o `Cert:` nome da unidade no caminho.</span><span class="sxs-lookup"><span data-stu-id="65766-141">To reference an alias from another location, use the `Cert:` drive name in the path.</span></span>

```powershell
PS Cert:\> Set-Location -Path LocalMachine\Root
```

<span data-ttu-id="65766-142">Para retornar a uma unidade de sistema de arquivos, digite o nome da unidade.</span><span class="sxs-lookup"><span data-stu-id="65766-142">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="65766-143">Por exemplo, digite:</span><span class="sxs-lookup"><span data-stu-id="65766-143">For example, type:</span></span>

```powershell
Set-Location C:
```

> [!NOTE]
> <span data-ttu-id="65766-144">O PowerShell usa aliases para permitir a você uma maneira familiar de trabalhar com caminhos de provedor.</span><span class="sxs-lookup"><span data-stu-id="65766-144">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="65766-145">Comandos como `dir` e `ls` agora são aliases para [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` é um alias para [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span><span class="sxs-lookup"><span data-stu-id="65766-145">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span>
> <span data-ttu-id="65766-146">e `pwd` é um alias para [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span><span class="sxs-lookup"><span data-stu-id="65766-146">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

## <a name="displaying-the-contents-of-the-cert-drive"></a><span data-ttu-id="65766-147">Exibindo o conteúdo da unidade CERT:</span><span class="sxs-lookup"><span data-stu-id="65766-147">Displaying the Contents of the Cert: drive</span></span>

<span data-ttu-id="65766-148">Esse comando usa o `Get-ChildItem` cmdlet para exibir os repositórios de certificados no local do repositório de certificados CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="65766-148">This command uses the `Get-ChildItem` cmdlet to display the certificate stores in the CurrentUser certificate store location.</span></span>

<span data-ttu-id="65766-149">Se você não estiver na `Cert:` unidade, use um caminho absoluto.</span><span class="sxs-lookup"><span data-stu-id="65766-149">If you are not in the `Cert:` drive, use an absolute path.</span></span>

```powershell
PS Cert:\CurrentUser\> Get-ChildItem
```

### <a name="displaying-certificate-properties-within-the-cert-drive"></a><span data-ttu-id="65766-150">Exibindo Propriedades de certificado dentro da unidade CERT:</span><span class="sxs-lookup"><span data-stu-id="65766-150">Displaying certificate properties within the Cert: drive</span></span>

<span data-ttu-id="65766-151">Este exemplo obtém um certificado com `Get-Item` e o armazena em uma variável.</span><span class="sxs-lookup"><span data-stu-id="65766-151">This example gets a certificate with `Get-Item` and stores it in a variable.</span></span>
<span data-ttu-id="65766-152">O exemplo mostra as novas propriedades de script de certificado ( **DnsNameList** , **EnhancedKeyUsageList** , **SendAsTrustedIssuer** ) usando `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="65766-152">The example shows the new certificate script properties ( **DnsNameList** , **EnhancedKeyUsageList** , **SendAsTrustedIssuer** ) using `Select-Object`.</span></span>

```powershell
$c = Get-Item cert:\LocalMachine\My\52A149D0393CE8A8D4AF0B172ED667A9E3A1F44E
$c | Format-List DnsNameList, EnhancedKeyUsageList, SendAsTrustedIssuer
```

```output
DnsNameList          : {SERVER01.contoso.com}
EnhancedKeyUsageList : {WiFi-Machine (1.3.6.1.4.1.311.42.2.6),
                       Client Authentication (1.3.6.1.5.5.7.3.2)}
SendAsTrustedIssuer  : False
```

### <a name="find-all-codesigning-certificates"></a><span data-ttu-id="65766-153">Localizar todos os certificados de codesignação</span><span class="sxs-lookup"><span data-stu-id="65766-153">Find all CodeSigning certificates</span></span>

<span data-ttu-id="65766-154">Esse comando usa os parâmetros **CodeSigningCert** e **recurse** do `Get-ChildItem` cmdlet para obter todos os certificados no computador que têm autoridade de assinatura de código.</span><span class="sxs-lookup"><span data-stu-id="65766-154">This command uses the **CodeSigningCert** and **Recurse** parameters of the `Get-ChildItem` cmdlet to get all of the certificates on the computer that have code-signing authority.</span></span>

```powershell
Get-ChildItem -Path cert: -CodeSigningCert -Recurse
```

### <a name="find-expired-certificates"></a><span data-ttu-id="65766-155">Localizar certificados expirados</span><span class="sxs-lookup"><span data-stu-id="65766-155">Find expired certificates</span></span>

<span data-ttu-id="65766-156">Esse comando usa o parâmetro **ExpiringInDays** do `Get-ChildItem` cmdlet para obter certificados que irão expirar nos próximos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="65766-156">This command uses the **ExpiringInDays** parameter of the `Get-ChildItem` cmdlet to get certificates that will expire within the next 30 days.</span></span>

```powershell
Get-ChildItem -Path cert:\LocalMachine\WebHosting -ExpiringInDays 30
```

### <a name="find-server-ssl-certificates"></a><span data-ttu-id="65766-157">Localizar certificados SSL do servidor</span><span class="sxs-lookup"><span data-stu-id="65766-157">Find Server SSL Certificates</span></span>

<span data-ttu-id="65766-158">Esse comando usa o parâmetro **SSLServerAuthentication** do `Get-ChildItem` cmdlet para obter todos os certificados SSL do servidor nos repositórios My e webhosting.</span><span class="sxs-lookup"><span data-stu-id="65766-158">This command uses the **SSLServerAuthentication** parameter of the `Get-ChildItem` cmdlet to get all Server SSL Certificates in the My and WebHosting stores.</span></span>

```powershell
Get-ChildItem -Path cert:\LocalMachine\My, cert:\LocalMachine\WebHosting `
  -SSLServerAuthentication
```

### <a name="find-expired-certificates-on-remote-computers"></a><span data-ttu-id="65766-159">Localizar certificados expirados em computadores remotos</span><span class="sxs-lookup"><span data-stu-id="65766-159">Find expired certificates on remote computers</span></span>

<span data-ttu-id="65766-160">Esse comando usa o `Invoke-Command` cmdlet para executar um `Get-ChildItem` comando nos computadores Srv01 e Srv02.</span><span class="sxs-lookup"><span data-stu-id="65766-160">This command uses the `Invoke-Command` cmdlet to run a `Get-ChildItem` command on the Srv01 and Srv02 computers.</span></span> <span data-ttu-id="65766-161">Um valor de zero (0) no parâmetro **ExpiringInDays** obtém certificados nos computadores Srv01 e Srv02 que expiraram.</span><span class="sxs-lookup"><span data-stu-id="65766-161">A value of zero (0) in the **ExpiringInDays** parameter gets certificates on the Srv01 and Srv02 computers that have expired.</span></span>

```powershell
Invoke-Command -ComputerName Srv01, Srv02 {Get-ChildItem -Path cert:\* `
  -Recurse -ExpiringInDays 0}
```

### <a name="combining-filters-to-find-a-specific-set-of-certificates"></a><span data-ttu-id="65766-162">Combinando filtros para localizar um conjunto específico de certificados</span><span class="sxs-lookup"><span data-stu-id="65766-162">Combining filters to find a specific set of certificates</span></span>

<span data-ttu-id="65766-163">Esse comando obtém todos os certificados no local do repositório LocalMachine que têm os seguintes atributos:</span><span class="sxs-lookup"><span data-stu-id="65766-163">This command gets all certificates in the LocalMachine store location that have the following attributes:</span></span>

- <span data-ttu-id="65766-164">"fabrikam" em seu nome DNS</span><span class="sxs-lookup"><span data-stu-id="65766-164">"fabrikam" in their DNS name</span></span>
- <span data-ttu-id="65766-165">"Autenticação de cliente" em seu EKU</span><span class="sxs-lookup"><span data-stu-id="65766-165">"Client Authentication" in their EKU</span></span>
- <span data-ttu-id="65766-166">um valor de `$true` para a propriedade **SendAsTrustedIssuer**</span><span class="sxs-lookup"><span data-stu-id="65766-166">a value of `$true` for the **SendAsTrustedIssuer** property</span></span>
- <span data-ttu-id="65766-167">Não expire nos próximos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="65766-167">do not expire within the next 30 days.</span></span>

<span data-ttu-id="65766-168">A propriedade não **After** armazena a data de expiração do certificado.</span><span class="sxs-lookup"><span data-stu-id="65766-168">The **NotAfter** property stores the certificate expiration date.</span></span>

```powershell
[DateTime] $ValidThrough = (Get-Date) + (New-TimeSpan -Days 30)
Get-ChildItem -Path cert:\* -Recurse -DNSName "*fabrikam*" `
  -EKU "*Client Authentication*" | Where-Object {
                                     $_.SendAsTrustedIssuer -and `
                                     $_.NotAfter -gt $ValidThrough
                                   }
```

## <a name="opening-the-certificates-mmc-snap-in"></a><span data-ttu-id="65766-169">Abrir os certificados Snap-in MMC</span><span class="sxs-lookup"><span data-stu-id="65766-169">Opening the Certificates MMC Snap-in</span></span>

<span data-ttu-id="65766-170">O `Invoke-Item` cmdlet usará o aplicativo padrão para abrir um caminho que você especificar.</span><span class="sxs-lookup"><span data-stu-id="65766-170">The `Invoke-Item` cmdlet will use the default application to open a path you specify.</span></span> <span data-ttu-id="65766-171">Para certificados, o aplicativo padrão é o snap-in do MMC de certificados.</span><span class="sxs-lookup"><span data-stu-id="65766-171">For certificates, the default application is the Certificates MMC snap-in.</span></span>

<span data-ttu-id="65766-172">Esse comando abre o snap-in de certificados do MMC para gerenciar o certificado especificado.</span><span class="sxs-lookup"><span data-stu-id="65766-172">This command opens the Certificates MMC snap-in to manage the specified certificate.</span></span>

```powershell
Invoke-Item cert:\CurrentUser\my\6B8223358119BB08840DEE50FD8AF9EA776CE66B
```

## <a name="copying-certificates"></a><span data-ttu-id="65766-173">Copiando certificados</span><span class="sxs-lookup"><span data-stu-id="65766-173">Copying Certificates</span></span>

<span data-ttu-id="65766-174">O provedor de **certificados** não dá suporte à cópia de certificados.</span><span class="sxs-lookup"><span data-stu-id="65766-174">Copying certificates is not supported by the **Certificate** provider.</span></span> <span data-ttu-id="65766-175">Ao tentar copiar um certificado, você verá esse erro.</span><span class="sxs-lookup"><span data-stu-id="65766-175">When you attempt to copy a certificate, you see this error.</span></span>

```
$path = "Cert:\LocalMachine\Root\E2C0F6662D3C569705B4B31FE2CBF3434094B254"
PS Cert:\LocalMachine\> Copy-Item -Path $path -Destination .\CA\
Copy-Item : Provider operation stopped because the provider does not support
this operation.
At line:1 char:1
+ Copy-Item -Path $path -Destination .\CA\
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotImplemented: (:) [Copy-Item],
                              PSNotSupportedException
    + FullyQualifiedErrorId : NotSupported,
                              Microsoft.PowerShell.Commands.CopyItemCommand
```

## <a name="moving-certificates"></a><span data-ttu-id="65766-176">Movendo certificados</span><span class="sxs-lookup"><span data-stu-id="65766-176">Moving Certificates</span></span>

### <a name="move-all-ssl-server-authentication-certs-to-the-webhosting-store"></a><span data-ttu-id="65766-177">Mover todos os certificados de autenticação de servidor SSL para o repositório webhosting</span><span class="sxs-lookup"><span data-stu-id="65766-177">Move all SSL Server authentication certs to the WebHosting store</span></span>

<span data-ttu-id="65766-178">Esse comando usa o `Move-Item` cmdlet para mover um certificado do repositório My para o repositório webhosting.</span><span class="sxs-lookup"><span data-stu-id="65766-178">This command uses the `Move-Item` cmdlet to move a certificate from the My store to the WebHosting store.</span></span>

<span data-ttu-id="65766-179">`Move-Item` Não moverá os repositórios de certificados e ele não moverá certificados para um local de repositório diferente, como mover um certificado de LocalMachine para CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="65766-179">`Move-Item` will not move certificate stores and it will not move certificates to a different store location, such as moving a certificate from LocalMachine to CurrentUser.</span></span> <span data-ttu-id="65766-180">O `Move-Item` cmdlet Move certificados, mas não move chaves privadas.</span><span class="sxs-lookup"><span data-stu-id="65766-180">The `Move-Item` cmdlet moves certificates, but it does not move private keys.</span></span>

<span data-ttu-id="65766-181">Esse comando usa o parâmetro **SSLServerAuthentication** do `Get-ChildItem` cmdlet para obter certificados de autenticação de servidor SSL no meu repositório de certificados.</span><span class="sxs-lookup"><span data-stu-id="65766-181">This command uses the **SSLServerAuthentication** parameter of the `Get-ChildItem` cmdlet to get SSL server authentication certificates in the MY certificate store.</span></span>

<span data-ttu-id="65766-182">Os certificados retornados são canalizados para o `Move-Item` cmdlet, que move os certificados para o repositório webhosting.</span><span class="sxs-lookup"><span data-stu-id="65766-182">The returned certificates are piped to the `Move-Item` cmdlet, which moves the certificates to the WebHosting store.</span></span>

```powershell
Get-ChildItem cert:\LocalMachine\My -SSLServerAuthentication | Move-Item `
  -Destination cert:\LocalMachine\WebHosting
```

## <a name="deleting-certificates-and-private-keys"></a><span data-ttu-id="65766-183">Excluindo certificados e chaves privadas</span><span class="sxs-lookup"><span data-stu-id="65766-183">Deleting Certificates and Private Keys</span></span>

<span data-ttu-id="65766-184">O `Remove-Item` cmdlet removerá os certificados que você especificar.</span><span class="sxs-lookup"><span data-stu-id="65766-184">The `Remove-Item` cmdlet will remove certificates that you specify.</span></span> <span data-ttu-id="65766-185">O `-DeleteKey` parâmetro dinâmico exclui a chave privada.</span><span class="sxs-lookup"><span data-stu-id="65766-185">The `-DeleteKey` dynamic parameter deletes the private key.</span></span>

### <a name="delete-a-certificate-from-the-ca-store"></a><span data-ttu-id="65766-186">Excluir um certificado do repositório de AC</span><span class="sxs-lookup"><span data-stu-id="65766-186">Delete a Certificate from the CA store</span></span>

<span data-ttu-id="65766-187">Esse comando exclui um certificado do repositório de certificados de AC, mas deixa a chave privada associada intacta.</span><span class="sxs-lookup"><span data-stu-id="65766-187">This command deletes a certificate from the CA certificate store, but leaves the associated private key intact.</span></span>

<span data-ttu-id="65766-188">Na `Cert:` unidade, o `Remove-Item` cmdlet dá suporte apenas aos parâmetros **DeleteKey** , **Path** , **WhatIf** e **Confirm** .</span><span class="sxs-lookup"><span data-stu-id="65766-188">In the `Cert:` drive, the `Remove-Item` cmdlet supports only the **DeleteKey** , **Path** , **WhatIf** , and **Confirm** parameters.</span></span> <span data-ttu-id="65766-189">Todos os outros parâmetros são ignorados.</span><span class="sxs-lookup"><span data-stu-id="65766-189">All other parameters are ignored.</span></span>

```powershell
Remove-Item cert:\LocalMachine\CA\5DDC44652E62BF9AA1116DC41DE44AB47C87BDD0
```

### <a name="delete-a-certificate-using-a-wildcards-in-the-dns-name"></a><span data-ttu-id="65766-190">Excluir um certificado usando curingas no nome DNS</span><span class="sxs-lookup"><span data-stu-id="65766-190">Delete a Certificate using a wildcards in the DNS name</span></span>

<span data-ttu-id="65766-191">Esse comando exclui todos os certificados que têm um nome DNS que contém "Fabrikam".</span><span class="sxs-lookup"><span data-stu-id="65766-191">This command deletes all certificates that have a DNS name that contains "Fabrikam".</span></span> <span data-ttu-id="65766-192">Ele usa o parâmetro **DnsName** do `Get-ChildItem` cmdlet para obter os certificados e o `Remove-Item` cmdlet para excluí-los.</span><span class="sxs-lookup"><span data-stu-id="65766-192">It uses the **DNSName** parameter of the `Get-ChildItem` cmdlet to get the certificates and the `Remove-Item` cmdlet to delete them.</span></span>

```powershell
Get-ChildItem -Path cert:\LocalMachine -DnsName *Fabrikam* | Remove-Item
```

### <a name="delete-private-keys-from-a-remote-computer"></a><span data-ttu-id="65766-193">Excluir chaves privadas de um computador remoto</span><span class="sxs-lookup"><span data-stu-id="65766-193">Delete private keys from a remote computer</span></span>

<span data-ttu-id="65766-194">Esta série de comandos permite a delegação e, em seguida, a exclusão do certificado e da chave privada associada em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="65766-194">This series of commands enables delegation and then deletes the certificate and associated private key on a remote computer.</span></span> <span data-ttu-id="65766-195">Para excluir uma chave privada em um computador remoto, você deve usar credenciais delegadas.</span><span class="sxs-lookup"><span data-stu-id="65766-195">To delete a private key on a remote computer, you must use delegated credentials.</span></span>

<span data-ttu-id="65766-196">Use o `Enable-WSManCredSSP` cmdlet para habilitar a autenticação de CredSSP (provedor de serviços de segurança de credencial) em um cliente no computador remoto S1.</span><span class="sxs-lookup"><span data-stu-id="65766-196">Use the `Enable-WSManCredSSP` cmdlet to enable Credential Security Service Provider (CredSSP) authentication on a client on the S1 remote computer.</span></span>
<span data-ttu-id="65766-197">O CredSSP permite a autenticação delegada.</span><span class="sxs-lookup"><span data-stu-id="65766-197">CredSSP permits delegated authentication.</span></span>

```powershell
Enable-WSManCredSSP -Role Client -DelegateComputer S1
```

<span data-ttu-id="65766-198">Use o `Connect-WSMan` cmdlet para conectar o computador S1 ao serviço WinRM no computador local.</span><span class="sxs-lookup"><span data-stu-id="65766-198">Use the `Connect-WSMan` cmdlet to connect the S1 computer to the WinRM service on the local computer.</span></span> <span data-ttu-id="65766-199">Quando esse comando for concluído, o computador S1 aparecerá na `WSMan:` unidade local no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65766-199">When this command completes, the S1 computer appears in the local `WSMan:` drive in PowerShell.</span></span>

```powershell
Connect-WSMan -ComputerName S1 -Credential Domain01\Admin01
```

<span data-ttu-id="65766-200">Agora, você pode usar o cmdlet Set-Item na unidade WSMan: para habilitar o atributo CredSSP para o serviço WinRM.</span><span class="sxs-lookup"><span data-stu-id="65766-200">Now, you can use the Set-Item cmdlet in the WSMan: drive to enable the CredSSP attribute for the WinRM service.</span></span>

```powershell
Set-Item -Path WSMan:\S1\Service\Auth\CredSSP -Value $true
```

<span data-ttu-id="65766-201">Inicie uma sessão remota no computador S1 usando o `New-PSSession` cmdlet e especifique a autenticação CredSSP.</span><span class="sxs-lookup"><span data-stu-id="65766-201">Start a remote session on the s1 computer using the `New-PSSession` cmdlet, and specify CredSSP authentication.</span></span> <span data-ttu-id="65766-202">Salva a sessão na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="65766-202">Saves the session in the `$s` variable.</span></span>

```powershell
$s  = New-PSSession S1 -Authentication CredSSP -Credential Domain01\Admin01
```

<span data-ttu-id="65766-203">Por fim, use o `Invoke-Command` cmdlet para executar um `Remove-Item` comando na sessão na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="65766-203">Finally, use the `Invoke-Command` cmdlet to run a `Remove-Item` command in the session in the `$s` variable.</span></span> <span data-ttu-id="65766-204">O `Remove-Item` comando usa o parâmetro **DeleteKey** para remover a chave privada junto com o certificado especificado.</span><span class="sxs-lookup"><span data-stu-id="65766-204">The `Remove-Item` command uses the **DeleteKey** parameter to remove the private key along with the specified certificate.</span></span>

```powershell
Invoke-Command -Session $s { Remove-Item `
  -Path cert:\LocalMachine\My\D2D38EBA60CAA1C12055A2E1C83B15AD450110C2 `
  -DeleteKey
  }
```

### <a name="delete-expired-certificates"></a><span data-ttu-id="65766-205">Excluir certificados expirados</span><span class="sxs-lookup"><span data-stu-id="65766-205">Delete expired Certificates</span></span>

<span data-ttu-id="65766-206">Esse comando usa o parâmetro **ExpiringInDays** do `Get-ChildItem` cmdlet com um valor de 0 para obter certificados no repositório webhosting que expirou.</span><span class="sxs-lookup"><span data-stu-id="65766-206">This command uses the **ExpiringInDays** parameter of the `Get-ChildItem` cmdlet with a value of 0 to get certificates in the WebHosting store that have expired.</span></span>

<span data-ttu-id="65766-207">A variável que contém os certificados retornados é canalizada para o `Remove-Item` cmdlet, que os exclui.</span><span class="sxs-lookup"><span data-stu-id="65766-207">The variable containing the returned certificates is piped to the `Remove-Item` cmdlet, which deletes them.</span></span> <span data-ttu-id="65766-208">O comando usa o parâmetro **DeleteKey** para excluir a chave privada junto com o certificado.</span><span class="sxs-lookup"><span data-stu-id="65766-208">The command uses the **DeleteKey** parameter to delete the private key along with the certificate.</span></span>

```powershell
$expired = Get-ChildItem cert:\LocalMachine\WebHosting -ExpiringInDays 0
$expired | Remove-Item -DeleteKey
```

## <a name="creating-certificates"></a><span data-ttu-id="65766-209">Criando certificados</span><span class="sxs-lookup"><span data-stu-id="65766-209">Creating Certificates</span></span>

<span data-ttu-id="65766-210">O `New-Item` cmdlet não cria novos certificados no provedor de **certificados** .</span><span class="sxs-lookup"><span data-stu-id="65766-210">The `New-Item` cmdlet does not create new certificates in the **Certificate** provider.</span></span> <span data-ttu-id="65766-211">Use o cmdlet [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate) para criar um certificado para fins de teste.</span><span class="sxs-lookup"><span data-stu-id="65766-211">Use the [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet to create a certificate for testing purposes.</span></span>

## <a name="creating-certificate-stores"></a><span data-ttu-id="65766-212">Criação de repositórios de certificados</span><span class="sxs-lookup"><span data-stu-id="65766-212">Creating Certificate Stores</span></span>

<span data-ttu-id="65766-213">Na unidade CERT:, o `New-Item` cmdlet cria repositórios de certificados no local de armazenamento LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="65766-213">In the Cert: drive, the `New-Item` cmdlet creates certificate stores in the LocalMachine store location.</span></span> <span data-ttu-id="65766-214">Ele dá suporte aos parâmetros **Name** , **Path** , **WhatIf** e **Confirm** .</span><span class="sxs-lookup"><span data-stu-id="65766-214">It supports the **Name** , **Path** , **WhatIf** , and **Confirm** parameters.</span></span> <span data-ttu-id="65766-215">Todos os outros parâmetros são ignorados.</span><span class="sxs-lookup"><span data-stu-id="65766-215">All other parameters are ignored.</span></span> <span data-ttu-id="65766-216">O comando retorna um **System. Security. Cryptography. X509Certificates. X509Store** que representa o novo repositório de certificados.</span><span class="sxs-lookup"><span data-stu-id="65766-216">The command returns a **System.Security.Cryptography.X509Certificates.X509Store** that represents the new certificate store.</span></span>

<span data-ttu-id="65766-217">Este comando cria um novo repositório de certificados denominado "CustomStore" no local de armazenamento LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="65766-217">This command creates a new certificate store named "CustomStore" in the LocalMachine store location.</span></span>

```powershell
New-Item -Path cert:\LocalMachine\CustomStore
```

### <a name="create-a-new-certificate-store-on-a-remote-computer"></a><span data-ttu-id="65766-218">Criar um novo repositório de certificados em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="65766-218">Create a new certificate store on a remote computer</span></span>

<span data-ttu-id="65766-219">Este comando cria um novo repositório de certificados denominado "HostingStore" no local de repositório LocalMachine no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="65766-219">This command creates a new certificate store named "HostingStore" in the LocalMachine store location on the Server01 computer.</span></span>

<span data-ttu-id="65766-220">O comando usa o `Invoke-Command` cmdlet para executar um `New-Item` comando no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="65766-220">The command uses the `Invoke-Command` cmdlet to run a `New-Item` command on the Server01 computer.</span></span> <span data-ttu-id="65766-221">O comando retorna um **System. Security. Cryptography. X509Certificates. X509Store** que representa o novo repositório de certificados.</span><span class="sxs-lookup"><span data-stu-id="65766-221">The command returns a **System.Security.Cryptography.X509Certificates.X509Store** that represents the new certificate store.</span></span>

```powershell
Invoke-Command { New-Item -Path cert:\LocalMachine\CustomStore } `
  -ComputerName Server01
```

## <a name="creating-client-certificates-for-ws-man"></a><span data-ttu-id="65766-222">Criando certificados de cliente para WS-Man</span><span class="sxs-lookup"><span data-stu-id="65766-222">Creating Client Certificates for WS-Man</span></span>

<span data-ttu-id="65766-223">Esse comando cria a entrada **ClientCertificate** que pode ser usada pelo cliente **WS-Management** .</span><span class="sxs-lookup"><span data-stu-id="65766-223">This command creates **ClientCertificate** entry that can be used by the **WS-Management** client.</span></span> <span data-ttu-id="65766-224">O novo **ClientCertificate** aparecerá no diretório **ClientCertificate** como "ClientCertificate_1234567890".</span><span class="sxs-lookup"><span data-stu-id="65766-224">The new **ClientCertificate** will show up under the **ClientCertificate** directory as "ClientCertificate_1234567890".</span></span> <span data-ttu-id="65766-225">Todos os parâmetros são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="65766-225">All of the parameters are mandatory.</span></span> <span data-ttu-id="65766-226">O **emissor** precisa ser impressão digital do certificado dos emissores.</span><span class="sxs-lookup"><span data-stu-id="65766-226">The **Issuer** needs to be thumbprint of the issuers certificate.</span></span>

```powershell
$cred = Get-Credential
New-Item -Path WSMan:\localhost\ClientCertificate `
         -Issuer 1b3fd224d66c6413fe20d21e38b304226d192dfe `
         -URI wmicimv2/* -Credential $cred
```

## <a name="deleting-certificate-stores"></a><span data-ttu-id="65766-227">Excluindo repositórios de certificados</span><span class="sxs-lookup"><span data-stu-id="65766-227">Deleting Certificate Stores</span></span>

### <a name="delete-a-certificate-store-from-a-remote-computer"></a><span data-ttu-id="65766-228">Excluir um repositório de certificados de um computador remoto</span><span class="sxs-lookup"><span data-stu-id="65766-228">Delete a certificate store from a remote computer</span></span>

<span data-ttu-id="65766-229">Esse comando usa o `Invoke-Command` cmdlet para executar um `Remove-Item` comando nos computadores S1 e S2.</span><span class="sxs-lookup"><span data-stu-id="65766-229">This command uses the `Invoke-Command` cmdlet to run a `Remove-Item` command on the S1 and S2 computers.</span></span> <span data-ttu-id="65766-230">O `Remove-Item` comando inclui o parâmetro **recurse** , que exclui os certificados no repositório antes de excluir o repositório.</span><span class="sxs-lookup"><span data-stu-id="65766-230">The `Remove-Item` command includes the **Recurse** parameter, which deletes the certificates in the store before it deletes the store.</span></span>

```powershell
Invoke-Command { Remove-Item -Path cert:\LocalMachine\TestStore -Recurse } `
  -ComputerName S1, S2
```

## <a name="dynamic-parameters"></a><span data-ttu-id="65766-231">Parâmetros dinâmicos</span><span class="sxs-lookup"><span data-stu-id="65766-231">Dynamic parameters</span></span>

<span data-ttu-id="65766-232">Parâmetros dinâmicos são parâmetros de cmdlet que são adicionados por um provedor do PowerShell e estão disponíveis somente quando o cmdlet está sendo usado na unidade habilitada para provedor.</span><span class="sxs-lookup"><span data-stu-id="65766-232">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span> <span data-ttu-id="65766-233">Esses parâmetros são válidos em todos os subdiretórios do provedor de certificado, mas entram em vigor apenas em certificados.</span><span class="sxs-lookup"><span data-stu-id="65766-233">These parameters are valid in all subdirectories of the Certificate provider, but are effective only on certificates.</span></span>

> [!NOTE]
> <span data-ttu-id="65766-234">Os parâmetros que executam a filtragem em relação à `EnhancedKeyUsageList` propriedade também retornam itens com um `EnhancedKeyUsageList` valor de propriedade vazio.</span><span class="sxs-lookup"><span data-stu-id="65766-234">Parameters that perform filtering against the `EnhancedKeyUsageList` property also return items with an empty `EnhancedKeyUsageList` property value.</span></span>
> <span data-ttu-id="65766-235">Os certificados que têm um **EnhancedKeyUsageList** vazio podem ser usados para todas as finalidades.</span><span class="sxs-lookup"><span data-stu-id="65766-235">Certificates that have an empty **EnhancedKeyUsageList** can be used for all purposes.</span></span>

### <a name="codesigningcert-systemmanagementautomationswitchparameter"></a><span data-ttu-id="65766-236">CodeSigningCert <System. Management. Automation. SwitchParameter></span><span class="sxs-lookup"><span data-stu-id="65766-236">CodeSigningCert <System.Management.Automation.SwitchParameter></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="65766-237">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="65766-237">Cmdlets supported</span></span>

- [<span data-ttu-id="65766-238">Get-Item</span><span class="sxs-lookup"><span data-stu-id="65766-238">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)

- [<span data-ttu-id="65766-239">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="65766-239">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

<span data-ttu-id="65766-240">Esse parâmetro obtém certificados que têm "assinatura de código" em seu valor de propriedade **EnhancedKeyUsageList** .</span><span class="sxs-lookup"><span data-stu-id="65766-240">This parameter gets certificates that have "Code Signing" in their **EnhancedKeyUsageList** property value.</span></span>

### <a name="deletekey-systemmanagementautomationswitchparameter"></a><span data-ttu-id="65766-241">DeleteKey <System. Management. Automation. SwitchParameter></span><span class="sxs-lookup"><span data-stu-id="65766-241">DeleteKey <System.Management.Automation.SwitchParameter></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="65766-242">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="65766-242">Cmdlets supported</span></span>

- [<span data-ttu-id="65766-243">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="65766-243">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)

<span data-ttu-id="65766-244">Esse parâmetro exclui a chave privada associada ao excluir o certificado.</span><span class="sxs-lookup"><span data-stu-id="65766-244">This parameter deletes the associated private key when it deletes the certificate.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="65766-245">Para excluir uma chave privada associada a um certificado de usuário no `Cert:\CurrentUser` repositório em um computador remoto, você deve usar credenciais delegadas.</span><span class="sxs-lookup"><span data-stu-id="65766-245">To delete a private key that is associated with a user certificate in the `Cert:\CurrentUser` store on a remote computer, you must use delegated credentials.</span></span> <span data-ttu-id="65766-246">O `Invoke-Command` cmdlet dá suporte à delegação de credenciais usando o parâmetro **CredSSP** .</span><span class="sxs-lookup"><span data-stu-id="65766-246">The `Invoke-Command` cmdlet supports credential delegation using the **CredSSP** parameter.</span></span> <span data-ttu-id="65766-247">Você deve considerar qualquer risco de segurança antes `Remove-Item` de usar with `Invoke-Command` e a delegação de credenciais.</span><span class="sxs-lookup"><span data-stu-id="65766-247">You should consider any security risks before using `Remove-Item` with `Invoke-Command` and credential delegation.</span></span>

<span data-ttu-id="65766-248">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="65766-248">This parameter was introduced in PowerShell 3.0.</span></span>

### <a name="dnsname-microsoftpowershellcommandsdnsnamerepresentation"></a><span data-ttu-id="65766-249">DnsName <Microsoft. PowerShell. Commands. DnsNameRepresentation></span><span class="sxs-lookup"><span data-stu-id="65766-249">DnsName <Microsoft.PowerShell.Commands.DnsNameRepresentation></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="65766-250">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="65766-250">Cmdlets supported</span></span>

- [<span data-ttu-id="65766-251">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="65766-251">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

<span data-ttu-id="65766-252">Esse parâmetro obtém certificados que têm o nome de domínio ou padrão de nome especificado na propriedade **DNSNameList** do certificado.</span><span class="sxs-lookup"><span data-stu-id="65766-252">This parameter gets certificates that have the specified domain name or name pattern in the **DNSNameList** property of the certificate.</span></span> <span data-ttu-id="65766-253">O valor desse parâmetro pode ser "Unicode" ou "ASCII".</span><span class="sxs-lookup"><span data-stu-id="65766-253">The value of this parameter can either be "Unicode" or "ASCII".</span></span> <span data-ttu-id="65766-254">Os valores Punycode são convertidos para Unicode.</span><span class="sxs-lookup"><span data-stu-id="65766-254">Punycode values are converted to Unicode.</span></span> <span data-ttu-id="65766-255">Caracteres curinga ( `*` ) são permitidos.</span><span class="sxs-lookup"><span data-stu-id="65766-255">Wildcard characters (`*`) are permitted.</span></span>

<span data-ttu-id="65766-256">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="65766-256">This parameter was introduced in PowerShell 3.0.</span></span>

### <a name="documentencryptioncert-systemmanagementautomationswitchparameter"></a><span data-ttu-id="65766-257">DocumentEncryptionCert <System. Management. Automation. SwitchParameter></span><span class="sxs-lookup"><span data-stu-id="65766-257">DocumentEncryptionCert <System.Management.Automation.SwitchParameter></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="65766-258">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="65766-258">Cmdlets supported</span></span>

- [<span data-ttu-id="65766-259">Get-Item</span><span class="sxs-lookup"><span data-stu-id="65766-259">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)

- [<span data-ttu-id="65766-260">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="65766-260">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

<span data-ttu-id="65766-261">Esse parâmetro obtém certificados que têm "criptografia de documentos" em seu valor de propriedade **EnhancedKeyUsageList** .</span><span class="sxs-lookup"><span data-stu-id="65766-261">This parameter gets certificates that have "Document Encryption" in their **EnhancedKeyUsageList** property value.</span></span>

### <a name="eku-systemstring"></a><span data-ttu-id="65766-262">> EKU <System. String</span><span class="sxs-lookup"><span data-stu-id="65766-262">EKU <System.String></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="65766-263">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="65766-263">Cmdlets supported</span></span>

- [<span data-ttu-id="65766-264">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="65766-264">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

<span data-ttu-id="65766-265">Esse parâmetro obtém certificados que têm o texto ou padrão de texto especificado na `EnhancedKeyUsageList` Propriedade do certificado.</span><span class="sxs-lookup"><span data-stu-id="65766-265">This parameter gets certificates that have the specified text or text pattern in the `EnhancedKeyUsageList` property of the certificate.</span></span> <span data-ttu-id="65766-266">Caracteres curinga ( `*` ) são permitidos.</span><span class="sxs-lookup"><span data-stu-id="65766-266">Wildcard characters (`*`) are permitted.</span></span> <span data-ttu-id="65766-267">A `EnhancedKeyUsageList` propriedade contém o nome amigável e os campos de OID do EKU.</span><span class="sxs-lookup"><span data-stu-id="65766-267">The `EnhancedKeyUsageList` property contains the friendly name and the OID fields of the EKU.</span></span>

<span data-ttu-id="65766-268">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="65766-268">This parameter was introduced in PowerShell 3.0.</span></span>

### <a name="expiringindays-systemint32"></a><span data-ttu-id="65766-269">ExpiringInDays <System. Int32></span><span class="sxs-lookup"><span data-stu-id="65766-269">ExpiringInDays <System.Int32></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="65766-270">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="65766-270">Cmdlets supported</span></span>

- [<span data-ttu-id="65766-271">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="65766-271">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

<span data-ttu-id="65766-272">Esse parâmetro obtém certificados que expiram no número de dias especificado ou antes dele.</span><span class="sxs-lookup"><span data-stu-id="65766-272">This parameter gets certificates that are expiring in or before the specified number of days.</span></span> <span data-ttu-id="65766-273">Um valor de 0 (zero) obtém certificados expirados.</span><span class="sxs-lookup"><span data-stu-id="65766-273">A value of 0 (zero) gets certificates that have expired.</span></span>

<span data-ttu-id="65766-274">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="65766-274">This parameter was introduced in PowerShell 3.0.</span></span>

### <a name="itemtype-string"></a><span data-ttu-id="65766-275">ItemType \<String\></span><span class="sxs-lookup"><span data-stu-id="65766-275">ItemType \<String\></span></span>

<span data-ttu-id="65766-276">Esse parâmetro permite que você especifique o tipo de item criado por `New-Item` .</span><span class="sxs-lookup"><span data-stu-id="65766-276">This parameter allows you to specify the type of item created by `New-Item`.</span></span>

<span data-ttu-id="65766-277">Em uma `Certificate` unidade, os seguintes valores são permitidos:</span><span class="sxs-lookup"><span data-stu-id="65766-277">In a `Certificate` drive, the following values are allowed:</span></span>

- <span data-ttu-id="65766-278">Provedor Certificate</span><span class="sxs-lookup"><span data-stu-id="65766-278">Certificate Provider</span></span>
- <span data-ttu-id="65766-279">Certificado</span><span class="sxs-lookup"><span data-stu-id="65766-279">Certificate</span></span>
- <span data-ttu-id="65766-280">Repositório</span><span class="sxs-lookup"><span data-stu-id="65766-280">Store</span></span>
- <span data-ttu-id="65766-281">StoreLocation</span><span class="sxs-lookup"><span data-stu-id="65766-281">StoreLocation</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="65766-282">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="65766-282">Cmdlets Supported</span></span>

- [<span data-ttu-id="65766-283">New-Item</span><span class="sxs-lookup"><span data-stu-id="65766-283">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="sslserverauthentication-systemmanagementautomationswitchparameter"></a><span data-ttu-id="65766-284">SSLServerAuthentication <System. Management. Automation. SwitchParameter></span><span class="sxs-lookup"><span data-stu-id="65766-284">SSLServerAuthentication <System.Management.Automation.SwitchParameter></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="65766-285">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="65766-285">Cmdlets supported</span></span>

- [<span data-ttu-id="65766-286">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="65766-286">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

<span data-ttu-id="65766-287">Obtém somente os certificados de servidor de hospedagem web SSL.</span><span class="sxs-lookup"><span data-stu-id="65766-287">Gets only server certificates for SSL web hosting.</span></span> <span data-ttu-id="65766-288">Esse parâmetro obtém certificados que têm "autenticação de servidor" em seu `EnhancedKeyUsageList` valor de propriedade.</span><span class="sxs-lookup"><span data-stu-id="65766-288">This parameter gets certificates that have "Server Authentication" in their `EnhancedKeyUsageList` property value.</span></span>

<span data-ttu-id="65766-289">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="65766-289">This parameter was introduced in PowerShell 3.0.</span></span>

## <a name="script-properties"></a><span data-ttu-id="65766-290">Propriedades do script</span><span class="sxs-lookup"><span data-stu-id="65766-290">Script properties</span></span>

<span data-ttu-id="65766-291">Novas propriedades de script foram adicionadas ao objeto **X509Certificate2** que representa os certificados para facilitar a pesquisa e o gerenciamento dos certificados.</span><span class="sxs-lookup"><span data-stu-id="65766-291">New script properties have been added to the **x509Certificate2** object that represents the certificates to make it easy to search and manage the certificates.</span></span>

- <span data-ttu-id="65766-292">`DnsNameList`: Para popular a `DnsNameList` propriedade, o provedor de certificado copia o conteúdo da entrada DnsName na extensão SubjectAlternativeName (San).</span><span class="sxs-lookup"><span data-stu-id="65766-292">`DnsNameList`: To populate the `DnsNameList` property, the Certificate provider copies the content from the DNSName entry in the SubjectAlternativeName (SAN) extension.</span></span> <span data-ttu-id="65766-293">Se a extensão de SAN estiver vazia, a propriedade será preenchida com o conteúdo do campo Assunto do certificado.</span><span class="sxs-lookup"><span data-stu-id="65766-293">If the SAN extension is empty, the property is populated with content from the Subject field of the certificate.</span></span>

- <span data-ttu-id="65766-294">`EnhancedKeyUsageList`: Para popular a `EnhancedKeyUsageList` propriedade, o provedor de certificado copia as propriedades de OID do campo EnhancedKeyUsage (EKU) no certificado e cria um nome amigável para ele.</span><span class="sxs-lookup"><span data-stu-id="65766-294">`EnhancedKeyUsageList`: To populate the `EnhancedKeyUsageList` property, the Certificate provider copies the OID properties of the EnhancedKeyUsage (EKU) field in the certificate and creates a friendly name for it.</span></span>

- <span data-ttu-id="65766-295">`SendAsTrustedIssuer`: Para popular a `SendAsTrustedIssuer` propriedade, o provedor de certificado copia a `SendAsTrustedIssuer` Propriedade do certificado.</span><span class="sxs-lookup"><span data-stu-id="65766-295">`SendAsTrustedIssuer`: To populate the `SendAsTrustedIssuer` property, the Certificate provider copies the `SendAsTrustedIssuer` property from the certificate.</span></span>  <span data-ttu-id="65766-296">Para obter mais informações, consulte [Gerenciamento de emissores confiáveis para autenticação de cliente](/windows-server/security/tls/what-s-new-in-tls-ssl-schannel-ssp-overview#BKMK_TrustedIssuers).</span><span class="sxs-lookup"><span data-stu-id="65766-296">For more information see [Management of trusted issuers for client authentication](/windows-server/security/tls/what-s-new-in-tls-ssl-schannel-ssp-overview#BKMK_TrustedIssuers).</span></span>

<span data-ttu-id="65766-297">Esses novos recursos permitem pesquisar certificados com base em seus nomes DNS e datas de vencimento e distinguir os certificados de autenticação de cliente e servidor, o valor de suas propriedades de Uso Avançado de Chave (EKU).</span><span class="sxs-lookup"><span data-stu-id="65766-297">These new features let you search for certificates based on their DNS names and expiration dates, and distinguish client and server authentication certificates by the value of their Enhanced Key Usage (EKU) properties.</span></span>

## <a name="using-the-pipeline"></a><span data-ttu-id="65766-298">Usando o pipeline</span><span class="sxs-lookup"><span data-stu-id="65766-298">Using the pipeline</span></span>

<span data-ttu-id="65766-299">Os cmdlets do provedor aceitam a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="65766-299">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="65766-300">Você pode usar o pipeline para simplificar a tarefa enviando dados do provedor de um cmdlet para outro cmdlet do provedor.</span><span class="sxs-lookup"><span data-stu-id="65766-300">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="65766-301">Para ler mais sobre como usar o pipeline com cmdlets de provedor, consulte as referências de cmdlet fornecidas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="65766-301">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="65766-302">Obtendo ajuda</span><span class="sxs-lookup"><span data-stu-id="65766-302">Getting help</span></span>

<span data-ttu-id="65766-303">A partir do PowerShell 3,0, você pode obter tópicos de ajuda personalizados para cmdlets de provedor que explicam como esses cmdlets se comportam em uma unidade de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="65766-303">Beginning in PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="65766-304">Para obter os tópicos de ajuda personalizados para a unidade do sistema de arquivos, execute um comando [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) em uma unidade do sistema de arquivos ou use o `-Path` parâmetro de `Get-Help` para especificar uma unidade do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="65766-304">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of `Get-Help` to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path cert:
```

## <a name="see-also"></a><span data-ttu-id="65766-305">Confira também</span><span class="sxs-lookup"><span data-stu-id="65766-305">See also</span></span>

[<span data-ttu-id="65766-306">about_Providers</span><span class="sxs-lookup"><span data-stu-id="65766-306">about_Providers</span></span>](../../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="65766-307">about_Signing</span><span class="sxs-lookup"><span data-stu-id="65766-307">about_Signing</span></span>](../../Microsoft.PowerShell.Core/About/about_Signing.md)

[<span data-ttu-id="65766-308">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="65766-308">Get-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Get-AuthenticodeSignature)

[<span data-ttu-id="65766-309">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="65766-309">Set-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

[<span data-ttu-id="65766-310">Get-PfxCertificate</span><span class="sxs-lookup"><span data-stu-id="65766-310">Get-PfxCertificate</span></span>](xref:Microsoft.PowerShell.Security.Get-PfxCertificate)
