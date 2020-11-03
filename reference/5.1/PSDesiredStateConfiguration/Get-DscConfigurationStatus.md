---
external help file: Get-DscConfigurationStatus.cdxml-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dscconfigurationstatus?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscConfigurationStatus
ms.openlocfilehash: 0d59ce58a70eab68441ea1fe6097bbdf7792a54f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194157"
---
# <span data-ttu-id="0268d-103">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="0268d-103">Get-DscConfigurationStatus</span></span>

## <span data-ttu-id="0268d-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="0268d-104">SYNOPSIS</span></span>
<span data-ttu-id="0268d-105">Recupera dados sobre execuções de configuração concluídas.</span><span class="sxs-lookup"><span data-stu-id="0268d-105">Retrieves data about completed configuration runs.</span></span>

## <span data-ttu-id="0268d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0268d-106">SYNTAX</span></span>

```
Get-DscConfigurationStatus [-All] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## <span data-ttu-id="0268d-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0268d-107">DESCRIPTION</span></span>
<span data-ttu-id="0268d-108">O cmdlet **Get-DscConfigurationStatus** recupera informações detalhadas sobre as execuções de configuração concluídas no sistema.</span><span class="sxs-lookup"><span data-stu-id="0268d-108">The **Get-DscConfigurationStatus** cmdlet retrieves detailed information about completed configuration runs on the system.</span></span>
<span data-ttu-id="0268d-109">Por padrão, ele retorna as informações sobre a última execução de configuração.</span><span class="sxs-lookup"><span data-stu-id="0268d-109">By default, it returns the information about the last configuration run.</span></span>
<span data-ttu-id="0268d-110">Esse cmdlet é útil para encontrar informações históricas sobre as execuções de configuração, como quando as configurações foram executadas, o status das execuções, o número de recursos nas configurações e quais recursos tiveram êxito ou falharam.</span><span class="sxs-lookup"><span data-stu-id="0268d-110">This cmdlet is useful for finding historical information about configuration runs, such as when the configurations were run, the status of the runs, the number of resources in the configurations, and which resources succeeded or failed.</span></span>

## <span data-ttu-id="0268d-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="0268d-111">EXAMPLES</span></span>

### <span data-ttu-id="0268d-112">Exemplo 1: obter informações sobre a última execução de configuração</span><span class="sxs-lookup"><span data-stu-id="0268d-112">Example 1: Get information on the last configuration run</span></span>

```
PS C:\> Get-DscConfigurationStatus
```

<span data-ttu-id="0268d-113">Este comando obtém informações sobre a última execução de configuração.</span><span class="sxs-lookup"><span data-stu-id="0268d-113">This command gets information on the last configuration run.</span></span>

### <span data-ttu-id="0268d-114">Exemplo 2: obter informações sobre todas as configurações</span><span class="sxs-lookup"><span data-stu-id="0268d-114">Example 2: Get information on all configurations</span></span>

```
PS C:\> Get-DscConfigurationStatus -All
```

<span data-ttu-id="0268d-115">Esse comando obtém informações sobre todas as configurações que foram executadas no sistema, incluindo a verificação de consistência da DSC (configuração de estado desejado) do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0268d-115">This command gets information about all the configurations that were run on the system, including the Windows PowerShell Desired State Configuration (DSC) consistency check.</span></span>

### <span data-ttu-id="0268d-116">Exemplo 3: obter informações sobre a execução da configuração em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="0268d-116">Example 3: Get information on the configuration run on a remote computer</span></span>

```
PS C:\> Get-DscConfigurationStatus -CimSession "Server01"
```

<span data-ttu-id="0268d-117">Esse comando obtém os detalhes de execução da configuração do computador remoto chamado Server01.</span><span class="sxs-lookup"><span data-stu-id="0268d-117">This command gets the configuration run details of the remote computer named Server01.</span></span>
<span data-ttu-id="0268d-118">Isso usa o transporte WSMan para se conectar ao computador remoto e requer que o usuário que está se conectando seja um administrador no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="0268d-118">This uses the WSMan transport to connect to the remote computer and requires that the connecting user be an administrator on the remote computer.</span></span>

## <span data-ttu-id="0268d-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0268d-119">PARAMETERS</span></span>

### <span data-ttu-id="0268d-120">-All</span><span class="sxs-lookup"><span data-stu-id="0268d-120">-All</span></span>
<span data-ttu-id="0268d-121">Indica que esse cmdlet recupera informações sobre todas as execuções de configuração no computador, incluindo o aplicativo de configuração e a verificação de consistência.</span><span class="sxs-lookup"><span data-stu-id="0268d-121">Indicates that this cmdlet retrieves information about all the configuration runs on the computer, including the configuration application and the consistency check.</span></span>

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

### <span data-ttu-id="0268d-122">-AsJob</span><span class="sxs-lookup"><span data-stu-id="0268d-122">-AsJob</span></span>
<span data-ttu-id="0268d-123">Indica que esse cmdlet executa o comando como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="0268d-123">Indicates that this cmdlet runs the command as a background job.</span></span>

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

### <span data-ttu-id="0268d-124">-CimSession</span><span class="sxs-lookup"><span data-stu-id="0268d-124">-CimSession</span></span>
<span data-ttu-id="0268d-125">Executa o cmdlet em uma sessão remota ou em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="0268d-125">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="0268d-126">Insira um nome de computador ou um objeto de sessão, como a saída de um cmdlet [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) ou [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) .</span><span class="sxs-lookup"><span data-stu-id="0268d-126">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="0268d-127">O padrão é a sessão atual do computador local.</span><span class="sxs-lookup"><span data-stu-id="0268d-127">The default is the current session on the local computer.</span></span>

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

### <span data-ttu-id="0268d-128">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="0268d-128">-ThrottleLimit</span></span>
<span data-ttu-id="0268d-129">Especifica o número máximo de operações simultâneas que podem ser estabelecidas para executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0268d-129">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="0268d-130">Se esse parâmetro for omitido ou um valor de `0` for inserido, o Windows PowerShell calculará um limite de aceleração ideal para o cmdlet com base no número de cmdlets CIM em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="0268d-130">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="0268d-131">O limite de aceleração aplica-se somente ao cmdlet atual, e não à sessão ou ao computador.</span><span class="sxs-lookup"><span data-stu-id="0268d-131">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="0268d-132">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0268d-132">CommonParameters</span></span>
<span data-ttu-id="0268d-133">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0268d-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0268d-134">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0268d-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0268d-135">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="0268d-135">INPUTS</span></span>

## <span data-ttu-id="0268d-136">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="0268d-136">OUTPUTS</span></span>

## <span data-ttu-id="0268d-137">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="0268d-137">NOTES</span></span>

## <span data-ttu-id="0268d-138">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="0268d-138">RELATED LINKS</span></span>

[<span data-ttu-id="0268d-139">Visão geral da Desired State Configuration do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0268d-139">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="0268d-140">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="0268d-140">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="0268d-141">Get-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="0268d-141">Get-DscLocalConfigurationManager</span></span>](Get-DscLocalConfigurationManager.md)

[<span data-ttu-id="0268d-142">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="0268d-142">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="0268d-143">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="0268d-143">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="0268d-144">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="0268d-144">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
