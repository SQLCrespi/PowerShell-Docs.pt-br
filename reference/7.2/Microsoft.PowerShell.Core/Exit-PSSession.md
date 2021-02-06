---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pssession?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSSession
ms.openlocfilehash: b76f7dc87105318285c930b6cd2ae4ae10c2b0e7
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597195"
---
# <span data-ttu-id="3d09f-102">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="3d09f-102">Exit-PSSession</span></span>

## <span data-ttu-id="3d09f-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="3d09f-103">SYNOPSIS</span></span>
<span data-ttu-id="3d09f-104">Encerra uma sessão interativa com um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="3d09f-104">Ends an interactive session with a remote computer.</span></span>

## <span data-ttu-id="3d09f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3d09f-105">SYNTAX</span></span>

```
Exit-PSSession [<CommonParameters>]
```

## <span data-ttu-id="3d09f-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3d09f-106">DESCRIPTION</span></span>

<span data-ttu-id="3d09f-107">O cmdlet **Exit-PSSession** encerra as sessões interativas que você iniciou usando o cmdlet Enter-PSSession.</span><span class="sxs-lookup"><span data-stu-id="3d09f-107">The **Exit-PSSession** cmdlet ends interactive sessions that you started by using the Enter-PSSession cmdlet.</span></span>

<span data-ttu-id="3d09f-108">Você também pode usar a palavra-chave **Exit** para encerrar uma sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="3d09f-108">You can also use the **Exit** keyword to end an interactive session.</span></span>
<span data-ttu-id="3d09f-109">O efeito é o mesmo que usar **Exit-PSSession**.</span><span class="sxs-lookup"><span data-stu-id="3d09f-109">The effect is the same as using **Exit-PSSession**.</span></span>

## <span data-ttu-id="3d09f-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="3d09f-110">EXAMPLES</span></span>

### <span data-ttu-id="3d09f-111">Exemplo 1: Iniciar e parar uma sessão interativa</span><span class="sxs-lookup"><span data-stu-id="3d09f-111">Example 1: Start and stop an interactive session</span></span>

```
PS> Enter-PSSession -computername Server01
Server01\PS> Exit-PSSession
PS>
```

<span data-ttu-id="3d09f-112">Esses comandos iniciam e param uma sessão interativa com o computador remoto Server01.</span><span class="sxs-lookup"><span data-stu-id="3d09f-112">These commands start and then stop an interactive session with the Server01 remote computer.</span></span>

### <span data-ttu-id="3d09f-113">Exemplo 2: Iniciar e parar uma sessão interativa usando um objeto PSSession</span><span class="sxs-lookup"><span data-stu-id="3d09f-113">Example 2: Start and stop an interactive session by using a PSSession object</span></span>

```
PS> $s = New-PSSession -ComputerName Server01
PS> Enter-PSSession -Session $s
Server01\PS> Exit-PSSession
PS> $s
Id Name            ComputerName    State    ConfigurationName
-- ----            ------------    -----    -----------------
1  Session1        Server01        Opened   Microsoft.PowerShell
```

<span data-ttu-id="3d09f-114">Esses comandos iniciam e param uma sessão interativa com o computador Server01 que usa uma sessão do PowerShell (**PSSession**).</span><span class="sxs-lookup"><span data-stu-id="3d09f-114">These commands start and stop an interactive session with the Server01 computer that uses a PowerShell session (**PSSession**).</span></span>

<span data-ttu-id="3d09f-115">Como a sessão interativa foi iniciada usando uma sessão do PowerShell, a **PSSession** ainda está disponível quando a sessão interativa termina.</span><span class="sxs-lookup"><span data-stu-id="3d09f-115">Because the interactive session was started by using a PowerShell session, the **PSSession** is still available when the interactive session ends.</span></span>
<span data-ttu-id="3d09f-116">Se você usar o parâmetro *ComputerName* , **Enter-PSSession** criará uma sessão temporária que será fechada quando a sessão interativa terminar.</span><span class="sxs-lookup"><span data-stu-id="3d09f-116">If you use the *ComputerName* parameter, **Enter-PSSession** creates a temporary session that it closes when the interactive session ends.</span></span>

<span data-ttu-id="3d09f-117">O primeiro comando usa o cmdlet New-PSSession para criar uma **PSSession** no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="3d09f-117">The first command uses the New-PSSession cmdlet to create a **PSSession** on the Server01 computer.</span></span>
<span data-ttu-id="3d09f-118">O comando salva a **PSSession** na variável $s.</span><span class="sxs-lookup"><span data-stu-id="3d09f-118">The command saves the **PSSession** in the $s variable.</span></span>

<span data-ttu-id="3d09f-119">O segundo comando usa **Enter-PSSession** para iniciar uma sessão interativa usando a **PSSession** em $s.</span><span class="sxs-lookup"><span data-stu-id="3d09f-119">The second command uses **Enter-PSSession** to start an interactive session using the **PSSession** in $s.</span></span>

<span data-ttu-id="3d09f-120">O terceiro comando usa **Exit-PSSession** para interromper a sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="3d09f-120">The third command uses **Exit-PSSession** to stop the interactive session.</span></span>

<span data-ttu-id="3d09f-121">O comando final exibe a **PSSession** na variável $s.</span><span class="sxs-lookup"><span data-stu-id="3d09f-121">The final command displays the **PSSession** in the $s variable.</span></span>
<span data-ttu-id="3d09f-122">A propriedade **State** mostra que **PSSession** ainda está aberto e disponível para uso.</span><span class="sxs-lookup"><span data-stu-id="3d09f-122">The **State** property shows the **PSSession** is still open and available for use.</span></span>

### <span data-ttu-id="3d09f-123">Exemplo 3: usar a palavra-chave EXIT para interromper uma sessão</span><span class="sxs-lookup"><span data-stu-id="3d09f-123">Example 3: Use the Exit keyword to stop a session</span></span>

```
PS> Enter-PSSession -computername Server01
Server01\PS> exit
PS>
```

<span data-ttu-id="3d09f-124">Este exemplo usa a palavra-chave **Exit** para interromper uma sessão interativa iniciada usando **Enter-PSSession**.</span><span class="sxs-lookup"><span data-stu-id="3d09f-124">This example uses the **Exit** keyword to stop an interactive session started by using **Enter-PSSession**.</span></span>
<span data-ttu-id="3d09f-125">A palavra-chave **Exit** tem o mesmo efeito que usar **Exit-PSSession**.</span><span class="sxs-lookup"><span data-stu-id="3d09f-125">The **Exit** keyword has the same effect as using **Exit-PSSession**.</span></span>

## <span data-ttu-id="3d09f-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3d09f-126">PARAMETERS</span></span>

### <span data-ttu-id="3d09f-127">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3d09f-127">CommonParameters</span></span>

<span data-ttu-id="3d09f-128">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3d09f-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3d09f-129">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3d09f-129">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3d09f-130">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="3d09f-130">INPUTS</span></span>

### <span data-ttu-id="3d09f-131">Nenhum</span><span class="sxs-lookup"><span data-stu-id="3d09f-131">None</span></span>

<span data-ttu-id="3d09f-132">Não é possível transferir objetos para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3d09f-132">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="3d09f-133">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="3d09f-133">OUTPUTS</span></span>

### <span data-ttu-id="3d09f-134">Nenhum</span><span class="sxs-lookup"><span data-stu-id="3d09f-134">None</span></span>

<span data-ttu-id="3d09f-135">Este cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="3d09f-135">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="3d09f-136">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="3d09f-136">NOTES</span></span>

* <span data-ttu-id="3d09f-137">Esse cmdlet usa apenas os parâmetros comuns.</span><span class="sxs-lookup"><span data-stu-id="3d09f-137">This cmdlet takes only the common parameters.</span></span>

*

## <span data-ttu-id="3d09f-138">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="3d09f-138">RELATED LINKS</span></span>

[<span data-ttu-id="3d09f-139">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="3d09f-139">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="3d09f-140">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="3d09f-140">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="3d09f-141">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="3d09f-141">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="3d09f-142">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="3d09f-142">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="3d09f-143">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="3d09f-143">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="3d09f-144">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="3d09f-144">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="3d09f-145">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="3d09f-145">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="3d09f-146">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="3d09f-146">Remove-PSSession</span></span>](Remove-PSSession.md)

