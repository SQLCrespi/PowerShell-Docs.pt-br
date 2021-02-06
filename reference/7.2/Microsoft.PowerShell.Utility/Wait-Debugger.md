---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/wait-debugger?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Debugger
ms.openlocfilehash: a2ef114a43a63b18f5dc2d28acf7cbc0de8392bd
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597618"
---
# <span data-ttu-id="6d23e-102">Wait-Debugger</span><span class="sxs-lookup"><span data-stu-id="6d23e-102">Wait-Debugger</span></span>

## <span data-ttu-id="6d23e-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="6d23e-103">SYNOPSIS</span></span>
<span data-ttu-id="6d23e-104">Interrompe um script no depurador antes de executar a próxima instrução no script.</span><span class="sxs-lookup"><span data-stu-id="6d23e-104">Stops a script in the debugger before running the next statement in the script.</span></span>

## <span data-ttu-id="6d23e-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6d23e-105">SYNTAX</span></span>

```
Wait-Debugger [<CommonParameters>]
```

## <span data-ttu-id="6d23e-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6d23e-106">DESCRIPTION</span></span>

<span data-ttu-id="6d23e-107">Interrompe o mecanismo de execução de script do PowerShell no ponto imediatamente após o `Wait-Debugger` cmdlet e aguarda a anexação de um depurador.</span><span class="sxs-lookup"><span data-stu-id="6d23e-107">Stops the PowerShell script execution engine at the point immediately after the `Wait-Debugger` cmdlet and waits for a debugger to be attached.</span></span> <span data-ttu-id="6d23e-108">Isso é semelhante ao uso `Enable-RunspaceDebug -BreakAll` em um recurso de DSC, mas interrompe em um ponto específico no script.</span><span class="sxs-lookup"><span data-stu-id="6d23e-108">This is similar to using `Enable-RunspaceDebug -BreakAll` in a DSC resource but breaks at a specific point in the script.</span></span>

> [!CAUTION]
> <span data-ttu-id="6d23e-109">Certifique-se de remover as `Wait-Debugger` linhas depois de terminar.</span><span class="sxs-lookup"><span data-stu-id="6d23e-109">Make sure you remove the `Wait-Debugger` lines after you are done.</span></span> <span data-ttu-id="6d23e-110">Um script em execução parece estar suspenso quando é interrompido em um `Wait-Debugger` .</span><span class="sxs-lookup"><span data-stu-id="6d23e-110">A running script appears to be hung when it is stopped at a `Wait-Debugger`.</span></span>

## <span data-ttu-id="6d23e-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="6d23e-111">EXAMPLES</span></span>

### <span data-ttu-id="6d23e-112">Exemplo 1: Inserir ponto de interrupção para depuração</span><span class="sxs-lookup"><span data-stu-id="6d23e-112">Example 1: Insert breakpoint for debugging</span></span>

```
[DscResource()]
class FileResource
{
    [DscProperty(Key)]
    [string] $Path

    [DscProperty(Mandatory)]
    [Ensure] $Ensure

    [DscProperty(Mandatory)]
    [string] $SourcePath

    [DscProperty(NotConfigurable)]
    [Nullable[datetime]] $CreationTime


    [void] Set()
    {
        $fileExists = $this.TestFilePath($this.Path)
        if ($this.ensure -eq [Ensure]::Present)
        {
            if (! $fileExists)
            {
               $this.CopyFile()
            }
        }
        else
        {
            if ($fileExists)
            {
                Write-Verbose -Message "Deleting the file $($this.Path)"
                Remove-Item -LiteralPath $this.Path -Force
            }
        }
    }

    [bool] Test()
    {
        $present = Test-Path -LiteralPath $this.Path

        if ($this.Ensure -eq [Ensure]::Present)
        {
            return $present
        }
        else
        {
            return (! $present)
        }
    }

    [FileResource] Get()
    {
        $present = Test-Path -Path $this.Path

        if ($present)
        {
            $file = Get-ChildItem -LiteralPath $this.Path
            $this.CreationTime = $file.CreationTime
            $this.Ensure = [Ensure]::Present
        }
        else
        {
            $this.CreationTime = $null
            $this.Ensure = [Ensure]::Absent
        }

        return $this
    }

    [void] CopyFile()
    {
        # Testing only - Remove before deployment!
        Wait-Debugger

        if (! (Test-Path -LiteralPath $this.SourcePath))
        {
            throw "SourcePath $($this.SourcePath) is not found."
        }

        if (Test-Path -LiteralPath $this.Path -PathType Container)
        {
            throw "Path $($this.Path) is a directory path"
        }

        Write-Verbose "Copying $($this.SourcePath) to $($this.Path)"

        Copy-Item -LiteralPath $this.SourcePath -Destination $this.Path -Force
    }
}
```

## <span data-ttu-id="6d23e-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6d23e-113">PARAMETERS</span></span>

### <span data-ttu-id="6d23e-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6d23e-114">CommonParameters</span></span>

<span data-ttu-id="6d23e-115">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6d23e-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6d23e-116">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="6d23e-116">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="6d23e-117">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="6d23e-117">INPUTS</span></span>

### <span data-ttu-id="6d23e-118">Nenhum</span><span class="sxs-lookup"><span data-stu-id="6d23e-118">None</span></span>

## <span data-ttu-id="6d23e-119">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="6d23e-119">OUTPUTS</span></span>

### <span data-ttu-id="6d23e-120">Nenhum</span><span class="sxs-lookup"><span data-stu-id="6d23e-120">None</span></span>

## <span data-ttu-id="6d23e-121">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="6d23e-121">NOTES</span></span>

## <span data-ttu-id="6d23e-122">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="6d23e-122">RELATED LINKS</span></span>

[<span data-ttu-id="6d23e-123">Enable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="6d23e-123">Enable-DscDebug</span></span>](/powershell/module/PSDesiredStateConfiguration/Enable-DscDebug)

