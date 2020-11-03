---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/publish-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-DscConfiguration
ms.openlocfilehash: 139de2bfdb88c443e7bc48d36e37e95644556bf5
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194142"
---
# <span data-ttu-id="4aa5a-103">Publish-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="4aa5a-103">Publish-DscConfiguration</span></span>

## <span data-ttu-id="4aa5a-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="4aa5a-104">SYNOPSIS</span></span>
<span data-ttu-id="4aa5a-105">Publica uma configuração DSC em um conjunto de computadores.</span><span class="sxs-lookup"><span data-stu-id="4aa5a-105">Publishes a DSC configuration to a set of computers.</span></span>

## <span data-ttu-id="4aa5a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4aa5a-106">SYNTAX</span></span>

### <span data-ttu-id="4aa5a-107">ComputerNameSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="4aa5a-107">ComputerNameSet (Default)</span></span>

```
Publish-DscConfiguration [-Path] <String> [-Force] [[-ComputerName] <String[]>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4aa5a-108">CimSessionSet</span><span class="sxs-lookup"><span data-stu-id="4aa5a-108">CimSessionSet</span></span>

```
Publish-DscConfiguration [-Path] <String> [-Force] [-ThrottleLimit <Int32>] -CimSession <CimSession[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="4aa5a-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4aa5a-109">DESCRIPTION</span></span>
<span data-ttu-id="4aa5a-110">O cmdlet **Publish-DscConfiguration** publica um documento de configuração de DSC (configuração de estado desejado) do Windows PowerShell no conjunto de computadores.</span><span class="sxs-lookup"><span data-stu-id="4aa5a-110">The **Publish-DscConfiguration** cmdlet publishes a Windows PowerShell Desired State Configuration (DSC) configuration document on set of computers.</span></span>
<span data-ttu-id="4aa5a-111">Esse cmdlet não aplica a configuração.</span><span class="sxs-lookup"><span data-stu-id="4aa5a-111">This cmdlet does not apply the configuration.</span></span>
<span data-ttu-id="4aa5a-112">As configurações são aplicadas pelo cmdlet Start-DscConfiguration quando ele é usado com o parâmetro *UseExisting* ou quando o mecanismo de DSC executa seu ciclo de consistência.</span><span class="sxs-lookup"><span data-stu-id="4aa5a-112">Configurations are applied by either the Start-DscConfiguration cmdlet when it is used with the *UseExisting* parameter or when the DSC engine runs its consistency cycle.</span></span>
<span data-ttu-id="4aa5a-113">O mecanismo de DSC também é conhecido como o Configuration Manager local (LCM).</span><span class="sxs-lookup"><span data-stu-id="4aa5a-113">The DSC engine is also known as the Local Configuration Manager (LCM).</span></span>

<span data-ttu-id="4aa5a-114">Esse cmdlet é especialmente útil quando são entregues fragmentos de vários documentos de configuração.</span><span class="sxs-lookup"><span data-stu-id="4aa5a-114">This cmdlet is especially useful when fragments of multiple configuration documents are delivered.</span></span>
<span data-ttu-id="4aa5a-115">Quando vários fragmentos de documentos de configuração são entregues, eles substituem os fragmentos de documentos de configuração mais antigos.</span><span class="sxs-lookup"><span data-stu-id="4aa5a-115">When multiple configuration documents fragments are delivered, they overwrite the older configuration document fragments.</span></span>

## <span data-ttu-id="4aa5a-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="4aa5a-116">EXAMPLES</span></span>

### <span data-ttu-id="4aa5a-117">Exemplo 1: publicar uma configuração em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="4aa5a-117">Example 1: Publish a configuration to a remote computer</span></span>

```
PS C:\> Publish-DscConfiguration -Path '$home\WebServer' -ComputerName "ContosoWebServer" -Credential (get-credential Contoso\webadministrator)
```

<span data-ttu-id="4aa5a-118">Esse comando publica uma configuração em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="4aa5a-118">This command publishes a configuration to a remote computer.</span></span>
<span data-ttu-id="4aa5a-119">O usuário que executa o cmdlet deve ser administrador no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="4aa5a-119">The user who runs the cmdlet should be administrator on the remote computer.</span></span>

## <span data-ttu-id="4aa5a-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4aa5a-120">PARAMETERS</span></span>

### <span data-ttu-id="4aa5a-121">-CimSession</span><span class="sxs-lookup"><span data-stu-id="4aa5a-121">-CimSession</span></span>
<span data-ttu-id="4aa5a-122">Executa o cmdlet em uma sessão remota ou em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="4aa5a-122">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="4aa5a-123">Insira um nome de computador ou um objeto de sessão, como a saída de um cmdlet [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) ou [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) .</span><span class="sxs-lookup"><span data-stu-id="4aa5a-123">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="4aa5a-124">O padrão é a sessão atual do computador local.</span><span class="sxs-lookup"><span data-stu-id="4aa5a-124">The default is the current session on the local computer.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4aa5a-125">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="4aa5a-125">-ComputerName</span></span>
<span data-ttu-id="4aa5a-126">Especifica um ou mais computadores nos quais esse cmdlet publica a configuração.</span><span class="sxs-lookup"><span data-stu-id="4aa5a-126">Specifies one or more computers on which this cmdlet publishes the configuration.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4aa5a-127">-Credential</span><span class="sxs-lookup"><span data-stu-id="4aa5a-127">-Credential</span></span>
<span data-ttu-id="4aa5a-128">Especifica as credenciais que são usadas para acessar o dispositivo de destino.</span><span class="sxs-lookup"><span data-stu-id="4aa5a-128">Specifies credentials that are used to access the target device.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4aa5a-129">-Force</span><span class="sxs-lookup"><span data-stu-id="4aa5a-129">-Force</span></span>
<span data-ttu-id="4aa5a-130">Força o cmdlet a ser concluído.</span><span class="sxs-lookup"><span data-stu-id="4aa5a-130">Forces the cmdlet to finish.</span></span>
<span data-ttu-id="4aa5a-131">Se o modo de atualização de Configuration Manager local for definido como PULL, o uso desse parâmetro o alterará para enviar por PUSH e habilitará a publicação da configuração DSC.</span><span class="sxs-lookup"><span data-stu-id="4aa5a-131">If the Local Configuration Manager refresh mode is set to PULL, usage of this parameter changes it to PUSH and enables publication of the DSC configuration.</span></span>
<span data-ttu-id="4aa5a-132">Além disso, se existir uma configuração de DSC pendente, o uso desse parâmetro substituirá essa configuração pendente.</span><span class="sxs-lookup"><span data-stu-id="4aa5a-132">Also, if a pending DSC configuration exists, usage of this parameter overwrites that pending configuration.</span></span>

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

### <span data-ttu-id="4aa5a-133">-Path</span><span class="sxs-lookup"><span data-stu-id="4aa5a-133">-Path</span></span>
<span data-ttu-id="4aa5a-134">Especifica um caminho que contém as configurações para publicar nos computadores de destino.</span><span class="sxs-lookup"><span data-stu-id="4aa5a-134">Specifies a path that contains configurations to publish to target computers.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4aa5a-135">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="4aa5a-135">-ThrottleLimit</span></span>
<span data-ttu-id="4aa5a-136">Especifica o número máximo de operações simultâneas que podem ser estabelecidas para executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4aa5a-136">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="4aa5a-137">Se esse parâmetro for omitido ou um valor de `0` for inserido, o Windows PowerShell calculará um limite de aceleração ideal para o cmdlet com base no número de cmdlets CIM em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="4aa5a-137">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="4aa5a-138">O limite de aceleração aplica-se somente ao cmdlet atual, e não à sessão ou ao computador.</span><span class="sxs-lookup"><span data-stu-id="4aa5a-138">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="4aa5a-139">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4aa5a-139">-Confirm</span></span>
<span data-ttu-id="4aa5a-140">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4aa5a-140">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="4aa5a-141">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4aa5a-141">-WhatIf</span></span>
<span data-ttu-id="4aa5a-142">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="4aa5a-142">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="4aa5a-143">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="4aa5a-143">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="4aa5a-144">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4aa5a-144">CommonParameters</span></span>
<span data-ttu-id="4aa5a-145">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4aa5a-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4aa5a-146">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4aa5a-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4aa5a-147">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="4aa5a-147">INPUTS</span></span>

## <span data-ttu-id="4aa5a-148">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="4aa5a-148">OUTPUTS</span></span>

## <span data-ttu-id="4aa5a-149">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="4aa5a-149">NOTES</span></span>

## <span data-ttu-id="4aa5a-150">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="4aa5a-150">RELATED LINKS</span></span>

[<span data-ttu-id="4aa5a-151">Visão geral da Desired State Configuration do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4aa5a-151">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="4aa5a-152">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="4aa5a-152">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="4aa5a-153">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="4aa5a-153">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="4aa5a-154">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="4aa5a-154">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="4aa5a-155">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="4aa5a-155">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="4aa5a-156">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="4aa5a-156">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
