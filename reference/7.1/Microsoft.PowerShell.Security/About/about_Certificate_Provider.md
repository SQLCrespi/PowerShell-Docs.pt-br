---
description: Certificado
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/about/about_certificate_provider?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Provedor Certificate
ms.openlocfilehash: 6d78c587f79bb09c66700fb71519fe0f32318386
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196323"
---
# <a name="certificate-provider"></a><span data-ttu-id="fea14-104">Provedor Certificate</span><span class="sxs-lookup"><span data-stu-id="fea14-104">Certificate Provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="fea14-105">Nome do provedor</span><span class="sxs-lookup"><span data-stu-id="fea14-105">Provider name</span></span>

<span data-ttu-id="fea14-106">Certificado</span><span class="sxs-lookup"><span data-stu-id="fea14-106">Certificate</span></span>

## <a name="drives"></a><span data-ttu-id="fea14-107">Unidades</span><span class="sxs-lookup"><span data-stu-id="fea14-107">Drives</span></span>

`Cert:`

## <a name="capabilities"></a><span data-ttu-id="fea14-108">Funcionalidades</span><span class="sxs-lookup"><span data-stu-id="fea14-108">Capabilities</span></span>

<span data-ttu-id="fea14-109">**ShouldProcess**</span><span class="sxs-lookup"><span data-stu-id="fea14-109">**ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="fea14-110">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="fea14-110">Short description</span></span>

<span data-ttu-id="fea14-111">Fornece acesso a repositórios de certificados X. 509 e certificados no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fea14-111">Provides access to X.509 certificate stores and certificates in PowerShell.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="fea14-112">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="fea14-112">Detailed description</span></span>

<span data-ttu-id="fea14-113">O provedor de **certificados** do PowerShell permite que você obtenha, adicione, altere, apague e exclua certificados e repositórios de certificados no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fea14-113">The PowerShell **Certificate** provider lets you get, add, change, clear, and delete certificates and certificate stores in PowerShell.</span></span>

<span data-ttu-id="fea14-114">A unidade de **certificado** é um namespace hierárquico que contém os repositórios de certificados e certificados em seu computador.</span><span class="sxs-lookup"><span data-stu-id="fea14-114">The **Certificate** drive is a hierarchical namespace containing the certificate stores and certificates on your computer.</span></span>

<span data-ttu-id="fea14-115">O provedor de **certificado** dá suporte aos seguintes cmdlets, que são abordados neste artigo.</span><span class="sxs-lookup"><span data-stu-id="fea14-115">The **Certificate** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="fea14-116">Get-Location</span><span class="sxs-lookup"><span data-stu-id="fea14-116">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="fea14-117">Set-Location</span><span class="sxs-lookup"><span data-stu-id="fea14-117">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="fea14-118">Get-Item</span><span class="sxs-lookup"><span data-stu-id="fea14-118">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="fea14-119">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="fea14-119">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [<span data-ttu-id="fea14-120">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="fea14-120">Invoke-Item</span></span>](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [<span data-ttu-id="fea14-121">Move-Item</span><span class="sxs-lookup"><span data-stu-id="fea14-121">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="fea14-122">New-Item</span><span class="sxs-lookup"><span data-stu-id="fea14-122">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="fea14-123">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="fea14-123">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="fea14-124">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="fea14-124">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="fea14-125">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="fea14-125">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [<span data-ttu-id="fea14-126">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="fea14-126">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [<span data-ttu-id="fea14-127">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="fea14-127">Get-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Get-AuthenticodeSignature)
- [<span data-ttu-id="fea14-128">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="fea14-128">Set-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="fea14-129">Tipos expostos por este provedor</span><span class="sxs-lookup"><span data-stu-id="fea14-129">Types exposed by this provider</span></span>

<span data-ttu-id="fea14-130">A unidade do certificado expõe os tipos a seguir.</span><span class="sxs-lookup"><span data-stu-id="fea14-130">The Certificate drive exposes the following types.</span></span>

- <span data-ttu-id="fea14-131">Locais de armazenamento (Microsoft. PowerShell. Commands. X509StoreLocation), que são contêineres de alto nível que agrupam os certificados para o usuário atual e para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="fea14-131">Store locations (Microsoft.PowerShell.Commands.X509StoreLocation), which are high-level containers that group the certificates for the current user and for all users.</span></span> <span data-ttu-id="fea14-132">Cada sistema tem um local de armazenamento CurrentUser e LocalMachine (todos os usuários).</span><span class="sxs-lookup"><span data-stu-id="fea14-132">Each system has a CurrentUser and LocalMachine (all users) store location.</span></span>

- <span data-ttu-id="fea14-133">Os certificados armazena (System. Security. Cryptography. X509Certificates. X509Store), que são repositórios físicos nos quais os certificados são salvos e gerenciados.</span><span class="sxs-lookup"><span data-stu-id="fea14-133">Certificates stores (System.Security.Cryptography.X509Certificates.X509Store), which are physical stores in which certificates are saved and managed.</span></span>

- <span data-ttu-id="fea14-134">Os certificados x. 509 **System. Security. Cryptography. X509Certificates. X509Certificate2** , cada um representando um certificado X. 509 no computador.</span><span class="sxs-lookup"><span data-stu-id="fea14-134">X.509 **System.Security.Cryptography.X509Certificates.X509Certificate2** certificates, each of which represent an X.509 certificate on the computer.</span></span>
  <span data-ttu-id="fea14-135">Certificados são identificados por suas impressões digitais.</span><span class="sxs-lookup"><span data-stu-id="fea14-135">Certificates are identified by their thumbprints.</span></span>

## <a name="navigating-the-certificate-drive"></a><span data-ttu-id="fea14-136">Navegando pela unidade de certificado</span><span class="sxs-lookup"><span data-stu-id="fea14-136">Navigating the Certificate drive</span></span>

<span data-ttu-id="fea14-137">O provedor de **certificado** expõe o namespace do certificado como a `Cert:` unidade no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fea14-137">The **Certificate** provider exposes the certificate namespace as the `Cert:` drive in PowerShell.</span></span> <span data-ttu-id="fea14-138">Esse comando usa o `Set-Location` comando para alterar o local atual para o repositório de certificados raiz no local de armazenamento LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="fea14-138">This command uses the `Set-Location` command to change the current location to the Root certificate store in the LocalMachine store location.</span></span> <span data-ttu-id="fea14-139">Use uma barra invertida ( \\ ) ou uma barra (/) para indicar um nível da `Cert:` unidade.</span><span class="sxs-lookup"><span data-stu-id="fea14-139">Use a backslash (\\) or a forward slash (/) to indicate a level of the `Cert:` drive.</span></span>

```powershell
Set-Location Cert:
```

<span data-ttu-id="fea14-140">Você também pode trabalhar com o provedor de certificado de qualquer outra unidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fea14-140">You can also work with the certificate provider from any other PowerShell drive.</span></span> <span data-ttu-id="fea14-141">Para fazer referência a um alias de outro local, use o `Cert:` nome da unidade no caminho.</span><span class="sxs-lookup"><span data-stu-id="fea14-141">To reference an alias from another location, use the `Cert:` drive name in the path.</span></span>

```powershell
PS Cert:\> Set-Location -Path LocalMachine\Root
```

<span data-ttu-id="fea14-142">Para retornar a uma unidade de sistema de arquivos, digite o nome da unidade.</span><span class="sxs-lookup"><span data-stu-id="fea14-142">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="fea14-143">Por exemplo, digite:</span><span class="sxs-lookup"><span data-stu-id="fea14-143">For example, type:</span></span>

```powershell
Set-Location C:
```

> [!NOTE]
> <span data-ttu-id="fea14-144">O PowerShell usa aliases para permitir a você uma maneira familiar de trabalhar com caminhos de provedor.</span><span class="sxs-lookup"><span data-stu-id="fea14-144">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="fea14-145">Comandos como `dir` e `ls` agora são aliases para [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` é um alias para [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span><span class="sxs-lookup"><span data-stu-id="fea14-145">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span>
> <span data-ttu-id="fea14-146">e `pwd` é um alias para [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span><span class="sxs-lookup"><span data-stu-id="fea14-146">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

## <a name="displaying-the-contents-of-the-cert-drive"></a><span data-ttu-id="fea14-147">Exibindo o conteúdo da unidade CERT:</span><span class="sxs-lookup"><span data-stu-id="fea14-147">Displaying the Contents of the Cert: drive</span></span>

<span data-ttu-id="fea14-148">Esse comando usa o `Get-ChildItem` cmdlet para exibir os repositórios de certificados no local do repositório de certificados CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="fea14-148">This command uses the `Get-ChildItem` cmdlet to display the certificate stores in the CurrentUser certificate store location.</span></span>

<span data-ttu-id="fea14-149">Se você não estiver na `Cert:` unidade, use um caminho absoluto.</span><span class="sxs-lookup"><span data-stu-id="fea14-149">If you are not in the `Cert:` drive, use an absolute path.</span></span>

```powershell
PS Cert:\CurrentUser\> Get-ChildItem
```

### <a name="displaying-certificate-properties-within-the-cert-drive"></a><span data-ttu-id="fea14-150">Exibindo Propriedades de certificado dentro da unidade CERT:</span><span class="sxs-lookup"><span data-stu-id="fea14-150">Displaying certificate properties within the Cert: drive</span></span>

<span data-ttu-id="fea14-151">Este exemplo obtém um certificado com `Get-Item` e o armazena em uma variável.</span><span class="sxs-lookup"><span data-stu-id="fea14-151">This example gets a certificate with `Get-Item` and stores it in a variable.</span></span>
<span data-ttu-id="fea14-152">O exemplo mostra as novas propriedades de script de certificado ( **DnsNameList** , **EnhancedKeyUsageList** , **SendAsTrustedIssuer** ) usando `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="fea14-152">The example shows the new certificate script properties ( **DnsNameList** , **EnhancedKeyUsageList** , **SendAsTrustedIssuer** ) using `Select-Object`.</span></span>

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

### <a name="find-all-codesigning-certificates"></a><span data-ttu-id="fea14-153">Localizar todos os certificados de codesignação</span><span class="sxs-lookup"><span data-stu-id="fea14-153">Find all CodeSigning certificates</span></span>

<span data-ttu-id="fea14-154">Esse comando usa os parâmetros **CodeSigningCert** e **recurse** do `Get-ChildItem` cmdlet para obter todos os certificados no computador que têm autoridade de assinatura de código.</span><span class="sxs-lookup"><span data-stu-id="fea14-154">This command uses the **CodeSigningCert** and **Recurse** parameters of the `Get-ChildItem` cmdlet to get all of the certificates on the computer that have code-signing authority.</span></span>

```powershell
Get-ChildItem -Path cert: -CodeSigningCert -Recurse
```

### <a name="find-expired-certificates"></a><span data-ttu-id="fea14-155">Localizar certificados expirados</span><span class="sxs-lookup"><span data-stu-id="fea14-155">Find expired certificates</span></span>

<span data-ttu-id="fea14-156">Esse comando usa o parâmetro **ExpiringInDays** do `Get-ChildItem` cmdlet para obter certificados que irão expirar nos próximos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="fea14-156">This command uses the **ExpiringInDays** parameter of the `Get-ChildItem` cmdlet to get certificates that will expire within the next 30 days.</span></span>

```powershell
Get-ChildItem -Path cert:\LocalMachine\WebHosting -ExpiringInDays 30
```

### <a name="find-server-ssl-certificates"></a><span data-ttu-id="fea14-157">Localizar certificados SSL do servidor</span><span class="sxs-lookup"><span data-stu-id="fea14-157">Find Server SSL Certificates</span></span>

<span data-ttu-id="fea14-158">Esse comando usa o parâmetro **SSLServerAuthentication** do `Get-ChildItem` cmdlet para obter todos os certificados SSL do servidor nos repositórios My e webhosting.</span><span class="sxs-lookup"><span data-stu-id="fea14-158">This command uses the **SSLServerAuthentication** parameter of the `Get-ChildItem` cmdlet to get all Server SSL Certificates in the My and WebHosting stores.</span></span>

```powershell
Get-ChildItem -Path cert:\LocalMachine\My, cert:\LocalMachine\WebHosting `
  -SSLServerAuthentication
```

### <a name="find-expired-certificates-on-remote-computers"></a><span data-ttu-id="fea14-159">Localizar certificados expirados em computadores remotos</span><span class="sxs-lookup"><span data-stu-id="fea14-159">Find expired certificates on remote computers</span></span>

<span data-ttu-id="fea14-160">Esse comando usa o `Invoke-Command` cmdlet para executar um `Get-ChildItem` comando nos computadores Srv01 e Srv02.</span><span class="sxs-lookup"><span data-stu-id="fea14-160">This command uses the `Invoke-Command` cmdlet to run a `Get-ChildItem` command on the Srv01 and Srv02 computers.</span></span> <span data-ttu-id="fea14-161">Um valor de zero (0) no parâmetro **ExpiringInDays** obtém certificados nos computadores Srv01 e Srv02 que expiraram.</span><span class="sxs-lookup"><span data-stu-id="fea14-161">A value of zero (0) in the **ExpiringInDays** parameter gets certificates on the Srv01 and Srv02 computers that have expired.</span></span>

```powershell
Invoke-Command -ComputerName Srv01, Srv02 {Get-ChildItem -Path cert:\* `
  -Recurse -ExpiringInDays 0}
```

### <a name="combining-filters-to-find-a-specific-set-of-certificates"></a><span data-ttu-id="fea14-162">Combinando filtros para localizar um conjunto específico de certificados</span><span class="sxs-lookup"><span data-stu-id="fea14-162">Combining filters to find a specific set of certificates</span></span>

<span data-ttu-id="fea14-163">Esse comando obtém todos os certificados no local do repositório LocalMachine que têm os seguintes atributos:</span><span class="sxs-lookup"><span data-stu-id="fea14-163">This command gets all certificates in the LocalMachine store location that have the following attributes:</span></span>

- <span data-ttu-id="fea14-164">"fabrikam" em seu nome DNS</span><span class="sxs-lookup"><span data-stu-id="fea14-164">"fabrikam" in their DNS name</span></span>
- <span data-ttu-id="fea14-165">"Autenticação de cliente" em seu EKU</span><span class="sxs-lookup"><span data-stu-id="fea14-165">"Client Authentication" in their EKU</span></span>
- <span data-ttu-id="fea14-166">um valor de `$true` para a propriedade **SendAsTrustedIssuer**</span><span class="sxs-lookup"><span data-stu-id="fea14-166">a value of `$true` for the **SendAsTrustedIssuer** property</span></span>
- <span data-ttu-id="fea14-167">Não expire nos próximos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="fea14-167">do not expire within the next 30 days.</span></span>

<span data-ttu-id="fea14-168">A propriedade não **After** armazena a data de expiração do certificado.</span><span class="sxs-lookup"><span data-stu-id="fea14-168">The **NotAfter** property stores the certificate expiration date.</span></span>

```powershell
[DateTime] $ValidThrough = (Get-Date) + (New-TimeSpan -Days 30)
Get-ChildItem -Path cert:\* -Recurse -DNSName "*fabrikam*" `
  -EKU "*Client Authentication*" | Where-Object {
                                     $_.SendAsTrustedIssuer -and `
                                     $_.NotAfter -gt $ValidThrough
                                   }
```

## <a name="opening-the-certificates-mmc-snap-in"></a><span data-ttu-id="fea14-169">Abrir os certificados Snap-in MMC</span><span class="sxs-lookup"><span data-stu-id="fea14-169">Opening the Certificates MMC Snap-in</span></span>

<span data-ttu-id="fea14-170">O `Invoke-Item` cmdlet usará o aplicativo padrão para abrir um caminho que você especificar.</span><span class="sxs-lookup"><span data-stu-id="fea14-170">The `Invoke-Item` cmdlet will use the default application to open a path you specify.</span></span> <span data-ttu-id="fea14-171">Para certificados, o aplicativo padrão é o snap-in do MMC de certificados.</span><span class="sxs-lookup"><span data-stu-id="fea14-171">For certificates, the default application is the Certificates MMC snap-in.</span></span>

<span data-ttu-id="fea14-172">Esse comando abre o snap-in de certificados do MMC para gerenciar o certificado especificado.</span><span class="sxs-lookup"><span data-stu-id="fea14-172">This command opens the Certificates MMC snap-in to manage the specified certificate.</span></span>

```powershell
Invoke-Item cert:\CurrentUser\my\6B8223358119BB08840DEE50FD8AF9EA776CE66B
```

## <a name="copying-certificates"></a><span data-ttu-id="fea14-173">Copiando certificados</span><span class="sxs-lookup"><span data-stu-id="fea14-173">Copying Certificates</span></span>

<span data-ttu-id="fea14-174">O provedor de **certificados** não dá suporte à cópia de certificados.</span><span class="sxs-lookup"><span data-stu-id="fea14-174">Copying certificates is not supported by the **Certificate** provider.</span></span> <span data-ttu-id="fea14-175">Ao tentar copiar um certificado, você verá esse erro.</span><span class="sxs-lookup"><span data-stu-id="fea14-175">When you attempt to copy a certificate, you see this error.</span></span>

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

## <a name="moving-certificates"></a><span data-ttu-id="fea14-176">Movendo certificados</span><span class="sxs-lookup"><span data-stu-id="fea14-176">Moving Certificates</span></span>

### <a name="move-all-ssl-server-authentication-certs-to-the-webhosting-store"></a><span data-ttu-id="fea14-177">Mover todos os certificados de autenticação de servidor SSL para o repositório webhosting</span><span class="sxs-lookup"><span data-stu-id="fea14-177">Move all SSL Server authentication certs to the WebHosting store</span></span>

<span data-ttu-id="fea14-178">Esse comando usa o `Move-Item` cmdlet para mover um certificado do repositório My para o repositório webhosting.</span><span class="sxs-lookup"><span data-stu-id="fea14-178">This command uses the `Move-Item` cmdlet to move a certificate from the My store to the WebHosting store.</span></span>

<span data-ttu-id="fea14-179">`Move-Item` Não moverá os repositórios de certificados e ele não moverá certificados para um local de repositório diferente, como mover um certificado de LocalMachine para CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="fea14-179">`Move-Item` will not move certificate stores and it will not move certificates to a different store location, such as moving a certificate from LocalMachine to CurrentUser.</span></span> <span data-ttu-id="fea14-180">O `Move-Item` cmdlet Move certificados, mas não move chaves privadas.</span><span class="sxs-lookup"><span data-stu-id="fea14-180">The `Move-Item` cmdlet moves certificates, but it does not move private keys.</span></span>

<span data-ttu-id="fea14-181">Esse comando usa o parâmetro **SSLServerAuthentication** do `Get-ChildItem` cmdlet para obter certificados de autenticação de servidor SSL no meu repositório de certificados.</span><span class="sxs-lookup"><span data-stu-id="fea14-181">This command uses the **SSLServerAuthentication** parameter of the `Get-ChildItem` cmdlet to get SSL server authentication certificates in the MY certificate store.</span></span>

<span data-ttu-id="fea14-182">Os certificados retornados são canalizados para o `Move-Item` cmdlet, que move os certificados para o repositório webhosting.</span><span class="sxs-lookup"><span data-stu-id="fea14-182">The returned certificates are piped to the `Move-Item` cmdlet, which moves the certificates to the WebHosting store.</span></span>

```powershell
Get-ChildItem cert:\LocalMachine\My -SSLServerAuthentication | Move-Item `
  -Destination cert:\LocalMachine\WebHosting
```

## <a name="deleting-certificates-and-private-keys"></a><span data-ttu-id="fea14-183">Excluindo certificados e chaves privadas</span><span class="sxs-lookup"><span data-stu-id="fea14-183">Deleting Certificates and Private Keys</span></span>

<span data-ttu-id="fea14-184">O `Remove-Item` cmdlet removerá os certificados que você especificar.</span><span class="sxs-lookup"><span data-stu-id="fea14-184">The `Remove-Item` cmdlet will remove certificates that you specify.</span></span> <span data-ttu-id="fea14-185">O `-DeleteKey` parâmetro dinâmico exclui a chave privada.</span><span class="sxs-lookup"><span data-stu-id="fea14-185">The `-DeleteKey` dynamic parameter deletes the private key.</span></span>

### <a name="delete-a-certificate-from-the-ca-store"></a><span data-ttu-id="fea14-186">Excluir um certificado do repositório de AC</span><span class="sxs-lookup"><span data-stu-id="fea14-186">Delete a Certificate from the CA store</span></span>

<span data-ttu-id="fea14-187">Esse comando exclui um certificado do repositório de certificados de AC, mas deixa a chave privada associada intacta.</span><span class="sxs-lookup"><span data-stu-id="fea14-187">This command deletes a certificate from the CA certificate store, but leaves the associated private key intact.</span></span>

<span data-ttu-id="fea14-188">Na `Cert:` unidade, o `Remove-Item` cmdlet dá suporte apenas aos parâmetros **DeleteKey** , **Path** , **WhatIf** e **Confirm** .</span><span class="sxs-lookup"><span data-stu-id="fea14-188">In the `Cert:` drive, the `Remove-Item` cmdlet supports only the **DeleteKey** , **Path** , **WhatIf** , and **Confirm** parameters.</span></span> <span data-ttu-id="fea14-189">Todos os outros parâmetros são ignorados.</span><span class="sxs-lookup"><span data-stu-id="fea14-189">All other parameters are ignored.</span></span>

```powershell
Remove-Item cert:\LocalMachine\CA\5DDC44652E62BF9AA1116DC41DE44AB47C87BDD0
```

### <a name="delete-a-certificate-using-a-wildcards-in-the-dns-name"></a><span data-ttu-id="fea14-190">Excluir um certificado usando curingas no nome DNS</span><span class="sxs-lookup"><span data-stu-id="fea14-190">Delete a Certificate using a wildcards in the DNS name</span></span>

<span data-ttu-id="fea14-191">Esse comando exclui todos os certificados que têm um nome DNS que contém "Fabrikam".</span><span class="sxs-lookup"><span data-stu-id="fea14-191">This command deletes all certificates that have a DNS name that contains "Fabrikam".</span></span> <span data-ttu-id="fea14-192">Ele usa o parâmetro **DnsName** do `Get-ChildItem` cmdlet para obter os certificados e o `Remove-Item` cmdlet para excluí-los.</span><span class="sxs-lookup"><span data-stu-id="fea14-192">It uses the **DNSName** parameter of the `Get-ChildItem` cmdlet to get the certificates and the `Remove-Item` cmdlet to delete them.</span></span>

```powershell
Get-ChildItem -Path cert:\LocalMachine -DnsName *Fabrikam* | Remove-Item
```

### <a name="delete-private-keys-from-a-remote-computer"></a><span data-ttu-id="fea14-193">Excluir chaves privadas de um computador remoto</span><span class="sxs-lookup"><span data-stu-id="fea14-193">Delete private keys from a remote computer</span></span>

<span data-ttu-id="fea14-194">Esta série de comandos permite a delegação e, em seguida, a exclusão do certificado e da chave privada associada em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="fea14-194">This series of commands enables delegation and then deletes the certificate and associated private key on a remote computer.</span></span> <span data-ttu-id="fea14-195">Para excluir uma chave privada em um computador remoto, você deve usar credenciais delegadas.</span><span class="sxs-lookup"><span data-stu-id="fea14-195">To delete a private key on a remote computer, you must use delegated credentials.</span></span>

<span data-ttu-id="fea14-196">Use o `Enable-WSManCredSSP` cmdlet para habilitar a autenticação de CredSSP (provedor de serviços de segurança de credencial) em um cliente no computador remoto S1.</span><span class="sxs-lookup"><span data-stu-id="fea14-196">Use the `Enable-WSManCredSSP` cmdlet to enable Credential Security Service Provider (CredSSP) authentication on a client on the S1 remote computer.</span></span>
<span data-ttu-id="fea14-197">O CredSSP permite a autenticação delegada.</span><span class="sxs-lookup"><span data-stu-id="fea14-197">CredSSP permits delegated authentication.</span></span>

```powershell
Enable-WSManCredSSP -Role Client -DelegateComputer S1
```

<span data-ttu-id="fea14-198">Use o `Connect-WSMan` cmdlet para conectar o computador S1 ao serviço WinRM no computador local.</span><span class="sxs-lookup"><span data-stu-id="fea14-198">Use the `Connect-WSMan` cmdlet to connect the S1 computer to the WinRM service on the local computer.</span></span> <span data-ttu-id="fea14-199">Quando esse comando for concluído, o computador S1 aparecerá na `WSMan:` unidade local no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fea14-199">When this command completes, the S1 computer appears in the local `WSMan:` drive in PowerShell.</span></span>

```powershell
Connect-WSMan -ComputerName S1 -Credential Domain01\Admin01
```

<span data-ttu-id="fea14-200">Agora, você pode usar o cmdlet Set-Item na unidade WSMan: para habilitar o atributo CredSSP para o serviço WinRM.</span><span class="sxs-lookup"><span data-stu-id="fea14-200">Now, you can use the Set-Item cmdlet in the WSMan: drive to enable the CredSSP attribute for the WinRM service.</span></span>

```powershell
Set-Item -Path WSMan:\S1\Service\Auth\CredSSP -Value $true
```

<span data-ttu-id="fea14-201">Inicie uma sessão remota no computador S1 usando o `New-PSSession` cmdlet e especifique a autenticação CredSSP.</span><span class="sxs-lookup"><span data-stu-id="fea14-201">Start a remote session on the s1 computer using the `New-PSSession` cmdlet, and specify CredSSP authentication.</span></span> <span data-ttu-id="fea14-202">Salva a sessão na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="fea14-202">Saves the session in the `$s` variable.</span></span>

```powershell
$s  = New-PSSession S1 -Authentication CredSSP -Credential Domain01\Admin01
```

<span data-ttu-id="fea14-203">Por fim, use o `Invoke-Command` cmdlet para executar um `Remove-Item` comando na sessão na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="fea14-203">Finally, use the `Invoke-Command` cmdlet to run a `Remove-Item` command in the session in the `$s` variable.</span></span> <span data-ttu-id="fea14-204">O `Remove-Item` comando usa o parâmetro **DeleteKey** para remover a chave privada junto com o certificado especificado.</span><span class="sxs-lookup"><span data-stu-id="fea14-204">The `Remove-Item` command uses the **DeleteKey** parameter to remove the private key along with the specified certificate.</span></span>

```powershell
Invoke-Command -Session $s { Remove-Item `
  -Path cert:\LocalMachine\My\D2D38EBA60CAA1C12055A2E1C83B15AD450110C2 `
  -DeleteKey
  }
```

### <a name="delete-expired-certificates"></a><span data-ttu-id="fea14-205">Excluir certificados expirados</span><span class="sxs-lookup"><span data-stu-id="fea14-205">Delete expired Certificates</span></span>

<span data-ttu-id="fea14-206">Esse comando usa o parâmetro **ExpiringInDays** do `Get-ChildItem` cmdlet com um valor de 0 para obter certificados no repositório webhosting que expirou.</span><span class="sxs-lookup"><span data-stu-id="fea14-206">This command uses the **ExpiringInDays** parameter of the `Get-ChildItem` cmdlet with a value of 0 to get certificates in the WebHosting store that have expired.</span></span>

<span data-ttu-id="fea14-207">A variável que contém os certificados retornados é canalizada para o `Remove-Item` cmdlet, que os exclui.</span><span class="sxs-lookup"><span data-stu-id="fea14-207">The variable containing the returned certificates is piped to the `Remove-Item` cmdlet, which deletes them.</span></span> <span data-ttu-id="fea14-208">O comando usa o parâmetro **DeleteKey** para excluir a chave privada junto com o certificado.</span><span class="sxs-lookup"><span data-stu-id="fea14-208">The command uses the **DeleteKey** parameter to delete the private key along with the certificate.</span></span>

```powershell
$expired = Get-ChildItem cert:\LocalMachine\WebHosting -ExpiringInDays 0
$expired | Remove-Item -DeleteKey
```

## <a name="creating-certificates"></a><span data-ttu-id="fea14-209">Criando certificados</span><span class="sxs-lookup"><span data-stu-id="fea14-209">Creating Certificates</span></span>

<span data-ttu-id="fea14-210">O `New-Item` cmdlet não cria novos certificados no provedor de **certificados** .</span><span class="sxs-lookup"><span data-stu-id="fea14-210">The `New-Item` cmdlet does not create new certificates in the **Certificate** provider.</span></span> <span data-ttu-id="fea14-211">Use o cmdlet [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate) para criar um certificado para fins de teste.</span><span class="sxs-lookup"><span data-stu-id="fea14-211">Use the [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet to create a certificate for testing purposes.</span></span>

## <a name="creating-certificate-stores"></a><span data-ttu-id="fea14-212">Criação de repositórios de certificados</span><span class="sxs-lookup"><span data-stu-id="fea14-212">Creating Certificate Stores</span></span>

<span data-ttu-id="fea14-213">Na unidade CERT:, o `New-Item` cmdlet cria repositórios de certificados no local de armazenamento LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="fea14-213">In the Cert: drive, the `New-Item` cmdlet creates certificate stores in the LocalMachine store location.</span></span> <span data-ttu-id="fea14-214">Ele dá suporte aos parâmetros **Name** , **Path** , **WhatIf** e **Confirm** .</span><span class="sxs-lookup"><span data-stu-id="fea14-214">It supports the **Name** , **Path** , **WhatIf** , and **Confirm** parameters.</span></span> <span data-ttu-id="fea14-215">Todos os outros parâmetros são ignorados.</span><span class="sxs-lookup"><span data-stu-id="fea14-215">All other parameters are ignored.</span></span> <span data-ttu-id="fea14-216">O comando retorna um **System. Security. Cryptography. X509Certificates. X509Store** que representa o novo repositório de certificados.</span><span class="sxs-lookup"><span data-stu-id="fea14-216">The command returns a **System.Security.Cryptography.X509Certificates.X509Store** that represents the new certificate store.</span></span>

<span data-ttu-id="fea14-217">Este comando cria um novo repositório de certificados denominado "CustomStore" no local de armazenamento LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="fea14-217">This command creates a new certificate store named "CustomStore" in the LocalMachine store location.</span></span>

```powershell
New-Item -Path cert:\LocalMachine\CustomStore
```

### <a name="create-a-new-certificate-store-on-a-remote-computer"></a><span data-ttu-id="fea14-218">Criar um novo repositório de certificados em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="fea14-218">Create a new certificate store on a remote computer</span></span>

<span data-ttu-id="fea14-219">Este comando cria um novo repositório de certificados denominado "HostingStore" no local de repositório LocalMachine no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="fea14-219">This command creates a new certificate store named "HostingStore" in the LocalMachine store location on the Server01 computer.</span></span>

<span data-ttu-id="fea14-220">O comando usa o `Invoke-Command` cmdlet para executar um `New-Item` comando no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="fea14-220">The command uses the `Invoke-Command` cmdlet to run a `New-Item` command on the Server01 computer.</span></span> <span data-ttu-id="fea14-221">O comando retorna um **System. Security. Cryptography. X509Certificates. X509Store** que representa o novo repositório de certificados.</span><span class="sxs-lookup"><span data-stu-id="fea14-221">The command returns a **System.Security.Cryptography.X509Certificates.X509Store** that represents the new certificate store.</span></span>

```powershell
Invoke-Command { New-Item -Path cert:\LocalMachine\CustomStore } `
  -ComputerName Server01
```

## <a name="creating-client-certificates-for-ws-man"></a><span data-ttu-id="fea14-222">Criando certificados de cliente para WS-Man</span><span class="sxs-lookup"><span data-stu-id="fea14-222">Creating Client Certificates for WS-Man</span></span>

<span data-ttu-id="fea14-223">Esse comando cria a entrada **ClientCertificate** que pode ser usada pelo cliente **WS-Management** .</span><span class="sxs-lookup"><span data-stu-id="fea14-223">This command creates **ClientCertificate** entry that can be used by the **WS-Management** client.</span></span> <span data-ttu-id="fea14-224">O novo **ClientCertificate** aparecerá no diretório **ClientCertificate** como "ClientCertificate_1234567890".</span><span class="sxs-lookup"><span data-stu-id="fea14-224">The new **ClientCertificate** will show up under the **ClientCertificate** directory as "ClientCertificate_1234567890".</span></span> <span data-ttu-id="fea14-225">Todos os parâmetros são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="fea14-225">All of the parameters are mandatory.</span></span> <span data-ttu-id="fea14-226">O **emissor** precisa ser impressão digital do certificado dos emissores.</span><span class="sxs-lookup"><span data-stu-id="fea14-226">The **Issuer** needs to be thumbprint of the issuers certificate.</span></span>

```powershell
$cred = Get-Credential
New-Item -Path WSMan:\localhost\ClientCertificate `
         -Issuer 1b3fd224d66c6413fe20d21e38b304226d192dfe `
         -URI wmicimv2/* -Credential $cred
```

## <a name="deleting-certificate-stores"></a><span data-ttu-id="fea14-227">Excluindo repositórios de certificados</span><span class="sxs-lookup"><span data-stu-id="fea14-227">Deleting Certificate Stores</span></span>

### <a name="delete-a-certificate-store-from-a-remote-computer"></a><span data-ttu-id="fea14-228">Excluir um repositório de certificados de um computador remoto</span><span class="sxs-lookup"><span data-stu-id="fea14-228">Delete a certificate store from a remote computer</span></span>

<span data-ttu-id="fea14-229">Esse comando usa o `Invoke-Command` cmdlet para executar um `Remove-Item` comando nos computadores S1 e S2.</span><span class="sxs-lookup"><span data-stu-id="fea14-229">This command uses the `Invoke-Command` cmdlet to run a `Remove-Item` command on the S1 and S2 computers.</span></span> <span data-ttu-id="fea14-230">O `Remove-Item` comando inclui o parâmetro **recurse** , que exclui os certificados no repositório antes de excluir o repositório.</span><span class="sxs-lookup"><span data-stu-id="fea14-230">The `Remove-Item` command includes the **Recurse** parameter, which deletes the certificates in the store before it deletes the store.</span></span>

```powershell
Invoke-Command { Remove-Item -Path cert:\LocalMachine\TestStore -Recurse } `
  -ComputerName S1, S2
```

## <a name="dynamic-parameters"></a><span data-ttu-id="fea14-231">Parâmetros dinâmicos</span><span class="sxs-lookup"><span data-stu-id="fea14-231">Dynamic parameters</span></span>

<span data-ttu-id="fea14-232">Parâmetros dinâmicos são parâmetros de cmdlet que são adicionados por um provedor do PowerShell e estão disponíveis somente quando o cmdlet está sendo usado na unidade habilitada para provedor.</span><span class="sxs-lookup"><span data-stu-id="fea14-232">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span> <span data-ttu-id="fea14-233">Esses parâmetros são válidos em todos os subdiretórios do provedor de certificado, mas entram em vigor apenas em certificados.</span><span class="sxs-lookup"><span data-stu-id="fea14-233">These parameters are valid in all subdirectories of the Certificate provider, but are effective only on certificates.</span></span>

> [!NOTE]
> <span data-ttu-id="fea14-234">Os parâmetros que executam a filtragem em relação à `EnhancedKeyUsageList` propriedade também retornam itens com um `EnhancedKeyUsageList` valor de propriedade vazio.</span><span class="sxs-lookup"><span data-stu-id="fea14-234">Parameters that perform filtering against the `EnhancedKeyUsageList` property also return items with an empty `EnhancedKeyUsageList` property value.</span></span>
> <span data-ttu-id="fea14-235">Os certificados que têm um **EnhancedKeyUsageList** vazio podem ser usados para todas as finalidades.</span><span class="sxs-lookup"><span data-stu-id="fea14-235">Certificates that have an empty **EnhancedKeyUsageList** can be used for all purposes.</span></span>

<span data-ttu-id="fea14-236">Os seguintes parâmetros do provedor de certificado foram reintroduzidos no PowerShell 7,1.</span><span class="sxs-lookup"><span data-stu-id="fea14-236">The following Certificate provider parameters were reintroduced in PowerShell 7.1.</span></span>

- <span data-ttu-id="fea14-237">DNSName</span><span class="sxs-lookup"><span data-stu-id="fea14-237">DNSName</span></span>
- <span data-ttu-id="fea14-238">DocumentEncryptionCert</span><span class="sxs-lookup"><span data-stu-id="fea14-238">DocumentEncryptionCert</span></span>
- <span data-ttu-id="fea14-239">EKU</span><span class="sxs-lookup"><span data-stu-id="fea14-239">EKU</span></span>
- <span data-ttu-id="fea14-240">ExpiringInDays</span><span class="sxs-lookup"><span data-stu-id="fea14-240">ExpiringInDays</span></span>
- <span data-ttu-id="fea14-241">SSLServerAuthentication</span><span class="sxs-lookup"><span data-stu-id="fea14-241">SSLServerAuthentication</span></span>

### <a name="codesigningcert-systemmanagementautomationswitchparameter"></a><span data-ttu-id="fea14-242">CodeSigningCert <System. Management. Automation. SwitchParameter></span><span class="sxs-lookup"><span data-stu-id="fea14-242">CodeSigningCert <System.Management.Automation.SwitchParameter></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="fea14-243">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="fea14-243">Cmdlets supported</span></span>

- [<span data-ttu-id="fea14-244">Get-Item</span><span class="sxs-lookup"><span data-stu-id="fea14-244">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)

- [<span data-ttu-id="fea14-245">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="fea14-245">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

<span data-ttu-id="fea14-246">Esse parâmetro obtém certificados que têm "assinatura de código" em seu valor de propriedade **EnhancedKeyUsageList** .</span><span class="sxs-lookup"><span data-stu-id="fea14-246">This parameter gets certificates that have "Code Signing" in their **EnhancedKeyUsageList** property value.</span></span>

### <a name="deletekey-systemmanagementautomationswitchparameter"></a><span data-ttu-id="fea14-247">DeleteKey <System. Management. Automation. SwitchParameter></span><span class="sxs-lookup"><span data-stu-id="fea14-247">DeleteKey <System.Management.Automation.SwitchParameter></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="fea14-248">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="fea14-248">Cmdlets supported</span></span>

- [<span data-ttu-id="fea14-249">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="fea14-249">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)

<span data-ttu-id="fea14-250">Esse parâmetro exclui a chave privada associada ao excluir o certificado.</span><span class="sxs-lookup"><span data-stu-id="fea14-250">This parameter deletes the associated private key when it deletes the certificate.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fea14-251">Para excluir uma chave privada associada a um certificado de usuário no `Cert:\CurrentUser` repositório em um computador remoto, você deve usar credenciais delegadas.</span><span class="sxs-lookup"><span data-stu-id="fea14-251">To delete a private key that is associated with a user certificate in the `Cert:\CurrentUser` store on a remote computer, you must use delegated credentials.</span></span> <span data-ttu-id="fea14-252">O `Invoke-Command` cmdlet dá suporte à delegação de credenciais usando o parâmetro **CredSSP** .</span><span class="sxs-lookup"><span data-stu-id="fea14-252">The `Invoke-Command` cmdlet supports credential delegation using the **CredSSP** parameter.</span></span> <span data-ttu-id="fea14-253">Você deve considerar qualquer risco de segurança antes `Remove-Item` de usar with `Invoke-Command` e a delegação de credenciais.</span><span class="sxs-lookup"><span data-stu-id="fea14-253">You should consider any security risks before using `Remove-Item` with `Invoke-Command` and credential delegation.</span></span>

<span data-ttu-id="fea14-254">Esse parâmetro foi reintroduzido no PowerShell 7,1</span><span class="sxs-lookup"><span data-stu-id="fea14-254">This parameter was reintroduced in PowerShell 7.1</span></span>

### <a name="dnsname-microsoftpowershellcommandsdnsnamerepresentation"></a><span data-ttu-id="fea14-255">DnsName <Microsoft. PowerShell. Commands. DnsNameRepresentation></span><span class="sxs-lookup"><span data-stu-id="fea14-255">DnsName <Microsoft.PowerShell.Commands.DnsNameRepresentation></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="fea14-256">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="fea14-256">Cmdlets supported</span></span>

- [<span data-ttu-id="fea14-257">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="fea14-257">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

<span data-ttu-id="fea14-258">Esse parâmetro obtém certificados que têm o nome de domínio ou padrão de nome especificado na propriedade **DNSNameList** do certificado.</span><span class="sxs-lookup"><span data-stu-id="fea14-258">This parameter gets certificates that have the specified domain name or name pattern in the **DNSNameList** property of the certificate.</span></span> <span data-ttu-id="fea14-259">O valor desse parâmetro pode ser "Unicode" ou "ASCII".</span><span class="sxs-lookup"><span data-stu-id="fea14-259">The value of this parameter can either be "Unicode" or "ASCII".</span></span> <span data-ttu-id="fea14-260">Os valores Punycode são convertidos para Unicode.</span><span class="sxs-lookup"><span data-stu-id="fea14-260">Punycode values are converted to Unicode.</span></span> <span data-ttu-id="fea14-261">Caracteres curinga ( `*` ) são permitidos.</span><span class="sxs-lookup"><span data-stu-id="fea14-261">Wildcard characters (`*`) are permitted.</span></span>

<span data-ttu-id="fea14-262">Esse parâmetro foi reintroduzido no PowerShell 7,1</span><span class="sxs-lookup"><span data-stu-id="fea14-262">This parameter was reintroduced in PowerShell 7.1</span></span>

### <a name="documentencryptioncert-systemmanagementautomationswitchparameter"></a><span data-ttu-id="fea14-263">DocumentEncryptionCert <System. Management. Automation. SwitchParameter></span><span class="sxs-lookup"><span data-stu-id="fea14-263">DocumentEncryptionCert <System.Management.Automation.SwitchParameter></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="fea14-264">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="fea14-264">Cmdlets supported</span></span>

- [<span data-ttu-id="fea14-265">Get-Item</span><span class="sxs-lookup"><span data-stu-id="fea14-265">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)

- [<span data-ttu-id="fea14-266">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="fea14-266">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

<span data-ttu-id="fea14-267">Esse parâmetro obtém certificados que têm "criptografia de documentos" em seu valor de propriedade **EnhancedKeyUsageList** .</span><span class="sxs-lookup"><span data-stu-id="fea14-267">This parameter gets certificates that have "Document Encryption" in their **EnhancedKeyUsageList** property value.</span></span>

### <a name="eku-systemstring"></a><span data-ttu-id="fea14-268">> EKU <System. String</span><span class="sxs-lookup"><span data-stu-id="fea14-268">EKU <System.String></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="fea14-269">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="fea14-269">Cmdlets supported</span></span>

- [<span data-ttu-id="fea14-270">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="fea14-270">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

<span data-ttu-id="fea14-271">Esse parâmetro obtém certificados que têm o texto ou padrão de texto especificado na `EnhancedKeyUsageList` Propriedade do certificado.</span><span class="sxs-lookup"><span data-stu-id="fea14-271">This parameter gets certificates that have the specified text or text pattern in the `EnhancedKeyUsageList` property of the certificate.</span></span> <span data-ttu-id="fea14-272">Caracteres curinga ( `*` ) são permitidos.</span><span class="sxs-lookup"><span data-stu-id="fea14-272">Wildcard characters (`*`) are permitted.</span></span> <span data-ttu-id="fea14-273">A `EnhancedKeyUsageList` propriedade contém o nome amigável e os campos de OID do EKU.</span><span class="sxs-lookup"><span data-stu-id="fea14-273">The `EnhancedKeyUsageList` property contains the friendly name and the OID fields of the EKU.</span></span>

<span data-ttu-id="fea14-274">Esse parâmetro foi reintroduzido no PowerShell 7,1</span><span class="sxs-lookup"><span data-stu-id="fea14-274">This parameter was reintroduced in PowerShell 7.1</span></span>

### <a name="expiringindays-systemint32"></a><span data-ttu-id="fea14-275">ExpiringInDays <System. Int32></span><span class="sxs-lookup"><span data-stu-id="fea14-275">ExpiringInDays <System.Int32></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="fea14-276">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="fea14-276">Cmdlets supported</span></span>

- [<span data-ttu-id="fea14-277">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="fea14-277">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

<span data-ttu-id="fea14-278">Esse parâmetro obtém certificados que expiram no número de dias especificado ou antes dele.</span><span class="sxs-lookup"><span data-stu-id="fea14-278">This parameter gets certificates that are expiring in or before the specified number of days.</span></span> <span data-ttu-id="fea14-279">Um valor de 0 (zero) obtém certificados expirados.</span><span class="sxs-lookup"><span data-stu-id="fea14-279">A value of 0 (zero) gets certificates that have expired.</span></span>

<span data-ttu-id="fea14-280">Esse parâmetro foi reintroduzido no PowerShell 7,1</span><span class="sxs-lookup"><span data-stu-id="fea14-280">This parameter was reintroduced in PowerShell 7.1</span></span>

### <a name="itemtype-string"></a><span data-ttu-id="fea14-281">ItemType \<String\></span><span class="sxs-lookup"><span data-stu-id="fea14-281">ItemType \<String\></span></span>

<span data-ttu-id="fea14-282">Esse parâmetro permite que você especifique o tipo de item criado por `New-Item` .</span><span class="sxs-lookup"><span data-stu-id="fea14-282">This parameter allows you to specify the type of item created by `New-Item`.</span></span>

<span data-ttu-id="fea14-283">Em uma `Certificate` unidade, os seguintes valores são permitidos:</span><span class="sxs-lookup"><span data-stu-id="fea14-283">In a `Certificate` drive, the following values are allowed:</span></span>

- <span data-ttu-id="fea14-284">Provedor Certificate</span><span class="sxs-lookup"><span data-stu-id="fea14-284">Certificate Provider</span></span>
- <span data-ttu-id="fea14-285">Certificado</span><span class="sxs-lookup"><span data-stu-id="fea14-285">Certificate</span></span>
- <span data-ttu-id="fea14-286">Repositório</span><span class="sxs-lookup"><span data-stu-id="fea14-286">Store</span></span>
- <span data-ttu-id="fea14-287">StoreLocation</span><span class="sxs-lookup"><span data-stu-id="fea14-287">StoreLocation</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="fea14-288">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="fea14-288">Cmdlets Supported</span></span>

- [<span data-ttu-id="fea14-289">New-Item</span><span class="sxs-lookup"><span data-stu-id="fea14-289">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="sslserverauthentication-systemmanagementautomationswitchparameter"></a><span data-ttu-id="fea14-290">SSLServerAuthentication <System. Management. Automation. SwitchParameter></span><span class="sxs-lookup"><span data-stu-id="fea14-290">SSLServerAuthentication <System.Management.Automation.SwitchParameter></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="fea14-291">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="fea14-291">Cmdlets supported</span></span>

- [<span data-ttu-id="fea14-292">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="fea14-292">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

<span data-ttu-id="fea14-293">Obtém somente os certificados de servidor de hospedagem web SSL.</span><span class="sxs-lookup"><span data-stu-id="fea14-293">Gets only server certificates for SSL web hosting.</span></span> <span data-ttu-id="fea14-294">Esse parâmetro obtém certificados que têm "autenticação de servidor" em seu `EnhancedKeyUsageList` valor de propriedade.</span><span class="sxs-lookup"><span data-stu-id="fea14-294">This parameter gets certificates that have "Server Authentication" in their `EnhancedKeyUsageList` property value.</span></span>

<span data-ttu-id="fea14-295">Esse parâmetro foi reintroduzido no PowerShell 7,1</span><span class="sxs-lookup"><span data-stu-id="fea14-295">This parameter was reintroduced in PowerShell 7.1</span></span>

## <a name="script-properties"></a><span data-ttu-id="fea14-296">Propriedades do script</span><span class="sxs-lookup"><span data-stu-id="fea14-296">Script properties</span></span>

<span data-ttu-id="fea14-297">Novas propriedades de script foram adicionadas ao objeto **X509Certificate2** que representa os certificados para facilitar a pesquisa e o gerenciamento dos certificados.</span><span class="sxs-lookup"><span data-stu-id="fea14-297">New script properties have been added to the **x509Certificate2** object that represents the certificates to make it easy to search and manage the certificates.</span></span>

- <span data-ttu-id="fea14-298">`DnsNameList`: Para popular a `DnsNameList` propriedade, o provedor de certificado copia o conteúdo da entrada DnsName na extensão SubjectAlternativeName (San).</span><span class="sxs-lookup"><span data-stu-id="fea14-298">`DnsNameList`: To populate the `DnsNameList` property, the Certificate provider copies the content from the DNSName entry in the SubjectAlternativeName (SAN) extension.</span></span> <span data-ttu-id="fea14-299">Se a extensão de SAN estiver vazia, a propriedade será preenchida com o conteúdo do campo Assunto do certificado.</span><span class="sxs-lookup"><span data-stu-id="fea14-299">If the SAN extension is empty, the property is populated with content from the Subject field of the certificate.</span></span>

- <span data-ttu-id="fea14-300">`EnhancedKeyUsageList`: Para popular a `EnhancedKeyUsageList` propriedade, o provedor de certificado copia as propriedades de OID do campo EnhancedKeyUsage (EKU) no certificado e cria um nome amigável para ele.</span><span class="sxs-lookup"><span data-stu-id="fea14-300">`EnhancedKeyUsageList`: To populate the `EnhancedKeyUsageList` property, the Certificate provider copies the OID properties of the EnhancedKeyUsage (EKU) field in the certificate and creates a friendly name for it.</span></span>

- <span data-ttu-id="fea14-301">`SendAsTrustedIssuer`: Para popular a `SendAsTrustedIssuer` propriedade, o provedor de certificado copia a `SendAsTrustedIssuer` Propriedade do certificado.</span><span class="sxs-lookup"><span data-stu-id="fea14-301">`SendAsTrustedIssuer`: To populate the `SendAsTrustedIssuer` property, the Certificate provider copies the `SendAsTrustedIssuer` property from the certificate.</span></span>  <span data-ttu-id="fea14-302">Para obter mais informações, consulte [Gerenciamento de emissores confiáveis para autenticação de cliente](/windows-server/security/tls/what-s-new-in-tls-ssl-schannel-ssp-overview#BKMK_TrustedIssuers).</span><span class="sxs-lookup"><span data-stu-id="fea14-302">For more information see [Management of trusted issuers for client authentication](/windows-server/security/tls/what-s-new-in-tls-ssl-schannel-ssp-overview#BKMK_TrustedIssuers).</span></span>

<span data-ttu-id="fea14-303">Esses novos recursos permitem pesquisar certificados com base em seus nomes DNS e datas de vencimento e distinguir os certificados de autenticação de cliente e servidor, o valor de suas propriedades de Uso Avançado de Chave (EKU).</span><span class="sxs-lookup"><span data-stu-id="fea14-303">These new features let you search for certificates based on their DNS names and expiration dates, and distinguish client and server authentication certificates by the value of their Enhanced Key Usage (EKU) properties.</span></span>

## <a name="using-the-pipeline"></a><span data-ttu-id="fea14-304">Usando o pipeline</span><span class="sxs-lookup"><span data-stu-id="fea14-304">Using the pipeline</span></span>

<span data-ttu-id="fea14-305">Os cmdlets do provedor aceitam a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="fea14-305">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="fea14-306">Você pode usar o pipeline para simplificar a tarefa enviando dados do provedor de um cmdlet para outro cmdlet do provedor.</span><span class="sxs-lookup"><span data-stu-id="fea14-306">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="fea14-307">Para ler mais sobre como usar o pipeline com cmdlets de provedor, consulte as referências de cmdlet fornecidas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="fea14-307">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="fea14-308">Obtendo ajuda</span><span class="sxs-lookup"><span data-stu-id="fea14-308">Getting help</span></span>

<span data-ttu-id="fea14-309">A partir do Windows PowerShell 3.0, você pode obter tópicos da Ajuda personalizados para cmdlets do provedor que explicam como esses cmdlets se comportam em uma unidade de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="fea14-309">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="fea14-310">Para obter os tópicos de ajuda personalizados para a unidade do sistema de arquivos, execute um comando [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) em uma unidade do sistema de arquivos ou use o `-Path` parâmetro de `Get-Help` para especificar uma unidade do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="fea14-310">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of `Get-Help` to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path cert:
```

## <a name="see-also"></a><span data-ttu-id="fea14-311">Confira também</span><span class="sxs-lookup"><span data-stu-id="fea14-311">See also</span></span>

[<span data-ttu-id="fea14-312">about_Providers</span><span class="sxs-lookup"><span data-stu-id="fea14-312">about_Providers</span></span>](../../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="fea14-313">about_Signing</span><span class="sxs-lookup"><span data-stu-id="fea14-313">about_Signing</span></span>](../../Microsoft.PowerShell.Core/About/about_Signing.md)

[<span data-ttu-id="fea14-314">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="fea14-314">Get-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Get-AuthenticodeSignature)

[<span data-ttu-id="fea14-315">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="fea14-315">Set-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

[<span data-ttu-id="fea14-316">Get-PfxCertificate</span><span class="sxs-lookup"><span data-stu-id="fea14-316">Get-PfxCertificate</span></span>](xref:Microsoft.PowerShell.Security.Get-PfxCertificate)
