---
external help file: Disable-DscDebug.cdxml-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/disable-dscdebug?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-DscDebug
ms.openlocfilehash: fdaba8358772f559a33117c796a923d774b009cb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194154"
---
# <span data-ttu-id="066e0-103">Disable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="066e0-103">Disable-DscDebug</span></span>

## <span data-ttu-id="066e0-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="066e0-104">SYNOPSIS</span></span>
<span data-ttu-id="066e0-105">Interrompe a depuração de recursos de DSC.</span><span class="sxs-lookup"><span data-stu-id="066e0-105">Stops debugging of DSC resources.</span></span>

## <span data-ttu-id="066e0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="066e0-106">SYNTAX</span></span>

```
Disable-DscDebug [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="066e0-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="066e0-107">DESCRIPTION</span></span>
<span data-ttu-id="066e0-108">O cmdlet **Disable-DscDebug** solicita que o mecanismo de configuração de estado desejado (DSC) do Windows PowerShell interrompa a depuração de recursos de DSC.</span><span class="sxs-lookup"><span data-stu-id="066e0-108">The **Disable-DscDebug** cmdlet requests that the Windows PowerShell Desired State Configuration (DSC) engine stop debugging of DSC resources.</span></span>
<span data-ttu-id="066e0-109">Esse cmdlet não tem efeito se o mecanismo de DSC não estiver no modo de depuração no momento.</span><span class="sxs-lookup"><span data-stu-id="066e0-109">This cmdlet has no effect if the DSC engine is not currently in debugging mode.</span></span>

## <span data-ttu-id="066e0-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="066e0-110">EXAMPLES</span></span>

### <span data-ttu-id="066e0-111">Exemplo 1: parar a depuração de recursos</span><span class="sxs-lookup"><span data-stu-id="066e0-111">Example 1: Stop resource debugging</span></span>

```
PS C:\> Disable-DscDebug
```

<span data-ttu-id="066e0-112">Esse comando indica ao mecanismo de DSC no Configuration Manager local (LCM) para interromper a depuração de recursos.</span><span class="sxs-lookup"><span data-stu-id="066e0-112">This command indicates to the DSC engine on the Local Configuration Manager (LCM) to stop resource debugging.</span></span>

### <span data-ttu-id="066e0-113">Exemplo 2: verificar o estado do mecanismo e parar a depuração</span><span class="sxs-lookup"><span data-stu-id="066e0-113">Example 2: Check the engine state and stop debugging</span></span>

```
PS C:\> if((Get-DscLocalConfigurationManager).DebugMode -like '*Break*'){Disable-DscDebug}
```

<span data-ttu-id="066e0-114">Esse comando verifica o estado do mecanismo de DSC e parará a depuração de recursos somente se ele já estiver no modo de depuração</span><span class="sxs-lookup"><span data-stu-id="066e0-114">This command checks the DSC engine state, and stops resource debugging only if it is already in debugging mode</span></span>

## <span data-ttu-id="066e0-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="066e0-115">PARAMETERS</span></span>

### <span data-ttu-id="066e0-116">-AsJob</span><span class="sxs-lookup"><span data-stu-id="066e0-116">-AsJob</span></span>
<span data-ttu-id="066e0-117">Indica que esse cmdlet executa o comando como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="066e0-117">Indicates that this cmdlet runs the command as a background job.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="066e0-118">-CimSession</span><span class="sxs-lookup"><span data-stu-id="066e0-118">-CimSession</span></span>
<span data-ttu-id="066e0-119">Executa o cmdlet em uma sessão remota ou em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="066e0-119">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="066e0-120">Insira um nome de computador ou um objeto de sessão, como a saída de um cmdlet [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) ou [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) .</span><span class="sxs-lookup"><span data-stu-id="066e0-120">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="066e0-121">O padrão é a sessão atual do computador local.</span><span class="sxs-lookup"><span data-stu-id="066e0-121">The default is the current session on the local computer.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="066e0-122">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="066e0-122">-ThrottleLimit</span></span>
<span data-ttu-id="066e0-123">Especifica o número máximo de operações simultâneas que podem ser estabelecidas para executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="066e0-123">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="066e0-124">Se esse parâmetro for omitido ou um valor de `0` for inserido, o Windows PowerShell calculará um limite de aceleração ideal para o cmdlet com base no número de cmdlets CIM em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="066e0-124">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="066e0-125">O limite de aceleração aplica-se somente ao cmdlet atual, e não à sessão ou ao computador.</span><span class="sxs-lookup"><span data-stu-id="066e0-125">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="066e0-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="066e0-126">-Confirm</span></span>
<span data-ttu-id="066e0-127">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="066e0-127">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="066e0-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="066e0-128">-WhatIf</span></span>
<span data-ttu-id="066e0-129">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="066e0-129">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="066e0-130">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="066e0-130">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="066e0-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="066e0-131">CommonParameters</span></span>
<span data-ttu-id="066e0-132">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="066e0-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="066e0-133">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="066e0-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="066e0-134">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="066e0-134">INPUTS</span></span>

## <span data-ttu-id="066e0-135">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="066e0-135">OUTPUTS</span></span>

## <span data-ttu-id="066e0-136">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="066e0-136">NOTES</span></span>

## <span data-ttu-id="066e0-137">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="066e0-137">RELATED LINKS</span></span>

[<span data-ttu-id="066e0-138">Visão geral da Desired State Configuration do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="066e0-138">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="066e0-139">Enable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="066e0-139">Enable-DscDebug</span></span>](Enable-DscDebug.md)

[<span data-ttu-id="066e0-140">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="066e0-140">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="066e0-141">Get-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="066e0-141">Get-DscLocalConfigurationManager</span></span>](Get-DscLocalConfigurationManager.md)

[<span data-ttu-id="066e0-142">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="066e0-142">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="066e0-143">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="066e0-143">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="066e0-144">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="066e0-144">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
