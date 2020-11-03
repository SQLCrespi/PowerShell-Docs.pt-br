---
external help file: Enable-DscDebug.cdxml-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/enable-dscdebug?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-DscDebug
ms.openlocfilehash: 136481c5a1945c3d5cbd1ca7fc8ce5f580c39b0f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194156"
---
# <span data-ttu-id="43933-103">Enable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="43933-103">Enable-DscDebug</span></span>

## <span data-ttu-id="43933-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="43933-104">SYNOPSIS</span></span>
<span data-ttu-id="43933-105">Inicia a depuração de todos os recursos de DSC.</span><span class="sxs-lookup"><span data-stu-id="43933-105">Starts debugging of all DSC resources.</span></span>

## <span data-ttu-id="43933-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="43933-106">SYNTAX</span></span>

```
Enable-DscDebug [-BreakAll] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="43933-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="43933-107">DESCRIPTION</span></span>
<span data-ttu-id="43933-108">O cmdlet **Enable-DscDebug** habilita a depuração de recursos de DSC (configuração de estado desejado) do Windows PowerShell pelo mecanismo de DSC, que também é conhecido como o Configuration Manager local (LCM).</span><span class="sxs-lookup"><span data-stu-id="43933-108">The **Enable-DscDebug** cmdlet enables Windows PowerShell Desired State Configuration (DSC) resource debugging by the DSC engine, which is also known as the Local Configuration Manager (LCM).</span></span>
<span data-ttu-id="43933-109">Por padrão, todas as instâncias de recurso são interrompidas no depurador.</span><span class="sxs-lookup"><span data-stu-id="43933-109">By default, all resource instances break into the debugger.</span></span>

## <span data-ttu-id="43933-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="43933-110">EXAMPLES</span></span>

### <span data-ttu-id="43933-111">Exemplo 1: Iniciar Depuração</span><span class="sxs-lookup"><span data-stu-id="43933-111">Example 1: Start debugging</span></span>

```
PS C:\> Enable-DscDebug -BreakAll
```

<span data-ttu-id="43933-112">Esse comando indica para o mecanismo de DSC ou o LCM para iniciar a depuração de recursos.</span><span class="sxs-lookup"><span data-stu-id="43933-112">This command indicates to the DSC engine or LCM to start resource debugging.</span></span>
<span data-ttu-id="43933-113">Na próxima vez em que a configuração for executada, o processo entrará no depurador.</span><span class="sxs-lookup"><span data-stu-id="43933-113">The next time the configuration is run, the process enters the debugger.</span></span>

### <span data-ttu-id="43933-114">Exemplo 2: iniciar a depuração remota</span><span class="sxs-lookup"><span data-stu-id="43933-114">Example 2: Start remote debugging</span></span>

```
PS C:\> Enable-DscDebug -BreakAll -CimSession DeploymentServer
```

<span data-ttu-id="43933-115">Esse comando indica ao mecanismo de DSC do computador remoto para iniciar a depuração de recursos.</span><span class="sxs-lookup"><span data-stu-id="43933-115">This command indicates to the DSC engine of the remote computer to start resource debugging.</span></span>

## <span data-ttu-id="43933-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="43933-116">PARAMETERS</span></span>

### <span data-ttu-id="43933-117">-AsJob</span><span class="sxs-lookup"><span data-stu-id="43933-117">-AsJob</span></span>
<span data-ttu-id="43933-118">Indica que esse cmdlet executa o comando como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="43933-118">Indicates that this cmdlet runs the command as a background job.</span></span>

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

### <span data-ttu-id="43933-119">-BreakAll</span><span class="sxs-lookup"><span data-stu-id="43933-119">-BreakAll</span></span>
<span data-ttu-id="43933-120">Indica que todos os recursos entram no depurador quando uma configuração é executada.</span><span class="sxs-lookup"><span data-stu-id="43933-120">Indicates that all resources enter the debugger when a configuration runs.</span></span>

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

### <span data-ttu-id="43933-121">-CimSession</span><span class="sxs-lookup"><span data-stu-id="43933-121">-CimSession</span></span>
<span data-ttu-id="43933-122">Executa o cmdlet em uma sessão remota ou em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43933-122">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="43933-123">Insira um nome de computador ou um objeto de sessão, como a saída de um cmdlet [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) ou [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) .</span><span class="sxs-lookup"><span data-stu-id="43933-123">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="43933-124">O padrão é a sessão atual do computador local.</span><span class="sxs-lookup"><span data-stu-id="43933-124">The default is the current session on the local computer.</span></span>

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

### <span data-ttu-id="43933-125">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="43933-125">-ThrottleLimit</span></span>
<span data-ttu-id="43933-126">Especifica o número máximo de operações simultâneas que podem ser estabelecidas para executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="43933-126">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="43933-127">Se esse parâmetro for omitido ou um valor de `0` for inserido, o Windows PowerShell calculará um limite de aceleração ideal para o cmdlet com base no número de cmdlets CIM em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="43933-127">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="43933-128">O limite de aceleração aplica-se somente ao cmdlet atual, e não à sessão ou ao computador.</span><span class="sxs-lookup"><span data-stu-id="43933-128">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="43933-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="43933-129">-Confirm</span></span>
<span data-ttu-id="43933-130">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="43933-130">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="43933-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="43933-131">-WhatIf</span></span>
<span data-ttu-id="43933-132">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="43933-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="43933-133">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="43933-133">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="43933-134">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="43933-134">CommonParameters</span></span>
<span data-ttu-id="43933-135">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="43933-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="43933-136">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="43933-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="43933-137">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="43933-137">INPUTS</span></span>

## <span data-ttu-id="43933-138">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="43933-138">OUTPUTS</span></span>

## <span data-ttu-id="43933-139">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="43933-139">NOTES</span></span>

## <span data-ttu-id="43933-140">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="43933-140">RELATED LINKS</span></span>

[<span data-ttu-id="43933-141">Visão geral da Desired State Configuration do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="43933-141">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="43933-142">Disable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="43933-142">Disable-DscDebug</span></span>](Disable-DscDebug.md)

[<span data-ttu-id="43933-143">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="43933-143">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="43933-144">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="43933-144">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="43933-145">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="43933-145">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="43933-146">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="43933-146">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="43933-147">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="43933-147">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
