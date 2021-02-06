---
description: Explica como assinar scripts para que eles estejam em conformidade com as políticas de execução do PowerShell.
Locale: en-US
ms.date: 07/31/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_signing?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Signing
ms.openlocfilehash: 560ecc385e970224a23af7a1195c99d8423f503f
ms.sourcegitcommit: 021ea294327dec542ec040619dac0d2171397a90
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/29/2020
ms.locfileid: "99598038"
---
# <a name="about-signing"></a><span data-ttu-id="1ad5b-103">Sobre a assinatura</span><span class="sxs-lookup"><span data-stu-id="1ad5b-103">About Signing</span></span>

## <a name="short-description"></a><span data-ttu-id="1ad5b-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="1ad5b-104">Short description</span></span>
<span data-ttu-id="1ad5b-105">Explica como assinar scripts para que eles estejam em conformidade com as políticas de execução do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-105">Explains how to sign scripts so that they comply with the PowerShell execution policies.</span></span>

## <a name="long-description"></a><span data-ttu-id="1ad5b-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="1ad5b-106">Long description</span></span>

<span data-ttu-id="1ad5b-107">A política de execução restrita não permite que nenhum script seja executado.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-107">The Restricted execution policy does not permit any scripts to run.</span></span> <span data-ttu-id="1ad5b-108">As políticas de execução **AllSigned** e **RemoteSigned** impedem que o PowerShell execute scripts que não têm uma assinatura digital.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-108">The **AllSigned** and **RemoteSigned** execution policies prevent PowerShell from running scripts that do not have a digital signature.</span></span>

<span data-ttu-id="1ad5b-109">Este tópico explica como executar scripts selecionados que não são assinados, mesmo que a política de execução seja **RemoteSigned** e como assinar scripts para seu próprio uso.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-109">This topic explains how to run selected scripts that are not signed, even while the execution policy is **RemoteSigned**, and how to sign scripts for your own use.</span></span>

<span data-ttu-id="1ad5b-110">Para obter mais informações sobre as políticas de execução do PowerShell, consulte [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="1ad5b-110">For more information about PowerShell execution policies, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

## <a name="to-permit-signed-scripts-to-run"></a><span data-ttu-id="1ad5b-111">Para permitir que scripts assinados sejam executados</span><span class="sxs-lookup"><span data-stu-id="1ad5b-111">To permit signed scripts to run</span></span>

<span data-ttu-id="1ad5b-112">Quando você inicia o PowerShell em um computador pela primeira vez, a política de execução **restrita** (o padrão) provavelmente estará em vigor.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-112">When you start PowerShell on a computer for the first time, the **Restricted** execution policy (the default) is likely to be in effect.</span></span>

<span data-ttu-id="1ad5b-113">A política **restrita** não permite que nenhum script seja executado.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-113">The **Restricted** policy does not permit any scripts to run.</span></span>

<span data-ttu-id="1ad5b-114">Para localizar a política de execução efetiva em seu computador, digite:</span><span class="sxs-lookup"><span data-stu-id="1ad5b-114">To find the effective execution policy on your computer, type:</span></span>

```powershell
Get-ExecutionPolicy
```

<span data-ttu-id="1ad5b-115">Para executar scripts não assinados que você escreve no computador local e os scripts assinados de outros usuários, inicie o PowerShell com a opção Executar como administrador e use o seguinte comando para alterar a política de execução no computador para **RemoteSigned**:</span><span class="sxs-lookup"><span data-stu-id="1ad5b-115">To run unsigned scripts that you write on your local computer and signed scripts from other users, start PowerShell with the Run as Administrator option and then use the following command to change the execution policy on the computer to **RemoteSigned**:</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```

<span data-ttu-id="1ad5b-116">Para obter mais informações, consulte o tópico da ajuda para o `Set-ExecutionPolicy` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-116">For more information, see the help topic for the `Set-ExecutionPolicy` cmdlet.</span></span>

## <a name="running-unsigned-scripts-using-the-remotesigned-execution-policy"></a><span data-ttu-id="1ad5b-117">Executando scripts não assinados usando a política de execução RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="1ad5b-117">Running unsigned scripts using the RemoteSigned execution policy</span></span>

<span data-ttu-id="1ad5b-118">Se a sua política de execução do PowerShell for **RemoteSigned**, o PowerShell não executará scripts não assinados que são baixados da Internet, incluindo scripts não assinados recebidos por email e programas de mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-118">If your PowerShell execution policy is **RemoteSigned**, PowerShell will not run unsigned scripts that are downloaded from the internet, including unsigned scripts you receive through email and instant messaging programs.</span></span>

<span data-ttu-id="1ad5b-119">Se você tentar executar um script baixado, o PowerShell exibirá a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="1ad5b-119">If you try to run a downloaded script, PowerShell displays the following error message:</span></span>

```Output
The file <file-name> cannot be loaded. The file <file-name> is not digitally
signed. The script will not execute on the system. Please see "Get-Help
about_Signing" for more details.
```

<span data-ttu-id="1ad5b-120">Antes de executar o script, examine o código para garantir que você confie nele.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-120">Before you run the script, review the code to be sure that you trust it.</span></span>
<span data-ttu-id="1ad5b-121">Os scripts têm o mesmo efeito que qualquer programa executável.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-121">Scripts have the same effect as any executable program.</span></span>

<span data-ttu-id="1ad5b-122">Para executar um script não assinado, use o cmdlet Unblock-File ou use o procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-122">To run an unsigned script, use the Unblock-File cmdlet or use the following procedure.</span></span>

1. <span data-ttu-id="1ad5b-123">Salve o arquivo de script em seu computador.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-123">Save the script file on your computer.</span></span>
2. <span data-ttu-id="1ad5b-124">Clique em Iniciar, em Meu Computador e localize o arquivo de script salvo.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-124">Click Start, click My Computer, and locate the saved script file.</span></span>
3. <span data-ttu-id="1ad5b-125">Clique com o botão direito do mouse no arquivo de script e clique em Propriedades.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-125">Right-click the script file, and then click Properties.</span></span>
4. <span data-ttu-id="1ad5b-126">Clique em Desbloquear.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-126">Click Unblock.</span></span>

<span data-ttu-id="1ad5b-127">Se um script que foi baixado da Internet for assinado digitalmente, mas você ainda não tiver optado por confiar no editor, o PowerShell exibirá a seguinte mensagem:</span><span class="sxs-lookup"><span data-stu-id="1ad5b-127">If a script that was downloaded from the internet is digitally signed, but you have not yet chosen to trust its publisher, PowerShell displays the following message:</span></span>

```Output
Do you want to run software from this untrusted publisher?
The file <file-name> is published by CN=<publisher-name>. This
publisher is not trusted on your system. Only run scripts
from trusted publishers.

[V] Never run  [D] Do not run  [R] Run once  [A] Always run
[?] Help (default is "D"):
```

<span data-ttu-id="1ad5b-128">Se você confiar no Publicador, selecione "executar uma vez" ou "sempre executar".</span><span class="sxs-lookup"><span data-stu-id="1ad5b-128">If you trust the publisher, select "Run once" or "Always run."</span></span> <span data-ttu-id="1ad5b-129">Se você não confiar no Publicador, selecione "Nunca executar" ou "não executar".</span><span class="sxs-lookup"><span data-stu-id="1ad5b-129">If you do not trust the publisher, select either "Never run" or "Do not run."</span></span> <span data-ttu-id="1ad5b-130">Se você selecionar "Nunca executar" ou "sempre executar", o PowerShell não solicitará novamente esse Publicador.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-130">If you select "Never run" or "Always run," PowerShell will not prompt you again for this publisher.</span></span>

## <a name="methods-of-signing-scripts"></a><span data-ttu-id="1ad5b-131">Métodos de assinatura de scripts</span><span class="sxs-lookup"><span data-stu-id="1ad5b-131">Methods of signing scripts</span></span>

<span data-ttu-id="1ad5b-132">Você pode assinar os scripts que você escreve e os scripts obtidos de outras fontes.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-132">You can sign the scripts that you write and the scripts that you obtain from other sources.</span></span> <span data-ttu-id="1ad5b-133">Antes de assinar qualquer script, examine cada comando para verificar se é seguro executá-lo.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-133">Before you sign any script, examine each command to verify that it is safe to run.</span></span>

<span data-ttu-id="1ad5b-134">Para obter as práticas recomendadas sobre a assinatura de código, consulte [práticas recomendadas de assinatura de código](/previous-versions/windows/hardware/design/dn653556(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="1ad5b-134">For best practices about code signing, see [Code-Signing Best Practices](/previous-versions/windows/hardware/design/dn653556(v=vs.85)).</span></span>

<span data-ttu-id="1ad5b-135">Para obter mais informações sobre como assinar um arquivo de script, consulte [Set-AuthenticodeSignature](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature).</span><span class="sxs-lookup"><span data-stu-id="1ad5b-135">For more information about how to sign a script file, see [Set-AuthenticodeSignature](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature).</span></span>

<span data-ttu-id="1ad5b-136">O `New-SelfSignedCertificate` cmdlet, introduzido no módulo PKI no PowerShell 3,0, cria um certificado autoassinado apropriado para teste.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-136">The `New-SelfSignedCertificate` cmdlet, introduced in the PKI module in PowerShell 3.0, creates a self-signed certificate that is Appropriate for testing.</span></span> <span data-ttu-id="1ad5b-137">Para obter mais informações, consulte o tópico da ajuda para o cmdlet New-SelfSignedCertificate.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-137">For more information, see the help topic for the New-SelfSignedCertificate cmdlet.</span></span>

<span data-ttu-id="1ad5b-138">Para adicionar uma assinatura digital a um script, você deve assiná-lo com um certificado de assinatura de código.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-138">To add a digital signature to a script, you must sign it with a code signing certificate.</span></span> <span data-ttu-id="1ad5b-139">Dois tipos de certificados são adequados para assinar um arquivo de script:</span><span class="sxs-lookup"><span data-stu-id="1ad5b-139">Two types of certificates are suitable for signing a script file:</span></span>

- <span data-ttu-id="1ad5b-140">Certificados que são criados por uma autoridade de certificação: para uma taxa, uma autoridade de certificação pública verifica sua identidade e fornece um certificado de assinatura de código.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-140">Certificates that are created by a certification authority: For a fee, a public certification authority verifies your identity and gives you a code signing certificate.</span></span> <span data-ttu-id="1ad5b-141">Ao comprar seu certificado de uma autoridade de certificação respeitável, você poderá compartilhar seu script com usuários em outros computadores que estejam executando o Windows, pois esses outros computadores confiam na autoridade de certificação.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-141">When you purchase your certificate from a reputable certification authority, you are able to share your script with users on other computers that are running Windows because those other computers trust the certification authority.</span></span>

- <span data-ttu-id="1ad5b-142">Certificados que você cria: você pode criar um certificado autoassinado para o qual seu computador é a autoridade que cria o certificado.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-142">Certificates that you create: You can create a self-signed certificate for which your computer is the authority that creates the certificate.</span></span> <span data-ttu-id="1ad5b-143">Esse certificado é gratuito e permite que você escreva, assine e execute scripts em seu computador.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-143">This certificate is free of charge and enables you to write, sign, and run scripts on your computer.</span></span> <span data-ttu-id="1ad5b-144">No entanto, um script assinado por um certificado autoassinado não será executado em outros computadores.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-144">However, a script signed by a self-signed certificate will not run on other computers.</span></span>

<span data-ttu-id="1ad5b-145">Normalmente, você usaria um certificado autoassinado somente para assinar scripts que você escreve para seu próprio uso e para assinar scripts que você obtém de outras fontes que você verificou que são seguros.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-145">Typically, you would use a self-signed certificate only to sign scripts that you write for your own use and to sign scripts that you get from other sources that you have verified to be safe.</span></span> <span data-ttu-id="1ad5b-146">Não é apropriado para scripts que serão compartilhados, mesmo dentro de uma empresa.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-146">It is not appropriate for scripts that will be shared, even within an enterprise.</span></span>

<span data-ttu-id="1ad5b-147">Se você criar um certificado autoassinado, certifique-se de habilitar a proteção forte de chave privada em seu certificado.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-147">If you create a self-signed certificate, be sure to enable strong private key protection on your certificate.</span></span> <span data-ttu-id="1ad5b-148">Isso impede que programas mal-intencionados inscrevam scripts em seu nome.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-148">This prevents malicious programs from signing scripts on your behalf.</span></span> <span data-ttu-id="1ad5b-149">As instruções estão incluídas no final deste tópico.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-149">The instructions are included at the end of this topic.</span></span>

## <a name="create-a-self-signed-certificate"></a><span data-ttu-id="1ad5b-150">Criará um certificado autoassinado</span><span class="sxs-lookup"><span data-stu-id="1ad5b-150">Create a self-signed certificate</span></span>

<span data-ttu-id="1ad5b-151">Para criar um certificado autoassinado, use o `New-SelfSignedCertificate` cmdlet no módulo PKI.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-151">To create a self-signed certificate, use the `New-SelfSignedCertificate` cmdlet in the PKI module.</span></span> <span data-ttu-id="1ad5b-152">Esse módulo é introduzido no PowerShell 3,0 e está incluído no Windows 8 e no Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-152">This module is introduced in PowerShell 3.0 and is included in Windows 8 and Windows Server 2012.</span></span> <span data-ttu-id="1ad5b-153">Para obter mais informações, consulte o tópico da ajuda para o `New-SelfSignedCertificate` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-153">For more information, see the help topic for the `New-SelfSignedCertificate` cmdlet.</span></span>

<span data-ttu-id="1ad5b-154">Para criar um certificado autoassinado em versões anteriores do Windows, use a ferramenta de criação de certificado `MakeCert.exe` .</span><span class="sxs-lookup"><span data-stu-id="1ad5b-154">To create a self-signed certificate in earlier versions of Windows, use the Certificate Creation tool `MakeCert.exe`.</span></span> <span data-ttu-id="1ad5b-155">Essa ferramenta está incluída no SDK do Microsoft .NET (versões 1,1 e posteriores) e no SDK do Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-155">This tool is included in the Microsoft .NET SDK (versions 1.1 and later) and in the Microsoft Windows SDK.</span></span>

<span data-ttu-id="1ad5b-156">Para obter mais informações sobre a sintaxe e as descrições de parâmetro da ferramenta de MakeCert.exe, consulte [ferramenta de criação de certificado (MakeCert.exe)](/previous-versions/dotnet/netframework-2.0/bfsktky3(v=vs.80)).</span><span class="sxs-lookup"><span data-stu-id="1ad5b-156">For more information about the syntax and the parameter descriptions of the MakeCert.exe tool, see [Certificate Creation Tool (MakeCert.exe)](/previous-versions/dotnet/netframework-2.0/bfsktky3(v=vs.80)).</span></span>

<span data-ttu-id="1ad5b-157">Para usar a ferramenta MakeCert.exe para criar um certificado, execute os comandos a seguir em uma janela de prompt de comando do SDK.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-157">To use the MakeCert.exe tool to create a certificate, run the following commands in an SDK Command Prompt window.</span></span>

<span data-ttu-id="1ad5b-158">Observação: o primeiro comando cria uma autoridade de certificação local para seu computador.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-158">Note: The first command creates a local certification authority for your computer.</span></span> <span data-ttu-id="1ad5b-159">O segundo comando gera um certificado pessoal da autoridade de certificação.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-159">The second command generates a personal certificate from the certification authority.</span></span>

<span data-ttu-id="1ad5b-160">Observação: você pode copiar ou digitar os comandos exatamente como eles aparecem.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-160">Note: You can copy or type the commands exactly as they appear.</span></span> <span data-ttu-id="1ad5b-161">Nenhuma substituição é necessária, embora você possa alterar o nome do certificado.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-161">No substitutions are necessary, although you can change the certificate name.</span></span>

```powershell
makecert -n "CN=PowerShell Local Certificate Root" -a sha1 `
-eku 1.3.6.1.5.5.7.3.3 -r -sv root.pvk root.cer `
-ss Root -sr localMachine

makecert -pe -n "CN=PowerShell User" -ss MY -a sha1 `
-eku 1.3.6.1.5.5.7.3.3 -iv root.pvk -ic root.cer
```

<span data-ttu-id="1ad5b-162">A ferramenta de MakeCert.exe solicitará uma senha de chave privada.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-162">The MakeCert.exe tool will prompt you for a private key password.</span></span> <span data-ttu-id="1ad5b-163">A senha garante que ninguém possa usar ou acessar o certificado sem o seu consentimento.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-163">The password ensures that no one can use or access the certificate without your consent.</span></span>
<span data-ttu-id="1ad5b-164">Crie e insira uma senha que você possa lembrar.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-164">Create and enter a password that you can remember.</span></span> <span data-ttu-id="1ad5b-165">Você usará essa senha posteriormente para recuperar o certificado.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-165">You will use this password later to retrieve the certificate.</span></span>

<span data-ttu-id="1ad5b-166">Para verificar se o certificado foi gerado corretamente, use o comando a seguir para obter o certificado no repositório de certificados no computador.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-166">To verify that the certificate was generated correctly, use the following command to get the certificate in the certificate store on the computer.</span></span> <span data-ttu-id="1ad5b-167">Você não encontrará um arquivo de certificado no diretório do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-167">You will not find a certificate file in the file system directory.</span></span>

<span data-ttu-id="1ad5b-168">No prompt do PowerShell, digite:</span><span class="sxs-lookup"><span data-stu-id="1ad5b-168">At the PowerShell prompt, type:</span></span>

```powershell
Get-ChildItem cert:\CurrentUser\my -codesigning
```

<span data-ttu-id="1ad5b-169">Esse comando usa o provedor de certificados do PowerShell para exibir informações sobre o certificado.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-169">This command uses the PowerShell Certificate provider to view information about the certificate.</span></span>

<span data-ttu-id="1ad5b-170">Se o certificado tiver sido criado, a saída mostrará a **impressão digital** que identifica o certificado em uma exibição semelhante à seguinte:</span><span class="sxs-lookup"><span data-stu-id="1ad5b-170">If the certificate was created, the output shows the **thumbprint** that identifies the certificate in a display that resembles the following:</span></span>

```Output
Directory: Microsoft.PowerShell.Security\Certificate::CurrentUser\My

Thumbprint                                Subject
----------                                -------
4D4917CB140714BA5B81B96E0B18AAF2C4564FDF  CN=PowerShell User ]
```

## <a name="sign-a-script"></a><span data-ttu-id="1ad5b-171">Assinar um script</span><span class="sxs-lookup"><span data-stu-id="1ad5b-171">Sign a script</span></span>

<span data-ttu-id="1ad5b-172">Depois de criar um certificado autoassinado, você pode assinar scripts.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-172">After you create a self-signed certificate, you can sign scripts.</span></span> <span data-ttu-id="1ad5b-173">Se você usar a política de execução **AllSigned** , assinar um script permitirá que você execute o script em seu computador.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-173">If you use the **AllSigned** execution policy, signing a script permits you to run the script on your computer.</span></span>

<span data-ttu-id="1ad5b-174">O script de exemplo a seguir, `Add-Signature.ps1` , assina um script.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-174">The following sample script, `Add-Signature.ps1`, signs a script.</span></span> <span data-ttu-id="1ad5b-175">No entanto, se você estiver usando a política de execução **AllSigned** , deverá assinar o `Add-Signature.ps1` script antes de executá-lo.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-175">However, if you are using the **AllSigned** execution policy, you must sign the `Add-Signature.ps1` script before you run it.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ad5b-176">O script deve ser salvo usando a codificação ASCII ou UTF8NoBOM. Você pode assinar um arquivo de script que usa uma codificação diferente.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-176">The script must be saved using ASCII or UTF8NoBOM encoding.You can sign a script file that uses a different encoding.</span></span> <span data-ttu-id="1ad5b-177">Mas o script não é executado ou o módulo que contém o script não é importado.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-177">But the script fails to run or the module containing the script fails to import.</span></span>

<span data-ttu-id="1ad5b-178">Para usar esse script, copie o texto a seguir em um arquivo de texto e nomeie-o `Add-Signature.ps1` .</span><span class="sxs-lookup"><span data-stu-id="1ad5b-178">To use this script, copy the following text into a text file, and name it `Add-Signature.ps1`.</span></span>

```powershell
## Signs a file
param([string] $file=$(throw "Please specify a filename."))
$cert = @(Get-ChildItem cert:\CurrentUser\My -codesigning)[0]
Set-AuthenticodeSignature $file $cert
```

<span data-ttu-id="1ad5b-179">Para assinar o `Add-Signature.ps1` arquivo de script, digite os seguintes comandos no prompt de comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1ad5b-179">To sign the `Add-Signature.ps1` script file, type the following commands at the PowerShell command prompt:</span></span>

```powershell
$cert = @(Get-ChildItem cert:\CurrentUser\My -codesigning)[0]
Set-AuthenticodeSignature add-signature.ps1 $cert
```

<span data-ttu-id="1ad5b-180">Depois que o script for assinado, você poderá executá-lo no computador local.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-180">After the script is signed, you can run it on the local computer.</span></span> <span data-ttu-id="1ad5b-181">No entanto, o script não será executado em computadores nos quais a política de execução do PowerShell requer uma assinatura digital de uma autoridade confiável.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-181">However, the script will not run on computers on which the PowerShell execution policy requires a digital signature from a trusted authority.</span></span> <span data-ttu-id="1ad5b-182">Se você tentar, o PowerShell exibirá a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="1ad5b-182">If you try, PowerShell displays the following error message:</span></span>

```Output
The file C:\remote_file.ps1 cannot be loaded. The signature of the
certificate cannot be verified.
At line:1 char:15
+ .\ remote_file.ps1 <<<<
```

<span data-ttu-id="1ad5b-183">Se o PowerShell exibir essa mensagem quando você executar um script que você não gravou, trate o arquivo como você trataria de qualquer script não assinado.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-183">If PowerShell displays this message when you run a script that you did not write, treat the file as you would treat any unsigned script.</span></span> <span data-ttu-id="1ad5b-184">Examine o código para determinar se você pode confiar no script.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-184">Review the code to determine whether you can trust the script.</span></span>

## <a name="enable-strong-private-key-protection-for-your-certificate"></a><span data-ttu-id="1ad5b-185">Habilitar a proteção de chave privada forte para seu certificado</span><span class="sxs-lookup"><span data-stu-id="1ad5b-185">Enable strong private key protection for your certificate</span></span>

<span data-ttu-id="1ad5b-186">Se você tiver um certificado particular em seu computador, programas mal-intencionados poderão assinar scripts em seu nome, o que autoriza o PowerShell a executá-los.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-186">If you have a private certificate on your computer, malicious programs might be able to sign scripts on your behalf, which authorizes PowerShell to run them.</span></span>

<span data-ttu-id="1ad5b-187">Para evitar a assinatura automatizada em seu nome, use `Certmgr.exe` o Gerenciador de certificados para exportar seu certificado de assinatura para um `.pfx` arquivo.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-187">To prevent automated signing on your behalf, use Certificate Manager `Certmgr.exe` to export your signing certificate to a `.pfx` file.</span></span> <span data-ttu-id="1ad5b-188">O Gerenciador de certificados está incluído no SDK do Microsoft .NET, no SDK do Microsoft Windows e no Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-188">Certificate Manager is included in the Microsoft .NET SDK, the Microsoft Windows SDK, and in internet Explorer.</span></span>

<span data-ttu-id="1ad5b-189">Para exportar o certificado:</span><span class="sxs-lookup"><span data-stu-id="1ad5b-189">To export the certificate:</span></span>

1. <span data-ttu-id="1ad5b-190">Inicie o Gerenciador de certificados.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-190">Start Certificate Manager.</span></span>
2. <span data-ttu-id="1ad5b-191">Selecione o certificado emitido pela raiz do certificado local do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-191">Select the certificate issued by PowerShell Local Certificate Root.</span></span>
3. <span data-ttu-id="1ad5b-192">Clique em exportar para iniciar o assistente para exportação de certificados.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-192">Click Export to start the Certificate Export Wizard.</span></span>
4. <span data-ttu-id="1ad5b-193">Selecione "Sim, exportar a chave privada" e clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-193">Select "Yes, export the private key", and then click Next.</span></span>
5. <span data-ttu-id="1ad5b-194">Selecione "Habilitar proteção forte".</span><span class="sxs-lookup"><span data-stu-id="1ad5b-194">Select "Enable strong protection."</span></span>
6. <span data-ttu-id="1ad5b-195">Digite uma senha e, em seguida, digite-a novamente para confirmar.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-195">Type a password, and then type it again to confirm.</span></span>
7. <span data-ttu-id="1ad5b-196">Digite um nome de arquivo que tenha a extensão de nome de arquivo. pfx.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-196">Type a file name that has the .pfx file name extension.</span></span>
8. <span data-ttu-id="1ad5b-197">Clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-197">Click Finish.</span></span>

<span data-ttu-id="1ad5b-198">Para importar novamente o certificado:</span><span class="sxs-lookup"><span data-stu-id="1ad5b-198">To re-import the certificate:</span></span>

1. <span data-ttu-id="1ad5b-199">Inicie o Gerenciador de certificados.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-199">Start Certificate Manager.</span></span>
2. <span data-ttu-id="1ad5b-200">Clique em importar para iniciar o assistente para importação de certificados.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-200">Click Import to start the Certificate Import Wizard.</span></span>
3. <span data-ttu-id="1ad5b-201">Abra o local do arquivo. pfx que você criou durante o processo de exportação.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-201">Open to the location of the .pfx file that you created during the export process.</span></span>
4. <span data-ttu-id="1ad5b-202">Na página senha, selecione "Habilitar proteção de chave privada forte" e insira a senha que você atribuiu durante o processo de exportação.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-202">On the Password page, select "Enable strong private key protection", and then enter the password that you assigned during the export process.</span></span>
5. <span data-ttu-id="1ad5b-203">Selecione o repositório de certificados pessoal.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-203">Select the Personal certificate store.</span></span>
6. <span data-ttu-id="1ad5b-204">Clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-204">Click Finish.</span></span>

## <a name="prevent-the-signature-from-expiring"></a><span data-ttu-id="1ad5b-205">Impedir que a assinatura expire</span><span class="sxs-lookup"><span data-stu-id="1ad5b-205">Prevent the signature from expiring</span></span>

<span data-ttu-id="1ad5b-206">A assinatura digital em um script é válida até que o certificado de autenticação expire ou desde que um servidor de carimbo de data/hora possa verificar se o script foi assinado enquanto o certificado de autenticação era válido.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-206">The digital signature in a script is valid until the signing certificate expires or as long as a timestamp server can verify that the script was signed while the signing certificate was valid.</span></span>

<span data-ttu-id="1ad5b-207">Como a maioria dos certificados de assinatura são válidos somente por um ano, o uso de um servidor de carimbo de data/hora garante que os usuários possam usar seu script por muitos anos.</span><span class="sxs-lookup"><span data-stu-id="1ad5b-207">Because most signing certificates are valid for one year only, using a time stamp server ensures that users can use your script for many years to come.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ad5b-208">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1ad5b-208">See also</span></span>

[<span data-ttu-id="1ad5b-209">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="1ad5b-209">about_Execution_Policies</span></span>](about_Execution_Policies.md)

[<span data-ttu-id="1ad5b-210">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="1ad5b-210">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="1ad5b-211">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="1ad5b-211">Get-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Get-ExecutionPolicy)

[<span data-ttu-id="1ad5b-212">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="1ad5b-212">Set-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)

[<span data-ttu-id="1ad5b-213">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="1ad5b-213">Set-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

<span data-ttu-id="1ad5b-214">[Introdução à assinatura de código](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537361(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="1ad5b-214">[Introduction to Code Signing](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537361(v=vs.85))</span></span>
