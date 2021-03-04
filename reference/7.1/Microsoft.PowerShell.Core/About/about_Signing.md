---
description: Explica como assinar scripts para que eles estejam em conformidade com as políticas de execução do PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 07/31/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_signing?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Signing
ms.openlocfilehash: 5ad2f417fc31c18f40e6ce823fe07883cb8367dc
ms.sourcegitcommit: 1dfd5554b70c7e8f4e3df19e29c384a9c0a4b227
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2021
ms.locfileid: "101685620"
---
# <a name="about-signing"></a><span data-ttu-id="4fe3e-104">Sobre a assinatura</span><span class="sxs-lookup"><span data-stu-id="4fe3e-104">About Signing</span></span>

## <a name="short-description"></a><span data-ttu-id="4fe3e-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="4fe3e-105">Short description</span></span>
<span data-ttu-id="4fe3e-106">Explica como assinar scripts para que eles estejam em conformidade com as políticas de execução do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-106">Explains how to sign scripts so that they comply with the PowerShell execution policies.</span></span>

## <a name="long-description"></a><span data-ttu-id="4fe3e-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="4fe3e-107">Long description</span></span>

<span data-ttu-id="4fe3e-108">A política de execução restrita não permite que nenhum script seja executado.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-108">The Restricted execution policy does not permit any scripts to run.</span></span> <span data-ttu-id="4fe3e-109">As políticas de execução **AllSigned** e **RemoteSigned** impedem que o PowerShell execute scripts que não têm uma assinatura digital.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-109">The **AllSigned** and **RemoteSigned** execution policies prevent PowerShell from running scripts that do not have a digital signature.</span></span>

<span data-ttu-id="4fe3e-110">Este tópico explica como executar scripts selecionados que não são assinados, mesmo que a política de execução seja **RemoteSigned** e como assinar scripts para seu próprio uso.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-110">This topic explains how to run selected scripts that are not signed, even while the execution policy is **RemoteSigned**, and how to sign scripts for your own use.</span></span>

<span data-ttu-id="4fe3e-111">Para obter mais informações sobre as políticas de execução do PowerShell, consulte [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="4fe3e-111">For more information about PowerShell execution policies, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

## <a name="to-permit-signed-scripts-to-run"></a><span data-ttu-id="4fe3e-112">Para permitir que scripts assinados sejam executados</span><span class="sxs-lookup"><span data-stu-id="4fe3e-112">To permit signed scripts to run</span></span>

<span data-ttu-id="4fe3e-113">Quando você inicia o PowerShell em um computador pela primeira vez, a política de execução **restrita** (o padrão) provavelmente estará em vigor.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-113">When you start PowerShell on a computer for the first time, the **Restricted** execution policy (the default) is likely to be in effect.</span></span>

<span data-ttu-id="4fe3e-114">A política **restrita** não permite que nenhum script seja executado.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-114">The **Restricted** policy does not permit any scripts to run.</span></span>

<span data-ttu-id="4fe3e-115">Para localizar a política de execução efetiva em seu computador, digite:</span><span class="sxs-lookup"><span data-stu-id="4fe3e-115">To find the effective execution policy on your computer, type:</span></span>

```powershell
Get-ExecutionPolicy
```

<span data-ttu-id="4fe3e-116">Para executar scripts não assinados que você escreve no computador local e os scripts assinados de outros usuários, inicie o PowerShell com a opção Executar como administrador e use o seguinte comando para alterar a política de execução no computador para **RemoteSigned**:</span><span class="sxs-lookup"><span data-stu-id="4fe3e-116">To run unsigned scripts that you write on your local computer and signed scripts from other users, start PowerShell with the Run as Administrator option and then use the following command to change the execution policy on the computer to **RemoteSigned**:</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```

<span data-ttu-id="4fe3e-117">Para obter mais informações, consulte o tópico da ajuda para o `Set-ExecutionPolicy` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-117">For more information, see the help topic for the `Set-ExecutionPolicy` cmdlet.</span></span>

## <a name="running-unsigned-scripts-using-the-remotesigned-execution-policy"></a><span data-ttu-id="4fe3e-118">Executando scripts não assinados usando a política de execução RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="4fe3e-118">Running unsigned scripts using the RemoteSigned execution policy</span></span>

<span data-ttu-id="4fe3e-119">Se a sua política de execução do PowerShell for **RemoteSigned**, o PowerShell não executará scripts não assinados que são baixados da Internet, incluindo scripts não assinados recebidos por email e programas de mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-119">If your PowerShell execution policy is **RemoteSigned**, PowerShell will not run unsigned scripts that are downloaded from the internet, including unsigned scripts you receive through email and instant messaging programs.</span></span>

<span data-ttu-id="4fe3e-120">Se você tentar executar um script baixado, o PowerShell exibirá a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="4fe3e-120">If you try to run a downloaded script, PowerShell displays the following error message:</span></span>

```Output
The file <file-name> cannot be loaded. The file <file-name> is not digitally
signed. The script will not execute on the system. Please see "Get-Help
about_Signing" for more details.
```

<span data-ttu-id="4fe3e-121">Antes de executar o script, examine o código para garantir que você confie nele.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-121">Before you run the script, review the code to be sure that you trust it.</span></span>
<span data-ttu-id="4fe3e-122">Os scripts têm o mesmo efeito que qualquer programa executável.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-122">Scripts have the same effect as any executable program.</span></span>

<span data-ttu-id="4fe3e-123">Para executar um script não assinado, use o cmdlet Unblock-File ou use o procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-123">To run an unsigned script, use the Unblock-File cmdlet or use the following procedure.</span></span>

1. <span data-ttu-id="4fe3e-124">Salve o arquivo de script em seu computador.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-124">Save the script file on your computer.</span></span>
2. <span data-ttu-id="4fe3e-125">Clique em Iniciar, em Meu Computador e localize o arquivo de script salvo.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-125">Click Start, click My Computer, and locate the saved script file.</span></span>
3. <span data-ttu-id="4fe3e-126">Clique com o botão direito do mouse no arquivo de script e clique em Propriedades.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-126">Right-click the script file, and then click Properties.</span></span>
4. <span data-ttu-id="4fe3e-127">Clique em Desbloquear.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-127">Click Unblock.</span></span>

<span data-ttu-id="4fe3e-128">Se um script que foi baixado da Internet for assinado digitalmente, mas você ainda não tiver optado por confiar no editor, o PowerShell exibirá a seguinte mensagem:</span><span class="sxs-lookup"><span data-stu-id="4fe3e-128">If a script that was downloaded from the internet is digitally signed, but you have not yet chosen to trust its publisher, PowerShell displays the following message:</span></span>

```Output
Do you want to run software from this untrusted publisher?
The file <file-name> is published by CN=<publisher-name>. This
publisher is not trusted on your system. Only run scripts
from trusted publishers.

[V] Never run  [D] Do not run  [R] Run once  [A] Always run
[?] Help (default is "D"):
```

<span data-ttu-id="4fe3e-129">Se você confiar no Publicador, selecione "executar uma vez" ou "sempre executar".</span><span class="sxs-lookup"><span data-stu-id="4fe3e-129">If you trust the publisher, select "Run once" or "Always run."</span></span> <span data-ttu-id="4fe3e-130">Se você não confiar no Publicador, selecione "Nunca executar" ou "não executar".</span><span class="sxs-lookup"><span data-stu-id="4fe3e-130">If you do not trust the publisher, select either "Never run" or "Do not run."</span></span> <span data-ttu-id="4fe3e-131">Se você selecionar "Nunca executar" ou "sempre executar", o PowerShell não solicitará novamente esse Publicador.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-131">If you select "Never run" or "Always run," PowerShell will not prompt you again for this publisher.</span></span>

## <a name="methods-of-signing-scripts"></a><span data-ttu-id="4fe3e-132">Métodos de assinatura de scripts</span><span class="sxs-lookup"><span data-stu-id="4fe3e-132">Methods of signing scripts</span></span>

<span data-ttu-id="4fe3e-133">Você pode assinar os scripts que você escreve e os scripts obtidos de outras fontes.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-133">You can sign the scripts that you write and the scripts that you obtain from other sources.</span></span> <span data-ttu-id="4fe3e-134">Antes de assinar qualquer script, examine cada comando para verificar se é seguro executá-lo.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-134">Before you sign any script, examine each command to verify that it is safe to run.</span></span>

<span data-ttu-id="4fe3e-135">Para obter as práticas recomendadas sobre a assinatura de código, consulte [práticas recomendadas de assinatura de código](/previous-versions/windows/hardware/design/dn653556(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="4fe3e-135">For best practices about code signing, see [Code-Signing Best Practices](/previous-versions/windows/hardware/design/dn653556(v=vs.85)).</span></span>

<span data-ttu-id="4fe3e-136">Para obter mais informações sobre como assinar um arquivo de script, consulte [Set-AuthenticodeSignature](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature).</span><span class="sxs-lookup"><span data-stu-id="4fe3e-136">For more information about how to sign a script file, see [Set-AuthenticodeSignature](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature).</span></span>

<span data-ttu-id="4fe3e-137">O `New-SelfSignedCertificate` cmdlet, introduzido no módulo PKI no PowerShell 3,0, cria um certificado autoassinado apropriado para teste.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-137">The `New-SelfSignedCertificate` cmdlet, introduced in the PKI module in PowerShell 3.0, creates a self-signed certificate that is Appropriate for testing.</span></span> <span data-ttu-id="4fe3e-138">Para obter mais informações, consulte o tópico da ajuda para o cmdlet New-SelfSignedCertificate.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-138">For more information, see the help topic for the New-SelfSignedCertificate cmdlet.</span></span>

<span data-ttu-id="4fe3e-139">Para adicionar uma assinatura digital a um script, você deve assiná-lo com um certificado de assinatura de código.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-139">To add a digital signature to a script, you must sign it with a code signing certificate.</span></span> <span data-ttu-id="4fe3e-140">Dois tipos de certificados são adequados para assinar um arquivo de script:</span><span class="sxs-lookup"><span data-stu-id="4fe3e-140">Two types of certificates are suitable for signing a script file:</span></span>

- <span data-ttu-id="4fe3e-141">Certificados que são criados por uma autoridade de certificação: para uma taxa, uma autoridade de certificação pública verifica sua identidade e fornece um certificado de assinatura de código.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-141">Certificates that are created by a certification authority: For a fee, a public certification authority verifies your identity and gives you a code signing certificate.</span></span> <span data-ttu-id="4fe3e-142">Ao comprar seu certificado de uma autoridade de certificação respeitável, você poderá compartilhar seu script com usuários em outros computadores que estejam executando o Windows, pois esses outros computadores confiam na autoridade de certificação.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-142">When you purchase your certificate from a reputable certification authority, you are able to share your script with users on other computers that are running Windows because those other computers trust the certification authority.</span></span>

- <span data-ttu-id="4fe3e-143">Certificados que você cria: você pode criar um certificado autoassinado para o qual seu computador é a autoridade que cria o certificado.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-143">Certificates that you create: You can create a self-signed certificate for which your computer is the authority that creates the certificate.</span></span> <span data-ttu-id="4fe3e-144">Esse certificado é gratuito e permite que você escreva, assine e execute scripts em seu computador.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-144">This certificate is free of charge and enables you to write, sign, and run scripts on your computer.</span></span> <span data-ttu-id="4fe3e-145">No entanto, um script assinado por um certificado autoassinado não será executado em outros computadores.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-145">However, a script signed by a self-signed certificate will not run on other computers.</span></span>

<span data-ttu-id="4fe3e-146">Normalmente, você usaria um certificado autoassinado somente para assinar scripts que você escreve para seu próprio uso e para assinar scripts que você obtém de outras fontes que você verificou que são seguros.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-146">Typically, you would use a self-signed certificate only to sign scripts that you write for your own use and to sign scripts that you get from other sources that you have verified to be safe.</span></span> <span data-ttu-id="4fe3e-147">Não é apropriado para scripts que serão compartilhados, mesmo dentro de uma empresa.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-147">It is not appropriate for scripts that will be shared, even within an enterprise.</span></span>

<span data-ttu-id="4fe3e-148">Se você criar um certificado autoassinado, certifique-se de habilitar a proteção forte de chave privada em seu certificado.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-148">If you create a self-signed certificate, be sure to enable strong private key protection on your certificate.</span></span> <span data-ttu-id="4fe3e-149">Isso impede que programas mal-intencionados inscrevam scripts em seu nome.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-149">This prevents malicious programs from signing scripts on your behalf.</span></span> <span data-ttu-id="4fe3e-150">As instruções estão incluídas no final deste tópico.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-150">The instructions are included at the end of this topic.</span></span>

## <a name="create-a-self-signed-certificate"></a><span data-ttu-id="4fe3e-151">Crie um certificado autoassinado</span><span class="sxs-lookup"><span data-stu-id="4fe3e-151">Create a self-signed certificate</span></span>

<span data-ttu-id="4fe3e-152">Para criar um certificado autoassinado, use o `New-SelfSignedCertificate` cmdlet no módulo PKI.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-152">To create a self-signed certificate, use the `New-SelfSignedCertificate` cmdlet in the PKI module.</span></span> <span data-ttu-id="4fe3e-153">Esse módulo é introduzido no PowerShell 3,0 e está incluído no Windows 8 e no Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-153">This module is introduced in PowerShell 3.0 and is included in Windows 8 and Windows Server 2012.</span></span> <span data-ttu-id="4fe3e-154">Para obter mais informações, consulte o tópico da ajuda para o `New-SelfSignedCertificate` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-154">For more information, see the help topic for the `New-SelfSignedCertificate` cmdlet.</span></span>

<span data-ttu-id="4fe3e-155">Para criar um certificado autoassinado em versões anteriores do Windows, use a ferramenta de criação de certificado `MakeCert.exe` .</span><span class="sxs-lookup"><span data-stu-id="4fe3e-155">To create a self-signed certificate in earlier versions of Windows, use the Certificate Creation tool `MakeCert.exe`.</span></span> <span data-ttu-id="4fe3e-156">Essa ferramenta está incluída no SDK do Microsoft .NET (versões 1,1 e posteriores) e no SDK do Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-156">This tool is included in the Microsoft .NET SDK (versions 1.1 and later) and in the Microsoft Windows SDK.</span></span>

<span data-ttu-id="4fe3e-157">Para obter mais informações sobre a sintaxe e as descrições de parâmetro da ferramenta de MakeCert.exe, consulte [ferramenta de criação de certificado (MakeCert.exe)](/previous-versions/dotnet/netframework-2.0/bfsktky3(v=vs.80)).</span><span class="sxs-lookup"><span data-stu-id="4fe3e-157">For more information about the syntax and the parameter descriptions of the MakeCert.exe tool, see [Certificate Creation Tool (MakeCert.exe)](/previous-versions/dotnet/netframework-2.0/bfsktky3(v=vs.80)).</span></span>

<span data-ttu-id="4fe3e-158">Para usar a ferramenta MakeCert.exe para criar um certificado, execute os comandos a seguir em uma janela de prompt de comando do SDK.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-158">To use the MakeCert.exe tool to create a certificate, run the following commands in an SDK Command Prompt window.</span></span>

<span data-ttu-id="4fe3e-159">Observação: o primeiro comando cria uma autoridade de certificação local para seu computador.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-159">Note: The first command creates a local certification authority for your computer.</span></span> <span data-ttu-id="4fe3e-160">O segundo comando gera um certificado pessoal da autoridade de certificação.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-160">The second command generates a personal certificate from the certification authority.</span></span>

<span data-ttu-id="4fe3e-161">Observação: você pode copiar ou digitar os comandos exatamente como eles aparecem.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-161">Note: You can copy or type the commands exactly as they appear.</span></span> <span data-ttu-id="4fe3e-162">Nenhuma substituição é necessária, embora você possa alterar o nome do certificado.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-162">No substitutions are necessary, although you can change the certificate name.</span></span>

```powershell
makecert -n "CN=PowerShell Local Certificate Root" -a sha1 `
-eku 1.3.6.1.5.5.7.3.3 -r -sv root.pvk root.cer `
-ss Root -sr localMachine

makecert -pe -n "CN=PowerShell User" -ss MY -a sha1 `
-eku 1.3.6.1.5.5.7.3.3 -iv root.pvk -ic root.cer
```

<span data-ttu-id="4fe3e-163">A ferramenta de MakeCert.exe solicitará uma senha de chave privada.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-163">The MakeCert.exe tool will prompt you for a private key password.</span></span> <span data-ttu-id="4fe3e-164">A senha garante que ninguém possa usar ou acessar o certificado sem o seu consentimento.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-164">The password ensures that no one can use or access the certificate without your consent.</span></span>
<span data-ttu-id="4fe3e-165">Crie e insira uma senha que você possa lembrar.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-165">Create and enter a password that you can remember.</span></span> <span data-ttu-id="4fe3e-166">Você usará essa senha posteriormente para recuperar o certificado.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-166">You will use this password later to retrieve the certificate.</span></span>

<span data-ttu-id="4fe3e-167">Para verificar se o certificado foi gerado corretamente, use o comando a seguir para obter o certificado no repositório de certificados no computador.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-167">To verify that the certificate was generated correctly, use the following command to get the certificate in the certificate store on the computer.</span></span> <span data-ttu-id="4fe3e-168">Você não encontrará um arquivo de certificado no diretório do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-168">You will not find a certificate file in the file system directory.</span></span>

<span data-ttu-id="4fe3e-169">No prompt do PowerShell, digite:</span><span class="sxs-lookup"><span data-stu-id="4fe3e-169">At the PowerShell prompt, type:</span></span>

```powershell
Get-ChildItem cert:\CurrentUser\my -codesigning
```

<span data-ttu-id="4fe3e-170">Esse comando usa o provedor de certificados do PowerShell para exibir informações sobre o certificado.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-170">This command uses the PowerShell Certificate provider to view information about the certificate.</span></span>

<span data-ttu-id="4fe3e-171">Se o certificado tiver sido criado, a saída mostrará a **impressão digital** que identifica o certificado em uma exibição semelhante à seguinte:</span><span class="sxs-lookup"><span data-stu-id="4fe3e-171">If the certificate was created, the output shows the **thumbprint** that identifies the certificate in a display that resembles the following:</span></span>

```Output
Directory: Microsoft.PowerShell.Security\Certificate::CurrentUser\My

Thumbprint                                Subject
----------                                -------
4D4917CB140714BA5B81B96E0B18AAF2C4564FDF  CN=PowerShell User ]
```

## <a name="sign-a-script"></a><span data-ttu-id="4fe3e-172">Assinar um script</span><span class="sxs-lookup"><span data-stu-id="4fe3e-172">Sign a script</span></span>

<span data-ttu-id="4fe3e-173">Depois de criar um certificado autoassinado, você pode assinar scripts.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-173">After you create a self-signed certificate, you can sign scripts.</span></span> <span data-ttu-id="4fe3e-174">Se você usar a política de execução **AllSigned** , assinar um script permitirá que você execute o script em seu computador.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-174">If you use the **AllSigned** execution policy, signing a script permits you to run the script on your computer.</span></span>

<span data-ttu-id="4fe3e-175">O script de exemplo a seguir, `Add-Signature.ps1` , assina um script.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-175">The following sample script, `Add-Signature.ps1`, signs a script.</span></span> <span data-ttu-id="4fe3e-176">No entanto, se você estiver usando a política de execução **AllSigned** , deverá assinar o `Add-Signature.ps1` script antes de executá-lo.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-176">However, if you are using the **AllSigned** execution policy, you must sign the `Add-Signature.ps1` script before you run it.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4fe3e-177">O script deve ser salvo usando a codificação ASCII ou UTF8NoBOM.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-177">The script must be saved using ASCII or UTF8NoBOM encoding.</span></span> <span data-ttu-id="4fe3e-178">Você pode assinar um arquivo de script que usa uma codificação diferente.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-178">You can sign a script file that uses a different encoding.</span></span> <span data-ttu-id="4fe3e-179">Mas o script não é executado ou o módulo que contém o script não é importado.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-179">But the script fails to run or the module containing the script fails to import.</span></span>

<span data-ttu-id="4fe3e-180">Para usar esse script, copie o texto a seguir em um arquivo de texto e nomeie-o `Add-Signature.ps1` .</span><span class="sxs-lookup"><span data-stu-id="4fe3e-180">To use this script, copy the following text into a text file, and name it `Add-Signature.ps1`.</span></span>

```powershell
## Signs a file
param([string] $file=$(throw "Please specify a filename."))
$cert = @(Get-ChildItem cert:\CurrentUser\My -codesigning)[0]
Set-AuthenticodeSignature $file $cert
```

<span data-ttu-id="4fe3e-181">Para assinar o `Add-Signature.ps1` arquivo de script, digite os seguintes comandos no prompt de comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4fe3e-181">To sign the `Add-Signature.ps1` script file, type the following commands at the PowerShell command prompt:</span></span>

```powershell
$cert = @(Get-ChildItem cert:\CurrentUser\My -codesigning)[0]
Set-AuthenticodeSignature add-signature.ps1 $cert
```

<span data-ttu-id="4fe3e-182">Depois que o script for assinado, você poderá executá-lo no computador local.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-182">After the script is signed, you can run it on the local computer.</span></span> <span data-ttu-id="4fe3e-183">No entanto, o script não será executado em computadores nos quais a política de execução do PowerShell requer uma assinatura digital de uma autoridade confiável.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-183">However, the script will not run on computers on which the PowerShell execution policy requires a digital signature from a trusted authority.</span></span> <span data-ttu-id="4fe3e-184">Se você tentar, o PowerShell exibirá a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="4fe3e-184">If you try, PowerShell displays the following error message:</span></span>

```Output
The file C:\remote_file.ps1 cannot be loaded. The signature of the
certificate cannot be verified.
At line:1 char:15
+ .\ remote_file.ps1 <<<<
```

<span data-ttu-id="4fe3e-185">Se o PowerShell exibir essa mensagem quando você executar um script que você não gravou, trate o arquivo como você trataria de qualquer script não assinado.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-185">If PowerShell displays this message when you run a script that you did not write, treat the file as you would treat any unsigned script.</span></span> <span data-ttu-id="4fe3e-186">Examine o código para determinar se você pode confiar no script.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-186">Review the code to determine whether you can trust the script.</span></span>

## <a name="enable-strong-private-key-protection-for-your-certificate"></a><span data-ttu-id="4fe3e-187">Habilitar a proteção de chave privada forte para seu certificado</span><span class="sxs-lookup"><span data-stu-id="4fe3e-187">Enable strong private key protection for your certificate</span></span>

<span data-ttu-id="4fe3e-188">Se você tiver um certificado particular em seu computador, programas mal-intencionados poderão assinar scripts em seu nome, o que autoriza o PowerShell a executá-los.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-188">If you have a private certificate on your computer, malicious programs might be able to sign scripts on your behalf, which authorizes PowerShell to run them.</span></span>

<span data-ttu-id="4fe3e-189">Para evitar a assinatura automatizada em seu nome, use `Certmgr.exe` o Gerenciador de certificados para exportar seu certificado de assinatura para um `.pfx` arquivo.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-189">To prevent automated signing on your behalf, use Certificate Manager `Certmgr.exe` to export your signing certificate to a `.pfx` file.</span></span> <span data-ttu-id="4fe3e-190">O Gerenciador de certificados está incluído no SDK do Microsoft .NET, no SDK do Microsoft Windows e no Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-190">Certificate Manager is included in the Microsoft .NET SDK, the Microsoft Windows SDK, and in internet Explorer.</span></span>

<span data-ttu-id="4fe3e-191">Para exportar o certificado:</span><span class="sxs-lookup"><span data-stu-id="4fe3e-191">To export the certificate:</span></span>

1. <span data-ttu-id="4fe3e-192">Inicie o Gerenciador de certificados.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-192">Start Certificate Manager.</span></span>
2. <span data-ttu-id="4fe3e-193">Selecione o certificado emitido pela raiz do certificado local do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-193">Select the certificate issued by PowerShell Local Certificate Root.</span></span>
3. <span data-ttu-id="4fe3e-194">Clique em exportar para iniciar o assistente para exportação de certificados.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-194">Click Export to start the Certificate Export Wizard.</span></span>
4. <span data-ttu-id="4fe3e-195">Selecione "Sim, exportar a chave privada" e clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-195">Select "Yes, export the private key", and then click Next.</span></span>
5. <span data-ttu-id="4fe3e-196">Selecione "Habilitar proteção forte".</span><span class="sxs-lookup"><span data-stu-id="4fe3e-196">Select "Enable strong protection."</span></span>
6. <span data-ttu-id="4fe3e-197">Digite uma senha e, em seguida, digite-a novamente para confirmar.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-197">Type a password, and then type it again to confirm.</span></span>
7. <span data-ttu-id="4fe3e-198">Digite um nome de arquivo que tenha a extensão de nome de arquivo. pfx.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-198">Type a file name that has the .pfx file name extension.</span></span>
8. <span data-ttu-id="4fe3e-199">Clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-199">Click Finish.</span></span>

<span data-ttu-id="4fe3e-200">Para importar novamente o certificado:</span><span class="sxs-lookup"><span data-stu-id="4fe3e-200">To re-import the certificate:</span></span>

1. <span data-ttu-id="4fe3e-201">Inicie o Gerenciador de certificados.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-201">Start Certificate Manager.</span></span>
2. <span data-ttu-id="4fe3e-202">Clique em importar para iniciar o assistente para importação de certificados.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-202">Click Import to start the Certificate Import Wizard.</span></span>
3. <span data-ttu-id="4fe3e-203">Abra o local do arquivo. pfx que você criou durante o processo de exportação.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-203">Open to the location of the .pfx file that you created during the export process.</span></span>
4. <span data-ttu-id="4fe3e-204">Na página senha, selecione "Habilitar proteção de chave privada forte" e insira a senha que você atribuiu durante o processo de exportação.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-204">On the Password page, select "Enable strong private key protection", and then enter the password that you assigned during the export process.</span></span>
5. <span data-ttu-id="4fe3e-205">Selecione o repositório de certificados pessoal.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-205">Select the Personal certificate store.</span></span>
6. <span data-ttu-id="4fe3e-206">Clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-206">Click Finish.</span></span>

## <a name="prevent-the-signature-from-expiring"></a><span data-ttu-id="4fe3e-207">Impedir que a assinatura expire</span><span class="sxs-lookup"><span data-stu-id="4fe3e-207">Prevent the signature from expiring</span></span>

<span data-ttu-id="4fe3e-208">A assinatura digital em um script é válida até que o certificado de autenticação expire ou desde que um servidor de carimbo de data/hora possa verificar se o script foi assinado enquanto o certificado de autenticação era válido.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-208">The digital signature in a script is valid until the signing certificate expires or as long as a timestamp server can verify that the script was signed while the signing certificate was valid.</span></span>

<span data-ttu-id="4fe3e-209">Como a maioria dos certificados de assinatura são válidos somente por um ano, o uso de um servidor de carimbo de data/hora garante que os usuários possam usar seu script por muitos anos.</span><span class="sxs-lookup"><span data-stu-id="4fe3e-209">Because most signing certificates are valid for one year only, using a time stamp server ensures that users can use your script for many years to come.</span></span>

## <a name="see-also"></a><span data-ttu-id="4fe3e-210">Confira também</span><span class="sxs-lookup"><span data-stu-id="4fe3e-210">See also</span></span>

[<span data-ttu-id="4fe3e-211">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="4fe3e-211">about_Execution_Policies</span></span>](about_Execution_Policies.md)

[<span data-ttu-id="4fe3e-212">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="4fe3e-212">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="4fe3e-213">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="4fe3e-213">Get-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Get-ExecutionPolicy)

[<span data-ttu-id="4fe3e-214">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="4fe3e-214">Set-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)

[<span data-ttu-id="4fe3e-215">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="4fe3e-215">Set-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

<span data-ttu-id="4fe3e-216">[Introdução à assinatura de código](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537361(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="4fe3e-216">[Introduction to Code Signing](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537361(v=vs.85))</span></span>
