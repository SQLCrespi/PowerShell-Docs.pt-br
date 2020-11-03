---
external help file: Remove-DscConfigurationDocument.cdxml-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DscConfigurationDocument
ms.openlocfilehash: d3e9b15dfeea94921503247adc08b291eed9d7d7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194141"
---
# <span data-ttu-id="8957b-103">Remove-DscConfigurationDocument</span><span class="sxs-lookup"><span data-stu-id="8957b-103">Remove-DscConfigurationDocument</span></span>

## <span data-ttu-id="8957b-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="8957b-104">SYNOPSIS</span></span>
<span data-ttu-id="8957b-105">Remove um documento de configuração do repositório de configuração DSC.</span><span class="sxs-lookup"><span data-stu-id="8957b-105">Removes a configuration document from the DSC configuration store.</span></span>

## <span data-ttu-id="8957b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8957b-106">SYNTAX</span></span>

```
Remove-DscConfigurationDocument -Stage <Stage> [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="8957b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8957b-107">DESCRIPTION</span></span>
<span data-ttu-id="8957b-108">O `Remove-DscConfigurationDocument` cmdlet Remove um documento de configuração (arquivo. MOF) do repositório de configuração de DSC (configuração de estado desejado) do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8957b-108">The `Remove-DscConfigurationDocument` cmdlet removes a configuration document (.mof file) from the Windows PowerShell Desired State Configuration (DSC) configuration store.</span></span>
<span data-ttu-id="8957b-109">Durante a configuração, o `Start-DscConfiguration` cmdlet copia um arquivo. MOF para uma pasta no computador de destino.</span><span class="sxs-lookup"><span data-stu-id="8957b-109">During configuration, the `Start-DscConfiguration` cmdlet copies a .mof file to a folder on the target computer.</span></span>
<span data-ttu-id="8957b-110">Esse cmdlet Remove esse documento de configuração e faz uma limpeza adicional.</span><span class="sxs-lookup"><span data-stu-id="8957b-110">This cmdlet removes that configuration document and does additional cleanup.</span></span>

<span data-ttu-id="8957b-111">Esse cmdlet está disponível somente como parte do [pacote cumulativo de atualizações de novembro de 2014 para Windows RT 8,1, Windows 8.1 e Windows Server 2012 R2](https://support.microsoft.com/kb/3000850) da biblioteca suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8957b-111">This cmdlet is available only as part of the [November 2014 update rollup for Windows RT 8.1, Windows 8.1, and Windows Server 2012 R2](https://support.microsoft.com/kb/3000850) from the Microsoft Support library.</span></span>

## <span data-ttu-id="8957b-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="8957b-112">EXAMPLES</span></span>

### <span data-ttu-id="8957b-113">Exemplo 1: remover o documento de configuração atual</span><span class="sxs-lookup"><span data-stu-id="8957b-113">Example 1: Remove the current configuration document</span></span>

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Remove-DscConfigurationDocument -Stage Current -CimSession $Session
```

<span data-ttu-id="8957b-114">O primeiro comando cria uma sessão CIM usando o cmdlet **New-CimSession** e, em seguida, armazena o objeto **CimSession** na variável $Session.</span><span class="sxs-lookup"><span data-stu-id="8957b-114">The first command creates a CIM session by using the **New-CimSession** cmdlet, and then stores the **CimSession** object in the $Session variable.</span></span>
<span data-ttu-id="8957b-115">O comando solicita uma senha.</span><span class="sxs-lookup"><span data-stu-id="8957b-115">The command prompts you for a password.</span></span>
<span data-ttu-id="8957b-116">Para obter mais informações, digite `Get-Help New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="8957b-116">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="8957b-117">O segundo comando Remove o documento de configuração atual do computador especificado no **CimSession** armazenado em $Session.</span><span class="sxs-lookup"><span data-stu-id="8957b-117">The second command removes the current configuration document for the computer specified in the **CimSession** stored in $Session.</span></span>

## <span data-ttu-id="8957b-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8957b-118">PARAMETERS</span></span>

### <span data-ttu-id="8957b-119">-AsJob</span><span class="sxs-lookup"><span data-stu-id="8957b-119">-AsJob</span></span>
<span data-ttu-id="8957b-120">Indica que esse cmdlet executa o comando como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="8957b-120">Indicates that this cmdlet runs the command as a background job.</span></span>

<span data-ttu-id="8957b-121">Se você especificar o parâmetro *AsJob* , o comando retornará um objeto que representa o trabalho e, em seguida, exibirá o prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="8957b-121">If you specify the *AsJob* parameter, the command returns an object that represents the job, and then displays the command prompt.</span></span>
<span data-ttu-id="8957b-122">Você pode continuar a trabalhar na sessão até que o trabalho seja concluído.</span><span class="sxs-lookup"><span data-stu-id="8957b-122">You can continue to work in the session until the job finishes.</span></span>
<span data-ttu-id="8957b-123">O trabalho é criado no computador local e os resultados de computadores remotos são retornados automaticamente para o computador local.</span><span class="sxs-lookup"><span data-stu-id="8957b-123">The job is created on the local computer and the results from remote computers are automatically returned to the local computer.</span></span>
<span data-ttu-id="8957b-124">Para gerenciar o trabalho, use os cmdlets Job.</span><span class="sxs-lookup"><span data-stu-id="8957b-124">To manage the job, use the Job cmdlets.</span></span>
<span data-ttu-id="8957b-125">Para obter os resultados do trabalho, use o cmdlet Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="8957b-125">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="8957b-126">Para usar esse parâmetro, os computadores locais e remotos devem ser configurados para comunicação remota e no Windows Vista e versões posteriores do sistema operacional Windows, você deve abrir o Windows PowerShell com a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="8957b-126">To use this parameter, the local and remote computers must be configured for remoting, and on Windows Vista and later versions of the Windows operating system, you must open Windows PowerShell with the Run as administrator option.</span></span>
<span data-ttu-id="8957b-127">Para obter mais informações, consulte [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8957b-127">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span></span>

<span data-ttu-id="8957b-128">Para obter mais informações sobre trabalhos em segundo plano do Windows PowerShell, consulte [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) e [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="8957b-128">For more information about Windows PowerShell background jobs, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) and [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span></span>

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

### <span data-ttu-id="8957b-129">-CimSession</span><span class="sxs-lookup"><span data-stu-id="8957b-129">-CimSession</span></span>
<span data-ttu-id="8957b-130">Executa o cmdlet em uma sessão remota ou em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="8957b-130">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="8957b-131">Insira um nome de computador ou um objeto de sessão, como a saída de um cmdlet **New-CimSession** ou **Get-CimSession** .</span><span class="sxs-lookup"><span data-stu-id="8957b-131">Enter a computer name or a session object, such as the output of a **New-CimSession** or **Get-CimSession** cmdlet.</span></span>

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

### <span data-ttu-id="8957b-132">-Force</span><span class="sxs-lookup"><span data-stu-id="8957b-132">-Force</span></span>
<span data-ttu-id="8957b-133">Indica que esse cmdlet interrompe o trabalho de configuração em execução antes de remover o documento de configuração.</span><span class="sxs-lookup"><span data-stu-id="8957b-133">Indicates that this cmdlet stops the running configuration job before it removes the configuration document.</span></span>
<span data-ttu-id="8957b-134">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="8957b-134">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="8957b-135">-Estágio</span><span class="sxs-lookup"><span data-stu-id="8957b-135">-Stage</span></span>
<span data-ttu-id="8957b-136">Especifica qual documento de configuração remover.</span><span class="sxs-lookup"><span data-stu-id="8957b-136">Specifies which configuration document to remove.</span></span>
<span data-ttu-id="8957b-137">Você pode especificar vários documentos.</span><span class="sxs-lookup"><span data-stu-id="8957b-137">You can specify multiple documents.</span></span>
<span data-ttu-id="8957b-138">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="8957b-138">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="8957b-139">Atual.</span><span class="sxs-lookup"><span data-stu-id="8957b-139">Current.</span></span>
<span data-ttu-id="8957b-140">Remova o documento de configuração que descreve o estado atual do sistema.</span><span class="sxs-lookup"><span data-stu-id="8957b-140">Remove the configuration document that describes the current state of the system.</span></span>
- <span data-ttu-id="8957b-141">Pendente.</span><span class="sxs-lookup"><span data-stu-id="8957b-141">Pending.</span></span>
<span data-ttu-id="8957b-142">Remova o documento de configuração que descreve o estado pendente do sistema.</span><span class="sxs-lookup"><span data-stu-id="8957b-142">Remove the configuration document that describes the pending state of the system.</span></span>
- <span data-ttu-id="8957b-143">Anterior.</span><span class="sxs-lookup"><span data-stu-id="8957b-143">Previous.</span></span>
<span data-ttu-id="8957b-144">Remova o documento de configuração que descreve o estado anterior do sistema.</span><span class="sxs-lookup"><span data-stu-id="8957b-144">Remove the configuration document that describes the previous state of the system.</span></span>

```yaml
Type: Microsoft.PowerShell.Cmdletization.GeneratedTypes.RemoveDscConfigurationDocument.Stage
Parameter Sets: (All)
Aliases:
Accepted values: Current, Pending, Previous

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8957b-145">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="8957b-145">-ThrottleLimit</span></span>
<span data-ttu-id="8957b-146">Especifica o número máximo de operações simultâneas que podem ser estabelecidas para executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8957b-146">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="8957b-147">Se esse parâmetro for omitido ou um valor de `0` for inserido, o Windows PowerShell calculará um limite de aceleração ideal para o cmdlet com base no número de cmdlets CIM em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="8957b-147">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="8957b-148">O limite de aceleração aplica-se somente ao cmdlet atual, e não à sessão ou ao computador.</span><span class="sxs-lookup"><span data-stu-id="8957b-148">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="8957b-149">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8957b-149">-Confirm</span></span>
<span data-ttu-id="8957b-150">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8957b-150">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="8957b-151">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8957b-151">-WhatIf</span></span>
<span data-ttu-id="8957b-152">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="8957b-152">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="8957b-153">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="8957b-153">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="8957b-154">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8957b-154">CommonParameters</span></span>
<span data-ttu-id="8957b-155">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8957b-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8957b-156">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8957b-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8957b-157">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="8957b-157">INPUTS</span></span>

### <span data-ttu-id="8957b-158">Nenhum</span><span class="sxs-lookup"><span data-stu-id="8957b-158">None</span></span>

## <span data-ttu-id="8957b-159">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="8957b-159">OUTPUTS</span></span>

### <span data-ttu-id="8957b-160">Nenhum</span><span class="sxs-lookup"><span data-stu-id="8957b-160">None</span></span>

## <span data-ttu-id="8957b-161">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="8957b-161">NOTES</span></span>

## <span data-ttu-id="8957b-162">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="8957b-162">RELATED LINKS</span></span>

[<span data-ttu-id="8957b-163">Visão geral da Desired State Configuration do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8957b-163">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="8957b-164">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="8957b-164">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="8957b-165">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="8957b-165">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)
