---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 02/08/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pssession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSSession
ms.openlocfilehash: 7947855afa08bc3301d02e64fcb2ad8bb6b59db7
ms.sourcegitcommit: 3a1d80e27438976101f216b8c3d623c61b868db8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "99975117"
---
# <span data-ttu-id="eac12-103">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="eac12-103">Exit-PSSession</span></span>

## <span data-ttu-id="eac12-104">Sinopse</span><span class="sxs-lookup"><span data-stu-id="eac12-104">Synopsis</span></span>
<span data-ttu-id="eac12-105">Encerra uma sessão interativa com um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="eac12-105">Ends an interactive session with a remote computer.</span></span>

## <span data-ttu-id="eac12-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="eac12-106">SYNTAX</span></span>

```
Exit-PSSession [<CommonParameters>]
```

## <span data-ttu-id="eac12-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="eac12-107">Description</span></span>

<span data-ttu-id="eac12-108">O `Exit-PSSession` cmdlet encerra as sessões interativas que você iniciou usando o `Enter-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="eac12-108">The `Exit-PSSession` cmdlet ends interactive sessions that you started by using the `Enter-PSSession` cmdlet.</span></span>

<span data-ttu-id="eac12-109">Você também pode usar a `exit` palavra-chave para encerrar uma sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="eac12-109">You can also use the `exit` keyword to end an interactive session.</span></span> <span data-ttu-id="eac12-110">O efeito é o mesmo que usar `Exit-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="eac12-110">The effect is the same as using `Exit-PSSession`.</span></span>

## <span data-ttu-id="eac12-111">Exemplos</span><span class="sxs-lookup"><span data-stu-id="eac12-111">Examples</span></span>

### <span data-ttu-id="eac12-112">Exemplo 1: Iniciar e parar uma sessão interativa</span><span class="sxs-lookup"><span data-stu-id="eac12-112">Example 1: Start and stop an interactive session</span></span>

```powershell
PS> Enter-PSSession -ComputerName Server01
Server01\PS> Exit-PSSession
PS>
```

<span data-ttu-id="eac12-113">Esses comandos iniciam e param uma sessão interativa com o computador remoto Server01.</span><span class="sxs-lookup"><span data-stu-id="eac12-113">These commands start and then stop an interactive session with the Server01 remote computer.</span></span>

### <span data-ttu-id="eac12-114">Exemplo 2: Iniciar e parar uma sessão interativa usando um objeto PSSession</span><span class="sxs-lookup"><span data-stu-id="eac12-114">Example 2: Start and stop an interactive session by using a PSSession object</span></span>

```powershell
PS> $s = New-PSSession -ComputerName Server01
PS> Enter-PSSession -Session $s
Server01\PS> Exit-PSSession
PS> $s
Id Name            ComputerName    State    ConfigurationName
-- ----            ------------    -----    -----------------
1  Session1        Server01        Opened   Microsoft.PowerShell
```

<span data-ttu-id="eac12-115">Esses comandos iniciam e param uma sessão interativa com o computador Server01 que usa uma sessão do PowerShell (**PSSession**).</span><span class="sxs-lookup"><span data-stu-id="eac12-115">These commands start and stop an interactive session with the Server01 computer that uses a PowerShell session (**PSSession**).</span></span>

<span data-ttu-id="eac12-116">Como a sessão interativa foi iniciada usando uma sessão do PowerShell, a **PSSession** ainda está disponível quando a sessão interativa termina.</span><span class="sxs-lookup"><span data-stu-id="eac12-116">Because the interactive session was started by using a PowerShell session, the **PSSession** is still available when the interactive session ends.</span></span> <span data-ttu-id="eac12-117">Se você usar o parâmetro _ComputerName_ , o `Enter-PSSession` criará uma sessão temporária que será fechada quando a sessão interativa terminar.</span><span class="sxs-lookup"><span data-stu-id="eac12-117">If you use the _ComputerName_ parameter, `Enter-PSSession` creates a temporary session that it closes when the interactive session ends.</span></span>

<span data-ttu-id="eac12-118">O primeiro comando usa o `New-PSSession` cmdlet para criar uma **PSSession** no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="eac12-118">The first command uses the `New-PSSession` cmdlet to create a **PSSession** on the Server01 computer.</span></span> <span data-ttu-id="eac12-119">O comando salva a **PSSession** na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="eac12-119">The command saves the **PSSession** in the `$s` variable.</span></span>

<span data-ttu-id="eac12-120">O segundo comando usa `Enter-PSSession` para iniciar uma sessão interativa usando a **PSSession** em `$s` .</span><span class="sxs-lookup"><span data-stu-id="eac12-120">The second command uses `Enter-PSSession` to start an interactive session using the **PSSession** in `$s`.</span></span>

<span data-ttu-id="eac12-121">O terceiro comando usa `Exit-PSSession` para interromper a sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="eac12-121">The third command uses `Exit-PSSession` to stop the interactive session.</span></span>

<span data-ttu-id="eac12-122">O comando final exibe a **PSSession** na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="eac12-122">The final command displays the **PSSession** in the `$s` variable.</span></span> <span data-ttu-id="eac12-123">A propriedade **State** mostra que **PSSession** ainda está aberto e disponível para uso.</span><span class="sxs-lookup"><span data-stu-id="eac12-123">The **State** property shows the **PSSession** is still open and available for use.</span></span>

### <span data-ttu-id="eac12-124">Exemplo 3: usar a palavra-chave EXIT para interromper uma sessão</span><span class="sxs-lookup"><span data-stu-id="eac12-124">Example 3: Use the Exit keyword to stop a session</span></span>

```powershell
PS> Enter-PSSession -ComputerName Server01
Server01\PS> exit
PS>
```

<span data-ttu-id="eac12-125">Este exemplo usa a `exit` palavra-chave para interromper uma sessão interativa iniciada usando `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="eac12-125">This example uses the `exit` keyword to stop an interactive session started by using `Enter-PSSession`.</span></span> <span data-ttu-id="eac12-126">A `exit` palavra-chave tem o mesmo efeito que usar `Exit-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="eac12-126">The `exit` keyword has the same effect as using `Exit-PSSession`.</span></span>

## <span data-ttu-id="eac12-127">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="eac12-127">Parameters</span></span>

### <span data-ttu-id="eac12-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="eac12-128">CommonParameters</span></span>

<span data-ttu-id="eac12-129">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="eac12-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="eac12-130">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="eac12-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="eac12-131">Entradas</span><span class="sxs-lookup"><span data-stu-id="eac12-131">Inputs</span></span>

### <span data-ttu-id="eac12-132">Nenhum</span><span class="sxs-lookup"><span data-stu-id="eac12-132">None</span></span>

<span data-ttu-id="eac12-133">Não é possível transferir objetos para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="eac12-133">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="eac12-134">Saídas</span><span class="sxs-lookup"><span data-stu-id="eac12-134">Outputs</span></span>

### <span data-ttu-id="eac12-135">Nenhum</span><span class="sxs-lookup"><span data-stu-id="eac12-135">None</span></span>

<span data-ttu-id="eac12-136">Este cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="eac12-136">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="eac12-137">Observações</span><span class="sxs-lookup"><span data-stu-id="eac12-137">Notes</span></span>

<span data-ttu-id="eac12-138">Esse cmdlet usa apenas os parâmetros comuns.</span><span class="sxs-lookup"><span data-stu-id="eac12-138">This cmdlet takes only the common parameters.</span></span>

## <span data-ttu-id="eac12-139">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="eac12-139">RELATED LINKS</span></span>

[<span data-ttu-id="eac12-140">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="eac12-140">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="eac12-141">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="eac12-141">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="eac12-142">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="eac12-142">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="eac12-143">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="eac12-143">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="eac12-144">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="eac12-144">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="eac12-145">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="eac12-145">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="eac12-146">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="eac12-146">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="eac12-147">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="eac12-147">Remove-PSSession</span></span>](Remove-PSSession.md)
