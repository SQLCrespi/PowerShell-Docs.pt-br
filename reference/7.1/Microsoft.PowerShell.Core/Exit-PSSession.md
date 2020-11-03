---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pssession?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSSession
ms.openlocfilehash: f6123bca498d753de1fe284d48f29407c3f8a465
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2020
ms.locfileid: "93192650"
---
# <span data-ttu-id="e1f75-103">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="e1f75-103">Exit-PSSession</span></span>

## <span data-ttu-id="e1f75-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="e1f75-104">SYNOPSIS</span></span>
<span data-ttu-id="e1f75-105">Encerra uma sessão interativa com um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="e1f75-105">Ends an interactive session with a remote computer.</span></span>

## <span data-ttu-id="e1f75-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e1f75-106">SYNTAX</span></span>

```
Exit-PSSession [<CommonParameters>]
```

## <span data-ttu-id="e1f75-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e1f75-107">DESCRIPTION</span></span>

<span data-ttu-id="e1f75-108">O cmdlet **Exit-PSSession** encerra as sessões interativas que você iniciou usando o cmdlet Enter-PSSession.</span><span class="sxs-lookup"><span data-stu-id="e1f75-108">The **Exit-PSSession** cmdlet ends interactive sessions that you started by using the Enter-PSSession cmdlet.</span></span>

<span data-ttu-id="e1f75-109">Você também pode usar a palavra-chave **Exit** para encerrar uma sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="e1f75-109">You can also use the **Exit** keyword to end an interactive session.</span></span>
<span data-ttu-id="e1f75-110">O efeito é o mesmo que usar **Exit-PSSession** .</span><span class="sxs-lookup"><span data-stu-id="e1f75-110">The effect is the same as using **Exit-PSSession** .</span></span>

## <span data-ttu-id="e1f75-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="e1f75-111">EXAMPLES</span></span>

### <span data-ttu-id="e1f75-112">Exemplo 1: Iniciar e parar uma sessão interativa</span><span class="sxs-lookup"><span data-stu-id="e1f75-112">Example 1: Start and stop an interactive session</span></span>

```
PS> Enter-PSSession -computername Server01
Server01\PS> Exit-PSSession
PS>
```

<span data-ttu-id="e1f75-113">Esses comandos iniciam e param uma sessão interativa com o computador remoto Server01.</span><span class="sxs-lookup"><span data-stu-id="e1f75-113">These commands start and then stop an interactive session with the Server01 remote computer.</span></span>

### <span data-ttu-id="e1f75-114">Exemplo 2: Iniciar e parar uma sessão interativa usando um objeto PSSession</span><span class="sxs-lookup"><span data-stu-id="e1f75-114">Example 2: Start and stop an interactive session by using a PSSession object</span></span>

```
PS> $s = New-PSSession -ComputerName Server01
PS> Enter-PSSession -Session $s
Server01\PS> Exit-PSSession
PS> $s
Id Name            ComputerName    State    ConfigurationName
-- ----            ------------    -----    -----------------
1  Session1        Server01        Opened   Microsoft.PowerShell
```

<span data-ttu-id="e1f75-115">Esses comandos iniciam e param uma sessão interativa com o computador Server01 que usa uma sessão do PowerShell ( **PSSession** ).</span><span class="sxs-lookup"><span data-stu-id="e1f75-115">These commands start and stop an interactive session with the Server01 computer that uses a PowerShell session ( **PSSession** ).</span></span>

<span data-ttu-id="e1f75-116">Como a sessão interativa foi iniciada usando uma sessão do PowerShell, a **PSSession** ainda está disponível quando a sessão interativa termina.</span><span class="sxs-lookup"><span data-stu-id="e1f75-116">Because the interactive session was started by using a PowerShell session, the **PSSession** is still available when the interactive session ends.</span></span>
<span data-ttu-id="e1f75-117">Se você usar o parâmetro *ComputerName* , **Enter-PSSession** criará uma sessão temporária que será fechada quando a sessão interativa terminar.</span><span class="sxs-lookup"><span data-stu-id="e1f75-117">If you use the *ComputerName* parameter, **Enter-PSSession** creates a temporary session that it closes when the interactive session ends.</span></span>

<span data-ttu-id="e1f75-118">O primeiro comando usa o cmdlet New-PSSession para criar uma **PSSession** no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="e1f75-118">The first command uses the New-PSSession cmdlet to create a **PSSession** on the Server01 computer.</span></span>
<span data-ttu-id="e1f75-119">O comando salva a **PSSession** na variável $s.</span><span class="sxs-lookup"><span data-stu-id="e1f75-119">The command saves the **PSSession** in the $s variable.</span></span>

<span data-ttu-id="e1f75-120">O segundo comando usa **Enter-PSSession** para iniciar uma sessão interativa usando a **PSSession** em $s.</span><span class="sxs-lookup"><span data-stu-id="e1f75-120">The second command uses **Enter-PSSession** to start an interactive session using the **PSSession** in $s.</span></span>

<span data-ttu-id="e1f75-121">O terceiro comando usa **Exit-PSSession** para interromper a sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="e1f75-121">The third command uses **Exit-PSSession** to stop the interactive session.</span></span>

<span data-ttu-id="e1f75-122">O comando final exibe a **PSSession** na variável $s.</span><span class="sxs-lookup"><span data-stu-id="e1f75-122">The final command displays the **PSSession** in the $s variable.</span></span>
<span data-ttu-id="e1f75-123">A propriedade **State** mostra que **PSSession** ainda está aberto e disponível para uso.</span><span class="sxs-lookup"><span data-stu-id="e1f75-123">The **State** property shows the **PSSession** is still open and available for use.</span></span>

### <span data-ttu-id="e1f75-124">Exemplo 3: usar a palavra-chave EXIT para interromper uma sessão</span><span class="sxs-lookup"><span data-stu-id="e1f75-124">Example 3: Use the Exit keyword to stop a session</span></span>

```
PS> Enter-PSSession -computername Server01
Server01\PS> exit
PS>
```

<span data-ttu-id="e1f75-125">Este exemplo usa a palavra-chave **Exit** para interromper uma sessão interativa iniciada usando **Enter-PSSession** .</span><span class="sxs-lookup"><span data-stu-id="e1f75-125">This example uses the **Exit** keyword to stop an interactive session started by using **Enter-PSSession** .</span></span>
<span data-ttu-id="e1f75-126">A palavra-chave **Exit** tem o mesmo efeito que usar **Exit-PSSession** .</span><span class="sxs-lookup"><span data-stu-id="e1f75-126">The **Exit** keyword has the same effect as using **Exit-PSSession** .</span></span>

## <span data-ttu-id="e1f75-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e1f75-127">PARAMETERS</span></span>

### <span data-ttu-id="e1f75-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e1f75-128">CommonParameters</span></span>

<span data-ttu-id="e1f75-129">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e1f75-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e1f75-130">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e1f75-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e1f75-131">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="e1f75-131">INPUTS</span></span>

### <span data-ttu-id="e1f75-132">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e1f75-132">None</span></span>

<span data-ttu-id="e1f75-133">Não é possível transferir objetos para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e1f75-133">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="e1f75-134">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="e1f75-134">OUTPUTS</span></span>

### <span data-ttu-id="e1f75-135">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e1f75-135">None</span></span>

<span data-ttu-id="e1f75-136">Este cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="e1f75-136">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="e1f75-137">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="e1f75-137">NOTES</span></span>

* <span data-ttu-id="e1f75-138">Esse cmdlet usa apenas os parâmetros comuns.</span><span class="sxs-lookup"><span data-stu-id="e1f75-138">This cmdlet takes only the common parameters.</span></span>

*

## <span data-ttu-id="e1f75-139">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="e1f75-139">RELATED LINKS</span></span>

[<span data-ttu-id="e1f75-140">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="e1f75-140">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="e1f75-141">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="e1f75-141">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="e1f75-142">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="e1f75-142">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="e1f75-143">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="e1f75-143">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="e1f75-144">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="e1f75-144">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="e1f75-145">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="e1f75-145">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="e1f75-146">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="e1f75-146">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="e1f75-147">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="e1f75-147">Remove-PSSession</span></span>](Remove-PSSession.md)

