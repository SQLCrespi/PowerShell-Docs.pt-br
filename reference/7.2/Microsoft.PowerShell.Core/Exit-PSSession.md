---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 02/08/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pssession?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSSession
ms.openlocfilehash: b1827929c53560cb261cd7b3ba1e5bd407c25700
ms.sourcegitcommit: 3a1d80e27438976101f216b8c3d623c61b868db8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "99975083"
---
# <span data-ttu-id="4a874-102">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="4a874-102">Exit-PSSession</span></span>

## <span data-ttu-id="4a874-103">Sinopse</span><span class="sxs-lookup"><span data-stu-id="4a874-103">Synopsis</span></span>
<span data-ttu-id="4a874-104">Encerra uma sessão interativa com um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="4a874-104">Ends an interactive session with a remote computer.</span></span>

## <span data-ttu-id="4a874-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4a874-105">SYNTAX</span></span>

```
Exit-PSSession [<CommonParameters>]
```

## <span data-ttu-id="4a874-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="4a874-106">Description</span></span>

<span data-ttu-id="4a874-107">O `Exit-PSSession` cmdlet encerra as sessões interativas que você iniciou usando o `Enter-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4a874-107">The `Exit-PSSession` cmdlet ends interactive sessions that you started by using the `Enter-PSSession` cmdlet.</span></span>

<span data-ttu-id="4a874-108">Você também pode usar a `exit` palavra-chave para encerrar uma sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="4a874-108">You can also use the `exit` keyword to end an interactive session.</span></span> <span data-ttu-id="4a874-109">O efeito é o mesmo que usar `Exit-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="4a874-109">The effect is the same as using `Exit-PSSession`.</span></span>

## <span data-ttu-id="4a874-110">Exemplos</span><span class="sxs-lookup"><span data-stu-id="4a874-110">Examples</span></span>

### <span data-ttu-id="4a874-111">Exemplo 1: Iniciar e parar uma sessão interativa</span><span class="sxs-lookup"><span data-stu-id="4a874-111">Example 1: Start and stop an interactive session</span></span>

```powershell
PS> Enter-PSSession -ComputerName Server01
Server01\PS> Exit-PSSession
PS>
```

<span data-ttu-id="4a874-112">Esses comandos iniciam e param uma sessão interativa com o computador remoto Server01.</span><span class="sxs-lookup"><span data-stu-id="4a874-112">These commands start and then stop an interactive session with the Server01 remote computer.</span></span>

### <span data-ttu-id="4a874-113">Exemplo 2: Iniciar e parar uma sessão interativa usando um objeto PSSession</span><span class="sxs-lookup"><span data-stu-id="4a874-113">Example 2: Start and stop an interactive session by using a PSSession object</span></span>

```powershell
PS> $s = New-PSSession -ComputerName Server01
PS> Enter-PSSession -Session $s
Server01\PS> Exit-PSSession
PS> $s
Id Name            ComputerName    State    ConfigurationName
-- ----            ------------    -----    -----------------
1  Session1        Server01        Opened   Microsoft.PowerShell
```

<span data-ttu-id="4a874-114">Esses comandos iniciam e param uma sessão interativa com o computador Server01 que usa uma sessão do PowerShell (**PSSession**).</span><span class="sxs-lookup"><span data-stu-id="4a874-114">These commands start and stop an interactive session with the Server01 computer that uses a PowerShell session (**PSSession**).</span></span>

<span data-ttu-id="4a874-115">Como a sessão interativa foi iniciada usando uma sessão do PowerShell, a **PSSession** ainda está disponível quando a sessão interativa termina.</span><span class="sxs-lookup"><span data-stu-id="4a874-115">Because the interactive session was started by using a PowerShell session, the **PSSession** is still available when the interactive session ends.</span></span> <span data-ttu-id="4a874-116">Se você usar o parâmetro _ComputerName_ , o `Enter-PSSession` criará uma sessão temporária que será fechada quando a sessão interativa terminar.</span><span class="sxs-lookup"><span data-stu-id="4a874-116">If you use the _ComputerName_ parameter, `Enter-PSSession` creates a temporary session that it closes when the interactive session ends.</span></span>

<span data-ttu-id="4a874-117">O primeiro comando usa o `New-PSSession` cmdlet para criar uma **PSSession** no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="4a874-117">The first command uses the `New-PSSession` cmdlet to create a **PSSession** on the Server01 computer.</span></span> <span data-ttu-id="4a874-118">O comando salva a **PSSession** na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="4a874-118">The command saves the **PSSession** in the `$s` variable.</span></span>

<span data-ttu-id="4a874-119">O segundo comando usa `Enter-PSSession` para iniciar uma sessão interativa usando a **PSSession** em `$s` .</span><span class="sxs-lookup"><span data-stu-id="4a874-119">The second command uses `Enter-PSSession` to start an interactive session using the **PSSession** in `$s`.</span></span>

<span data-ttu-id="4a874-120">O terceiro comando usa `Exit-PSSession` para interromper a sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="4a874-120">The third command uses `Exit-PSSession` to stop the interactive session.</span></span>

<span data-ttu-id="4a874-121">O comando final exibe a **PSSession** na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="4a874-121">The final command displays the **PSSession** in the `$s` variable.</span></span> <span data-ttu-id="4a874-122">A propriedade **State** mostra que **PSSession** ainda está aberto e disponível para uso.</span><span class="sxs-lookup"><span data-stu-id="4a874-122">The **State** property shows the **PSSession** is still open and available for use.</span></span>

### <span data-ttu-id="4a874-123">Exemplo 3: usar a palavra-chave EXIT para interromper uma sessão</span><span class="sxs-lookup"><span data-stu-id="4a874-123">Example 3: Use the Exit keyword to stop a session</span></span>

```powershell
PS> Enter-PSSession -ComputerName Server01
Server01\PS> exit
PS>
```

<span data-ttu-id="4a874-124">Este exemplo usa a `exit` palavra-chave para interromper uma sessão interativa iniciada usando `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="4a874-124">This example uses the `exit` keyword to stop an interactive session started by using `Enter-PSSession`.</span></span> <span data-ttu-id="4a874-125">A `exit` palavra-chave tem o mesmo efeito que usar `Exit-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="4a874-125">The `exit` keyword has the same effect as using `Exit-PSSession`.</span></span>

## <span data-ttu-id="4a874-126">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="4a874-126">Parameters</span></span>

### <span data-ttu-id="4a874-127">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4a874-127">CommonParameters</span></span>

<span data-ttu-id="4a874-128">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4a874-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4a874-129">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4a874-129">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4a874-130">Entradas</span><span class="sxs-lookup"><span data-stu-id="4a874-130">Inputs</span></span>

### <span data-ttu-id="4a874-131">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4a874-131">None</span></span>

<span data-ttu-id="4a874-132">Não é possível transferir objetos para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4a874-132">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="4a874-133">Saídas</span><span class="sxs-lookup"><span data-stu-id="4a874-133">Outputs</span></span>

### <span data-ttu-id="4a874-134">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4a874-134">None</span></span>

<span data-ttu-id="4a874-135">Este cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="4a874-135">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="4a874-136">Observações</span><span class="sxs-lookup"><span data-stu-id="4a874-136">Notes</span></span>

<span data-ttu-id="4a874-137">Esse cmdlet usa apenas os parâmetros comuns.</span><span class="sxs-lookup"><span data-stu-id="4a874-137">This cmdlet takes only the common parameters.</span></span>

## <span data-ttu-id="4a874-138">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="4a874-138">RELATED LINKS</span></span>

[<span data-ttu-id="4a874-139">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="4a874-139">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="4a874-140">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="4a874-140">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="4a874-141">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="4a874-141">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="4a874-142">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="4a874-142">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="4a874-143">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="4a874-143">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="4a874-144">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="4a874-144">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="4a874-145">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="4a874-145">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="4a874-146">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="4a874-146">Remove-PSSession</span></span>](Remove-PSSession.md)
