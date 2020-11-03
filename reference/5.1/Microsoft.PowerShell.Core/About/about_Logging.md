---
description: O PowerShell registra em log as operações internas do mecanismo, provedores e cmdlets.
keywords: powershell
Locale: en-US
ms.date: 12/14/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_logging?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Logging
ms.openlocfilehash: 5d061b38b5b0fa45cf0a86c2f5b7e0efcb8d1f7b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196010"
---
# <a name="about-logging"></a><span data-ttu-id="66a7e-104">Sobre registro em log</span><span class="sxs-lookup"><span data-stu-id="66a7e-104">About Logging</span></span>

## <a name="short-description"></a><span data-ttu-id="66a7e-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="66a7e-105">Short description</span></span>

<span data-ttu-id="66a7e-106">O PowerShell registra em log as operações internas do mecanismo, provedores e cmdlets.</span><span class="sxs-lookup"><span data-stu-id="66a7e-106">PowerShell logs internal operations from the engine, providers, and cmdlets.</span></span>

## <a name="long-description"></a><span data-ttu-id="66a7e-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="66a7e-107">Long description</span></span>

<span data-ttu-id="66a7e-108">O PowerShell registra detalhes sobre as operações do PowerShell, como iniciar e interromper o mecanismo e os provedores e executar comandos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="66a7e-108">PowerShell logs details about PowerShell operations, such as starting and stopping the engine and providers, and executing PowerShell commands.</span></span>

> [!NOTE]
> <span data-ttu-id="66a7e-109">As versões 3,0, 4,0, 5,0 e 5,1 do Windows PowerShell incluem cmdlets do **EventLog** para os logs de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="66a7e-109">Windows PowerShell versions 3.0, 4.0, 5.0, and 5.1 include **EventLog** cmdlets for the Windows event logs.</span></span> <span data-ttu-id="66a7e-110">Nessas versões, para exibir a lista de cmdlets do **EventLog** , digite: `Get-Command -Noun EventLog` .</span><span class="sxs-lookup"><span data-stu-id="66a7e-110">In those versions, to display the list of **EventLog** cmdlets type: `Get-Command -Noun EventLog`.</span></span> <span data-ttu-id="66a7e-111">Para obter mais informações, consulte a documentação do cmdlet e about_EventLogs para sua versão do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="66a7e-111">For more information, see the cmdlet documentation and about_EventLogs for your version of Windows PowerShell.</span></span>

## <a name="viewing-the-powershell-event-log-entries-on-windows"></a><span data-ttu-id="66a7e-112">Exibindo as entradas do log de eventos do PowerShell no Windows</span><span class="sxs-lookup"><span data-stu-id="66a7e-112">Viewing the PowerShell event log entries on Windows</span></span>

<span data-ttu-id="66a7e-113">Os logs do PowerShell podem ser exibidos usando o Windows Visualizador de Eventos.</span><span class="sxs-lookup"><span data-stu-id="66a7e-113">PowerShell logs can be viewed using the Windows Event Viewer.</span></span> <span data-ttu-id="66a7e-114">O log de eventos está localizado no grupo logs de aplicativos e serviços e é nomeado `Microsoft-Windows-PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="66a7e-114">The event log is located in the Application and Services Logs group and is named `Microsoft-Windows-PowerShell`.</span></span> <span data-ttu-id="66a7e-115">O provedor de ETW associado `GUID` é `{A0C1853B-5C40-4B15-8766-3CF1C58F985A}` .</span><span class="sxs-lookup"><span data-stu-id="66a7e-115">The associated ETW provider `GUID` is `{A0C1853B-5C40-4B15-8766-3CF1C58F985A}`.</span></span>

<span data-ttu-id="66a7e-116">Quando o log de bloco de script estiver habilitado, o PowerShell registrará os seguintes eventos no `Microsoft-Windows-PowerShell/Operational` log:</span><span class="sxs-lookup"><span data-stu-id="66a7e-116">When Script Block Logging is enabled, PowerShell logs the following events to the `Microsoft-Windows-PowerShell/Operational` log:</span></span>

|<span data-ttu-id="66a7e-117">Campo</span><span class="sxs-lookup"><span data-stu-id="66a7e-117">Field</span></span>| <span data-ttu-id="66a7e-118">Valor</span><span class="sxs-lookup"><span data-stu-id="66a7e-118">Value</span></span>|
|-|-|
|<span data-ttu-id="66a7e-119">EventId</span><span class="sxs-lookup"><span data-stu-id="66a7e-119">EventId</span></span>|`4104` / `0x1008`|
|<span data-ttu-id="66a7e-120">Canal</span><span class="sxs-lookup"><span data-stu-id="66a7e-120">Channel</span></span>|`Operational`|
|<span data-ttu-id="66a7e-121">Nível</span><span class="sxs-lookup"><span data-stu-id="66a7e-121">Level</span></span>|`Verbose`|
|<span data-ttu-id="66a7e-122">Opcode</span><span class="sxs-lookup"><span data-stu-id="66a7e-122">Opcode</span></span>|`Create`|
|<span data-ttu-id="66a7e-123">Tarefa</span><span class="sxs-lookup"><span data-stu-id="66a7e-123">Task</span></span>|`CommandStart`|
|<span data-ttu-id="66a7e-124">Palavra-chave</span><span class="sxs-lookup"><span data-stu-id="66a7e-124">Keyword</span></span>|`Runspace`|

## <a name="enabling-script-block-logging"></a><span data-ttu-id="66a7e-125">Habilitando o log de bloco de script</span><span class="sxs-lookup"><span data-stu-id="66a7e-125">Enabling Script Block Logging</span></span>

<span data-ttu-id="66a7e-126">Quando você habilita o log de bloco de script, o PowerShell registra o conteúdo de todos os blocos de script que ele processa.</span><span class="sxs-lookup"><span data-stu-id="66a7e-126">When you enable Script Block Logging, PowerShell records the content of all script blocks that it processes.</span></span> <span data-ttu-id="66a7e-127">Uma vez habilitada, qualquer sessão do PowerShell nova registra essas informações.</span><span class="sxs-lookup"><span data-stu-id="66a7e-127">Once enabled, any new PowerShell session logs this information.</span></span>

> [!NOTE]
> <span data-ttu-id="66a7e-128">É recomendável habilitar o log de eventos protegidos, conforme descrito abaixo, ao usar o log de bloco de script para algo diferente de fins de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="66a7e-128">It's recommended to enable Protected Event Logging, as described below, when using Script Block Logging for anything other than diagnostics purposes.</span></span>

<span data-ttu-id="66a7e-129">O log de bloco de script pode ser habilitado via Política de Grupo ou uma configuração de registro.</span><span class="sxs-lookup"><span data-stu-id="66a7e-129">Script Block Logging can be enabled via Group Policy or a registry setting.</span></span>

### <a name="using-group-policy"></a><span data-ttu-id="66a7e-130">Como usar a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="66a7e-130">Using Group Policy</span></span>

<span data-ttu-id="66a7e-131">Para habilitar a transcrição automática, habilite o `Turn on PowerShell Script Block
Logging` recurso no política de grupo por meio do `Administrative Templates -> Windows
Components -> Windows PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="66a7e-131">To enable automatic transcription, enable the `Turn on PowerShell Script Block
Logging` feature in Group Policy through `Administrative Templates -> Windows
Components -> Windows PowerShell`.</span></span>

### <a name="using-the-registry"></a><span data-ttu-id="66a7e-132">Usando o registro</span><span class="sxs-lookup"><span data-stu-id="66a7e-132">Using the Registry</span></span>

<span data-ttu-id="66a7e-133">Execute a seguinte função:</span><span class="sxs-lookup"><span data-stu-id="66a7e-133">Run the following function:</span></span>

```powershell
function Enable-PSScriptBlockLogging
{
    $basePath = 'HKLM:\Software\Policies\Microsoft\Windows' +
      '\PowerShell\ScriptBlockLogging'

    if(-not (Test-Path $basePath))
    {
        $null = New-Item $basePath -Force
    }

    Set-ItemProperty $basePath -Name EnableScriptBlockLogging -Value "1"
}
```

## <a name="protected-event-logging"></a><span data-ttu-id="66a7e-134">Log de eventos protegidos</span><span class="sxs-lookup"><span data-stu-id="66a7e-134">Protected Event Logging</span></span>

<span data-ttu-id="66a7e-135">Aumentar o nível de log em um sistema aumenta a possibilidade de que o conteúdo registrado possa conter dados confidenciais.</span><span class="sxs-lookup"><span data-stu-id="66a7e-135">Increasing the level of logging on a system increases the possibility that logged content may contain sensitive data.</span></span> <span data-ttu-id="66a7e-136">Por exemplo, com o log de script habilitado, as credenciais ou outros dados confidenciais usados por um script podem ser gravados no log de eventos.</span><span class="sxs-lookup"><span data-stu-id="66a7e-136">For example, with script logging enabled, credentials or other sensitive data used by a script can be written to the event log.</span></span> <span data-ttu-id="66a7e-137">Quando um computador que tem dados confidenciais registrados em log é comprometido, os logs podem fornecer a um invasor as informações necessárias para estender seu alcance.</span><span class="sxs-lookup"><span data-stu-id="66a7e-137">When a machine that has logged sensitive data is compromised, the logs can provide an attacker with information needed to extend their reach.</span></span>

<span data-ttu-id="66a7e-138">Para proteger essas informações, o Windows 10 apresenta o registro em log de eventos protegido.</span><span class="sxs-lookup"><span data-stu-id="66a7e-138">To protect this information, Windows 10 introduces Protected Event Logging.</span></span>
<span data-ttu-id="66a7e-139">O log de eventos protegido permite que os aplicativos participantes criptografem os dados confidenciais gravados no log de eventos.</span><span class="sxs-lookup"><span data-stu-id="66a7e-139">Protected Event Logging lets participating applications encrypt sensitive data written to the event log.</span></span> <span data-ttu-id="66a7e-140">Posteriormente, você pode descriptografar e processar esses logs em um coletor de logs mais seguro e centralizado.</span><span class="sxs-lookup"><span data-stu-id="66a7e-140">Later, you can decrypt and process these logs on a more secure and centralized log collector.</span></span>

<span data-ttu-id="66a7e-141">O conteúdo do log de eventos é protegido usando o padrão de CMS (sintaxe de mensagem criptográfica) da IETF.</span><span class="sxs-lookup"><span data-stu-id="66a7e-141">Event log content is protected using the IETF Cryptographic Message Syntax (CMS) standard.</span></span> <span data-ttu-id="66a7e-142">O CMS usa criptografia de chave pública.</span><span class="sxs-lookup"><span data-stu-id="66a7e-142">CMS uses public key cryptography.</span></span> <span data-ttu-id="66a7e-143">As chaves usadas para criptografar conteúdo e descriptografar conteúdo são mantidas separadas.</span><span class="sxs-lookup"><span data-stu-id="66a7e-143">The keys used to encrypt content and decrypt content are kept separate.</span></span>

<span data-ttu-id="66a7e-144">A chave pública pode ser compartilhada amplamente e não dados confidenciais.</span><span class="sxs-lookup"><span data-stu-id="66a7e-144">The public key can be shared widely and isn't sensitive data.</span></span> <span data-ttu-id="66a7e-145">Qualquer conteúdo criptografado com essa chave pública só pode ser descriptografado pela chave privada.</span><span class="sxs-lookup"><span data-stu-id="66a7e-145">Any content encrypted with this public key can only be decrypted by the private key.</span></span> <span data-ttu-id="66a7e-146">Para obter mais informações sobre criptografia de chave pública, consulte [Wikipédia-criptografia de chave pública](https://en.wikipedia.org/wiki/Public-key_cryptography).</span><span class="sxs-lookup"><span data-stu-id="66a7e-146">For more information about Public Key Cryptography, see [Wikipedia - Public Key Cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).</span></span>

<span data-ttu-id="66a7e-147">Para habilitar uma política de log de eventos protegida, implante uma chave pública em todos os computadores que têm dados de log de eventos a serem protegidos.</span><span class="sxs-lookup"><span data-stu-id="66a7e-147">To enable a Protected Event Logging policy, deploy a public key to all machines that have event log data to protect.</span></span> <span data-ttu-id="66a7e-148">A chave privada correspondente é usada para processar os logs de eventos em um local mais seguro, como um coletor de log de eventos central ou um agregador [Siem][] .</span><span class="sxs-lookup"><span data-stu-id="66a7e-148">The corresponding private key is used to post-process the event logs at a more secure location such as a central event log collector, or [SIEM][] aggregator.</span></span> <span data-ttu-id="66a7e-149">Você pode configurar o SIEM no Azure.</span><span class="sxs-lookup"><span data-stu-id="66a7e-149">You can set up SIEM in Azure.</span></span> <span data-ttu-id="66a7e-150">Para obter mais informações, consulte [integração de Siem genérico](/cloud-app-security/siem).</span><span class="sxs-lookup"><span data-stu-id="66a7e-150">For more information, see [Generic SIEM integration](/cloud-app-security/siem).</span></span>

### <a name="enabling-protected-event-logging-via-group-policy"></a><span data-ttu-id="66a7e-151">Habilitando o log de eventos protegidos via Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="66a7e-151">Enabling Protected Event Logging via Group Policy</span></span>

<span data-ttu-id="66a7e-152">Para habilitar o log de eventos protegidos, habilite o `Enable Protected Event Logging` recurso no política de grupo por meio do `Administrative Templates -> Windows Components
-> Event Logging` .</span><span class="sxs-lookup"><span data-stu-id="66a7e-152">To enable Protected Event Logging, enable the `Enable Protected Event Logging` feature in Group Policy through `Administrative Templates -> Windows Components
-> Event Logging`.</span></span> <span data-ttu-id="66a7e-153">Essa configuração requer um certificado de criptografia, que você pode fornecer em uma das várias formas:</span><span class="sxs-lookup"><span data-stu-id="66a7e-153">This setting requires an encryption certificate, which you can provide in one of several forms:</span></span>

- <span data-ttu-id="66a7e-154">O conteúdo de um certificado X. 509 codificado em base-64 (por exemplo, conforme oferecido pela `Export` opção no Gerenciador de certificados).</span><span class="sxs-lookup"><span data-stu-id="66a7e-154">The content of a base-64 encoded X.509 certificate (for example, as offered by the `Export` option in Certificate Manager).</span></span>
- <span data-ttu-id="66a7e-155">A impressão digital de um certificado que pode ser encontrado no repositório de certificados do computador local (pode ser implantado pela infraestrutura PKI).</span><span class="sxs-lookup"><span data-stu-id="66a7e-155">The thumbprint of a certificate that can be found in the Local Machine certificate store (can be deployed by PKI infrastructure).</span></span>
- <span data-ttu-id="66a7e-156">O caminho completo de um certificado (pode ser local ou um compartilhamento remoto).</span><span class="sxs-lookup"><span data-stu-id="66a7e-156">The full path to a certificate (can be local, or a remote share).</span></span>
- <span data-ttu-id="66a7e-157">O caminho para um diretório que contém um certificado ou certificados (pode ser local ou um compartilhamento remoto).</span><span class="sxs-lookup"><span data-stu-id="66a7e-157">The path to a directory containing a certificate or certificates (can be local, or a remote share).</span></span>
- <span data-ttu-id="66a7e-158">O nome da entidade de um certificado que pode ser encontrado no repositório de certificados do computador local (pode ser implantado pela infraestrutura PKI).</span><span class="sxs-lookup"><span data-stu-id="66a7e-158">The subject name of a certificate that can be found in the Local Machine certificate store (can be deployed by PKI infrastructure).</span></span>

<span data-ttu-id="66a7e-159">O certificado resultante deve ter `Document Encryption` como um uso avançado de chave ( `1.3.6.1.4.1.311.80.1` ) e um `Data Encipherment` ou mais `Key
Encipherment` usos de chave habilitados.</span><span class="sxs-lookup"><span data-stu-id="66a7e-159">The resulting certificate must have `Document Encryption` as an enhanced key usage (`1.3.6.1.4.1.311.80.1`), and either `Data Encipherment` or `Key
Encipherment` key usages enabled.</span></span>

> [!WARNING]
> <span data-ttu-id="66a7e-160">A chave privada não deve ser implantada nos eventos de log de máquinas.</span><span class="sxs-lookup"><span data-stu-id="66a7e-160">The private key shouldn't be deployed to the machines logging events.</span></span> <span data-ttu-id="66a7e-161">Ele deve ser mantido em um local seguro onde você descriptografa as mensagens.</span><span class="sxs-lookup"><span data-stu-id="66a7e-161">It should be kept in a secure location where you decrypt the messages.</span></span>

### <a name="decrypting-protected-event-logging-messages"></a><span data-ttu-id="66a7e-162">Descriptografando mensagens de log de eventos protegidas</span><span class="sxs-lookup"><span data-stu-id="66a7e-162">Decrypting Protected Event Logging messages</span></span>

<span data-ttu-id="66a7e-163">O script a seguir irá recuperar e descriptografar, supondo que você tenha a chave privada:</span><span class="sxs-lookup"><span data-stu-id="66a7e-163">The following script will retrieve and decrypt, assuming that you have the private key:</span></span>

```powershell
Get-WinEvent Microsoft-Windows-PowerShell/Operational |
  Where-Object Id -eq 4104 | Unprotect-CmsMessage
```

## <a name="see-also"></a><span data-ttu-id="66a7e-164">Confira também</span><span class="sxs-lookup"><span data-stu-id="66a7e-164">See also</span></span>

[<span data-ttu-id="66a7e-165">PowerShell para a equipe azul</span><span class="sxs-lookup"><span data-stu-id="66a7e-165">PowerShell the Blue Team</span></span>](https://devblogs.microsoft.com/powershell/powershell-the-blue-team/)

[<span data-ttu-id="66a7e-166">Integração genérica ao SIEM</span><span class="sxs-lookup"><span data-stu-id="66a7e-166">Generic SIEM integration</span></span>](/cloud-app-security/siem)

<!-- link references -->
[SIEM]: https://wikipedia.org/wiki/Security_information_and_event_management
