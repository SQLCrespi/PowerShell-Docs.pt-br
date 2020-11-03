---
description: Explica as limitações do Windows PowerShell 4,0 no Windows RT 8,1.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_windows_rt?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_RT
ms.openlocfilehash: 323f06a7a0d8253417510503c1011ac02c20179f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195943"
---
# <a name="about-windows-rt"></a><span data-ttu-id="47e12-104">Sobre o Windows RT</span><span class="sxs-lookup"><span data-stu-id="47e12-104">About Windows RT</span></span>

## <a name="short-description"></a><span data-ttu-id="47e12-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="47e12-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="47e12-106">Explica as limitações do Windows PowerShell 4,0 no Windows RT 8,1.</span><span class="sxs-lookup"><span data-stu-id="47e12-106">Explains limitations of  Windows PowerShell 4.0 on Windows RT 8.1.</span></span>

## <a name="long-description"></a><span data-ttu-id="47e12-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="47e12-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="47e12-108">O sistema operacional Windows RT 8,1 é instalado em computadores e dispositivos (como o Microsoft Surface 2, no qual é o sistema operacional fornecido com o computador) que usam processadores ARM (Advanced RISC Machine).</span><span class="sxs-lookup"><span data-stu-id="47e12-108">The Windows RT 8.1 operating system is installed on computers and devices (such as Microsoft Surface 2, on which it is the operating system that ships with the computer) that use Advanced RISC Machine (ARM) processors.</span></span>

<span data-ttu-id="47e12-109">O Windows PowerShell 4,0 está incluído no Windows RT 8,1.</span><span class="sxs-lookup"><span data-stu-id="47e12-109">Windows PowerShell 4.0 is included in Windows RT 8.1.</span></span> <span data-ttu-id="47e12-110">Todos os cmdlets, provedores e módulos e a maioria dos scripts projetados para o Windows PowerShell 2,0 e versões posteriores são executados no Windows RT 8,1 sem alterações.</span><span class="sxs-lookup"><span data-stu-id="47e12-110">All cmdlets, providers, and modules, and most scripts designed for Windows PowerShell 2.0 and later releases run on Windows RT 8.1 without changes.</span></span>

<span data-ttu-id="47e12-111">Como o Windows RT 8,1 não inclui todos os recursos do Windows, alguns recursos do Windows PowerShell funcionam de maneira diferente ou não funcionam em dispositivos baseados no Windows RT.</span><span class="sxs-lookup"><span data-stu-id="47e12-111">Because Windows RT 8.1 does not include all Windows features, some Windows PowerShell features work differently or do not work on Windows RT-based devices.</span></span> <span data-ttu-id="47e12-112">A lista a seguir explica as diferenças.</span><span class="sxs-lookup"><span data-stu-id="47e12-112">The following list explains the differences.</span></span>

- <span data-ttu-id="47e12-113">O ISE do Windows PowerShell não está incluído no e não pode ser executado no Windows RT 8,1.</span><span class="sxs-lookup"><span data-stu-id="47e12-113">Windows PowerShell ISE is not included in and cannot run on Windows RT 8.1.</span></span>
  <span data-ttu-id="47e12-114">ISE do Windows PowerShell requer Windows Presentation Foundation, que não está incluído no Windows RT 8,1.</span><span class="sxs-lookup"><span data-stu-id="47e12-114">Windows PowerShell ISE requires Windows Presentation Foundation, which is not included in Windows RT 8.1.</span></span>

- <span data-ttu-id="47e12-115">A comunicação remota do Windows PowerShell e o serviço WinRM são desabilitados por padrão.</span><span class="sxs-lookup"><span data-stu-id="47e12-115">Windows PowerShell remoting and the WinRM service are disabled by default.</span></span>
  <span data-ttu-id="47e12-116">Para habilitar a comunicação remota, execute o cmdlet Enable-PSRemoting.</span><span class="sxs-lookup"><span data-stu-id="47e12-116">To enable remoting, run the Enable-PSRemoting cmdlet.</span></span> <span data-ttu-id="47e12-117">Além disso, execute o cmdlet Set-Service para definir o tipo de inicialização do serviço WinRM como automático ou automático (início atrasado).</span><span class="sxs-lookup"><span data-stu-id="47e12-117">Also, run the Set-Service cmdlet to set the startup type of the WinRM service to Automatic, or Automatic (Delayed Start).</span></span>

  <span data-ttu-id="47e12-118">Embora a comunicação remota esteja desabilitada, você pode usar a comunicação remota do Windows PowerShell para executar comandos em outros computadores, mas outros computadores não podem executar comandos no dispositivo Windows RT.</span><span class="sxs-lookup"><span data-stu-id="47e12-118">While remoting is disabled, you can use Windows PowerShell remoting to run commands on other computers, but other computers cannot run commands on the Windows RT device.</span></span> <span data-ttu-id="47e12-119">Além disso, comunicação remota implícita, ou seja, a comunicação remota que é interna a um cmdlet ou script, e não explicitamente solicitada com parâmetros adicionados</span><span class="sxs-lookup"><span data-stu-id="47e12-119">Also, implicit remoting - that is, remoting that is built in to a cmdlet or script, and not explicitly requested with added parameters</span></span>
  - <span data-ttu-id="47e12-120">o não funciona no Windows PowerShell em execução no Windows RT 8,1.</span><span class="sxs-lookup"><span data-stu-id="47e12-120">does not work in Windows PowerShell running on Windows RT 8.1.</span></span>

- <span data-ttu-id="47e12-121">A computação ingressada no domínio e a autenticação Kerberos não têm suporte no Windows RT 8,1.</span><span class="sxs-lookup"><span data-stu-id="47e12-121">Domain-joined computing and Kerberos authentication are not supported on Windows RT 8.1.</span></span> <span data-ttu-id="47e12-122">Você não pode usar o Windows PowerShell para adicionar ou gerenciar esses recursos.</span><span class="sxs-lookup"><span data-stu-id="47e12-122">You cannot use Windows PowerShell to add or manage these features.</span></span>

- <span data-ttu-id="47e12-123">Microsoft .NET classes do Framework que não têm suporte no Windows RT 8,1 também não são suportadas pelo Windows PowerShell no Windows RT 8,1.</span><span class="sxs-lookup"><span data-stu-id="47e12-123">Microsoft .NET Framework classes that are not supported on Windows RT 8.1 are also not supported by Windows PowerShell on Windows RT 8.1.</span></span>

- <span data-ttu-id="47e12-124">As transações não estão habilitadas no Windows RT 8,1.</span><span class="sxs-lookup"><span data-stu-id="47e12-124">Transactions are not enabled on Windows RT 8.1.</span></span> <span data-ttu-id="47e12-125">Os cmdlets de transação, como a transação inicial e os parâmetros de transação, como UseTransaction, não funcionam corretamente.</span><span class="sxs-lookup"><span data-stu-id="47e12-125">Transaction cmdlets, such as Start-Transaction, and transaction parameters, such as UseTransaction, do not work properly.</span></span>

- <span data-ttu-id="47e12-126">Todas as sessões do Windows PowerShell em dispositivos Windows RT 8,1 usam o modo de linguagem ConstrainedLanguage.</span><span class="sxs-lookup"><span data-stu-id="47e12-126">All Windows PowerShell sessions on Windows RT 8.1 devices use the ConstrainedLanguage language mode.</span></span> <span data-ttu-id="47e12-127">O modo de linguagem ConstrainedLanguage é um complemento à integridade de código do modo de usuário (UMCI).</span><span class="sxs-lookup"><span data-stu-id="47e12-127">ConstrainedLanguage language mode is a companion to User Mode Code Integrity (UMCI).</span></span> <span data-ttu-id="47e12-128">Ele permite todos os cmdlets do Windows e elementos de linguagem do Windows PowerShell, mas restringe os tipos para garantir que os usuários não possam usar o Windows PowerShell para burlar ou violar as proteções UMCI.</span><span class="sxs-lookup"><span data-stu-id="47e12-128">It permits all Windows cmdlets and Windows PowerShell language elements, but restricts types to ensure that users cannot use Windows PowerShell to circumvent or violate the UMCI protections.</span></span>

<span data-ttu-id="47e12-129">Para obter mais informações sobre o modo de linguagem ConstrainedLanguage, consulte [about_Language_Modes](about_Language_Modes.md).</span><span class="sxs-lookup"><span data-stu-id="47e12-129">For more information about ConstrainedLanguage language mode, see [about_Language_Modes](about_Language_Modes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="47e12-130">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="47e12-130">SEE ALSO</span></span>

[<span data-ttu-id="47e12-131">about_Language_Modes</span><span class="sxs-lookup"><span data-stu-id="47e12-131">about_Language_Modes</span></span>](about_Language_Modes.md)

[<span data-ttu-id="47e12-132">about_Remote</span><span class="sxs-lookup"><span data-stu-id="47e12-132">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="47e12-133">about_Windows_PowerShell_ISE</span><span class="sxs-lookup"><span data-stu-id="47e12-133">about_Windows_PowerShell_ISE</span></span>](about_Windows_PowerShell_ISE.md)
